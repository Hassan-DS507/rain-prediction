# 🌧️ SkyCast – Rain Prediction System using AI

A capstone project from the **DEPI Data Science Scholarship**  
Built by a 6-member team under the supervision of Eng. Heba Mohamed  
**Led and managed by Hassan Abdul-Razeq (Team Leader)**

---

## 🔍 Overview

This project answers a practical and critical question:  
**Can we predict if it will rain tomorrow?**

Accurate rain prediction enables:
- Better planning for farmers, logistics, and transportation
- Early warning systems to reduce losses
- Improved public safety and awareness

---

## 📊 Dataset Information

- **Source:** Kaggle – Rain in Australia  
- **Filename:** `weatherAUS.csv`  
- **Entries:** ~145,000 records  
- **Main Features:** Date, Location, MinTemp, MaxTemp, Rainfall, Humidity, WindSpeed, etc.  
- **Target Variable:** `RainTomorrow` (Yes/No)

---

## 🔧 Steps Implemented

### 🧪 Exploratory Data Analysis (EDA)
- Visualized rainfall by city, season, temperature & humidity
- Checked feature correlations
- Identified class imbalance and outliers

### 🧹 Data Cleaning & Preprocessing
- Handled missing values using:
  - `KNNImputer` for numerical features
  - Mode for categorical features
- Treated outliers using the IQR method
- Encoded categorical variables (Label & OneHot)
- Applied `MinMaxScaler` for feature scaling

### ⚙️ Feature Engineering
- Created new features:
  - `TempDiff = MaxTemp - MinTemp`
  - `HumidityDiff`, `WindSpeedAvg`, etc.
- Extracted Day, Month, and Year from Date column

### 🤖 Model Building
- Train/test split  
- Trained models:
  - Decision Tree (baseline)
  - Random Forest (improved)
  - XGBoost (best performance)
- Evaluated using:
  - Accuracy, Precision, Recall, F1-score, ROC-AUC
- Used cross-validation & hyperparameter tuning

---

## 🧠 Models Used

| Model           | Role         | Accuracy |
|----------------|--------------|----------|
| Decision Tree  | Baseline     | ~72%     |
| Random Forest  | Improved     | ~79%     |
| XGBoost        | Final Model  | **~83%** |

- XGBoost performed best: robust to imbalance, missing values & outliers
- Balanced precision & recall

---

## 🌐 Deployment

An interactive **Streamlit Web App** was built with the following pages:

- `🏠 Home` – Project overview  
- `📊 Dashboard` – Rain insights and graphs  
- `☔ Predict Rain` – Enter your data to get prediction  
- `ℹ️ About` – Team, methodology, documentation

---

## 🚀 How to Run

```bash
pip install -r requirements.txt
streamlit run app.py
