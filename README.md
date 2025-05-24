# 🌧️ AI Rain Prediction System

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://rain-prediction-hassan.streamlit.app)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1IOTvmV9shwADEn4MpHCY1JALo_yadPo7?usp=sharing)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> Predict tomorrow's rainfall with AI – A capstone project from the **DEPI Data Science Scholarship**

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Dataset](#-dataset)
- [Workflow & Methodology](#-workflow--methodology)
- [Model Performance](#-model-performance)
- [Live Demo & Resources](#-live-demo--resources)
- [Installation](#-installation)
- [Usage](#-usage)
- [Team](#-team)
- [License](#-license)

---

## 🔍 Overview

**SkyCast** is a machine learning system that predicts the chance of rain tomorrow based on historical weather data from Australia.

### 💡 Why It Matters

- 🌾 **Agriculture:** Plan irrigation and harvest timing  
- 🚚 **Logistics:** Optimize routes and schedules  
- 🚨 **Public Safety:** Enable early warning systems  
- 💰 **Cost Efficiency:** Reduce weather-related risks and losses

Built over 6 months by a 6-member team under the DEPI Scholarship, the project showcases the full data science pipeline from exploration to deployment.

---

## ✨ Key Features

- 📊 **Interactive EDA Dashboard**
- ⚙️ **Custom Feature Engineering**
- 🧠 **Multiple ML Models (XGBoost, Random Forest, Decision Tree)**
- 🌐 **Streamlit Web App**
- 🔁 **Cross-Validation & Hyperparameter Tuning**
- 📦 **Production-ready & Open Source**

---

## 📊 Dataset

| Property        | Details                                 |
|----------------|------------------------------------------|
| Source          | [Kaggle - Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package) |
| Filename        | `weatherAUS.csv`                        |
| Records         | ~145,000 rows                           |
| Time Period     | 2007–2017                               |
| Locations       | 49 Australian cities                    |
| Target Variable | `RainTomorrow` (Yes/No)                 |
| Features        | Date, Location, MinTemp, MaxTemp, Rainfall, Humidity, WindSpeed, etc. |

---

## 🔧 Workflow & Methodology

### 1. 🧪 Exploratory Data Analysis (EDA)
- Rainfall distribution by city and season  
- Correlation heatmap  
- Temperature vs Humidity graphs  
- Outlier and class imbalance detection

### 2. 🧹 Data Preprocessing
- Handled missing values:
  - `KNNImputer` for numerical features
  - Mode for categorical features
- Outliers removed using IQR method
- Label & OneHot encoding for categorical data
- Scaled numerical features using `MinMaxScaler`

### 3. ⚙️ Feature Engineering
Created new features to improve prediction:
- `TempDiff = MaxTemp - MinTemp`
- `HumidityDiff = Humidity3pm - Humidity9am`
- `WindSpeedAvg = (WindSpeed9am + WindSpeed3pm) / 2`
- Extracted `Day`, `Month`, and `Year` from the `Date` column

### 4. 🤖 Model Building & Evaluation
| Model           | Description       | Accuracy |
|----------------|-------------------|----------|
| Decision Tree  | Baseline Model     | ~72%     |
| Random Forest  | Improved Accuracy  | ~79%     |
| XGBoost        | Final Best Model   | **~83%** |

- Cross-validation and GridSearchCV used for hyperparameter tuning  
- Metrics: Accuracy, Precision, Recall, F1-Score, ROC-AUC

---

## 🌐 Live Demo & Resources

- 🟢 **[Live Streamlit App](https://rain-prediction-hassan.streamlit.app)**
- 📓 **[Google Colab Notebook](https://colab.research.google.com/drive/1IOTvmV9shwADEn4MpHCY1JALo_yadPo7?usp=sharing)**
- 🗂️ **[GitHub Repository](https://github.com/Hassan-DS507/rain-prediction)**
- ✅ **[Trello Project Board](https://trello.com/invite/b/680ea606b97eee9aff68199e/ATTIc99335699bae965178d4f61a5cfc8ce3B3FE3E5C/rain-prediction-project)**

---

## 💻 Installation

```bash
# Clone the repository
git clone https://github.com/Hassan-DS507/rain-prediction.git
cd rain-prediction

# Create virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate     # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
