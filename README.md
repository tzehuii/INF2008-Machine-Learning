# INF2008-Machine-Learning
## 🩺 Stroke Risk Prediction Pipeline (INF2008 Assignment)

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Machine%20Learning-orange?style=flat-square&logo=scikit-learn)
![Dataset](https://img.shields.io/badge/Dataset-Kaggle-blueviolet?style=flat-square&logo=kaggle)

An end-to-end machine learning pipeline built to assess individual stroke risk using demographic, clinical, and lifestyle factors. Developed for the **INF2008** course by **Lab P3-1**.

---

## 👥 Team Members (Lab P3-1)

| Member | Student ID |
| :--- | :--- |
| **Teng Tze Hui** | 2502437 |
| **Ee Chew Fong, Olivia** | 2102743 |
| **Gador Sophia Helen Santiago** | 2503845 |
| **Yap Yi Hui Wynn** | 2501386 |

---

## 📌 Project Overview & Persona

### The Scenario: "Bob's Concern"
**Bob** is a 45-year-old office worker who leads a sedentary lifestyle, frequently eats fast meals, and was recently diagnosed with **hypertension**. After learning about the link between high blood pressure and stroke, Bob asks:

> *"Am I at risk of having a stroke? Should I see a doctor now?"*

### Problem Statement
How can tabular health data be analyzed to provide individuals like Bob with clear, reliable insights into their stroke risk, enabling informed decisions about seeking medical advice and adopting preventive measures?

---

## 🎯 Business Context & Failure Analysis Priority

Stroke risk prediction involves asymmetric costs between two types of classification errors:

```
                  ┌─────────────────────────────────────────────────────────────┐
                  │                 MODEL PREDICTION ERROR                      │
                  └──────────────┬──────────────────────────────┬───────────────┘
                                 │                              │
                                 ▼                              ▼
                 ┌───────────────────────────────┐  ┌───────────────────────────────┐
                 │        FALSE POSITIVE         │  │        FALSE NEGATIVE         │
                 │   (Predict Stroke / No Stroke)│  │   (Predict Safe / Has Stroke) │
                 ├───────────────────────────────┤  ├───────────────────────────────┤
                 │ • Unnecessary consultations   │  │ • No warning issued           │
                 │ • Mild stress & added costs   │  │ • Misses preventive treatment │
                 │ • Patient remains safe        │  │ • Potentially fatal outcome   │
                 └───────────────────────────────┘  └───────────────────────────────┘
                                                            ⚠️ HIGH PRIORITY
                                                          (Minimization Target)
```

> **Core Objective:** Minimizing **False Negatives** is the highest priority. Missing an actual stroke risk carries far more critical consequences than an unnecessary doctor's visit.

---

## 📁 Dataset & Stage Scope

* **Source:** [Kaggle Stroke Prediction Dataset](https://www.kaggle.com/datasets/fedesoriano/stroke-prediction-dataset/data)
* **Data Format:** Non-temporal, tabular data covering demographics (age, gender, marital status, work type), health conditions (hypertension, heart disease, average glucose level, BMI), and lifestyle choices (smoking status).
* **Notebook Links:**
  * [Stage 1 Baseline Notebook](https://colab.research.google.com/drive/194Uel3OYJtj5I12qKVOQ5beZD2y3hwG0?usp=sharing)
  * **Stage 2 Implementation:** Pipeline engineering, champion model selection, ablation studies, decision threshold optimization, and error analysis.

---

## 🛠️ Machine Learning Workflow

```
┌──────────────────┐    ┌──────────────────┐    ┌──────────────────┐    ┌──────────────────┐
│ 1. Data Cleaning │ ──>│ 2. Pipeline Eng. │ ──>│ 3. Model Tuning  │ ──>│ 4. Threshold Opt.│
│ Imputation & EDA │    │ Scaling & Encoders│    │ Ablation Studies │    │ Recall-Focused   │
└──────────────────┘    └──────────────────┘    └──────────────────┘    └──────────────────┘
```

1. **Preprocessing & Pipeline Engineering:** Handling missing values (e.g., BMI imputation), encoding categorical lifestyle features, and feature scaling.
2. **Imbalance Handling:** Applying sampling strategies to address severe target class imbalance (low base rate of stroke events).
3. **Model Selection & Ablation:** Evaluating baseline estimators vs. ensemble models to select a champion model.
4. **Decision Threshold Optimization:** Calibrating decision thresholds specifically to boost **Recall** and lower False Negatives without destroying Precision.

---

## 🚀 Getting Started

### Prerequisites & Installation

```bash
# Clone the repository
git clone https://github.com/your-username/stroke-risk-prediction.git
cd stroke-risk-prediction

# Install required dependencies
pip install -r requirements.txt
```

---

## 💡 Originality Statement

While existing community notebooks informed general methodology, all pipeline architecture, feature engineering, ablation experiment design, threshold calibration, and failure analyses in this repository are original work created by Lab P3-1.
