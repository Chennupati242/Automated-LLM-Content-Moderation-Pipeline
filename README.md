# Automated-LLM-Content-Moderation-Pipeline


## Overview

This project simulates a Trust & Safety content moderation workflow similar to those used by large-scale social media platforms such as YouTube.

The system classifies user-generated comments into moderation categories using both traditional machine learning and Large Language Models (LLMs). The project evaluates model performance using Precision, Recall, F1-score, and error analysis to understand moderation failures.

---

## Problem Statement

Online platforms receive millions of comments daily. Manual moderation is expensive and difficult to scale.

This project explores whether Large Language Models can assist or automate content moderation by classifying comments into policy violation categories and comparing performance against a traditional machine learning baseline.

---

## Moderation Categories

- Safe
- Harassment
- Violence

---

## Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Google Gemini API
- Streamlit
- Matplotlib

---

## Dataset

The project uses a publicly available hate speech and toxicity dataset containing over 135,000 annotated comments.

The dataset includes annotations related to:

- Insults
- Humiliation
- Dehumanization
- Violence

These annotations were transformed into moderation categories for classification.

---

## Methodology

### Data Preparation

- Loaded and explored the dataset
- Performed label engineering
- Created moderation categories
- Analyzed class distribution

### Baseline Model

TF-IDF Vectorization + Logistic Regression

Workflow:

Comment Text
→ TF-IDF Vectorizer
→ Logistic Regression
→ Predicted Category

### LLM-Based Moderation

Integrated Google Gemini API for prompt-based moderation.

Implemented:

- Zero-shot prompting
- Few-shot prompting
- Prompt engineering experiments

### Evaluation Metrics

The models were evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix

---

## Results

| Metric | Score |
|----------|----------|
| Accuracy | 72.5% |
| Macro F1 Score | 0.70 |

### Class-wise Performance

| Category | Precision | Recall | F1 |
|------------|------------|------------|------------|
| Harassment | 0.71 | 0.84 | 0.77 |
| Safe | 0.72 | 0.64 | 0.68 |
| Violence | 0.78 | 0.58 | 0.67 |

---

## Error Analysis

The largest source of classification error was confusion between Violence and Harassment categories.

Key findings:

- Harmful comments were often correctly detected but assigned to the wrong violation category.
- Violence-related comments frequently contained insulting or hateful language, causing overlap with Harassment.
- Dataset label ambiguity contributed to misclassifications.

This highlights the importance of policy design and label quality in Trust & Safety systems.

---

## Human Review Queue

To simulate a production moderation workflow, comments with low model confidence can be routed to a human moderator.

Example:

- Confidence ≥ 85% → Auto Moderate
- Confidence < 85% → Human Review

---

## Dashboard

The project includes a Streamlit dashboard that allows users to:

- Enter a comment
- Predict moderation category
- View confidence scores
- Simulate moderation decisions

### Dashboard Screenshot

Add screenshot here:

![Dashboard](screenshots/dashboard.png)

---

## Confusion Matrix

Add screenshot here:

![Confusion Matrix](screenshots/confusion_matrix.png)

---

## Future Improvements

- Expand moderation taxonomy
- Add Hate Speech category
- Add Scam/Fraud detection
- Evaluate larger Gemini samples
- Fine-tune transformer models
- Deploy dashboard publicly

---

## Key Learnings

- Prompt engineering for LLM moderation
- Trust & Safety policy design
- Classification model evaluation
- Error analysis and moderation failures
- Human-in-the-loop moderation systems

---

## Repository Structure

```text
Automated-LLM-Content-Moderation-Pipeline/

├── moderation_project.ipynb
├── README.md
├── requirements.txt
├── models/
├── screenshots/
└── sample_data/
```

## Author

Sreenihitha Chennupati
