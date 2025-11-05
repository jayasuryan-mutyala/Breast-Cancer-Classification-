# Breast-Cancer-Classification
Breast Cancer Histopathology Classification using Deep Learning (IDC Detection) This project builds a deep-learning pipeline to classify breast cancer histopathology images into IDC (Invasive Ductal Carcinoma) vs Non-IDC, using the publicly available in dataset from kaggle. This project focuses on detecting **Invasive Ductal Carcinoma (IDC)** in breast tissue histopathology slides using **Convolutional Neural Networks (CNNs)**. IDC is the most common and aggressive type of breast cancer, and early detection is crucial for improved patient outcomes. The model uses **patch-based training** and **transfer learning with ResNet-18** to classify image patches as cancerous or non-cancerous.

---

## Project Overview

Histopathological whole-slide images (WSIs) are extremely high-resolution. To make training feasible:

1. Each WSI is divided into **50×50 pixel patches**.
2. Each patch is labeled as either:
   - **1 → IDC present**
   - **0 → IDC absent**
3. A **ResNet-18** model (pretrained on ImageNet) is fine-tuned to classify patches.
4. Patch-level predictions are combined to generate **probability heatmaps** indicating cancer regions.

---

## Dataset

| Source | Kaggle - IDC Breast Cancer Histopathology Dataset |
|-------|---------------------------------------------------|
| Patients | 162 individuals diagnosed with IDC |
| Total Patches | **277,524** (50×50 px) |
| Class Distribution | ~198,738 negative vs. 78,786 positive patches |

> **Note:** The dataset is **imbalanced**, so class weighting and careful evaluation metrics are used.

---

## Model Architecture

We use **Transfer Learning with ResNet-18**, chosen for:
- Fewer trainable parameters (faster training)
- Residual skip connections (prevents vanishing gradients)
- Good generalization on small datasets

**Processing Pipeline:**

1. Patch Extraction from WSIs  
2. Preprocessing (Normalization, Color Space Conversion)
3. Feature Extraction using ResNet-18
4. Fully-connected Classification Layer
5. IDC Probability Map Reconstruction

---

## Results

| Dataset  | Accuracy |
|--------|----------|
| **Training Set** | 0.7911 |
| **Testing Set** | 0.8443 | 
- The model generalizes well due to transfer learning.


