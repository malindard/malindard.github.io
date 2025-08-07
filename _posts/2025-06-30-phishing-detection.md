---
layout: post
title: BUMATARA - Phishing URL Checker
date: 2025-06-30
excerpt: "A hybrid AI system to detect phishing URLs and emails using handcrafted features, tree-based models, and LLM reasoning for real-time cybersecurity defense."
project: true
tags:
- Phishing Detection
- XGBoost
- LLM
- CatBoost
- Flask
- Cybersecurity
- AI Engineering
- OpenRouter
comments: true
---

# Introduction

**BUMATARA** is a phishing detection system built for real-world usability. It classifies whether a submitted URL or email address is malicious, combining classic machine learning with large language models (LLMs) for content-level analysis. Designed for both performance and explainability, the system uses handcrafted features, tree-based classifiers, and LLM reasoning to deliver judgments with human-readable insight.

Built during a hackathon with my team, this project is now publicly deployed and fully usable via [`bumatara.com`](https://bumatara.com/).

# Dataset & Features

**Multi-level detection** is achieved by using separate feature pipelines for URLs, email addresses, and website content:

- **URL Classification**  
  Uses 23 handcrafted features extracted from user-submitted URLs, such as:
  - Domain structure & subdomain length
  - Use of HTTPS or suspicious port numbers
  - Character entropy, special symbol ratios, redirects  
  [`Dataset Source →`](https://data.mendeley.com/datasets/c2gw7fy2j4/3)

- **Email Address Classification**  
  Built on the CEAS dataset, the system derives:
  - Domain reputation
  - TLD analysis (e.g., uncommon extensions)
  - Numeric character ratio, length patterns  
  [`Dataset Source →`](https://www.kaggle.com/datasets/naserabdullahalam/phishing-email-dataset)

- **Web Content Analysis**  
  For URL inputs, the system scrapes:
  - Meta tags, title content, inline forms, scripts
  - Then uses a **DeepSeek v2 LLM** to evaluate if the page mimics legitimate services or contains suspicious intent.

# Model & Architecture

The backend architecture blends **tree-based models for speed** with **LLM inference for depth**.

1. **Classification Layer**
   - **URLs**: XGBoost model trained on 23 engineered features.
   - **Emails**: CatBoost model fine-tuned on CEAS + custom features.
   - Model performance:
     - 🔍 96% accuracy for phishing URLs
     - ✉️ 81% accuracy for phishing email addresses

2. **LLM Analysis Layer**
   - Web scraping captures HTML-based content.
   - Uses OpenRouter API to query DeepSeek v2 LLM.
   - LLM returns a natural-language assessment like:  
     *"This page mimics a PayPal login and uses IP-based redirection, commonly found in phishing pages."*

# System Workflow

1. User submits either a URL or email address.
2. The system detects the input type and routes it to:
   - XGBoost (URL) or CatBoost (email) model.
3. Extracted features are classified.
4. If the input is a URL:
   - Web content is scraped and sent to the LLM for further analysis.
5. The final verdict and explanation are displayed on the site and stored for audit/logging.

# Deployment & Tools

- **Backend**: Python, Flask REST API
- **Frontend**: Laravel (fully deployed)
- **Database**: MySQL for logging input history and results
- **LLM Access**: OpenRouter API using DeepSeek v2
- **Deployment**: Hosted on AWS EC2 (Ubuntu)

Explore the live system here:  
🔗 [`BUMATARA - Phishing Checker`](https://bumatara.com)

# Result

- ✅ **96% accuracy** on malicious URL detection using XGBoost
- ✅ **81% accuracy** for email classification using CatBoost
- ✅ LLM layer adds **contextual reasoning** and boosts explainability
- 🧠 Combines fast inference with deep semantic review for better trustworthiness

# Conclusion

BUMATARA demonstrates how **hybrid AI systems** can combine traditional ML pipelines with modern LLMs to solve real-world cybersecurity problems. As the AI engineer on this project, I designed and deployed the models then integrated the OpenRouter LLM pipeline for content analysis.

This system shows that phishing detection doesn't have to be a black box. By blending structure-based classification with explainable AI, BUMATARA balances precision with usability — a practical solution for individual users and organizations alike.

🚀 Future work includes expanding the LLM prompt library, refining the email classifier with newer datasets, and rolling out multi-language phishing detection.

[`See Project →`](https://bumatara.com)  
[`My Tasks on GitHub →`](https://github.com/malindard/phishing-checker-flask)
