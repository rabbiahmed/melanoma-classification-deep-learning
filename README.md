# Melanoma classification using deep learning and transfer learning.
## Model: Xception
### Rationales for Xception's superiority over Inception
1. Decoupled Feature Learning (using Depthwise Separable Convolutions)
Xception stands for "Extreme Inception". The core difference between Xception and Inception lies in how they perform the fundamental convolution operation, which is critical for feature extraction from images.
Inception's Approach: The original Inception module uses multiple parallel branches with different sized filters (1 * 1, 3 * 3, 5 * 5) to capture both spatial and cross-channel correlations simultanesously. Then it concatenates the results.
Xception's Approach: Xception replaces the traditional Inception module with Depthwise Separable Convolutions (DSC). This technique effectively decouples the learning of spatial correlations (e.g., shapes, textures) from cross-channel correlations (e.g., color, intensity changes).
- First, a depthwise convolution is applied to each input channel separately to learn spatial features.
- Then, a pointwise convolution (1 * 1) is used to combine the outputs across all channels, learning the cross-channel correlations.
Advantage in Medical Imaging: For complex medical images like dermoscopy (which show fine, intricate, and often subtle textures, borders, and color variations), the decoupled approach in Xception may allow the network to learn these distinct features more efficiently and effectively. Therefore, it would lead to better discrimination between subtle patterns of benign and malignant lesions.
### Evaluation: AUC
The best achieved area under the ROC curve (AUC) score: 0.8636. 
## State-of-the-Art Models for Melanoma Classification
## Future Work


