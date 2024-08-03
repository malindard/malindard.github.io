---
layout: post
title: Sentiment Analysis Using Transformers
date: 2024-07-26
excerpt: "Explore sentiment analysis on Indonesian presidential candidates' tweets using Naive Bayes and BERT models"
project: true
tags:
- Sentiment Analysis
- Naive Bayes
- BERT
- Transformers
comments: true
---


# Introduction

This project focuses on performing sentiment analysis using Python on tweets related to 2024 Indonesian presidential candidates. Sentiment analysis aims to classify text into positive or negative sentiment categories using machine learning techniques. The project employs two main methodologies: Naive Bayes as a baseline model and BERT (Bidirectional Encoder Representations from Transformers) for advanced sentiment analysis.

#### Dataset
The dataset consists of tweets from three Indonesian presidential candidates: Anies Baswedan, Prabowo Subianto, and Ganjar Pranowo. Each dataset includes columns such as 'Tweet Count', 'Text', and 'label' (indicating sentiment as 'Positive' or 'Negative'). The combined dataset is used for training and evaluating the sentiment analysis models. [`Dataset >>`](https://www.kaggle.com/datasets/jocelyndumlao/indonesia-presidential-candidates-dataset-2024)
#### Data Preprocessing
Data preprocessing involves several steps to clean and prepare the text data for analysis
* Text Cleaning: Removing special characters, URLs, mentions, and non-ASCII characters.
* Handling Missing Data: Dropping rows with missing values.
* Balancing Classes: Addressing class imbalance by oversampling using RandomOverSampler.
* Text Tokenization: Tokenizing text for both Naive Bayes (using CountVectorizer and TfidfTransformer) and Transformers (using BERT's tokenizer).

# Model Architecture

#### Base Model

* Utilizes CountVectorizer and TF-IDF Transformer for tokenizing and vectorizing text.
* Implements a Multinomial Naive Bayes classifier to predict sentiment based on tokenized features.

#### BERT (Bidirectional Encoder Representations from Transformers):

* Uses the BERT model from Hugging Face's transformers library.
* Tokenizes input text and generates input sequences using BERT's tokenizer.
* Develops a custom neural network architecture around TFBertModel for sentiment classification.
* Model architecture includes input tokenization, attention masks, and a dense softmax layer for classification.
* Trains the model on tokenized input data and evaluates its performance using various metrics.


# Result
#### Naive Bayes:
Achieved an accuracy of approximately 85% with balanced precision and recall scores for both 'Positive' and 'Negative' sentiments.
#### BERT Model:
* Achieved an accuracy of 93% with high precision, recall, and F1-scores for both sentiment classes ('Positive' and 'Negative').
* Outperformed the Naive Bayes baseline significantly, demonstrating superior performance in sentiment classification tasks.


# Conclusion

This project demonstrates the effectiveness of both traditional machine learning (Naive Bayes) and state-of-the-art deep learning techniques (BERT) for sentiment analysis of tweets. The BERT model, in particular, showed robust performance in classifying sentiment with high accuracy and reliability. Future work could involve further fine-tuning of models, exploring additional datasets, and potentially deploying the BERT model for real-time sentiment analysis applications.



[`Go to Kaggle >>`](https://www.kaggle.com/code/malindaratnaduhita/sentiment-analysis-using-transformers-bert)