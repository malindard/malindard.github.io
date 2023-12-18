---
layout: post
title: Brain Tumor Detection with 3 CNN Models
date: 2023-06-15
excerpt: "A Comparative Analysis of CNN Models with Augmented and Non-Augmented Datasets for Brain Tumor Detection"
project: true
tags:
- Augmentation Data
- Machine Learning
- Computer Vision
- Convolutional Neural Network (CNN)
- TensorFlow
comments: true
---


# Introduction

The timely detection of brain tumors is crucial for effective medical intervention and treatment. This project introduces an automated system leveraging Convolutional Neural Networks (CNNs) to accurately identify brain tumors in medical images. By implementing three distinct CNN models—ResNet50, InceptionV3, and VGG19—this study aims to evaluate their performance in brain tumor detection. Additionally, the impact of data augmentation on model accuracy is explored to enhance the overall efficacy of the detection system.


# Dataset

The dataset, comprising 253 brain MRI scans sourced from Kaggle, includes both tumor and non-tumor images. To ensure a balanced distribution, the dataset is divided into training and testing sets, and preprocessing is conducted to format it for compatibility with the CNN models. [`Dataset >>`](https://www.kaggle.com/datasets/navoneel/brain-mri-images-for-brain-tumor-detection)


# Models

Transfer learning is a deep learning technique where a model previously trained on a different task is used as a foundation to build a new model for a different task. By leveraging a pre-trained architecture as a starting point, the new model can be trained faster and requires less data compared to building a model from scratch. The following are the transfer learning models that will be utilized for this research:

#### 1. ResNet50:
ResNet50V2 is an enhanced variant of the ResNet50 architecture, boasting improved performance with 50 layers consisting of 49 convolutional layers and 1 fully connected layer.
<figure>
	<a href="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/resnet50v2.png"><img src="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/resnet50v2.png"></a>
	<figcaption><a>ResNet50V2 architecture.</a>.</figcaption>
</figure>

#### 2. VGG19:
VGG19 is a CNN model comprising 19 layers, featuring a relatively straightforward architecture.
<figure>
	<a href="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/vgg19.png"><img src="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/vgg19.png"></a>
	<figcaption><a>VGG19 architecture.</a>.</figcaption>
</figure>

#### 3. InceptionV3:
InceptionV3 is a CNN model specifically designed to address computational efficiency issues in deep CNN architectures.
<figure>
	<a href="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/inceptionv3.png"><img src="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/inceptionv3.png"></a>
	<figcaption><a>RInceptionV3 architecture.</a>.</figcaption>
</figure>


# Result

The utilization of data augmentation emerges as a pivotal factor in refining the CNN models' performance for brain tumor detection. Models trained without data augmentation exhibit signs of overfitting, characterized by higher training accuracy but lower validation accuracy and increased loss. In contrast, models trained with augmented data showcase improved results, demonstrating higher validation accuracy and reduced validation loss.

<figure class="third">
	<img src="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/resnet-without-augmentation.png">
	<img src="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/vgg-without-augmentation.png">
	<img src="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/inception-without-augmentation.png">
	<figcaption>Accuracy of ResNet50V2, VGG19, and InceptionV2 models with data without augmentation.</figcaption>
</figure>

<figure class="third">
	<img src="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/resnet-with-augmentation.png">
	<img src="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/vgg-with-augmentation.png">
	<img src="https://raw.githubusercontent.com/malindard/brain-tumor-detection/main/assets/inception-with-augmentation.png">
	<figcaption>Accuracy of ResNet50V2, VGG19, and InceptionV2 models with data augmentation.</figcaption>
</figure>

Data augmentation proves instrumental in enabling the models to grasp intricate patterns and variations within the dataset, ultimately facilitating more accurate predictions on unseen data. The robust performance of all three CNN models underscores their effectiveness in processing data and generating precise outputs for brain tumor detection.


# Conclusion

In conclusion, this project underscores the significance of data augmentation in enhancing the accuracy of CNN models for brain tumor detection. The implementation and comparative analysis of ResNet50, InceptionV3, and VGG19 reveal their capabilities in accurately identifying brain tumors in medical images. The findings provide valuable insights for further research and development in automated medical image analysis, contributing to the ongoing efforts to improve early diagnosis and treatment of brain tumors.


# References

[1] Sethy, Prabira Kumar. “A data constrained approach for brain tumour detection using fused deep features and SVM.” Multimedia Tools and Applications, vol. 80, 2021, pp. 28745–28760.

[2] “Transfer learning and fine-tuning.” TensorFlow, 15 December 2022, https://www.tensorflow.org/tutorials/images/transfer_learning. Accessed 1 April 2023.


[`Go to repo >>`](https://github.com/malindard/brain-tumor-detection)