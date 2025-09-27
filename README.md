# Bone Fracture Detection using YOLOv8 Segmentation
Automated detection and segmentation of bone fractures in X-ray images.

## Overview

**Project Name:** Bone Fracture Detection using YOLOv8 Segmentation  
**Objective:** Automatically detect and segment fractures in X-ray images  
**Model:** YOLOv8s-seg (Instance Segmentation)  
**Classes:** 6 fracture types

## Key Features

- 📷 **Medical Image Analysis:** Processes grayscale X-rays  
- 🎯 **Precision Segmentation:** Generates polygon masks for fracture regions  
- ⚡ **Real-time Inference:** Optimized for deployment and fast prediction  
- 🏥 **Clinical Assistance:** Supports radiologists in diagnosis workflows

## Image Characteristics

- **Format:** JPEG / PNG  
- **Average Size:** 437×503 px  
- **Size Range:** 158×157 to 1660×1305 px  
- **Color Mode:** Grayscale (X-ray)

## Dataset Information

**Total Images:** 1,591  
**Annotation Format:** YOLOv8 Segmentation (TXT with polygons)

### Dataset Split

| Split       | Images | Purpose               |
|-------------|--------|------------------------|
| Train       | 1,191  | Model training         |
| Validation  | 200    | Hyperparameter tuning  |
| Test        | 200    | Final evaluation       |

### Class Distribution

| Class Name         | ID  | Approx. Count | Description         |
|--------------------|-----|---------------|---------------------|
| elbow positive     | 0   | ~200          | Elbow fractures     |
| fingers positive   | 1   | ~200          | Finger fractures    |
| forearm fracture   | 2   | ~200          | Forearm fractures   |
| humerus            | 4   | ~200          | Humerus bone region |
| shoulder fracture  | 5   | ~200          | Shoulder fractures  |
| wrist positive     | 6   | ~200          | Wrist fractures     |

## Model Architecture

- **Model:** YOLOv8s-seg  
- **Parameters:** 11.79M  
- **Layers:** 151  
- **GFLOPs:** 39.9  
- **Input Size:** 640×640 px  

### Architecture Components

- **Backbone:** CSPDarknet  
- **Neck:** PANet  
- **Head:** Segmentation head with polygon mask output  

### Loss Functions

- CIoU Loss (bounding boxes)  
- BCE Loss (segmentation masks)  
- Focal Loss (classification)

## Training Configuration

- **Epochs:** 50  
- **Batch Size:** 16  
- **Image Size:** 640  
- **Optimizer:** AdamW  
- **Learning Rate:** 0.001  
- **Scheduler:** Cosine Annealing  
- **Early Stopping:** Patience = 15

### Data Augmentation

```yaml
hsv_h: 0.015
hsv_s: 0.5
hsv_v: 0.3
fliplr: 0.3
degrees: 5.0
scale: 0.3
mosaic: 0.8
