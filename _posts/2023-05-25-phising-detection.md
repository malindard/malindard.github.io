---
layout: post
title: Phising Detection with Traditional Machine Learning and Deep Learning Algorithms
date: 2023-12-10
excerpt: "Phising Detection With Decision Tree, Random Forest, Logistic Regression, Naive Bayes, CNN-LSTM, and Multi-Layer Perceptron."
#project: true
tags:
- Machine Learning
- Deep Learning
- Phising Detection
comments: true
---


# Introduction

In the rapidly evolving landscape of cyber threats, phishing remains a pervasive and cunning method employed by attackers to compromise sensitive information. To combat this menace, our project delves into the realm of phishing detection, employing a diverse set of algorithms ranging from traditional machine learning to cutting-edge deep learning models.


# Dataset

The dataset utilized in this project, titled **Dataset of Malicious and Benign Webpages** was sourced from Kaggle. It serves as a critical component for training and evaluating our phishing detection system. The dataset's primary objective is to classify webpages into either malicious or benign categories.
[`Dataset >>`](https://www.kaggle.com/datasets/aksingh2411/dataset-of-malicious-and-benign-webpages)


# Traditional Machine Learning Algorithms
#### Decision Tree
Decision Trees (DT) provide an intuitive approach to classify phishing websites based on a set of rules. By visualizing decision boundaries, DT helps us understand the factors that contribute to identifying potential threats.

#### Random Forest
Random Forest, an ensemble learning technique, combines multiple decision trees to enhance the accuracy of phishing detection. The collaborative decision-making process strengthens the model's resilience against false positives.

#### Logistic Regression
Logistic Regression, a classic classification algorithm, is adept at discerning between legitimate and phishing websites by mapping input features to a binary outcome. Its simplicity and efficiency make it a valuable addition to our detection arsenal.

#### Naive Bayes
Naive Bayes, based on Bayes' theorem, excels in probabilistic classification. Its ability to handle large datasets and quick training times make it an effective choice for identifying phishing attempts.

# Deep Learning Algorithms
#### Convolutional Neural Network - Long Short-Term Memory (CNN-LSTM)
The fusion of Convolutional Neural Networks (CNN) and Long Short-Term Memory (LSTM) networks enables our model to capture both spatial and temporal patterns in web page structures. This hybrid architecture proves potent in recognizing sophisticated phishing tactics.

#### Multi-Layer Perceptron (MLP)
A Multi-Layer Perceptron, a fundamental component of deep learning, is employed for its capability to discern intricate patterns within vast datasets. Its multiple layers facilitate the extraction of hierarchical features crucial for identifying phishing characteristics.


# Result

|      Algorithms   | Accuracy |
|:------------------|---------:|
|    Decision Tree  |   99.1%  |
|    Random Forest  |   99.5%  |
|Logistic Regression|   97.3%  |
|     Naive Bayes   |   97%    |
|      CNN-LSTM     |   99.5%  |
|         MLP       |   98.5%  |


# Conclusion

In conclusion, our project rigorously tested and trained each algorithm individually using a comprehensive dataset of both legitimate and phishing websites. Through this meticulous approach, we assessed the unique strengths and capabilities of Decision Trees, Random Forest, Logistic Regression, Naive Bayes, CNN-LSTM, and Multi-Layer Perceptron in the context of phishing detection. Each algorithm underwent rigorous testing using the same dataset, allowing for a thorough comparative analysis of their efficacy in identifying and thwarting phishing attempts.


For further details on the implementation and results, refer to the complete project documentation available [`here >>`](https://www.kaggle.com/code/malindaratnaduhita/phishing-detection-with-dt-rf-cnn-lstm)