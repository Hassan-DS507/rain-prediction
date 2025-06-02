# 🌧️ SkyCast: AI Rain Prediction System

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://rain-prediction-hassan.streamlit.app)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1IOTvmV9shwADEn4MpHCY1JALo_yadPo7?usp=sharing)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub last commit](https://img.shields.io/github/last-commit/Hassan-DS507/rain-prediction)](https://github.com/Hassan-DS507/rain-prediction/commits/main)
[![GitHub issues](https://img.shields.io/github/issues/Hassan-DS507/rain-prediction)](https://github.com/Hassan-DS507/rain-prediction/issues)
[![GitHub pull requests](https://img.shields.io/github/issues-pr/Hassan-DS507/rain-prediction)](https://github.com/Hassan-DS507/rain-prediction/pulls)

**SkyCast** is an AI-powered system designed to predict the likelihood of rainfall for the following day using historical weather data from Australia. This project was developed as a capstone for the **DEPI Data Science Scholarship**.

---

## 📖 Table of Contents

- [Overview](#-overview)
- [Problem Statement](#-problem-statement)
- [Key Features](#-key-features)
- [System Architecture](#-system-architecture)
- [Dataset](#-dataset)
- [Methodology](#-methodology)
- [Model Performance](#-model-performance)
- [Technology Stack](#-technology-stack)
- [Live Demo & Resources](#-live-demo--resources)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#-usage)
- [Contributing](#-contributing)
- [Team](#-team)
- [License](#-license)
- [Acknowledgments](#-acknowledgments)

---

## 🔍 Overview

SkyCast leverages machine learning techniques to provide actionable rainfall predictions. By analyzing patterns in historical weather data, the system aims to deliver reliable forecasts that can benefit various sectors.

---

## 🎯 Problem Statement

Accurate rainfall prediction is crucial for numerous industries and public services. Timely forecasts can:
-   🌾 **Agriculture:** Optimize irrigation schedules and protect crops during harvest.
-   🚚 **Logistics & Transportation:** Enhance route planning and minimize weather-related disruptions.
-   🚨 **Public Safety:** Facilitate early warnings for potentially hazardous weather conditions.
-   💰 **Economic Efficiency:** Mitigate financial losses associated with unforeseen weather events.

This project, developed over six months by a team of six under the DEPI Scholarship, demonstrates an end-to-end data science workflow, from initial data exploration and preprocessing to model deployment and a user-facing application.

---

## ✨ Key Features

-   📊 **Interactive EDA Dashboard:** For insightful data visualization and exploration.
-   ⚙️ **Advanced Feature Engineering:** Creation of new, impactful features from existing data.
-   🧠 **Multiple ML Model Implementation:** Including Decision Trees, Random Forests, and XGBoost for comparative analysis.
-   🌐 **User-Friendly Web Application:** Built with Streamlit for easy interaction and prediction.
-   🔁 **Robust Model Validation:** Employing cross-validation and hyperparameter tuning (GridSearchCV) for optimal performance.
-   📦 **Production-Ready & Open Source:** Designed for scalability and community contribution.

---

## 🏗️ System Architecture

*(Consider adding a high-level diagram here if possible, showing data flow from data acquisition -> preprocessing -> feature engineering -> model training -> prediction -> Streamlit app)*

The system follows a standard machine learning pipeline:
1.  **Data Ingestion:** Sourcing data from the Kaggle dataset.
2.  **Exploratory Data Analysis (EDA):** Understanding data characteristics and patterns.
3.  **Data Preprocessing:** Cleaning, transforming, and preparing data for modeling.
4.  **Feature Engineering:** Creating new predictive features.
5.  **Model Training & Selection:** Building, evaluating, and selecting the best-performing model.
6.  **Deployment:** Serving the model via a Streamlit web application.

---

## 📊 Dataset

The model is trained on the "Rain in Australia" dataset.

| Property        | Details                                                                                                |
| :-------------- | :----------------------------------------------------------------------------------------------------- |
| Source          | [Kaggle: Rain in Australia](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)     |
| Original Filename | `weatherAUS.csv`                                                                                       |
| Records         | Approximately 145,000                                                                                  |
| Time Period     | 2007 – 2017                                                                                            |
| Locations       | 49 Australian cities                                                                                   |
| Target Variable | `RainTomorrow` (Binary: Yes/No)                                                                        |
| Key Features    | Date, Location, MinTemp, MaxTemp, Rainfall, Evaporation, Sunshine, WindGustDir, WindGustSpeed, Humidity9am, Humidity3pm, Pressure9am, Pressure3pm, Cloud9am, Cloud3pm, Temp9am, Temp3pm, RainToday |

*Table based on information from the README.md.*

---

## 🛠️ Methodology

### 1. Exploratory Data Analysis (EDA)
-   Analyzed rainfall distribution across cities and seasons.
-   Generated correlation heatmaps to identify relationships between features.
-   Visualized Temperature vs. Humidity trends.
-   Conducted outlier detection and assessed class imbalance for the target variable.

### 2. Data Preprocessing
-   **Missing Value Imputation:**
    -   Numerical features: `KNNImputer`.
    -   Categorical features: Mode (most frequent value).
-   **Outlier Removal:** Applied the Interquartile Range (IQR) method.
-   **Encoding Categorical Data:** Utilized Label Encoding and One-Hot Encoding.
-   **Feature Scaling:** Scaled numerical features using `MinMaxScaler`.

### 3. Feature Engineering
New features were engineered to enhance predictive power:
-   `TempDiff = MaxTemp - MinTemp`
-   `HumidityDiff = Humidity3pm - Humidity9am`
-   `WindSpeedAvg = (WindSpeed9am + WindSpeed3pm) / 2`
-   Date-based features: `Day`, `Month`, `Year` extracted from the `Date` column.

### 4. Model Building, Evaluation & Selection
Multiple machine learning models were trained and evaluated:

| Model           | Description                       | Reported Accuracy |
| :-------------- | :-------------------------------- | :---------------- |
| Decision Tree   | Baseline Model                    | ~72%              |
| Random Forest   | Ensemble method for improved accuracy | ~79%              |
| **XGBoost** | **Final Selected Model (Best Performance)** | **~83%** |

-   **Validation Strategy:** Cross-validation.
-   **Hyperparameter Optimization:** GridSearchCV.
-   **Evaluation Metrics:** Accuracy, Precision, Recall, F1-Score, ROC-AUC.

---


## 💻 Technology Stack

-   **Programming Language:** Python
-   **Data Manipulation & Analysis:** Pandas, NumPy
-   **Data Visualization:** Matplotlib, Seaborn
-   **Machine Learning:** Scikit-learn, XGBoost
-   **Web Framework:** Streamlit
-   **Development Environment:** Jupyter Notebooks, Google Colab
-   **Version Control:** Git & GitHub

*(This is an assumed stack based on common tools for such projects. Please update with the actual tools used.)*

---

## 🌐 Live Demo & Resources

-   🟢 **[Live Streamlit Application](https://rain-prediction-hassan.streamlit.app)**
-   📓 **[Google Colab Notebook (Development & Exploration)](https://colab.research.google.com/drive/1IOTvmV9shwADEn4MpHCY1JALo_yadPo7?usp=sharing)**
-   🗂️ **[GitHub Repository (Source Code)](https://github.com/Hassan-DS507/rain-prediction)**
-   ✅ **[Trello Project Board (Project Management)](https://trello.com/invite/b/680ea606b97eee9aff68199e/ATTIc99335699bae965178d4f61a5cfc8ce3B3FE3E5C/rain-prediction-project)**

---

## 🏁 Getting Started

Follow these instructions to set up the project locally.

### Prerequisites

-   Python (version 3.8 or higher recommended)
-   pip (Python package installer)
-   Git

### Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/Hassan-DS507/rain-prediction.git](https://github.com/Hassan-DS507/rain-prediction.git)
    cd rain-prediction
    ```
  

2.  **Create and activate a virtual environment** (recommended):
    ```bash
    python -m venv venv
    ```
   
    -   On macOS/Linux:
        ```bash
        source venv/bin/activate
        ```
      
    -   On Windows:
        ```bash
        venv\Scripts\activate
        ```
      

3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
  

---

## 🚀 Usage

1.  **Navigate to the application directory** (if you haven't already):
    ```bash
    cd path/to/your/cloned/rain-prediction/app_src # Or wherever your main Streamlit script is
    ```
2.  **Run the Streamlit application:**
    ```bash
    streamlit run Home.py # Or your main Streamlit app file
    ```
    The application should now be accessible in your web browser (usually at `http://localhost:8501`).

*(Please verify the exact command and path to run the Streamlit app based on your project structure.)*

---

## 🤝 Contributing

Contributions are welcome! If you have suggestions for improvements or want to contribute to the project, please follow these steps:

1.  Fork the Project.
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the Branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

Please ensure your code adheres to the project's coding standards and includes appropriate tests.

---

## 👥 Team

This project was developed by a dedicated team of 6 members as part of the DEPI Data Science Scholarship.
*(Consider listing team members here if appropriate, e.g., "Lead Developer: Hassan DS507")*

---

## ⚖️ License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

*(Ensure you have a `LICENSE` file in your repository. If not, you can easily create one with the MIT License text.)*

---

## 🙏 Acknowledgments

-   The **DEPI Data Science Scholarship** for providing the platform and opportunity.
-   Kaggle for the "Rain in Australia" dataset.
-   The open-source community for the tools and libraries used.

---
