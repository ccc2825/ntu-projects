# E-Commerce Multimodal Compliance Detection

A multimodal AI system for detecting potentially non-compliant product listings through **text analysis, OCR, large language models, and vision-language models**.

## Overview

E-commerce platforms manage large volumes of product names, descriptions, and images, making manual compliance review difficult to scale. This project develops a **multimodal screening pipeline** to identify product listings that may violate Taiwan's *Tobacco Hazards Prevention Act*.

Rather than relying solely on keyword matching, the system combines rule-based detection with **LLaMA, LLaVA, and OCR**, enabling compliance screening across both textual and visual product information.

## Data

The analysis uses real product listings from the **momo e-commerce platform**, linked by a unique product identifier (`GOODS_CODE`).

| Data Type | Records | Products |
|---|---:|---:|
| Product Names | 4,743 | 4,743 |
| Product Descriptions | 2,647 | 2,559 |
| Product Images | 34,349 | 4,743 |

## Approach

### Text Detection

- **Keyword Matching** — Tobacco-related keyword dictionaries and exclusion rules are used for efficient initial screening.
- **LLaMA** — Multiple prompting strategies capture contextual and semantic violations beyond exact keyword matches.
- **Model Voting** — Outputs from different detection methods are combined through majority voting to improve robustness.

### Image Detection

- **Google Cloud Vision OCR** extracts text embedded in product images and passes it into the text detection pipeline.
- **LLaVA** interprets visual content such as cigarettes, smoking behavior, tobacco-related objects, and advertisements.

Alternative approaches—including **YOLO, CLIP, ResNet50, EfficientNet, RetinaNet, BLIP, and BERT-based classification**—were also explored to evaluate their suitability for this domain-specific task.

## Results

The final screening process identified:

- **44** potentially non-compliant products through product names
- **43** through product descriptions
- **1,021** through the combined image screening process

In sampled manual evaluation, **OCR + keyword screening achieved 47.5% precision**, while direct **LLaVA image classification achieved 46.73%**.

The system also identified potentially problematic listings that were not included in the platform's existing violation list. However, false positives remained substantial, suggesting that the system is better suited for **screening and prioritizing cases for human review** rather than fully automated compliance decisions.

## Repository Structure

```text
Capstone-for-Business-Analytics/
├── E-Commerce-Multimodal-Compliance-Detection-Report.pdf   # Full project report
├── E-Commerce-Multimodal-Compliance-Detection-Slides.pdf   # Final presentation slides
└── README.md
```

## Tech Stack

`Python` · `LLaMA` · `LLaVA` · `Google Cloud Vision OCR` · `BERT` · `YOLO` · `CLIP` · `ResNet50` · `EfficientNet`

## Project Context

**Capstone for Business Analytics, National Taiwan University**  
Team Project · E-Commerce · Multimodal AI · NLP · Computer Vision
