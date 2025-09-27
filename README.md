# 🦴 Bone Fracture Detection using YOLOv8 Segmentation  

## 📖 Table of Contents  
- [🎯 Project Overview](#-project-overview)  
- [📊 Dataset Information](#-dataset-information)  
- [🤖 Model Architecture](#-model-architecture)  
- [⚙️ Training Configuration](#️-training-configuration)  
- [📈 Performance Results](#-performance-results)  
- [📁 File Structure](#-file-structure)  
- [🔧 Deployment Guide](#-deployment-guide)  
- [🎉 Conclusion](#-conclusion)  

---

## 🎯 Project Overview  

**Project Name:** Bone Fracture Detection using YOLOv8 Segmentation  
**Objective:** Automated detection and segmentation of bone fractures in X-ray images  
**Model Type:** Instance Segmentation (YOLOv8s-seg)  
**Classes:** 6 types of bone fractures  
**Status:** ✅ Training Completed Successfully  

**Key Features**  
- 🖼️ **Medical Image Analysis:** X-ray fracture detection  
- 🎯 **Precise Segmentation:** Polygon masks around fractures  
- ⚡ **Real-time Capable:** Optimized for fast inference  
- 🏥 **Clinical Application:** Assist radiologists in diagnosis  

---

## 📊 Dataset Information  

**Dataset Statistics**  

| Split       | Images | Labels | Purpose               |
|-------------|--------|--------|-----------------------|
| Train       | 1,191  | 1,191  | Model Training        |
| Validation  | 200    | 200    | Hyperparameter Tuning |
| Test        | 200    | 200    | Final Evaluation      |
| **Total**   | 1,591  | 1,591  |                       |

**Class Distribution**  

| Class Name        | Class ID | Training Instances | Description        |
|-------------------|----------|---------------------|--------------------|
| Elbow positive    | 0        | ~200                | Elbow fractures    |
| Fingers positive  | 1        | ~200                | Finger fractures   |
| Forearm fracture  | 2        | ~200                | Forearm fractures  |
| Humerus           | 4        | ~200                | Humerus areas      |
| Shoulder fracture | 5        | ~200                | Shoulder fractures |
| Wrist positive    | 6        | ~200                | Wrist fractures    |

**Image Characteristics**  
- **Format:** JPEG/PNG  
- **Average Size:** 437×503 pixels  
- **Size Range:** 158×157 to 1660×1305 px  
- **Color:** Grayscale (X-ray images)  

---

## 🤖 Model Architecture  

**YOLOv8s-seg Specifications**  
- **Model:** YOLOv8s-seg (Small version)  
- **Parameters:** 11.79M  
- **GFLOPs:** 39.9  
- **Layers:** 151  
- **Input Size:** 640×640  

**Architecture Components**  
- **Backbone:** CSPDarknet with cross-stage partial connections  
- **Neck:** PANet (Path Aggregation Network)  
- **Head:** Segmentation head with mask prediction  

**Loss Functions:**  
- Box Loss: CIoU  
- Segmentation Loss: Binary Cross-Entropy  
- Classification Loss: Focal Loss  

---

## ⚙️ Training Configuration  

**Hyperparameters**  
- Epochs: 50  
- Batch Size: 16  
- Image Size: 640  
- Optimizer: AdamW  
- Learning Rate: 0.001  
- LR Scheduler: Cosine annealing  
- Early Stopping: Patience = 15  

**Data Augmentation**  
- HSV Hue: 0.015  
- HSV Saturation: 0.5  
- HSV Value: 0.3  
- Flip (Horizontal): 0.3  
- Rotation: 5°  
- Scale: 0.3  
- Mosaic: 0.8  

---

## 📈 Performance Results  

**Final Evaluation Metrics (Test Set)**  

| Metric          | Box Detection | Mask Segmentation |
|-----------------|---------------|-------------------|
| mAP@50          | 0.734         | 0.722             |
| mAP@50-95       | 0.412         | 0.358             |
| Precision       | 0.849         | 0.852             |
| Recall          | 0.635         | 0.638             |

**Class-wise Performance**  

| Class             | AP50 (Box) | AP50 (Mask) |
|-------------------|------------|-------------|
| Elbow positive    | 0.733      | 0.729       |
| Fingers positive  | 0.564      | 0.512       |
| Forearm fracture  | 0.870      | 0.807       |
| Shoulder fracture | 0.785      | 0.832       |
| Wrist positive    | 0.717      | 0.732       |
| **Average**       | **0.734**  | **0.722**   |

<img width="783" height="331" alt="Image" src="https://github.com/user-attachments/assets/ee3a977e-f34d-4370-abd4-e943697a8d63" />

<img width="774" height="454" alt="Image" src="https://github.com/user-attachments/assets/4800e41b-41fe-4ef5-9354-5f9393d2152b" />
---


## 📁 File Structure

<img width="536" height="723" alt="Image" src="https://github.com/user-attachments/assets/1a1a6c79-debc-4d14-bbd2-4970a54e392f" />

## Conclusion

Success Metrics:

✅ 72.2% mAP@50 for mask segmentation

✅ 6 fracture types detected

✅ Real-time inference supported


