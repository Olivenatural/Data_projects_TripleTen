# Data_projects_TripleTen

Welcome! This is my collection of TripleTen data projects.  
**Audience:** Recruiters, hiring managers, and mentors.  
**Reading level:** Clear and simple. No deep tech background required.

---

## Table of Contents
- [Sprint 14 — Machine Learning for Texts (NLP)](./Sprint14_Text_ML/README.md)
- [Sprint 15 — Computer Vision](./Sprint15_Computer_Vision/README.md)
- [Sprint 16 — Unsupervised Learning](./Sprint16_Unsupervised_Learning/README.md)
- [Sprint 17 — Final Project](./Sprint17_Final_Project/README.md)

---

## How to Explore
1. Click a project in the **Table of Contents** above.
2. In each folder, open `README.md` to see:
   - What the project is about
   - The data used
   - The steps I took (plain English)
   - Results and what they mean
   - How to run the notebook/code

  > Tip: You can browse without running code. The READMEs are written to be friendly and simple.

---

## About Me
I’m Tamauri — a wellness-focused Data Analyst / Jr. Data Scientist.  
I translate real-world massage therapy experience into data stories that help retain customers and grow revenue.

### Run with Sample Data (Quick Demo)
If you just want to try the notebook:
1) Keep `data/sample/imdb_reviews_sample.tsv` in the project folder.
2) In the notebook, set:

```python
DATA_PATH = "data/sample/imdb_reviews_sample.tsv"   # small demo
# DATA_PATH = "/datasets/imdb_reviews.tsv"          # full dataset (TripleTen env)

import pandas as pd
df = pd.read_csv(DATA_PATH, sep="\t" if DATA_PATH.endswith(".tsv") else ",")
df.head()
