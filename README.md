# X-ray Fracture Classification: Simple vs Comminuted
This project focuses on classifying X-ray images into two categories: simple fractures and comminuted fractures. It explores two deep learning approaches: a CNN trained from scratch and a transfer learning model using EfficientNetB2. The goal is to evaluate and compare their performance in medical image classification.

## 1. Dataset
We used the Simple vs Comminuted Fractures X-ray Data from Kaggle (Dec 2024), which includes both original and augmented images. The dataset contains a total of 16,061 JPG images, split between the two classes. Augmentation techniques such as zoom, rotation, brightness/contrast adjustment, and mirroring were applied to improve generalization and reduce overfitting.

## 2. CNN Trained from Scratch
The custom CNN architecture includes convolutional layers with batch normalization, pooling, and dropout for regularization. ReLU is used as the activation function in hidden layers, and sigmoid in the output layer for binary classification. The model was compiled with the Adam optimizer, binary crossentropy loss, and accuracy as the evaluation metric.

After tuning hyperparameters across 30 experiments, the best configuration achieved:

- Training Accuracy: 93.72%
- Validation Accuracy: 87.38%
- Test Accuracy: 87.60%
These results indicate good generalization with minimal overfitting.

## 3. Transfer Learning with EfficientNetB2
The EfficientNetB2 model was used as a pre-trained base on ImageNet, with two strategies applied: full freezing of all layers and partial fine-tuning of deeper layers. The architecture was extended with custom dense layers for binary classification. RMSprop was selected as the optimizer, with ReLU activation in intermediate layers and Dropout for regularization to reduce overfitting.

After testing various hyperparameter combinations, the best configuration achieved:

- Training Accuracy: 96.10%
- Validation Accuracy: 95.00%
- Test Accuracy: 92.85%

These results demonstrate the strong generalization and efficiency of transfer learning using EfficientNetB2 for medical image classification.

## 4. Evaluation
Both models were trained and validated using the same dataset splits. Performance was assessed using accuracy and loss on training, validation, and test sets. The CNN trained from scratch showed strong performance, while EfficientNetB2 offered faster convergence and competitive accuracy with fewer training epochs.

## 5. Conclusion
This project demonstrated how architectural choices and hyperparameter tuning significantly impact the performance of convolutional neural networks. Both the custom CNN and the EfficientNetB2-based models benefited from careful adjustments in learning rate, regularization, and layer configurations.

While the CNN trained from scratch achieved a solid test accuracy of 87.60%, the transfer learning approach with EfficientNetB2 reached up to 95% validation accuracy, highlighting the effectiveness of fine-tuning pre-trained models for specialized tasks.

These results reinforce the value of experimentation and the power of modern architectures in medical image classification.
