---
layout: post
title: Bone Fracture Detection Using Deep Learning
date: 2024-05-14
excerpt: "A deep learning model to detect bone fractures from X-ray images using the MobileNetV2 architecture"
project: true
tags:
- Convolutional Neural Network (CNN)
- Deep Learning
- MobileNetV2
comments: true
---


# Introduction

The objective of this project is to develop a deep learning model to classify bone fractures using X-ray images. This task is crucial for automating the diagnosis process, potentially reducing the time required for analysis and increasing the diagnostic accuracy. The chosen model leverages the MobileNetV2 architecture, a pre-trained convolutional neural network optimized for image classification tasks. This approach aims to achieve high accuracy in distinguishing between fractured and non-fractured bone images.

#### Dataset
The dataset consists of X-ray images labeled as 'fractured' and 'not fractured'. It is divided into three sets: training, validation, and testing, with a total of 9240 training images, 823 validation images, and 500 test images. [`Dataset >>`](https://www.kaggle.com/datasets/bmadushanirodrigo/fracture-multi-region-x-ray-data)
#### Data Preprocessing
The images are preprocessed using data augmentation techniques including random flip, brightness adjustment, contrast adjustment, saturation adjustment, and hue adjustment to enhance the model’s robustness. The images are resized to 224x224 pixels, normalized, and augmented to improve generalization.

# Model Architecture
#### Base Model
MobileNetV2: Utilized for its efficiency and effectiveness in image classification tasks, with pre-trained weights on ImageNet. The top layer is removed to allow for custom classification.
#### Custom Layers
* Flatten Layer: Converts the 2D feature maps to 1D feature vectors.
* Dense Layer: A fully connected layer with 512 neurons and ReLU activation.
* Dropout Layer: Applied with a rate of 0.5 to reduce overfitting.
* Output Layer: A Dense layer with 2 neurons and sigmoid activation for binary classification.


# Result
#### Training and Validation Metrics
* Accuracy: Achieved an accuracy of 97.67% on the training set and 94.53% on the validation set after 10 epochs.
* Loss: The training loss decreased steadily, with validation loss showing minor fluctuation

#### Test Set Evaluation
The model was evaluated on the test dataset. The classification report shows the following metrics:
* Accuracy: 94.80%
* Precision: 94.79%
* Recall: 94.79%
* F1 Score: 94.79%


# Conclusion

The model demonstrates high accuracy in classifying bone fractures from X-ray images, achieving nearly 95% accuracy on the test set. The use of MobileNetV2, combined with data augmentation and fine-tuned hyperparameters, proved effective in this binary classification task. Future work could explore additional data augmentation techniques, fine-tuning the model further, or experimenting with different architectures to potentially improve performance.



[`Go to Kaggle >>`](https://www.kaggle.com/code/malindaratnaduhita/bone-fracture-classification-with-mobilenetv2/)