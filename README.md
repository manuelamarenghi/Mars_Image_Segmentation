# Mars_Image_Segmentation

## 🚀 Project Overview

This project focuses on **semantic segmentation** of Mars terrain images using deep learning. The goal is to classify pixels into categories like rocks, soil, and other terrain features with high accuracy, measured by **mean Intersection Over Union (mean IoU)**. We explore advanced techniques in data augmentation, neural network architectures, and optimization to achieve state-of-the-art results.

---

## 🔑 Key Features

- **Data Augmentation**: Techniques like **general augmentation**, **copy-paste augmentation**, and **compositional image synthesis** to handle class imbalance and dataset limitations.
- **Model Architecture**: A modified **U-Net** architecture with:
  - **Nested U-Net**: Two encode-decode subnetworks for faster training.
  - **Dilated Spatial Pyramid Pooling**: Captures multi-scale features.
  - **Dual Attention Unit**: Improves feature sharing across spatial and channel dimensions.
  - **Transformer Blocks**: Initially used for long-range dependencies but removed due to overfitting.
- **Training**: Optimized with **Adam optimizer**, **sparse categorical cross-entropy loss**, and dynamic learning rate reduction. Early stopping prevents overfitting.

---

## 📊 Results

The best performance was achieved using **Dual Attention Unit** and **Dilated Spatial Pyramid Pooling**, with an **Inference Mean IoU** of **69.91**. Below are the results:

| Experiment               | Validation Mean IoU | Inference Mean IoU |
|--------------------------|---------------------|--------------------|
| Base U-Net               | 43.92               | 42.38              |
| U-Net++                  | 48.04               | 45.63              |
| With Augmentation        | 56.82               | 50.47              |
| With DSPP                | 63.29               | 69.70              |
| With Dual Attention      | 64.90               | 69.91              |


Implementation of a more sophisticated augmentation pipeline.

Use of larger architectures (e.g., deeper U-Net++).

Effective integration of transformers to capture long-range dependencies.

References
U-Net: Convolutional Networks for Biomedical Image Segmentation

DeepLab: Semantic Image Segmentation with Deep Convolutional Nets

Copy-Paste Augmentation for Instance Segmentation

Authors
Luca Cattani

Simone Lucca

Manuela Marenghi

Andrada Theodora Pascu
