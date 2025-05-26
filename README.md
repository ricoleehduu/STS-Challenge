# MICCAI 2023 STS Dental Segmentation Challenge 🦷

**Official Repository for Tooth Segmentation Challenges**
| [2D Track Introduction ](https://tianchi.aliyun.com/competition/entrance/532086/introduction)| [3D Track Introduction ](https://tianchi.aliyun.com/competition/entrance/532087/introduction)| [Leaderboard ](https://chat.qwen.ai/c/3ef31cf1-b5e3-4656-bced-6b162bb8fb3f#🏆-challenge-leaderboard)|

------

## 🔍 **Challenge Overview**

This challenge aims to advance dental segmentation techniques in both **2D panoramic radiography** and **3D CBCT** domains. Two tracks are designed to address critical clinical needs:

| **Track**    | **Task**                                  | **Evaluation Metrics**           | Link                                                         |
| ------------ | ----------------------------------------- | -------------------------------- | ------------------------------------------------------------ |
| **2D Track** | Tooth segmentation on 2D panoramic images | Dice, IoU, Hausdorff Distance    | https://tianchi.aliyun.com/competition/entrance/532086/rankingList |
| **3D Track** | Tooth segmentation on 3D CBCT volumes     | Dice, IoU, 3D Hausdorff Distance | https://tianchi.aliyun.com/competition/entrance/532087/rankingList |

### 2D Track

![](assets/2D-segmentation.png)

### 3D Track

![](assets/3D-segmemtation.png)

------

## ⭐ **Baseline Configuration and Checkpoints**

| Track | Configuration | Checkpoints                                                  | Methods                                      |
| ----- | ------------- | ------------------------------------------------------------ | -------------------------------------------- |
| 2D    | [2D Configuration](configuration/2D/)   | [2D Pretrained Checkpoints](baseline_checkpoints/2d-checkpoint_best.pth)            | [nnUNet](https://github.com/MIC-DKFZ/nnUNet) |
| 3D    | [3D Configuration](configuration/3D/)      | [3D Pretrained Checkpoints](baseline_checkpoints/3d-checkpoint_best.pth) | [nnUNet](https://github.com/MIC-DKFZ/nnUNet) |




## 🏆 **Technical reports and codes of Top participants**

### **2D Track Top 10**

| Rank | Team ID        | Technical Report                                                       | Code                                                         |
| ---- | -------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------ |
| 1    | louxianihao       | [Read Report](participants-technicalreport/2D-Rank1-louxiahao.md)             | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |
| 2    | baozaifan     | [Read Report](participants-technicalreport/2D-Rank2-baozaifan.pdf)       | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |
| 3    | c_c            | [Read Report](participants-technicalreport/2D-Rank3-c_c.pdf)             | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |
| 4    | HDU one       | [Read Report](participants-technicalreport/2D-Rank4-HDU_one.pdf)         | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |
| 5    | podi | [Read Report](participants-technicalreport/2D-Rank5-podi-mono.pdf)       | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |
| 6    | One Piece      | [Read Report](participants-technicalreport/2D-Rank6-One_Piece.pdf)       | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |
| 7    | A100x8         | [Read Report](participants-technicalreport/2D-Rank7-A100x8.pdf)          | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |
| 8    | dog team         | [Read Report](participants/2D-第七名-A100x8-技术说明.docx)    | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |
| 9    | Gostraight         | [Read Report](participants/2D-第七名-A100x8-技术说明.docx)    | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |
| 10    | do you want to         | [Read Report](participants/2D-第七名-A100x8-技术说明.docx)    | [Download Code](https://pan.baidu.com/s/15bVgpJ1juWX3r_rvVaAyeQ?pwd=z2py) |

### **3D Track Top 10**

| Rank | Team ID   | Technical Report                                                       | Code                                                         |
| ---- | --------- | ---------------------------------------------------------------------- | ------------------------------------------------------------ |
| 1    | RoboSurge | [Read Report](participants-technicalreport/3D-Rank1-RoboSurge.pdf)     | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |
| 2    | Yxx       | [Read Report](participants-technicalreport/3D-Rank2-Yxx.pdf)           | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |
| 3    | GUET-IICI | [Read Report](participants-technicalreport/3D-Rank3-GUET-IICI.pdf)     | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |
| 4    | IGIP-CBCT | [Read Report](participants-technicalreport/3D-Rank4-IGIP-CBCT.docx)   | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |
| 5    | sdkxd     | [Read Report](participants-technicalreport/3D-Rank5-sdkxd.docx)         | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |
| 6    | A100x8    | [Read Report](participants-technicalreport/3D-Rank6-A100x8.docx)       | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |
| 7    | solo      | [Read Report](participants-technicalreport/3D-Rank7-solo.docx)         | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |
| 8    | TheStranger      | [Read Report](participants/3D-第7名-单打独斗-技术说明.docx)  | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |
| 9    | hotpot      | [Read Report](participants/3D-第7名-单打独斗-技术说明.docx)  | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |
| 10    | GoStraight      | [Read Report](participants/3D-第7名-单打独斗-技术说明.docx)  | [Download Code](https://pan.baidu.com/s/1C3l6fN0Z1G256C6LaDGICQ?pwd=wsje) |

------

### Leaderboard

**2D Leadboard**

![](assets/2D-leaderboard.png)

![](assets/2D-leaderboard-1.png)

**3D Leadboard**

![](assets/3D-leadboard.png)

![image-20250524104422412](assets/image-20250524104422412.png)

## 📁 **Dataset & Resources**

### **2D Track**

- **Training** : 2,000 labeled panoramic images (500 with masks)
- **Test** : 1,500 unlabeled images (500 initial + 1,000 final)
- Evaluation :

  - Dice = ∣*A*∣+∣*B*∣2∣*A*∩*B*∣
  - IoU = ∣*A*∪*B*∣∣*A*∩*B*∣
  - 2D Hausdorff Distance = min(∣*x*1−*x*2∣+∣*y*1−*y*2∣)
  - Final Score = 0.4×Dice+0.3×IoU+0.3×(1−Normalized Hausdorff)

### **3D Track**

- **Training** : 312 CT scans (12 labeled, 300 unlabeled)

- **Test** : 50 CT scans (labels withheld)

- **Submission** : `.nii.gz` volume masks

- Evaluation :

  - 3D Hausdorff Distance = min(∣*x*1−*x*2∣+∣*y*1−*y*2∣+∣*z*1−*z*2∣)
- Scoring formula identical to 2D track

------

## 🧾 **Organizers & Collaborators**

### **Host Institutions**

- Zhejiang University of Media and Communications
- Hangzhou Dianzi University

### **Data Providers**

- Hangzhou Dental Group
- London Queen Mary University
- University of Electronic Science and Technology of China

### **Organizing Committee**

- Prof. Yaqi Wang (ZUMC)
- Prof. Xingru Huang (HDU)
- Prof. Weirui Cui (QMUL)
- Prof. Shuai Wang (HDU)
- Dr. Xiaodiao Chen (HDU)

------

## 📂 **Repository Structure**

```
STS-Challenge/
├── documentation/           # Technical specs & rulebooks  
├── participants/            # Team submissions (code/Report/presentation)  
│   └── Team-ID/           # Team-specific materials  
├── assets/                  # Visual assets (dataset examples, workflow diagrams)  
└── README.md                # This file  
```

------

## 📞 **Contact**

- **Email** : [SemiTeethSegChallenge@outlook.com](mailto: SemiTeethSegChallenge@outlook.com)
- **WeChat Group** : [Join via official website](https://tianchi.aliyun.com/competition/entrance/532087/introduction)

------

## Reference 

```
[1] Cui, W., Wang, Y., Zhang, Q., Zhou, H., Song, D., Zuo, X., ... & Zeng, L. (2022, August). CTooth: a fully annotated 3d dataset and benchmark for tooth volume segmentation on cone beam computed tomography images. In Intelligent Robotics and Applications: 15th International Conference, ICIRA 2022, Harbin, China, August 1–3, 2022, Proceedings, Part IV (pp. 191-200). Cham: Springer International Publishing.

[2] Cui, W., Wang, Y., Li, Y., Song, D., Zuo, X., Wang, J., ... & Zhang, Q. (2022, September). CTooth+: A Large-Scale Dental Cone Beam Computed Tomography Dataset and Benchmark for Tooth Volume Segmentation. In Data Augmentation, Labelling, and Imperfections: Second MICCAI Workshop, DALI 2022, Held in Conjunction with MICCAI 2022, Singapore, September 22, 2022, Proceedings (pp. 64-73). Cham: Springer Nature Switzerland.
```



## 📜 **License**

This project is released under the [MIT License ](https://chat.qwen.ai/c/LICENSE).

------

