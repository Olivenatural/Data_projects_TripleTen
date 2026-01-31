# ✨🧠 Age Prediction with Computer Vision

I design AI with empathy, intention, and impact.

As someone passionate about wellness and the human experience, I explored how AI can learn to estimate age through facial features in a thoughtful and responsible way. This project blends computer vision, ethical awareness, and real-world application — demonstrating how technology can support more personalized and inclusive experiences across different life stages.


📸 [Jump to Screenshot Gallery](#15--project-screenshots)
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
11. ⚙️ [11 — Training & Validation](#11--training--validation)  
12. 📉 [12 — Model Performance & Results](#12--model-performance--results)  
13. 🌿 [13 — Business & Wellness Value](#13--business--wellness-value)  
14. 🔮 [14 — Next Steps & Improvements](#14--next-steps--improvements)  
15. 🖼️ [15 — Project Screenshots](#15--project-screenshots)  
16. 👤 [16 — Author & Connect](#16--author--connect)

---

## ✨ 01 — Problem Statement

Predicting a person’s age from an image is a challenging computer vision task
due to variations in lighting, angles, genetics, skin tone, lifestyle, and
image quality.

Accurate age estimation can support more personalized user experiences —
including tailored content, accessibility, and safety — when designed and
applied responsibly.

### ⚖️ Ethical AI Note

Age prediction models can reflect biases present in the data they learn from.
This project emphasizes thoughtful and responsible use of computer vision,
with attention to fairness, consent, and inclusive design.


---

## 🎯 02 — Project Goals

This project was designed to:

- Build a regression model to predict age from facial images  
- Apply transfer learning to improve performance efficiently  
- Evaluate model behavior using Mean Absolute Error (MAE)  
- Connect technical results to human-centered and wellness-focused use cases  

---

## 🧵 03 — Dataset Overview

- ~7,600 labeled face images  
- Each image includes:
   - `file_name`
   - `real_age`  
- Data split into training, validation, and test sets  
- Age distribution is uneven, with fewer images for ages 60+

> ⚠️ The dataset is not included due to size constraints. Screenshots and
training logs are provided to document model behavior and results.


---

## 🧰 04 — Tech Stack

- **Languages:** Python  
- **Frameworks:** TensorFlow, Keras  
- **Libraries:** NumPy, Pandas, Matplotlib  
- **Environment:** Jupyter Notebook / Google Colab  

---

## ⚙️ 05 — Quickstart

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

---

## 📂 06 — Project Structure

```
Sprint15_Computer_Vision/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── raw/
│   └── processed/
│
├── notebooks/
├── src/
├── models/
├── figures/
├── reports/
└── docs/
    └── screenshots/
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
- Resized images
- split into train/validation/test set 

**Image Augmentation**  
- Horizontal flip  
- Small rotation & shift  
- Zoom  

**Modeling Approach**  
- Transfer learning with pretrained CNN  
- Regression head for age prediction  
- Evaluation metric: MAE  

---


## 09 🔍 Exploratory Data Analysis (EDA)  

#### Age Distribution  
Most samples are between 15 and 40 years old, creating a right-skewed distribution.  
Fewer elderly faces introduce a slight imbalance biasing younger predictions.  

![Age Distribution](docs/screenshots/01_age_distribution_01.jpg)
![Age Distribution](docs/screenshots/01_age_distribution_02.jpg)
![Age Distribution](docs/screenshots/01_age_distribution_03.jpg)



## 🧬 10 — Model Architecture Summary

Built with **ResNet50 (pre-trained on ImageNet)** + custom regression head:  
1. Global Average Pooling layer  
2. Dropout layer for regularization  
3. Dense output layer with linear activation  

![Modeling Functions](docs/screenshots/04a_modelling_functions_01.jpg)
> Additional modeling steps (data loaders, model creation, training loop) are shown in subsequent screenshots.

---


  ## 11 ⚙️ Training and Validation  

#### Early Epochs (1–16)  
Training and validation MAE trend at the start of training.  
![Training Logs 1–16](docs/screenshots/06_training_logs_epoch_1_16.jpg)

#### Later Epochs (17–20)  
Model stabilized around a validation MAE of ≈ 6.6 – 8.5 years.  
![Training Logs 17–20](docs/screenshots/07_training_logs_epoch_17_20.jpg)


---

## 📉 12 — Model Performance & Results

> **Note:**  
> Due to platform constraints, prediction visualizations and performance charts are described analytically rather than displayed as screenshots. All model behavior is supported by numerical metrics and training logs.


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

## 🌿 13 — Business & Wellness Value

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

## 🔮 14 — Next Steps & Improvements

1. Add stronger data augmentation (brightness, zoom, shifts).  
2. Fine-tune more layers of ResNet50 for better feature learning.  
3. Test regularization (dropout, weight decay).  
4. Expand dataset with older age groups to reduce bias.  
---

## 🖼️ 15 — Project Screenshots

<details>
<summary>📸 View Full Screenshot Gallery (11)</summary>
<br>

| # | Description | Image |
|:--|:-------------|:------|
| 1 | Initialization | [Initialization](docs/screenshots/00_initialization.jpg) |
| 2 | Load Data | [Load Data](docs/screenshots/00_load_data.jpg) |
| 3 | Sample Images (Data Preview) | ![Sample Images](docs/screenshots/01_sample_images.jpg) |
| 4 | EDA – Age Distribution | ![Age Distribution](docs/screenshots/02_age_distribution.jpg) |
| 5| Labels & Columns | ![Labels & Columns](docs/screenshots/03_labels_and_columns.jpg) |
| 6 | Train / Val / Test Split | ![Split](docs/screenshots/04_train_val_test_split.jpg) |
| 7 | Modeling Functions (GPU Script + Model Code) | ![Modeling Functions](docs/screenshots/04a_modelling_functions_01.jpg) |
| 8 | Training Logs (Epochs 1–16) | ![Logs 1–16](docs/screenshots/06_training_logs_epoch_1_16.jpg) |
| 9 | Training Logs (Epochs 17–20) | ![Logs 17–20](docs/screenshots/07_training_logs_epoch_17_20.jpg) |
| 10 | Business Value | ![Business Value](docs/screenshots/10_business_value.jpg) |
| 11 | Conclusion | ![Conclusion](docs/screenshots/12_conclusion.jpg) |

</details>
---

## 👤 16 — Author & Connect

**Author:** *Tamauri Olive*  
*Aspiring Wellness Data Scientist — Blending AI, Empathy & Impact*  

🔗 [Connect on LinkedIn](https://www.linkedin.com/in/tamauri-olive-499845113) 
🔗 [GitHub Profile](https://github.com/Olivenatural) | 📘 Sprint 15 Project

