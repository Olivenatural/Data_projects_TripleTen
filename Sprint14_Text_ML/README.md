# 🎬🧠 Sprint 14 — Machine Learning for Texts  
## Detecting Negative IMDb Movie Reviews

This project builds and evaluates multiple NLP pipelines to automatically
detect negative IMDb movie reviews using both classical machine learning
and transformer-based approaches.

🏷️ **Tech Stack:** Python · pandas · scikit-learn · NLTK · spaCy · LightGBM · BERT

---

## 📑 Table of Contents

1. 🎯 Problem Statement  
2. 🎯 Project Goals  
3. 🧾 Dataset Overview  
4. 🧠 Approach & Methodology  
5. 📊 Evaluation & Metrics  
6. 🧰 Tools & Libraries  
7. ▶️ How to Run the Project  
8. 📁 Project Structure  
9. 💡 Key Takeaways  
10. 🚀 Next Steps & Improvements  
11. 📌 Project Files  
12. 👤 Author & Connect  

---

## 🎯 01 — Problem Statement

Online platforms need scalable ways to moderate large volumes of text.
Manual review is time-consuming, inconsistent, and does not scale.

The goal of this project is to build a machine learning model that can
accurately classify movie reviews as **negative or positive** based on text alone.

---

## 🎯 02 — Project Goals

- Preprocess and normalize raw text data  
- Compare multiple NLP modeling approaches  
- Optimize performance using F1 score  
- Select a model suitable for production use  

---

## 🧾 03 — Dataset Overview

- IMDb movie reviews dataset  
- Binary sentiment labels (positive / negative)  
- Predefined train/test split  

**Key Columns**
- `review` — text of the review  
- `pos` — sentiment label  
- `ds_part` — dataset split indicator  

> ⚠️ The full dataset is not included. A small sample file is provided for reproducibility.

---

## 🧠 04 — Approach & Methodology

The modeling pipeline followed these steps:

- Text cleaning and normalization  
- Lemmatization using NLTK and spaCy  
- TF-IDF vectorization (bigrams, sublinear TF)  
- Model training and comparison  

**Models Evaluated**
- DummyClassifier (baseline)  
- Logistic Regression (NLTK + TF-IDF)  
- Logistic Regression (spaCy + TF-IDF)  
- LightGBM with TF-IDF features  
- BERT embeddings + Logistic Regression  

---

## 📊 05 — Evaluation & Metrics

Models were evaluated using:

- **F1 Score** (primary metric)  
- Precision and Recall  
- ROC-AUC  

**Best Performing Model**
- spaCy + TF-IDF + Logistic Regression  
- Balanced precision and recall  
- Strong generalization on unseen reviews  

---

## 🧰 06 — Tools & Libraries

- Python  
- pandas  
- NumPy  
- scikit-learn  
- NLTK  
- spaCy  
- LightGBM  
- Hugging Face Transformers  

---

## ▶️ 07 — How to Run the Project

### Option 1: Run using the included sample dataset (recommended)

This repository includes a small sample dataset so the notebook can run
quickly without access to the full IMDb dataset.

```python
import pandas as pd

DATA_PATH = "data/sample/imdb_reviews_sample.tsv"
df_reviews = pd.read_csv(DATA_PATH, sep="\t")
df_reviews.head()

---

```python
import pandas as pd

DATA_PATH = "data/sample/imdb_reviews_sample.tsv"
df_reviews = pd.read_csv(DATA_PATH, sep="\t")
df_reviews.head()
**Quick Demo Option**
- Use `data/sample/imdb_reviews_sample.tsv`  
- Adjust `DATA_PATH` in the notebook  

---

## 📁 08 — Project Structure


Sprint14_Text_ML/
│
├── data/
│   └── sample/
│       └── imdb_reviews_sample.tsv
│
├── Sprint14_Text_ML.ipynb
├── README.md
└── .gitignore
---

## 💡 09 — Key Takeaways

- Text preprocessing has a major impact on model performance

- Simpler models can outperform complex ones with strong feature engineering

- Model selection should balance accuracy, interpretability, and scalability
---

## 🚀 10 — Next Steps & Improvements

- Hyperparameter tuning

- Feature selection and refinement

- Production-level inference testing
---

## 📌11 - Project Files

- ✅ **Notebook:** [Sprint14_Text_ML.ipynb](./Sprint14_Text_ML.ipynb)
- ✅ **Sample Data:** `data/sample/imdb_reviews_sample.tsv`
- ✅ **Project Summary:** `README.md`

---

## 👤 12 — Author & Connect

Tamauri Olive

Aspiring Wellness Data Scientist — blending AI, empathy & impact

🔗 [Connect on LinkedIn](https://www.linkedin.com/in/tamauri-olive-499845113) 
🔗 [GitHub Profile](https://github.com/Olivenatural) | 📘 Sprint 14 Project

