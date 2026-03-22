# 🌧️ Australian Weather Rainfall Prediction

A machine learning project that predicts whether it will rain tomorrow in Melbourne, Australia, using daily weather observations from 2008 to 2017.

## 📌 Project Overview

This project builds and evaluates binary classification models to predict rainfall using the [Australian Weather Dataset](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package) from the Australian Government's Bureau of Meteorology.

The target variable is `RainTomorrow` — whether there will be at least 1mm of rain the following day.

## 🧠 Objectives

- Perform exploratory data analysis and feature engineering on real-world weather data
- Build a **scikit-learn Pipeline** combining preprocessing and classification
- Optimize models using **GridSearchCV** with stratified cross-validation
- Evaluate model performance using classification reports, confusion matrices, and feature importances
- Compare **Random Forest** vs **Logistic Regression** classifiers

## 📁 Repository Structure

```
aus-weather-prediction/
│
├── FinalProject_AUSWeather.ipynb   # Main project notebook
├── requirements.txt                 # Python dependencies
├── .gitignore                       # Files to exclude from version control
└── README.md                        # Project documentation
```

## 📊 Dataset

| Field         | Description                                           | Type   |
|:------------- |:----------------------------------------------------- |:-------|
| Date          | Date of observation (YYYY-MM-DD)                      | object |
| Location      | Location of observation                               | object |
| MinTemp       | Minimum temperature (°C)                              | float  |
| MaxTemp       | Maximum temperature (°C)                              | float  |
| Rainfall      | Amount of rainfall (mm)                               | float  |
| Humidity9am   | Humidity at 9am (%)                                   | float  |
| Humidity3pm   | Humidity at 3pm (%)                                   | float  |
| RainToday     | Whether it rained today (Yes/No)                      | object |
| RainTomorrow  | **Target** — Whether it will rain tomorrow (Yes/No)   | object |

> Dataset source: [Kaggle - Weather Dataset Rattle Package](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)

## 🔧 Methodology

1. **Data Cleaning** — Drop rows with missing values
2. **Feature Engineering** — Map dates to seasons, filter to Melbourne area (Melbourne + Watsonia)
3. **Preprocessing** — StandardScaler for numerical features, OneHotEncoder for categorical features via `ColumnTransformer`
4. **Modeling** — Scikit-learn `Pipeline` with GridSearchCV cross-validation
5. **Evaluation** — Classification report, confusion matrix, feature importance plot

## 🤖 Models Used

| Model                  | Notes                                      |
|:---------------------- |:------------------------------------------ |
| Random Forest          | Primary model; tuned via GridSearchCV      |
| Logistic Regression    | Comparison model; evaluated on same splits |

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook or JupyterLab

### Installation

```bash
# Clone the repository
git clone https://github.com/<your-username>/aus-weather-prediction.git
cd aus-weather-prediction

# Install dependencies
pip install -r requirements.txt

# Launch Jupyter
jupyter notebook FinalProject_AUSWeather.ipynb
```

### Dataset Download

Download `weatherAUS.csv` from [Kaggle](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package) and place it in the project root directory before running the notebook.

## 📈 Results

The notebook includes:
- Classification report (precision, recall, F1-score)
- Confusion matrix visualization
- Feature importance bar chart (identifying the most predictive weather variable)
- Comparison between Random Forest and Logistic Regression performance

## 📚 References

- [Australian Bureau of Meteorology](http://www.bom.gov.au/climate/dwo/)
- [Kaggle Dataset](https://www.kaggle.com/datasets/jsphyg/weather-dataset-rattle-package)
- [IBM Skills Network](https://skills.network/)

## 👤 Author

Built as part of the IBM Developer Skills Network Machine Learning course final project.
