# Detecting Pneumonia from Chest X-Ray Images Using DenseNet121

## Project Overview
This project classifies grayscale chest X-ray images into three categories: normal, bacterial pneumonia, and viral pneumonia using DenseNet121. Preprocessing steps included rescaling, data augmentation, class weighting, and K-fold cross-validation. It was developed in collaboration with Panagiotis Ioannou.

## Data
- **Training Set**: 4672 images
  - Normal: 1227 images
  - Bacterial Pneumonia: 2238 images
  - Viral Pneumonia: 1207 images
- **Test Set**: 1168 images

## Preprocessing
- Rescaling to normalize pixel values
- Data augmentation (random rotations, shifts, zooming)
- Class weighting to handle imbalance
- 5-fold cross-validation

## Model: DenseNet121
- Dense connectivity for better gradient flow and feature reuse
- Composite function (Batch Normalization, ReLU, 3x3 convolution)
- Transition layers for down-sampling
- Last 30 layers unfrozen for fine-tuning

## Hyperparameters
- **Learning rate**: 0.0001
- **Batch size**: 32
- **Epochs**: 25
- **Optimizer**: Adam
- **Loss function**: Categorical Crossentropy
- **Early stopping patience**: 7
- **Reduce LR factor**: 0.2
- **Reduce LR patience**: 5
- **Class weight**: {0: 1.27, 1: 0.70, 2: 1.29}
- **Dropout**: 0.5
- **L2 regularizer**: 0.001

## Best Submission Approache
- We followed the approach of selecting the best model weights based on validation metrics and averaged predictions across folds without reinitializing the model. This can lead to potential data leakage and overfitting issues.

## Conclusion
Successfully developed a model for classifying chest X-ray images with high accuracy using robust preprocessing and training methodologies. Further improvements can focus on refining hyperparameters and reducing overfitting.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Feedback
Your thoughts and feedback are welcome! Please feel free to open an issue or contact me directly at jimiatro@hotmail.com.
