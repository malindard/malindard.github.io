---
layout: post
title: MILA Chatbot – Aplikasi Chatbot Ibu Hamil Berbasis AI
date: 2025-06-30
excerpt: "An AI-powered chatbot designed to assist pregnant and postpartum women with accurate information through intent classification and generative responses"
project: true
tags:
- Chatbot
- IndoBERT
- LLM
- Flask API
comments: true
---


# Introduction

MILA Chatbot is an AI-powered conversational system designed to assist pregnant and postpartum women by providing accurate, context-aware information related to pregnancy, childbirth, and breastfeeding. Built for the PKM-AMLI competition, the project combines intent-based classification using IndoBERT with generative responses powered by LLM (Llama 3.1-8B-Instant). The system ensures both precision in detecting user intent and rich, natural dialogue experiences.

# Dataset
The dataset used for intent classification was manually constructed as a dummy dataset tailored to pregnancy-related topics. It consists of 307 training examples distributed across 54 unique intent labels. Each entry represents typical questions and statements made by pregnant women, ranging from prenatal care to breastfeeding guidance.

# Data Preprocessing & Model
* Data Preprocessing: Includes text cleaning, tokenization, padding, truncation, and attention mask creation.
* Model: Fine-tuned IndoBERT (pretrained) for multi-class intent classification.
* Generative Component: Integrated Llama-3.1-8B-Instant using Flask and Google App Engine to provide natural language responses.

# System Architecture
1. User inputs a question via the Android app.
2. Input is processed by both the IndoBERT classifier and the LLM.
3. The predicted intent (tag) is logged into a database.
4. The generative response from the LLM is displayed to the user.
5. Users can review past interactions by tag/category through the app.
The backend system includes a Flask API hosted on Google Cloud App Engine, while the frontend mobile client is built with Kotlin.

# Result
* The IndoBERT-based intent classifier achieved 81% accuracy.
* The chatbot was tested with real users including pregnant and postpartum women and received positive feedback
* Evaluations were supported by health professionals (midwives), affirming the chatbot’s relevance and usability.


# Conclusion
MILA Chatbot successfully demonstrates how AI can be applied to support maternal health education in a conversational format. Combining intent classification with generative AI enables more meaningful and helpful interactions. The deployment on Google Cloud ensures accessibility, and real-user testing confirms its practical value. This project highlights the potential for AI-driven health assistants to improve access to trusted information for mothers.

[`Go to Project >>`](https://github.com/ReginaAyumi/mila-chatbot/)