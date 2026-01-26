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
11. 🖼 Project Files 
12. 👤 Author & Connect  

---

## 🎯 01 — Problem Statement

Online communities need scalable ways to moderate large volumes of text.
Manual review is time-consuming, inconsistent, and does not scale.

---

## 🎯 02 — Project Goals

- Preprocess and normalize text data  
- Compare multiple NLP modeling approaches  
- Optimize performance using F1 score  
- Select a production-ready model  

---

## 🧾 03 — Dataset Overview

- IMDb movie reviews dataset  
- Binary sentiment labels (positive / negative)  
- Train/test split provided  

**Key Columns**
- `review` — text of the review  
- `pos` — sentiment label  
- `ds_part` — dataset split flag  

---

## 🧠 04 — Approach & Methodology

The modeling pipeline included the following stages:

- Text cleaning and normalization  
- Lemmatization (NLTK and spaCy)  
- TF-IDF vectorization (bigrams, sublinear TF)  
- Multiple model comparisons  

**Models Evaluated**
- DummyClassifier (baseline)  
- Logistic Regression (NLTK + TF-IDF)  
- Logistic Regression (spaCy + TF-IDF)  
- LightGBM with TF-IDF features  
- BERT embeddings + Logistic Regression  

---

## 📊 05 — Evaluation & Metrics

Models were evaluated using:

- F1 Score (primary metric)  
- Precision & Recall  
- ROC-AUC  

**Best Performing Model**
- spaCy + TF-IDF + Logistic Regression  
- Balanced precision and recall  
- Strong generalization on hand-labeled reviews  

---

## 🧰 06 — Tools & Libraries

- Python  
- pandas  
- NumPy  
- scikit-learn  
- NLTK  
- spaCy  
- LightGBM  
- Transformers (Hugging Face)  

---

## ▶️ 07 — How to Run the Project

### Option 1: Run with the included sample file (recommended for GitHub)
This repo includes a small sample dataset so the notebook can run quickly.

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
├── notebooks/
├── data/
│   └── sample/
├── README.md

---

## 💡 09 — Key Takeaways

Model selection is a business decision, not just a technical one.

Performance constraints strongly influence which models are practical in production.

---

## 🚀 10 — Next Steps & Improvements

- Feature selection and refinement

- Hyperparameter tuning

- Production-level inference testing

---

## 📌 Project Files

- ✅ **Notebook:** [Sprint14_Text_ML.ipynb](./Sprint14_Text_ML.ipynb)
- ✅ **Sample Data:** `data/sample/imdb_reviews_sample.tsv`
- ✅ **Project Summary:** `README.md`

---

## 👤 12 — Author & Connect

Tamauri Olive

Aspiring Wellness Data Scientist — blending AI, empathy & impact

🔗 [Connect on LinkedIn](https://www.linkedin.com/in/tamauri-olive-499845113) 
🔗 [GitHub Profile](https://github.com/Olivenatural) | 📘 Sprint 14 Project

