# NTU Projects Portfolio

A collection of academic projects completed at **National Taiwan University**, focusing on the application of **machine learning, artificial intelligence, data analytics, and optimization** to real-world problems.

This repository includes projects across e-commerce, social media, energy management, transportation, finance, and social science. Each project directory contains a detailed README along with available reports, presentation slides, and project results.

---

## Projects

### [E-Commerce Multimodal Compliance Detection](./Capstone-for-Business-Analytics)

Developed a multimodal AI framework to identify potentially non-compliant e-commerce product listings by integrating **product names, descriptions, and images**. The system combines rule-based screening with **LLaMA, LLaVA, and OCR** to capture both textual and visual compliance signals.

**Methods:** `LLaMA` · `LLaVA` · `OCR` · `BERT` · `Computer Vision` · `Python`

---

### [Sponsored Travel Post Detection on Social Media](./Social-Media-Analytics)

Developed a machine learning framework for detecting potentially sponsored travel posts on **Dcard** by combining semantic text representations with behavioral, engagement, sentiment, and promotional features. Compared stacking and early-fusion architectures under both content-management and real-time detection settings.

**Methods:** `BERT` · `Stacking` · `Random Forest` · `XGBoost` · `LightGBM` · `SMOTE`

---

### [Factory Energy Forecasting and Storage Scheduling Optimization](./Manufacturing-Data-Science)

Built an integrated forecasting-and-optimization framework for industrial energy management. Electricity demand and solar generation forecasts were incorporated into a hierarchical battery scheduling model to reduce electricity costs and peak-demand risk.

**Methods:** `XGBoost` · `Optuna` · `Time Series Forecasting` · `Quantile Regression` · `MILP`

---

### [Big Data and Business Analytics](./Big-Data-and-Business-Analytics)

Two projects exploring the application of machine learning to financial and customer analytics:

- **Text-Based Stock Price Prediction** — Used financial and social-media text to predict stock price movements, comparing multiple labeling strategies and classification models.
- **Customer Segmentation and LTV Prediction** — Combined RFM analysis, clustering, repurchase prediction, and spending prediction to estimate customer Lifetime Value.

**Methods:** `TF-IDF` · `SVM` · `Neural Networks` · `XGBoost` · `K-means` · `PCA`

---

### [TRTS Interval Train Scheduling Optimization](./Operations-Research)

Formulated a nonlinear optimization model for the **Taipei MRT Songshan–Xindian Line** to jointly determine train frequencies, fleet allocation, and short-turn service boundaries while minimizing passenger waiting time during peak periods.

**Methods:** `Operations Research` · `Nonlinear Programming` · `Gurobi` · `Transportation Analytics`

---

### [Political Spectrum Analysis via Social Media](./Data-Science-and-Social-Inquiry)

Analyzed Facebook posts from Taiwanese political figures and parties to examine whether political orientation could be inferred from social-media language. Compared traditional text representations with contextual BERT embeddings and visualized political positions across different policy topics.

**Methods:** `BERT` · `SVM` · `TF-IDF` · `NLP` · `Data Visualization`

---

### [DonChiDon Calorie Tracker](./Coding101-Calorie-Tracker-DonChiDon)

Developed a Python desktop application for personalized calorie management, including food and exercise tracking, calorie-goal calculation, food matching, and exercise recommendations.

**Methods:** `Python` · `Tkinter` · `Pandas` · `GUI Development`

---

## Repository Structure

```text
ntu-projects/
├── Capstone-for-Business-Analytics/
├── Social-Media-Analytics/
├── Manufacturing-Data-Science/
├── Big-Data-and-Business-Analytics/
├── Operations-Research/
├── Data-Science-and-Social-Inquiry/
├── Coding101-Calorie-Tracker-DonChiDon/
└── README.md
```

Each project directory provides further details on the **problem, data, methodology, results, and project materials**.
