# 🎯 PUBG Win Placement Prediction (Advanced Feature Engineering)

## 🌟 Project Goal

This project implements an end-to-end Machine Learning regression pipeline to accurately predict a player's final placement percentage (`winPlacePerc`) in a PlayerUnknown's Battlegrounds (PUBG) match.

The primary focus was overcoming complex data challenges: handling **data leakage** and developing robust **collective team features** to accurately capture match dynamics.

---

## 🔬 Key Techniques & Methodology

* **Advanced Feature Engineering:** Transformed granular individual player statistics into highly predictive **collective team-level features** (e.g., total team damage, collective distance traveled). This successfully captured the group-based nature of the game's outcome.
* **Data Leakage Mitigation:** Carefully identified and removed features that could lead to target variable leakage (such as those that directly encode ranking), ensuring the model is genuinely predictive on new, unseen match data.
* **Robust Prediction Pipeline:** The complete pipeline is serialized into **two distinct files**—the fitted Random Forest model and the crucial **StandardScaler** object—using `joblib`. This ensures that **every step** of the robust preprocessing chain (scaling, aggregation, etc.) can be replicated accurately for real-time prediction.
* **Model Selection:** Trained and evaluated several regression models, ultimately selecting the **Random Forest Regressor** for its superior performance, resistance to feature noise, and interpretability.

---

## 💻 Technical Stack

* **Language:** Python
* **Data Analysis & Feature Engineering:** Pandas, NumPy
* **Machine Learning:** Scikit-learn (RandomForestRegressor, **StandardScaler**)
* **Model Persistence:** `joblib`
* **Analysis:** Jupyter Notebook (`pubg_final.ipynb`)

---

## 📊 Results Summary

The final **Random Forest Regressor** model demonstrated high predictive accuracy on the test set:

| Metric | Score | Note |
| :--- | :--- | :--- |
| **Mean Absolute Error (MAE)** | **$0.0815$** | Represents minimal average error in predicting the final placement percentage. |
| Model | Random Forest Regressor | Selected for high performance and generalization capability. |

---

## ⚙️ Installation and Setup

### 1. Data Source

The dataset used is based on the large-scale PUBG competition data. Due to its large file size, the raw CSV file is not hosted directly on GitHub.

**Please download the raw `train_V2.csv` file from the link below and place it in the root directory of this project.**

DATA DOWNLOAD LINK: https://drive.google.com/drive/folders/1LqNXIOCHvEQYrYXe2MRsKwqvuDCYhLii?usp=drive_link

### 2. Prerequisites

Ensure you have Python 3.x installed.

### 3. Clone the Repository

```bash
git clone [https://github.com/Dhwanit5656/your-pubg-repo-name.git](https://github.com/Dhwanit5656/your-pubg-repo-name.git)
cd your-pubg-repo-name
