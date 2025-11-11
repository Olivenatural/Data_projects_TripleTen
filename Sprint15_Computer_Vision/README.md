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

📸 [Jump to Screenshot Gallery](#14--project-screenshots)
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

## ✨ 00 — Problem Statement

Predicting a person’s age from an image is a challenging computer vision task due to variations in lighting, angles, genetics, skin tone, lifestyle, and image quality. Understanding age through AI can support more personalized user experiences — including tailored content, accessibility, and safety.

> **Ethical AI Note:**  
> Age estimation models can reflect societal biases based on the data they learn from. This project encourages thoughtful and responsible use of computer vision systems, with an emphasis on fairness, respect, and consent.

---

## 🎯 01 — Project Goals

This project was designed to:

- Build a regression model capable of predicting a person’s age using facial images.  
- Apply transfer learning to improve model performance efficiently.  
- Demonstrate ethical, human-centered AI considerations in computer vision.  
- Translate technical results into meaningful business and user experience value.  

---

## 🧵 02 — Dataset Overview

- ~7,600 labeled face images  
- Each image includes: `file_name` and `real_age`  
- Data split into training, validation, and test sets  
- Age distribution is uneven, with fewer images for ages 60+

  **Example Data Sample:**  
![Sample Images](docs/screenshots/01_sample_images.jpg)


---

## 🧰 03 — Tech Stack

- **Languages:** Python  
- **Frameworks:** TensorFlow, Keras  
- **Libraries:** NumPy, Pandas, Matplotlib  
- **Environment:** Jupyter Notebook / Google Colab  

---

## ⚙️ 04 — Quickstart

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

---

## 📂 05 — Project Structure

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

## ▶️ 06 — How to Run the Project

### 📓 Run via Notebook (Recommended)

1. Open the notebook:  
   `notebooks/01_explore.ipynb`
2. Run all cells in sequence.

### 💻 Run via CLI (Optional)

```bash
python -m src.train --data_dir data/processed --out_dir models/
```

---

## 🧪 07 — Approach & Methodology

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


## 08 🔍 Exploratory Data Analysis (EDA)  

#### Age Distribution  
Most samples are between 15 and 40 years old, creating a right-skewed distribution.  
Fewer elderly faces introduce a slight imbalance biasing younger predictions.  

![Age Distribution](docs/screenshots/02_age_distribution.jpg)


## 🧬 09 — Model Architecture Summary

Built with **ResNet50 (pre-trained on ImageNet)** + custom regression head:  
1. Global Average Pooling layer  
2. Dropout layer for regularization  
3. Dense output layer with linear activation  

![Model Summary](docs/screenshots/05_model_summary.jpg)

---


  ## 10 ⚙️ Training and Validation  

#### Early Epochs (1–5)  
Training and validation MAE trend at the start of training.  
![Training Logs 1–5](docs/screenshots/06_training_logs_epoch_1_5.jpg)

#### Later Epochs (15–20)  
Model stabilized around a validation MAE of ≈ 6.6 – 8.5 years.  
![Training Logs 15–20](docs/screenshots/07_training_logs_epoch_15_20.jpg)


---

## 📉 11 — Model Performance & Results

The model achieved balanced performance with:

| Metric | Value |
|:--|:--|
| Train MAE (Epoch 1 → 20) | ≈ 7.4 → 3.1 years |
| Validation MAE | ≈ 6.6 – 8.5 years |
| Loss Function | MAE |
| Optimizer | Adam (learning rate 1e-4) |

**Observations**  
- Model learns meaningful facial features for age prediction.  
- Slight overfitting due to limited dataset size.  
- Augmentation and regularization help stabilize validation loss.  

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

  ![Business Value](docs/screenshots/10_business_value.jpg)


---

## 🔮 13 — Next Steps & Improvements

1. Add stronger data augmentation (brightness, zoom, shifts).  
2. Fine-tune more layers of ResNet50 for better feature learning.  
3. Test regularization (dropout, weight decay).  
4. Expand dataset with older age groups to reduce bias.  

![Next Steps](docs/screenshots/12_next_steps.jpg)
---

## 🖼️ 14 — Project Screenshots

<details>
<summary>📸 View Full Screenshot Gallery (12)</summary>
<br>

| # | Description | Image |
|:--|:-------------|:------|
| 1 | Sample Images (Data Preview) | ![Sample Images](docs/screenshots/01_sample_images.jpg) |
| 2 | EDA – Age Distribution | ![Age Distribution](docs/screenshots/02_age_distribution.jpg) |
| 3 | Labels & Columns | ![Labels & Columns](docs/screenshots/03_labels_and_columns.jpg) |
| 4 | Train / Val / Test Split | ![Split](docs/screenshots/04_train_val_test_split.jpg) |
| 5 | Model Summary (ResNet50 + Regression Head) | ![Model Summary](docs/screenshots/05_model_summary.jpg) |
| 6 | Training Logs (Epochs 1–5) | ![Logs 1–5](docs/screenshots/06_training_logs_epoch_1_5.jpg) |
| 7 | Training Logs (Epochs 15–20) | ![Logs 15–20](docs/screenshots/07_training_logs_epoch_15_20.jpg) |
| 8 | Predictions Examples | ![Predictions](docs/screenshots/08_predictions_examples.jpg) |
| 9 | Performance Chart | ![Performance](docs/screenshots/09_performance_chart.jpg) |
| 10 | Business Value | ![Business Value](docs/screenshots/10_business_value.jpg) |
| 11 | Conclusion | ![Conclusion](docs/screenshots/11_conclusion.jpg) |
| 12 | Next Steps | ![Next Steps](docs/screenshots/12_next_steps.jpg) |

</details>
---

## 👤 15 — Author & Connect

**Author:** *Tamauri Olive*  
*Aspiring Wellness Data Scientist — Blending AI, Empathy & Impact*  

[![Connect on LinkedIn](www.linkedin.com/in/tamauri-olive-499845113)](#)  
🔗 [GitHub Profile](https://github.com/Olivenatural) | 📘 Sprint 15 Project

