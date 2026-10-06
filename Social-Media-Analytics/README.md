# Sponsored Travel Post Detection on Social Media

A machine learning framework for detecting potentially sponsored travel posts on social media by combining **text semantics, user behavior, engagement signals, sentiment features, and promotional patterns**.

## Overview

Sponsored content on social media is often presented in the form of personal experience sharing, making it difficult for users and platforms to distinguish genuine recommendations from commercial promotion.

This project develops an automated detection framework for identifying **potentially sponsored travel posts on Dcard**, a major social media platform in Taiwan. The system combines semantic text representations with structured behavioral and engagement features to capture both the linguistic and behavioral patterns associated with sponsored content.

## Data

The dataset was collected from the **Dcard Travel forum** using Python-based crawling and platform APIs.

- **5,200** posts were initially collected
- **5,081** valid posts remained after data cleaning
- **2,000** posts were selected for manual labeling
- Two independent annotators achieved **94.5% agreement**
- Cohen’s Kappa reached **0.67**, indicating substantial agreement
- An additional **73 sponsored posts** were added to improve class balance

The final labeled dataset contains both sponsored and non-sponsored travel posts for model training and evaluation.

## Feature Engineering

The project combines multiple dimensions of social media information.

### Text and Content Features

- Post length and text length
- Line-break and layout patterns
- External link and UTM-link ratios
- Image and video usage
- Promotional keyword frequency
- Sentiment score and sentiment volatility

### Social and Behavioral Features

- Likes, comments, collections, and shares
- Comment timing and interaction depth
- Author reply behavior
- Creator and account attributes
- Historical posting frequency and posting intervals
- Travel-post ratio and forum diversity

### Semantic Features

Chinese BERT (`ckiplab/bert-base-chinese`) was used to extract semantic representations from post titles and content.

Two feature integration strategies were evaluated:

- **Stacking** — BERT-based sponsored-post probabilities were combined with structured features and passed to a meta-classifier.
- **Early Fusion** — PCA-reduced BERT embeddings were concatenated directly with structured features.

## Modeling

Several machine learning models were evaluated:

- Logistic Regression
- Support Vector Machine
- Random Forest
- XGBoost
- LightGBM

To address the strong class imbalance between sponsored and non-sponsored posts, the project also tested:

- **SMOTE**
- **Random Oversampling (ROS)**
- **Class-weight adjustment**
- **Decision-threshold tuning**

Two application scenarios were considered:

1. **Content Management** — Uses both post content and post-publication engagement features.
2. **Real-Time Detection** — Uses only information available at the moment a post is published.

## Results

For the **content management scenario**, the best-performing architecture was a **Stacking model using Random Forest with ROS**, achieving:

- **Accuracy:** 0.920
- **AUC:** 0.892
- **Sponsored-post F1-Score:** 0.607

For **real-time detection**, the best overall performance was obtained using **Stacking with Random Forest and SMOTE**, with:

- **Accuracy:** 0.920
- **AUC:** 0.895
- **Sponsored-post F1-Score:** 0.593

Feature importance analysis showed that semantic signals from post content and titles were among the strongest predictors, while post length, engagement metrics, posting behavior, image usage, and sentiment also contributed to sponsored-content detection.

The results suggest that combining **semantic text information with behavioral and structural features** provides more robust performance than relying on either type of information alone.

## Repository Structure

```text
Social-Media-Analytics/
├── Sponsored-Travel-Post-Detection-Report.pdf   # Full project report
├── Sponsored-Travel-Post-Detection-Slides.pdf   # Final presentation slides
└── README.md
```

## Tech Stack

`Python` · `BERT` · `scikit-learn` · `Random Forest` · `XGBoost` · `LightGBM` · `SVM` · `PCA` · `SMOTE` · `Sentiment Analysis`

## Project Context

**Social Media Analytics, National Taiwan University**  
Team Project · Social Media Analytics · NLP · Machine Learning · Behavioral Analytics
