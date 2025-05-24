# 🌧️ SkyCast – AI Rain Prediction System

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://rain-prediction-hassan.streamlit.app)
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1IOTvmV9shwADEn4MpHCY1JALo_yadPo7?usp=sharing)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A machine learning system that predicts next-day rainfall with 83% accuracy. Developed as a capstone project for the **DEPI Data Science Scholarship** by a 6-member team led by Hassan Abdul-Razeq.

![Dashboard Preview](https://github.com/Hassan-DS507/rain-prediction/raw/main/assets/dashboard-preview.png)

## 📖 Table of Contents
- [Project Overview](#-project-overview)
- [Key Features](#-key-features)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [Model Performance](#-model-performance)
- [Installation](#-installation)
- [Usage](#-usage)
- [Deployment](#-deployment)
- [Team](#-team)
- [License](#-license)

## 🌟 Project Overview

SkyCast answers a critical real-world question: **Will it rain tomorrow?** Using historical weather data from Australia and machine learning, we've built a predictive system with practical applications in:

- 🌾 Agriculture: Irrigation planning and harvest scheduling
- 🚚 Logistics: Route optimization for transportation
- 🚨 Public Safety: Early warning systems
- 💰 Economic Planning: Reducing weather-related losses

## 🚀 Key Features

- **Comprehensive Data Processing**: Advanced handling of missing values and outliers
- **Feature Engineering**: Created predictive features like temperature differentials
- **Optimized Models**: XGBoost outperformed with 83% accuracy
- **Interactive Dashboard**: Visual exploration of weather patterns
- **Production-Ready**: Deployed as a Streamlit web application

## 📊 Dataset

**Source**: [Rain in Australia Dataset (Kaggle)](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)

| Characteristic  | Detail  |
|----------------|---------|
| Records        | ~145,000 |
| Time Period    | 2007-2017 |
| Locations      | 49 Australian cities |
| Key Features   | MinTemp, MaxTemp, Rainfall, Humidity, WindSpeed, Pressure, etc. |
| Target         | RainTomorrow (Yes/No) |

## 🔬 Methodology

### 1. Exploratory Data Analysis
- Visualized rainfall distribution across locations and seasons
- Analyzed temperature-humidity relationships
- Identified class imbalance (22% rainy days)
- Detected and treated outliers

### 2. Data Preprocessing
```python
# Missing value treatment
numerical_imputer = KNNImputer(n_neighbors=5)
categorical_imputer = SimpleImputer(strategy='most_frequent')

# Feature scaling
scaler = MinMaxScaler()
