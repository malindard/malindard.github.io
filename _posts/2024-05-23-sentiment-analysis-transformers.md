---
layout: post
title: Sentiment Analysis Using Transformers
date: 2024-07-26
excerpt: "A sentiment classification pipeline using Naive Bayes and fine-tuned BERT on tweets from Indonesian presidential candidates"
project: true
tags:
- Sentiment Analysis
- Naive Bayes
- BERT
- Transformers
- NLP
- HuggingFace
- Data Cleaning
comments: true
---

# Introduction

This project showcases a complete sentiment analysis pipeline built from scratch using Python and Transformers. The target data consists of tweets related to the 2024 Indonesian presidential candidates, classified into 'Positive' or 'Negative' sentiments. The project compares two modeling approaches:

- A traditional baseline using **Naive Bayes**
- A modern deep learning solution using **fine-tuned BERT**

As a solo project, I handled all stages — from data cleaning and class balancing to model training, evaluation, and benchmarking. The goal was to explore the contrast between classic machine learning and transformer-based NLP in a real-world political sentiment context.

#### Dataset

The dataset contains labeled tweets mentioning three candidates:
- **Anies Baswedan**
- **Prabowo Subianto**
- **Ganjar Pranowo**

Each tweet includes columns such as `Text`, `Tweet Count`, and `label` (positive/negative). The dataset was combined, preprocessed, and split into training and test sets.  
[`Dataset >>`](https://www.kaggle.com/datasets/jocelyndumlao/indonesia-presidential-candidates-dataset-2024)

#### Data Preprocessing

Robust preprocessing was critical due to the noisy nature of real-world tweets. Steps included:

- **Text Cleaning**:
  - Removed emojis, non-ASCII characters, mentions (`@`), hashtags, and URLs
  - Lowercased text, stripped punctuation
- **Handling Missing Data**:
  - Rows with null values were dropped
- **Class Balancing**:
  - Used `RandomOverSampler` to address imbalance between sentiment classes
- **Tokenization**:
  - For Naive Bayes: CountVectorizer + TfidfTransformer
  - For BERT: Hugging Face's BERT tokenizer with attention masks, padding, and truncation

# Model Architecture

#### Baseline: Naive Bayes
- Applied `CountVectorizer` + `TfidfTransformer` for feature extraction
- Used `MultinomialNB` for sentiment classification
- Fast, interpretable, and good baseline performance

#### Fine-Tuned BERT (Transformers)
- Leveraged Hugging Face's `bert-base-multilingual-cased` model
- Built a custom Keras model with:
  - BERT encoding layer (TFBertModel)
  - Dense layers for classification
  - Softmax activation
- Trained using tokenized inputs with attention masks
- Evaluated using accuracy, precision, recall, and F1-score

# Result

#### Naive Bayes:
- Accuracy: **~85%**
- Performed well on both sentiment classes with balanced precision and recall

#### Fine-Tuned BERT:
- Accuracy: **93%**
- Significantly outperformed Naive Bayes on all metrics
- High-quality sentiment classification even with informal or sarcastic tweets

# Conclusion

This project demonstrates the effectiveness of fine-tuning transformer models for sentiment analysis, particularly in noisy and politically charged tweet data. Compared to a Naive Bayes baseline, BERT showed superior accuracy and generalization across both sentiment classes.

Built entirely as a solo project, this work reflects my ability to handle real-world data preprocessing, apply modern NLP techniques, and evaluate model performance rigorously. It also highlights the practical strengths of transformer-based models for sentiment mining in social media.

[`Go to Kaggle >>`](https://www.kaggle.com/code/malindaratnaduhita/sentiment-analysis-using-transformers-bert)
