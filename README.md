# Melanoma classification using deep learning and transfer learning.
## Model: Xception
### Rationales for Xception's superiority over Inception
1. Decoupled Feature Learning (using Depthwise Separable Convolutions) <br> Xception stands for "Extreme Inception". The core difference between Xception and Inception lies in how they perform the fundamental convolution operation, which is critical for feature extraction from images. <br>
Inception's Approach: The original Inception module uses multiple parallel branches with different sized filters (1 * 1, 3 * 3, 5 * 5) to capture both spatial and cross-channel correlations simultanesously. Then it concatenates the results. <br>
Xception's Approach: Xception replaces the traditional Inception module with Depthwise Separable Convolutions (DSC). This technique effectively decouples the learning of spatial correlations (e.g., shapes, textures) from cross-channel correlations (e.g., color, intensity changes).
  - First, a depthwise convolution is applied to each input channel separately to learn spatial features.
  - Then, a pointwise convolution (1 * 1) is used to combine the outputs across all channels, learning the cross-channel correlations.
Advantage in Medical Imaging: For complex medical images like dermoscopy (which show fine, intricate, and often subtle textures, borders, and color variations), the decoupled approach in Xception may allow the network to learn these distinct features more efficiently and effectively. Therefore, it would lead to better discrimination between subtle patterns of benign and malignant lesions.
2. Parameter Efficiency <br>
DSCs significantly reduce the total number of parameters compared to the multiple standard convolutions used in the Inception model, especially when the number of filters is large.
3. Computational Efficiency <br>
Fewer parameters and the structured nature of DSCs geenrally translate to faster training times and inference (prediction). This makes Xception model more practical for eal-time or resource-constrained clinical applications.
4. Simplified Architecture <br>
Xception uses a linear stack of DSC layers with residual connections. This structure is simpler than the multi-branch design of Inception models. The simpler and more direct path lead to better gradient flow during training. This potentially aides convergence and prevents the "vanishing gradient" problem in very deep networks. This is crucial for maximizing performance from transfer learning.
### Evaluation: AUC
In this study, the best achieved area under the ROC curve (AUC) score was 0.8636. The result of 0.86 AUC is excellent and a strong indicator of Xception's potential in medical imaging. Howeover, I want to study sthe state of the art of melanoma classification to better understand the optimization route.
## State-of-the-Art Models for Melanoma Classification
## Future Work


