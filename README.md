# Mars_Image_Segmentation
## Project Description
This project aims to develop a deep neural network for semantic segmentation of Mars terrain images. The model is designed to classify pixels into different categories (e.g., rocks, soil, etc.) with high accuracy, measured using mean Intersection Over Union (mean IoU). The project explores various data augmentation techniques, network architectures, and optimization strategies to improve model performance.

## Methodology
### 1. Preprocessing and Data Augmentation
To address class imbalance and the limited size of the dataset, several data augmentation techniques were applied:

General augmentation: Random rotation, zoom, shear, and shifting.

Copy-paste augmentation: Increasing the presence of the least represented class (e.g., large rocks) by pasting objects onto other images.

Compositional image synthesis: Creating new synthetic images by combining objects extracted from the dataset.

2. Model Architecture
The model is based on a variant of the U-Net architecture, with the following features:

Backbone: Nested U-Net with two encode-decode subnetworks to reduce training time.

Additional constructs:

Dilated Spatial Pyramid Pooling: To capture objects at various scales.

Dual Attention Unit: To share information across spatial and channel dimensions.

Transformer blocks: To capture long-range dependencies between pixels (removed due to overfitting).

Loss function: Sparse Categorical Cross-Entropy.

Optimizer: Adam with weight decay and dynamic learning rate reduction.

3. Training and Evaluation
Training was performed with early stopping and learning rate reduction based on validation performance. The main metrics were:

Validation Mean IoU: Average accuracy on the validation set.

Inference Mean IoU: Average accuracy on an external test set.

Results
Experimental results show that the combination of Dual Attention Unit and Dilated Spatial Pyramid Pooling delivered the best performance, achieving an Inference Mean IoU of 69.91. Below is a summary table of the results:

Experiment	Validation Mean IoU	Inference Mean IoU
Base U-Net	43.92	42.38
U-Net++	48.04	45.63
With augmentation	56.82	50.47
With DSPP	63.29	69.70
With Dual Attention	64.90	69.91
Conclusions and Future Work
The project demonstrates that the use of advanced data augmentation techniques and network architectures can significantly improve performance in semantic segmentation. However, there is still room for improvement:

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
