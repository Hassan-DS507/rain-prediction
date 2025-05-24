# 🌧️ SkyCast – AI Rain Prediction System

A capstone project from the **DEPI Data Science Scholarship**, delivered over 6 months with real teamwork, machine learning, and product deployment.

**Led and developed by:** Hassan Abdul-Razeq (Team Leader)

---

## 🔍 Overview

This project answers a real-world question:  
**Can we predict if it will rain tomorrow?**

Why it matters:
- Better planning for agriculture & logistics
- Public safety and early warning
- Reducing costs from weather-related risks

---

## 📊 Dataset Information

- **Source:** Kaggle – Rain in Australia  
- **Records:** ~145,000  
- **Target:** `RainTomorrow` (Yes/No)  
- **Main features:** MinTemp, MaxTemp, Rainfall, Humidity, WindSpeed, Location, etc.

---

## 🔧 Project Pipeline

### 🧪 EDA
- Rainfall distribution by location and time
- Temperature and humidity analysis
- Correlation heatmap
- Outliers and imbalance detection

### 🧹 Data Preprocessing
- Missing values: KNNImputer (numeric), Mode (categorical)
- Outliers handled with IQR
- Encoding: Label & OneHot
- Scaling: MinMaxScaler

### ⚙️ Feature Engineering
- `TempDiff`, `HumidityDiff`, `WindSpeedAvg`
- Extracted day, month, year from `Date`

### 🤖 Model Building
- Models: Decision Tree, Random Forest, **XGBoost**
- Metrics: Accuracy (~83%), F1, ROC-AUC
- Tuned with Cross-Validation and GridSearch

---

## 🌐 Deployment

✅ **Streamlit App (Live):**  
[https://rain-prediction-hassan.streamlit.app](https://rain-prediction-hassan.streamlit.app)

✅ **Google Colab Notebook (Preview):**  
[Open in Colab](https://colab.research.google.com/drive/1IOTvmV9shwADEn4MpHCY1JALo_yadPo7?usp=sharing)

✅ **GitHub Repo (Source Code):**  
[https://github.com/Hassan-DS507/rain-prediction](https://github.com/Hassan-DS507/rain-prediction)

✅ **Project Board on Trello (Team Workflow):**  
[https://trello.com/.../rain-prediction-project](https://trello.com/invite/b/680ea606b97eee9aff68199e/ATTIc99335699bae965178d4f61a5cfc8ce3B3FE3E5C/rain-prediction-project)

---

## 🚀 How to Run

```bash
pip install -r requirements.txt
streamlit run app.py
