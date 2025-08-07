---
layout: post
title: Bone Fracture Detection Using Deep Learning
date: 2024-05-14
excerpt: "A deep learning pipeline for classifying bone fractures from X-ray images using MobileNetV2 and advanced image augmentation techniques"
project: true
tags:
- Convolutional Neural Network (CNN)
- Deep Learning
- MobileNetV2
- Medical Imaging
- TensorFlow
comments: true
---

# Introduction

This project explores the application of deep learning to automate bone fracture detection from X-ray images. Built entirely as a solo effort for college course, Metode Penelitian, the goal was to create a lightweight and accurate classifier to distinguish between fractured and non-fractured bone scans.

The model architecture is based on **MobileNetV2**, a highly efficient CNN designed for fast inference on low-resource devices, making it an ideal candidate for medical imaging tasks where speed and scalability matter. Combined with aggressive data augmentation and hyperparameter tuning, the model achieves strong performance with minimal overfitting — a critical factor in medical AI applications.

#### Dataset

The dataset includes X-ray images labeled as 'fractured' and 'not fractured'. It is divided into:

- **Training**: 9,240 images  
- **Validation**: 823 images  
- **Testing**: 500 images  
[`Dataset >>`](https://www.kaggle.com/datasets/bmadushanirodrigo/fracture-multi-region-x-ray-data)

#### Data Preprocessing

To improve robustness and reduce overfitting, the images were preprocessed using a comprehensive augmentation pipeline:

- **Transformations**:
  - Random horizontal flipping
  - Brightness & contrast variation
  - Saturation & hue jittering
- **Resizing & Normalization**:
  - All images resized to 224x224 pixels
  - Pixel normalization applied
- **Class Balance**:
  - Ensured even representation of fracture and non-fracture images during batching

# Model Architecture

#### Base Model: MobileNetV2

Selected for its balance of **accuracy and computational efficiency**, MobileNetV2 is well-suited for mobile and embedded deployment scenarios — key for real-world medical applications in under-resourced environments.

- Pretrained weights from **ImageNet** were used as a feature extractor
- The top classification head was removed and replaced with a custom classifier

#### Custom Layers

- `Flatten` → to reshape feature maps
- `Dense (512, ReLU)` → core learnable layer
- `Dropout (0.5)` → added for regularization
- `Dense (2, Sigmoid)` → binary classifier output layer

#### Training Strategy

- **Loss Function**: Binary Cross-Entropy
- **Optimizer**: Adam with tuned learning rate
- **Regularization**: Dropout, data augmentation
- **Callback**: Early stopping based on validation loss

# Result

#### Training & Validation Metrics

- **Training Accuracy**: 97.67%
- **Validation Accuracy**: 94.53%
- Clear convergence with minimal overfitting due to regularization and augmentation strategies

#### Test Set Evaluation

Evaluated on 500 held-out test images:

- **Accuracy**: 94.80%
- **Precision**: 94.79%
- **Recall**: 94.79%
- **F1-Score**: 94.79%

# Conclusion

This project demonstrates how a carefully tuned deep learning model, built with production-aware design (MobileNetV2), can deliver high accuracy in a critical medical imaging task. The strong results, even on unseen data, reflect the impact of combining modern architectures with proper augmentation, regularization, and validation strategies.

From architecture selection to test evaluation, all components were developed independently as part of a research-driven capstone — showcasing both **technical depth** and the ability to apply deep learning responsibly to health-related challenges.

[`Go to Kaggle >>`](https://www.kaggle.com/code/malindaratnaduhita/bone-fracture-classification-with-mobilenetv2/)
