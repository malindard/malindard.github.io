---
layout: post
title: BUMATARA - Phishing URL Checker
date: 2025-06-30
excerpt: "An AI-based system to detect phishing websites and email addresses using feature extraction, XGBoost classification, and LLM content analysis"
project: true
tags:
- Phishing Detection
- XGBoost
- LLM
- Flask
- Streamlit
- Cybersecurity
- Email Classification
comments: true
---


# Introduction

This project focuses on building a phishing detection system that classifies whether a given URL or email address is phishing. The system uses a two-stage pipeline: the first stage applies machine learning to extract and classify feature-based patterns, and the second stage integrates a large language model (LLM) to analyze website content. This hybrid approach enables a more accurate and explainable phishing detection workflow for both URLs and email addresses.

# Dataset & Features
* URL Classification: 23 handcrafted features are extracted from the user-submitted URL, including domain structure, HTTPS usage, character patterns, and redirect behavior. [`Phishing Dataset >>`](https://data.mendeley.com/datasets/c2gw7fy2j4/3)
* Email Classification: Email address features are derived from the CEAS dataset. Only email-related features are used, and additional engineered features are created from the email string (e.g., domain reputation, uncommon subdomains, numeric ratio). [`Email Dataset >>`](https://www.kaggle.com/datasets/naserabdullahalam/phishing-email-dataset)
* Content Analysis: After classifying the URL, web content (meta tags, titles, forms, scripts) is scraped and analyzed using a LLM. 

# Model & Architecture
1. URL and Email Classification
* Extract features from input URLs and email addresses.
* URLs are classified using an XGBoost model, while emails are classified using a CatBoost model.
* URL model achieved 96% accuracy, and the email classifier achieved 81% accuracy with CEAS-based features.
2. Content Analysis with LLM
* Scraped content from the target website is sent to DeepSeek v2 LLM via OpenRouter API.
* The LLM returns a human-readable judgment and reasoning for phishing detection.

# System Workflow
1. User submits either a URL or an email address.
2. The system identifies the input type and routes it to the appropriate classifier: XGBoost for URLs or CatBoost for emails.
3. Features are extracted and classified using the corresponding model.
4. If the input is a URL, the website is scraped and its content analyzed by the LLM.
5. Final results and reasoning are displayed to the user, and stored for review.

# Deployment & Tools
* Backend: Python, Flask API, MySQL
* Frontend: Laravel (in development)
* LLM Access: OpenRouter API with DeepSeek v3
* Hosting: Models deployed on AWS EC2 instance

# Result
* URL classifier achieved 96% accuracy.
* Email classifier using CatBoost achieved 81% accuracy with CEAS-based and engineered features.
* LLM-enhanced output enables deeper understanding of phishing behavior.

# Conclusion
The phishing detection system combines traditional ML and LLM to create a unified tool for detecting malicious URLs and email addresses. It emphasizes both accuracy and explainability, making it useful for general users and cybersecurity applications. Future developments will focus on refining the email classifier and fully deploying the platform.

[`Go to Project - BUMATARA >>`](https://bumatara.com/)
[`Go to my task in this project >>`](https://github.com/malindard/phishing-checker-flask)