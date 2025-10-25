# 🎬 Sprint 14 — Machine Learning for Texts  
**Project Title:** Detecting Negative IMDb Movie Reviews Using TF-IDF, spaCy, LightGBM & BERT  

---

## 🎯 Goal  
Build and evaluate several text-classification pipelines that automatically detect **negative IMDb reviews**, achieving an **F1 ≥ 0.85** on the test set.

---

## 💡 Why It Matters  
For a movie-lover community like *Film Junky Union*, sentiment analysis helps keep discussions positive and prevents negativity from dominating. Automating review moderation saves hours of manual screening.

---

## 🧩 Dataset  
**File:** `/datasets/imdb_reviews.tsv`  
**Description:** A balanced dataset of IMDb movie reviews labeled as positive (1) or negative (0).  
**Key Columns:**  
- `review` — text of the review  
- `pos` — sentiment label  
- `ds_part` — train/test split flag  

---

## ⚙️ Pipeline Steps  

| Step | Description |
|:--|:--|
| **EDA** | Checked sentiment balance and review length distribution. |
| **Pre-processing** | Normalized text (lowercase, removed HTML & punctuation, kept negations). |
| **Lemmatization** | Applied NLTK and spaCy lemmatizers. |
| **Vectorization** | TF-IDF (bigrams, `sublinear_tf=True`, `strip_accents='unicode'`). |
| **Models** | Dummy → Logistic Regression → LightGBM → BERT embeddings (LogReg on top). |
| **Evaluation** | Accuracy, F1, Precision, Recall, ROC-AUC, Average Precision (APS). |

---

## 📊 Model Results  

### 🧱 Baseline (DummyClassifier)
F1 = 0.00 → used for reference only.  

---

### 🧠 Model 1 — NLTK + TF-IDF + Logistic Regression  
- Accuracy = 0.95 / 0.89  
- F1 = 0.95 / 0.89  
- ROC-AUC = 0.99 / 0.96  
✅ Reached goal F1 ≥ 0.85  

---

### 🧩 Model 3 — spaCy + TF-IDF + Logistic Regression  
- Accuracy = 0.95 / 0.89  
- F1 = 0.95 / 0.89  
- ROC-AUC = 0.99 / 0.96  
**Summary:** Matched NLTK version but cleaner handling of negations and lemmatization.  

---

### ⚡ Model 4 — spaCy + TF-IDF + LightGBM  
- Accuracy = 0.99 / 0.89  
- F1 = 0.99 / 0.89  
- ROC-AUC = 1.00 / 0.96  
**Takeaway:** Strongest overall fit; captured non-linear patterns with slight overfitting.  

---

### 🤖 Model 9 — BERT Embeddings + Logistic Regression  
- Accuracy = 1.00 / 0.76  
- F1 = 1.00 / 0.74  
- ROC-AUC = 1.00 / 0.85  
**Note:** Trained on ≈ 200 samples due to CPU limits (no GPU).  
Reviewer credited proper batching and transformer integration.  

---

## 🧮 Mini-Set Validation on Hand-Labeled Reviews  

I authored a custom set of 21 real movie reviews with known sentiment to test generalization.

| Model | Threshold | F1 | Precision | Recall | Observation |
|:--|:--|:--|:--|:--|:--|
| **Model 1** | 0.45 | 0.75 | 0.64 | 0.90 | Good recall; some false positives. |
| **Model 3** | 0.50 | 0.90 | 0.90 | 0.90 | Best overall (one FP, one FN). |
| **Model 4** | 0.50 | 0.77 | 0.60 | 1.00 | Caught all positives but flagged many negatives. |

**Confusion Matrix (Model 3):**  `[[TN = 10, FP = 1], [FN = 1, TP = 9]]`  
**Highlights:** Only one false positive and one false negative → strong balance.  

---

## 🧭 Final Model & Operating Threshold  

**🧩 Chosen Model:** `spaCy + TF-IDF + LogisticRegression (1–2 grams)`  
- Test F1 = 0.89 (official set) / 0.90 (custom reviews).  
- Balanced and robust on sarcasm and contrastive phrases.  
- Fast, simple, and easy to deploy.  

**Threshold Policy:**  
- Use τ = 0.50 for balanced precision and recall.  
- Lower to τ = 0.45 if goal is to catch more negatives (improve recall).  

---

## 🧠 Error Patterns & Insights  
- Sarcasm and irony (e.g., “emotionally empty”, “never a good sign”) cause most mistakes.  
- Mixed phrases like “not bad at all — actually pretty great” confuse the model.  
- Keeping apostrophes and bigrams is crucial for negation detection.  

---

## 🚀 Next Steps  
1. Threshold tuning on validation set targeted to business goal.  
2. Apply Platt/Isotonic calibration for better probabilities.  
3. Try TF-IDF → TruncatedSVD (300–500 dims) → LR/LightGBM to reduce sparsity.  
4. Retrain BERT with GPU hardware for fair comparison.  
5. Deploy as API for automated sentiment screening.  

---

## 🧰 Tech Stack  
Python • pandas • NumPy • Matplotlib • NLTK • spaCy • scikit-learn • LightGBM • Transformers (Hugging Face)

---

## 🗝️ Keywords  
NLP · Sentiment Analysis · TF-IDF · spaCy · LightGBM · BERT · IMDb · Logistic Regression · Text Classification · Machine Learning

---

## 💫 About Me  

Hi, I’m **Tamauri** — a wellness-focused **Data Analyst / Junior Data Scientist**.  
I combine 10+ years of massage therapy experience with data storytelling to uncover insights that help retain customers and increase revenue.  

This project connects to my long-term goal of applying machine learning and NLP to the **wellness industry**, such as predicting client feedback tone or analyzing spa reviews to improve customer experience.

---

## ⚙️ Run with Sample Data (Quick Demo)

If you’d like to explore this notebook without loading the full IMDb dataset:

1. Place this file in your project folder:  
   `data/sample/imdb_reviews_sample.tsv`

2. In your notebook, set the path:
   ```python
   DATA_PATH = "data/sample/imdb_reviews_sample.tsv"   # small demo
   # DATA_PATH = "/datasets/imdb_reviews.tsv"          # full dataset (TripleTen env)

   import pandas as pd
   df = pd.read_csv(DATA_PATH, sep="\t" if DATA_PATH.endswith(".tsv") else ",")
   df.head()
