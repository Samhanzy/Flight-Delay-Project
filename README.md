# ✈️ Flight Delay Prediction: Classification & Clustering

![R](https://img.shields.io/badge/R-%E2%89%A54.0-blue)
![License](https://img.shields.io/github/license/Samhanzy/Flight-Delay-Project)
![Last Commit](https://img.shields.io/github/last-commit/Samhanzy/Flight-Delay-Project)
![Models](https://img.shields.io/badge/Models-Logistic%20Regression%20%7C%20Random%20Forest%20%7C%20XGBoost-orange)

A complete machine learning pipeline to **predict flight delays** using classification models and discover hidden flight patterns through unsupervised clustering — built end-to-end in R.

> 📄 [Download Full Report (PDF)](reports/Flight-Prediction-Report.pdf) | [DOCX Version](reports/Flight-Prediction-Report.docx)

---

## 🎯 Problem Statement

Flight delays cost the aviation industry billions annually and significantly impact passenger experience. This project tackles the question: **can we predict whether a flight will be delayed before it departs?**

Using features like flight duration, day of week, and weather conditions, three classification models are trained, evaluated, and compared — alongside a clustering analysis to uncover natural groupings in flight behavior.

---

## 🧠 Models & Results

| Model | AUC Score | Notes |
|---|---|---|
| Penalized Logistic Regression | 0.924 | Baseline model, interpretable coefficients |
| Random Forest | 0.922 | Best feature importance insights |
| XGBoost | 0.921 | Gradient boosting, handles class imbalance well |


**Key technique:** Class imbalance handled via **SMOTE** (Synthetic Minority Oversampling) to prevent the model from ignoring the minority delay class.

---

## 📊 Visualizations

### ROC Curve — Model Comparison
![ROC Curve](figures/roc_curve.png)

### Random Forest: Feature Importance
![Random Forest Feature Importance](figures/rf_feature_importance.png)

### XGBoost: Feature Importance
![XGBoost Feature Importance](figures/xgb_feature_importance.png)

### K-Means Clustering
![K-Means Clusters](figures/kmeans_clusters.png)

---

## 🔍 Key Findings

- **Weather conditions** emerged as the strongest predictor of delays across both Random Forest and XGBoost models
- **Flight duration** showed a positive correlation with delay probability — longer flights carry higher risk
- **K-Means clustering** (optimal k selected via elbow method) revealed distinct behavioral groups in the data, separating short domestic hops from longer routes
- SMOTE oversampling meaningfully improved recall for the delayed class, reducing false negatives

---

## 🗃️ Dataset

- **File:** `flights_200.csv`
- **Size:** 200 flight records × 7 features
- **Source:** US Bureau of Transportation Statistics via Kaggle (2015 Flight Delays dataset)
- **Features:** `Flight_Duration`, `Day_of_Week`, `Weather_Conditions`, `Airline`, `Scheduled_Departure`, `Delay_Status`

> *Note: 50,000 rows sampled from the full dataset for training efficiency. A production version of this pipeline would benefit from real-world data (e.g., BTS, FAA sources) at a larger scale.*

---

## 🧰 Tech Stack

| Tool | Purpose |
|---|---|
| R (≥ 4.0) | Core language |
| `tidymodels` | ML pipeline & model training |
| `tidyverse` | Data wrangling |
| `xgboost` | Gradient boosting |
| `ranger` | Fast Random Forest |
| `themis` / SMOTE | Class balancing |
| `vip` | Feature importance |
| `doParallel` | Parallel processing |

---

## 🚀 How to Run

```r
# Install dependencies
install.packages(c("tidymodels", "tidyverse", "xgboost", "ranger", "themis", "vip", "doParallel"))

# Run the analysis
# 1. Place flights_200.csv in your working directory
# 2. Open and run R/analysis.R
# 3. Outputs: ROC curves, feature importance plots, clustering visualizations
```

---

## 📁 Project Structure

```
Flight-Delay-Project/
│
├── R/
│   └── analysis.R              # Main modelling script
│
├── figures/
│   ├── roc_curve.png
│   ├── rf_feature_importance.png
│   ├── xgb_feature_importance.png
│   └── kmeans_clusters.png
│
├── reports/
│   ├── Flight-Prediction-Report.pdf
│   └── Flight-Prediction-Report.docx
│
├── README.md
└── LICENSE
```

---

## 👤 Author

**Oklogo Samuel**
📧 sam.oklogo@gmail.com
🔗 [LinkedIn](https://www.linkedin.com/in/samuel-oklogo-351542370/)
🐙 [@Samhanzy](https://github.com/Samhanzy)

---

*Part of a growing data science portfolio focused on Nigerian and global economic datasets.*
