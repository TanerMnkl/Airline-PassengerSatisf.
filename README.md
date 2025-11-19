# ✈️ Airline Passenger Satisfaction Prediction

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![XGBoost](https://img.shields.io/badge/XGBoost-2.0%2B-green)
![Optuna](https://img.shields.io/badge/Optuna-Hyperparameter%20Tuning-orange)
![Status](https://img.shields.io/badge/Status-Completed-success)

An end-to-end Machine Learning pipeline designed to predict airline passenger satisfaction with high accuracy. This project moves beyond basic modeling by incorporating **Bayesian Optimization (Optuna)**, **Pruning strategies**, and **Insight-Driven EDA** to derive actionable business intelligence.

## 📖 Project Overview

In the highly competitive airline industry, understanding customer satisfaction is key to retention. This project analyzes a dataset of passenger feedback to:
* Predict whether a passenger will be satisfied or dissatisfied.
* Identify the key drivers (features) that influence satisfaction.
* Provide data-driven recommendations for airline management.

**Key Result:** The final optimized XGBoost model achieved an **Accuracy of 96.57%** and an **ROC-AUC of 0.9955**.

## 📊 Dataset

The dataset contains survey results from airline passengers, including demographic information, flight details, and satisfaction ratings for various services.

* **Source:** [Kaggle - Airline Passenger Satisfaction](https://www.kaggle.com/datasets/teejmahal20/airline-passenger-satisfaction)
* **Size:** ~100k training samples, ~25k testing samples.
* **Target Variable:** `satisfaction` (Binary: Satisfied / Neutral or Dissatisfied)

## 💡 Key Insights & Business Impact

Through deep analysis and Feature Importance extraction (Gain), the following critical insights were uncovered:

* **Digital Experience is King 👑:** `Online boarding` and `Inflight wifi service` are among the top 3 predictors of satisfaction. The ease of the digital interface outweighs traditional metrics like food quality.
* **Travel Purpose Matters:** The model distinguishes heavily between `Business` and `Personal` travel, indicating these segments have vastly different expectations.
* **Pre-Flight > In-Flight:** Factors like `Online boarding` and `Gate location` have a massive impact on the passenger's mood before they even sit down.

> **Recommendation:** To maximize ROI, the airline should prioritize improving their mobile app/web interface and stabilizing inflight connectivity rather than investing heavily in physical amenities like legroom or food.

## 🛠️ Technical Methodology

The project follows a professional Data Science workflow:

### 1. Advanced Preprocessing
* **Data Cleaning:** Handled missing values and dropped irrelevant IDs.
* **Feature Engineering:** Created `Total Service Score` and binned `Flight Distance` into short/medium/long haul groups.
* **Native Categorical Handling:** Utilized XGBoost's `enable_categorical=True` for efficient processing without massive One-Hot Encoding vectors.

### 2. Insight-Driven EDA
* Moved beyond basic countplots to **Normalized Stacked Bar Charts** to visualize probability distributions.
* Used **Point Plots** to analyze the trend and confidence intervals of service ratings.

### 3. Modeling & Optimization
* **Algorithm:** XGBoost Classifier (Histogram-based).
* **Hyperparameter Tuning:** Implemented **Optuna** for Bayesian Optimization.
* **Resource Efficiency:** Used `XGBoostPruningCallback` to prune unpromising trials early, saving computational time.
* **Overfitting Prevention:** Strict `early_stopping_rounds` were applied during both tuning and final training.

## 📈 Model Performance

The model was evaluated on a held-out test set:

| Metric | Score |
| :--- | :--- |
| **Accuracy** | **96.57%** |
| **F1 Score** | **96.00%** |
| **ROC AUC** | **0.9955** |

*Confusion Matrix indicates a balanced classification ability with very low False Positives/Negatives.*

## 🚀 Install dependencies:
pip install pandas numpy matplotlib seaborn scikit-learn xgboost optuna

📂 Project Structure:
├── PassengerSatisfy.ipynb
├── train.csv
├── test.csv
└── README.md
