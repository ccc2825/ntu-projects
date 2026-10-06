# Political Spectrum Analysis via Social Media

A text classification project that analyzes **political orientation from social media posts** and visualizes the political spectrum of Taiwanese public figures across different issues.

## Overview

Social media has become an important channel through which politicians communicate their positions and engage with the public. This project explores whether political orientation can be inferred from the language used in social media posts.

Using Facebook posts from Taiwanese political figures and political parties, the project builds a supervised text classification model and applies it to estimate the political tendency of individual politicians across multiple policy topics.

## Data

The dataset contains approximately **33,773 Facebook posts** collected from:

- **18 political figures**
- **25 political parties**

The analysis covers politicians and parties from different political camps, including major parties such as the Kuomintang (KMT), Democratic Progressive Party (DPP), Taiwan People's Party (TPP), New Power Party, and Taiwan Statebuilding Party.

## Methodology

### Text Processing

Posts were cleaned and processed through text segmentation and keyword extraction. **TF-IDF** was used to construct text-based features for initial model experiments.

### Model Comparison

Several classification approaches were evaluated:

- **Keras-based model**
- **Support Vector Machine (SVM)**
- **BERT sentence embeddings + SVM**

The Keras-based approaches achieved approximately **0.53–0.56 accuracy**, while the BERT-based SVM achieved the strongest performance at approximately **0.83 accuracy**.

The final model therefore used **BERT sentence embeddings with SVM** for downstream political-position analysis.

### Political Spectrum Estimation

After training the classifier, the model was applied to posts from individual politicians to estimate their political orientation.

The results were then visualized across different topics to compare how politicians' positions changed depending on the issue being discussed.

## Results

The analysis suggests that:

- Politicians within the same party may still show different political positions.
- The same politician may shift position depending on the policy topic.
- Political orientation is not purely binary and is better interpreted as a spectrum.
- Most politicians' overall positions remain broadly consistent with public perceptions.

The project also shows that **contextual text representations from BERT** provide substantially better classification performance than simpler text-based approaches.

## Repository Structure

```text
Data-Science-and-Social-Inquiry/
├── Political-Spectrum-Analysis-via-Social-Media-Poster.png   # Project poster and results
└── README.md
```

## Tech Stack

`Python` · `BERT` · `SVM` · `Keras` · `TF-IDF` · `NLP` · `Text Classification` · `Data Visualization`

## Project Context

**Data Science and Social Inquiry, National Taiwan University**  
Team Project · Political Text Analysis · NLP · Social Media Analytics
