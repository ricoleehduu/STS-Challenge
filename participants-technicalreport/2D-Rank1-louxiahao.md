
# Overall Workflow for Segmentation Task

## Preliminary Round

### Selecting the Optimal Data Augmentation Strategy
- Sliding Window Approach:
  - Given the limited amount of data in semi-supervised learning, we used a sliding window strategy to generate many similar but not identical images for training, effectively expanding the dataset.
  - Each image has dimensions of 320x640. We set the sliding window to 320x320 with a stride of 32 pixels. This eliminates the need for resizing, preserving as much original information as possible.
  - For validation and testing, we adopted a technique where overlapping regions are averaged. Each overlapping region adds 1 to a count map, and the final stitched image averages the overlapping areas to achieve a smooth visual output.

- Other Data Augmentations (using Albumentations):
  - Random 90-degree rotation
  - Horizontal flip
  - Vertical flip
  - Random brightness/contrast
  - Random shift, scale, rotate
  - Gaussian noise, blur, motion blur, gamma correction
  - Random affine transformation
  - Normalization

### Designing a Custom Evaluation Metric
- Based on the competition formula:  
  score = 0.4 x Dice + 0.3 x IOU + 0.3 x (1 - H(d))
- We reused scoring code from the MONAI library to implement this metric.

### Model Comparison
- Compared various models:
  - UNet
  - UNet++
  - SegResNet_8
  - SegResNet_32
  - SegResNet_64
  - SwinUNETR
  - AttentionUNet
  - SegResNetDS
  - DynUNet
- Based on scores and validation accuracy (via wandb), we selected two models for the final round:
  - SegResNet_64
  - DynUNet

## Final Round

### Analysis
Only 900 labeled images were provided, along with 2100 unlabeled images. We used the labeled data to train two different models (teacher models), fused their outputs to generate soft labels for all 3000 images, then trained two new models (student models) on these soft labels. All models were then fused for final predictions. The steps:

1. Train two teacher models on 900 labeled images, using a smaller stride (from 32 to 16) to increase data volume.
2. Combine the 900 labeled and 2100 unlabeled images to produce soft labels using the fused teacher models.
3. Use these 3000 soft-labeled images to train two student models.
4. Fuse all teacher and student models for final predictions and submission.

## Experiment Deployment Details

### Data
- Made file suffix configurable in config to support .npy, .jpg, or .tiff.
- train_batchsize is set based on available GPU memory.
- valid_batchsize and test_batchsize can be set equal to train_batchsize.
- Images are loaded in grayscale using OpenCV:
  ```python
  image = cv2.imread(img_path, 0)
  ```

### Model

SegResNet_64 Configuration:
```python
from monai.networks.nets.segresnet import SegResNet 
self.model = SegResNet(
    spatial_dims=2,
    init_filters=64,
    in_channels=CFG.in_chans,
    out_channels=CFG.target
)
```

DynUNet Configuration:
```python
from monai.networks.nets.dynunet import DynUNet
self.model = DynUNet(
    spatial_dims=2,
    in_channels=CFG.in_chans,
    out_channels=CFG.target,
    kernel_size=[[3, 3]] * 5,
    strides=[[1, 1]] + [[2, 2]] * 4,
    upsample_kernel_size=[[2, 2]] * 4,
    norm_name=("INSTANCE", {"affine": True}),
    act_name=("leakyrelu", {"inplace": True, "negative_slope": 0.01})
)
```

## Other Components

### Loss Functions
- BCEWithLogitsLoss: Used for training teacher models. This loss function includes a sigmoid operation internally.
- MSELoss: Used for student models with soft labels. Encourages student predictions to match teacher output pixel-wise.

### Scheduler
- Learning rate scheduler is adapted from this Kaggle notebook.
- Based on GradualWarmupScheduler. When multiplier=1.0, learning rate goes from 0 to base_lr. If multiplier > 1.0, it goes from base_lr to base_lr x multiplier.

### Optimizer
- AdamW:
  - Learning rate: 3e-3
  - weight_decay: 1e-5 to reduce overfitting

### Test-Time Augmentation (TTA)
- Each trained model uses TTA during inference:
  - Rotate image in multiple directions
  - Invert the transformations after prediction
  - Stack outputs and average over the channel dimension
  - For input of shape (C=1, H=320, W=320), TTA yields (C=4, H=320, W=320) then averaged back to (C=1, H=320, W=320)

## Result Visualization

## References
- U-Net: Convolutional Networks for Biomedical Image Segmentation
- UNet++: A Nested U-Net Architecture for Medical Image Segmentation
- SegResNet: 3D MRI brain tumor segmentation using autoencoder regularization
- Swin UNETR: Swin Transformers for Semantic Segmentation of Brain Tumors in MRI Images
- Attention UNet: Attention U-Net: Learning Where to Look for the Pancreas
- SegResNetDS: Based on SegResNet with deep supervision
- DynUNet: Automated Design of Deep Learning Methods for Biomedical Image Segmentation
- nnU-Net: Self-adapting Framework for U-Net-Based Medical Image Segmentation
- Optimized U-Net for Brain Tumor Segmentation
