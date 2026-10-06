# Big Data and Business Analytics Projects

This repository contains two course projects from **Big Data and Business Analytics at National Taiwan University**, covering both **text-based financial prediction** and **customer analytics for e-commerce**.

---

## Project 1 — Text-Based Stock Price Prediction

A text classification project that explores whether social media and market-related textual information can be used to predict stock price movements.

### Overview

The project focuses on **Alchip Technologies (世芯-KY, 3661)**, selected because of its high discussion volume and substantial price volatility.

From January 2023 to March 2025, approximately **5,230 related articles** were collected for analysis.

### Data Processing

Two labeling strategies were compared:

- **Market-reaction labeling** — Articles were labeled as bullish, bearish, or neutral according to the stock return three days after publication.
- **LLM-based labeling** — `Llama-3.1-8B` was used in a zero-shot setting to infer whether each article expressed a bullish, bearish, or neutral view.

Chinese text was segmented using **Monpa**, followed by noise filtering and TF-IDF vectorization.

Two TF-IDF approaches were evaluated:

- A manually selected vocabulary based on discriminative TF-IDF scores
- Full-vocabulary vectorization using `TfidfVectorizer`

### Modeling

Eight classification models were evaluated across different labeling and vectorization settings:

`Naive Bayes` · `SVM` · `KNN` · `Decision Tree` · `Random Forest` · `MLP` · `XGBoost` · `Keras`

A total of **32 model configurations** were compared.

### Results

The strongest performance came from **LLM-labeled data with full-vocabulary TF-IDF features**.

Top-performing models included:

- **Keras:** 92% accuracy
- **MLP Neural Network:** 91% accuracy
- **Linear SVM:** 91% accuracy

A rolling backtest was then conducted using a linear SVM trained on the previous month's articles.

The best backtesting approach achieved approximately **61.5% accuracy**, but performance was strongly biased toward predicting upward movements, resulting in low recall for downward movements.

This highlighted an important distinction between **text classification performance** and **real-world predictive usefulness in financial markets**.

---

## Project 2 — Customer Segmentation and LTV Prediction

A customer analytics framework that combines **RFM segmentation, clustering, machine learning, repurchase prediction, and Lifetime Value estimation** to support more targeted marketing decisions.

### Overview

Traditional RFM analysis provides a simple way to classify customers based on:

- **Recency**
- **Frequency**
- **Monetary value**

However, static RFM segmentation alone may not fully capture customer heterogeneity or future value.

This project extends RFM analysis by combining **K-means clustering with predictive machine learning models** to identify customer segments, predict repurchase behavior, estimate future spending, and calculate customer Lifetime Value (LTV).

### Data

The analysis uses member and transaction-level data.

- **Training period:** January 2022 – June 2023
- **Prediction period:** July 2023 – February 2024
- **Reference date:** June 30, 2023

Features include:

- Age and gender
- Registration source
- Membership level
- Email, push-notification, and SMS settings
- App / Web / offline purchasing channels
- Purchase amount
- Payment method
- Discount usage

Outliers were filtered using the **1.5× IQR rule** before modeling.

### Customer Segmentation

Multiple clustering approaches were explored:

- K-means
- Agglomerative Clustering
- HDBSCAN

The final solution used **K-means with four clusters**, producing four customer profiles:

1. **Stable Consumers**
2. **Churn-Risk Customers**
3. **New-Potential Customers**
4. **High-Frequency High-Value Customers**

PCA was used to visualize the resulting customer segments.

### Repurchase and Spending Analysis

Linear regression and XGBoost were used to identify key drivers of:

- Purchase amount
- Repurchase behavior

Three definitions of repurchase were compared:

- Customers who purchased more than once
- Repurchase within 365 days before the reference date
- Repurchase within 365 days after the first purchase

Important predictors included variables such as:

- Purchase frequency
- Recency
- Membership level
- Registration source
- App installation
- Email and SMS notification settings

### LTV Modeling

Customer Lifetime Value was modeled as:

**LTV = Predicted Purchase Amount × Predicted Repurchase Probability**

XGBoost was used for both regression and classification tasks.

The resulting framework links customer segmentation with predictive modeling, allowing different marketing strategies to be designed for each customer segment.

---

## Repository Structure

```text
Big-Data-and-Business-Analytics/
├── Customer-Segmentation-RFM-LTV-Prediction-Slides.pdf   # Final project: customer segmentation and LTV modeling
├── Text-Based-Stock-Price-Prediction-Slides.pdf           # Midterm project: text-based stock movement prediction
└── README.md
```

## Tech Stack

`Python` · `Pandas` · `scikit-learn` · `XGBoost` · `K-means` · `PCA` · `TF-IDF` · `SVM` · `MLP` · `Keras` · `Llama-3.1-8B` · `Monpa`

## Project Context

**Big Data and Business Analytics, National Taiwan University**  
Team Projects · Business Analytics · Customer Analytics · NLP · Machine Learning · Predictive Modeling
