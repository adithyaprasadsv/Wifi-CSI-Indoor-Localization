# 📡 Indoor Localization using Wi-Fi CSI Fingerprinting

## 🔍 Project Overview

This project investigates **indoor localization** as a multi-class classification problem using **Wi-Fi Channel State Information (CSI)** and supervised machine learning.

The objective is to predict device position among 10 indoor locations using engineered CSI fingerprints.

The system transforms raw complex CSI measurements into structured features (Amplitude, Phase, RSSI, DCT coefficients) and evaluates multiple ML classifiers under robust validation schemes.

---

## 🏫 Academic Context

Course: Artificial Intelligence for Connected Industries\
Institution: Ulm University\
Authors: Carlos Hincapie, Adithya Prasad

---

## 🧠 Problem Statement

GPS is unreliable indoors. This project explores Wi-Fi-based localization using:

* CSI amplitude & phase extraction
* DCT-based denoising and dimensionality reduction
* RSSI-based distance estimation
* Angle-of-Arrival derived features
* SHAP-based feature interpretation

The task is formulated as a **10-class classification problem**.

---

## ⚙️ Machine Learning Pipeline

1. Raw CSI preprocessing
2. Feature engineering

   * Amplitude normalization
   * DCT (k=13 components, 99% energy retained)
   * RSSI descriptors
   * Phase slope & delay
3. Model training
4. Group K-Fold Cross Validation
5. Hyperparameter tuning (Grid Search)
6. Evaluation using Macro F1-score
7. SHAP interpretability analysis

---

## 🤖 Models Evaluated

* K-Nearest Neighbors
* SVM (RBF Kernel)
* Random Forest
* XGBoost (Best Performing)

### 🏆 Best Model: XGBoost

| Metric              | Score         |
| ------------------- | ------------- |
| Macro F1 (test data)| 0.975         |
| Validation Strategy | Group K-Fold  |
| Objective           | multi:softmax |
| Estimators          | 600           |
| Max Depth           | 5             |

---

## 📊 Key Results

* DCT denoising significantly improved stability and separability
* RSSI shows inverse relationship with distance
* XGBoost outperformed SVM and Random Forest
* Group K-Fold prevents temporal leakage
* SHAP revealed timestamp and RSSI as strong predictors

Ablation study confirmed consistent performance improvements from feature engineering.

---

## 📁 Repository Structure

```
├── notebooks/
│   └── CSI_Localization.ipynb
│
├── report/
│   └── Indoor_Localization_Report.pdf
│
├── README.md
└── requirements.txt
```

---

## 🛠️ Tech Stack

* Python
* NumPy
* Pandas
* Scikit-learn
* XGBoost
* SHAP
* Matplotlib / Seaborn

---

## 🚀 Future Work

* Session-independent validation
* Environment-independent testing
* Real-time CSI streaming deployment
* Deep learning approaches (CNN on CSI matrices)

---

## 📌 Takeaways

This project demonstrates:

* Strong feature engineering skills
* Robust ML evaluation methodology
* Handling of data leakage risks
* Model interpretability
* Practical application of ensemble learning

---

## 📎 Report

Full technical report available in the `report/` directory.\
Dataset not included due to academic restrictions.
---
