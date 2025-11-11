# ✨🧠 Age Prediction with Computer Vision

I design AI with empathy, intention, and impact.

As someone passionate about wellness and the human experience, I explored how AI can learn to estimate age through facial features in a thoughtful and responsible way. This project blends computer vision, ethical awareness, and real-world application — demonstrating how technology can support more personalized and inclusive experiences across different life stages.

<p align="center">

<img src="https://img.shields.io/badge/Python-3.x-blue" alt="Python"/>
<img src="https://img.shields.io/badge/TensorFlow-Deep%20Learning-orange" alt="TensorFlow"/>
<img src="https://img.shields.io/badge/Keras-Neural%20Networks-red" alt="Keras"/>

<br>

<img src="https://img.shields.io/badge/Pandas-Data%20Analysis-yellow" alt="Pandas"/>
<img src="https://img.shields.io/badge/NumPy-Numerical%20Computing-purple" alt="NumPy"/>
<img src="https://img.shields.io/badge/Matplotlib-Visualization-green" alt="Matplotlib"/>
<img src="https://img.shields.io/badge/Jupyter-Notebook-orange" alt="Jupyter Notebook"/>

</p>

---

## 📚 Table of Contents
1. ✨ [01 — Problem Statement](#01--problem-statement)  
2. 🎯 [02 — Project Goals](#02--project-goals)  
3. 🧵 [03 — Dataset Overview](#03--dataset-overview)  
4. 🧰 [04 — Tech Stack](#04--tech-stack)  
5. ⚙️ [05 — Quickstart](#05--quickstart)  
6. 📂 [06 — Project Structure](#06--project-structure)  
7. ▶️ [07 — How to Run the Project](#07--how-to-run-the-project)  
8. 🧪 [08 — Approach & Methodology](#08--approach--methodology)  
9. 🧬 [09 — Model Architecture Summary](#09--model-architecture-summary)  
10. 📊 [10 — Exploratory Data Analysis (EDA)](#10--exploratory-data-analysis-eda)  
11. 📉 [11 — Model Performance & Results](#11--model-performance--results)  
12. 🌿 [12 — Business & Wellness Value](#12--business--wellness-value)  
13. 🔮 [13 — Next Steps & Improvements](#13--next-steps--improvements)  
14. 🖼️ [14 — Project Screenshots](#14--project-screenshots)  
15. 👤 [15 — Author & Connect](#15--author--connect)  

---

## ✨ 01 — Problem Statement

Predicting a person’s age from an image is a challenging computer vision task due to variations in lighting, angles, genetics, skin tone, lifestyle, and image quality. Understanding age through AI can support more personalized user experiences — including tailored content, accessibility, and safety.

> **Ethical AI Note:**  
> Age estimation models can reflect societal biases based on the data they learn from. This project encourages thoughtful and responsible use of computer vision systems, with an emphasis on fairness, respect, and consent.

---

## 🎯 02 — Project Goals

This project was designed to:

- Build a regression model capable of predicting a person’s age using facial images.  
- Apply transfer learning to improve model performance efficiently.  
- Demonstrate ethical, human-centered AI considerations in computer vision.  
- Translate technical results into meaningful business and user experience value.  

---

## 🧵 03 — Dataset Overview

- ~7,600 labeled face images  
- Each image includes: `file_name` and `real_age`  
- Data split into training, validation, and test sets  
- Age distribution is uneven, with fewer images for ages 60+  

---

## 🧰 04 — Tech Stack

- **Languages:** Python  
- **Frameworks:** TensorFlow, Keras  
- **Libraries:** NumPy, Pandas, Matplotlib  
- **Environment:** Jupyter Notebook / Google Colab  

---

## ⚙️ 05 — Quickstart

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

---

## 📂 06 — Project Structure

```
Sprint15_Computer_Vision/
├─ README.md
├─ requirements.txt
├─ .gitignore
├─ data/
│  ├─ raw/
│  └─ processed/
├─ notebooks/
├─ src/
├─ models/
├─ figures/
├─ reports/
└─ docs/
   └─ screenshots/
```

---

## ▶️ 07 — How to Run the Project

### 📓 Run via Notebook (Recommended)

1. Open the notebook:  
   `notebooks/01_explore.ipynb`
2. Run all cells in sequence.

### 💻 Run via CLI (Optional)

```bash
python -m src.train --data_dir data/processed --out_dir models/
```

---

## 🧪 08 — Approach & Methodology

**Data Preparation**  
- Loaded image data & labels  
- Resized images and split into train/val/test  

**Image Augmentation**  
- Horizontal flip  
- Small rotation & shift  
- Zoom  

**Modeling Approach**  
- Transfer learning with pretrained CNN  
- Regression head for age prediction  
- Evaluation metric: MAE  

---

## 🧬 09 — Model Architecture Summary

- **Backbone:** ResNet50 (frozen base layers)  
- **Head:** Custom regression layers  
- **Loss Function:** MAE  
- **Optimizer:** Adam  

---

## 📊 10 — Exploratory Data Analysis (EDA)

Key insights:

- Dataset is right-skewed with fewer samples for older ages  
- Variation in lighting and angle required augmentation  
- Data imbalance impacts model generalization  

---

## 📉 11 — Model Performance & Results

The model achieved balanced performance with:

- 📍 Training MAE improved from ~7.4 → ~3.1 years  
- 📍 Validation MAE stabilized around **≈ ±7 years on unseen data**  
- 🔍 Mild overfitting observed  

### 🖼️ Example Results

![Training Logs (Epochs 1–5)](docs/screenshots/05_training_logs_epoch_1_5.jpg)  
![Training Logs (Epochs 15–20)](docs/screenshots/06_training_logs_epoch_15_20.jpg)  
![Sample Predictions](docs/screenshots/08_predictions_examples.jpg)  

---

## 🌿 12 — Business & Wellness Value

AI-based age estimation can support human-centered applications across multiple industries:

**Retail & E-Commerce**  
- Personalized product recommendations by age group  
- Age-appropriate UX flows  

**Security & Safety**  
- Age verification for restricted platforms  

**Wellness & Human Experience**  
- Personalized content or care suggestions aligned to life stages  
- Can support more inclusive and thoughtful user experiences  

---

## 🔮 13 — Next Steps & Improvements

- Fine-tune the top layers of the CNN backbone  
- Add regularization (Dropout, L2)  
- Increase data for older age groups  
- Try alternate architectures (MobileNetV2, EfficientNet)  
- Evaluate fairness across demographic subgroups  

---

## 🖼️ 14 — Project Screenshots

<details>
<summary><strong>📊 Exploratory Data Analysis (EDA)</strong></summary>
<br>

**Data Insights**  
• [Age Distribution](docs/screenshots/01_age_distribution.jpg)  
• [Labels & Columns](docs/screenshots/03_labels_and_columns.jpg)  

**Data Setup**  
• [Train/Val/Test Split](docs/screenshots/04_train_val_test_split.jpg)  

</details>

<details>
<summary><strong>🖼️ Sample Images</strong></summary>
<br>

• [Sample Images](docs/screenshots/02_sample_images.jpg)  

</details>

<details>
<summary><strong>🧬 Model Architecture</strong></summary>
<br>

• [Model Summary](docs/screenshots/07_model_summary.jpg)  

</details>

<details>
<summary><strong>📉 Training Logs</strong></summary>
<br>

• [Early Epoch Logs (1–5)](docs/screenshots/05_training_logs_epoch_1_5.jpg)  
• [Later Epoch Logs (15–20)](docs/screenshots/06_training_logs_epoch_15_20.jpg)  

</details>

<details>
<summary><strong>📈 Results & Insights</strong></summary>
<br>

• [Predictions Examples](docs/screenshots/08_predictions_examples.jpg)  
• [Performance Chart](docs/screenshots/09_performance_chart.jpg)  
• [Business Value Summary](docs/screenshots/10_business_value.jpg)  
• [Conclusion Summary](docs/screenshots/11_conclusion.jpg)  
• [Next Steps Snapshot](docs/screenshots/12_next_steps.jpg)  

</details>

---

## 👤 15 — Author & Connect

**Author:** *Tamauri Olive*  
*Aspiring Wellness Data Scientist — Blending AI, Empathy & Impact*  

[![Connect on LinkedIn](www.linkedin.com/in/tamauri-olive-499845113)](#)  
