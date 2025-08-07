---
layout: post
title: MILA Chatbot – Aplikasi Chatbot Ibu Hamil Berbasis AI
date: 2025-06-30
excerpt: "An AI-powered maternal health assistant that combines intent classification using IndoBERT and generative dialogue via LLM to support pregnant and postpartum women."
project: true
tags:
- Chatbot
- IndoBERT
- LLM
- Flask API
- AI Engineering
- HealthTech
comments: true
---

# Introduction

**MILA Chatbot** is an AI-based conversational assistant built to support pregnant and postpartum women in accessing reliable, context-aware information related to maternal health. Developed for the PKM-AMLI competition, the system integrates a fine-tuned **IndoBERT** model for intent classification with **LLM-based generative responses**, creating an accessible solution for real-world maternal care challenges. This chatbot represents a proof of concept for AI applications in health literacy and digital empowerment.

# Dataset

A custom intent classification dataset was manually compiled, covering 54 pregnancy-related intent categories. It includes a total of **307 annotated samples**, designed to reflect real-world queries from pregnant and postpartum users, including:

- Prenatal care questions (e.g., "Bolehkah makan durian saat hamil?")
- Labor concerns (e.g., "Kapan harus ke rumah sakit?")
- Breastfeeding issues (e.g., "ASI tidak keluar, apa yang harus dilakukan?")

The dataset was sourced through domain research, online forums, and keyword extraction, followed by cleaning and labeling to match multi-class intent classification requirements.

# Data Preprocessing & Model

- **Preprocessing**:
  - Text normalization, tokenization, padding, truncation
  - Attention mask generation for transformer input
- **Classifier**:
  - Fine-tuned **IndoBERT** (Bahasa Indonesia BERT model)
  - Trained for multi-class intent recognition across 54 tags
- **LLM Integration**:
  - Integrated **Llama 3.1–8B-Instant** via Flask backend
  - Enables flexible, generative replies to complement fixed-intent response templates

# System Architecture

The system architecture follows a hybrid pipeline of classification + generation:

1. Users submit a message via the Android app interface.
2. The message is processed in parallel:
   - **IndoBERT** model classifies the user’s intent (e.g., "kontrol kehamilan", "ASI", "nutrisi").
   - The same input is sent to the **LLM** for generative response generation.
3. The predicted intent is stored in a database to enable learning and analytics.
4. The final response is returned to the user and displayed in the chat interface.
5. Users can also review prior chats by topic using the app.

- **Backend**: Python + Flask REST API
- **Frontend**: Android client (Kotlin)
- **Hosting**: Flask app deployed via **Google App Engine**

# Result

- ✅ **81% classification accuracy** from the IndoBERT fine-tuned model across 54 intent classes
- ✅ Integrated LLM responses for natural, human-like replies in Bahasa Indonesia
- ✅ Tested with **9 pregnant and postpartum users**, yielding positive informal feedback
- ✅ Evaluation supported by licensed midwives who reviewed generated responses for accuracy and tone

# Conclusion

MILA Chatbot demonstrates how AI can be applied to improve health literacy in underserved communities. By combining **intent-aware classification with LLM-powered replies**, the system creates dynamic, relevant, and trustworthy information access for expecting mothers.

From sourcing the dataset to fine-tuning IndoBERT and integrating Llama 3.1 for generative capabilities, this project reflects my end-to-end role as an AI engineer in building a conversational health assistant.

While the system is not yet public, it has been validated through user testing and healthcare expert review, and showcases the potential of AI to deliver impact-driven innovation in maternal health.

# Team & Credits

This project was developed collaboratively for PKM-AMLI by a multidisciplinary team of **Computer Science** and **Public Health** students, combining technical innovation with domain expertise in maternal healthcare.

🔗 Instagram: [@mila.chatbot](https://www.instagram.com/pkmkc.mila?igsh=zzlvcG9wN28yYmV2)

[`See Project →`](https://github.com/ReginaAyumi/mila-chatbot/)