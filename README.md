# Mental Health Risk Prediction Using Social Media and Behavioral Patterns

## Project Overview

This repository contains the code, data processing steps, machine learning models, and visualizations developed for predicting mental health risk levels based on social media usage and behavioral factors. The project leverages exploratory data analysis (EDA), feature engineering, and two classification models—Logistic Regression and Random Forest—to identify individuals at risk of mental health challenges. Interactive dashboards built in Tableau and Power BI accompany the analysis for deeper insights and real-time monitoring.

## Table of Contents

* [Objectives](#objectives)
* [Technology Stack](#technology-stack)
* [Data Description](#data-description)
* [Methodology](#methodology)

  * [Data Preprocessing](#data-preprocessing)
  * [Exploratory Data Analysis](#exploratory-data-analysis)
  * [Feature Engineering](#feature-engineering)
  * [Modeling](#modeling)
* [Results](#results)
* [Dashboards and Visualizations](#dashboards-and-visualizations)
* [Installation and Usage](#installation-and-usage)
* [Future Work](#future-work)
* [References](#references)

## Objectives

* Develop a predictive model to identify individuals at risk of mental health challenges based on social media usage and behavioral indicators.
* Engineer a custom binary risk indicator (`risk_flag`) using domain-driven rules.
* Handle class imbalance with SMOTE.
* Compare model performance between Logistic Regression and Random Forest.
* Provide interactive visual insights via Tableau and Power BI dashboards.

## Technology Stack

* **Programming Language:** Python 3
* **Libraries:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, imbalanced-learn
* **BI Tools:** Tableau, Power BI
* **Environment:** Google Colab, Jupyter Notebooks

## Data Description

The dataset comprises survey responses capturing:

* Social media usage (hours per day)
* Sleep duration (hours per night)
* Stress level (categorical: low, medium, high)
* Physical activity hours
* Work hours
* Lifestyle factors (smoking, alcohol consumption)
* Consultation history with mental health professionals

Data were sampled across demographics to ensure balanced feature distributions, though the target class (`risk_flag`) remained imbalanced.

## Methodology

### Data Preprocessing

* Cleaned and standardized column names
* Handled missing values and duplicates
* Formatted categorical fields (e.g., stress levels)

### Exploratory Data Analysis

1. **Univariate Analysis:** Histograms and count plots for age, social media usage, and sleep duration (bins: <6 h, 6–8 h, >8 h).
2. **Bivariate Analysis:** Box plots and scatter plots with LOWESS curves revealed nuanced interactions among features.
3. **Risk Funnel Analysis:** Sequential filters (high stress, low sleep, heavy social media use, low activity) traced a health-risk cascade from \~3.8% core cases.

### Feature Engineering

* Created `risk_flag` based on composite behavioral thresholds.
* Ensured consistent labeling for supervised learning.

### Modeling

1. **SMOTE:** Balanced classes in the training split.
2. **Logistic Regression:** Achieved 88.3% test accuracy with 93% recall on the at-risk class (prioritizing sensitivity).
3. **Random Forest:** Achieved 94.2% accuracy but only 52% recall for at-risk individuals (highlighting a recall–precision trade-off).

<ins>**Final Model:**</ins> Logistic Regression with SMOTE was selected for its high recall, ensuring fewer false negatives in a healthcare context.

## Results

* **At-risk detection rate:** \~3.8% of survey respondents flagged.
* **Logistic Regression Recall:** 93%
* **Random Forest Recall:** 52%

## Dashboards and Visualizations

Accessible via Tableau:

* **Country Map Overview:** Interactive map displaying at-risk distribution.
* **Occupation vs. Social Media:** Correlating job categories with usage hours.
* **Risk Insights Dashboards:** Detailed drilldowns on behavioral patterns and risk trajectories.

## Installation and Usage

1. **Clone the repo:**

   ```bash
   git clone https://github.com/sanabada/mental-health-risk-prediction.git
   cd mental-health-risk-prediction
   ```
2. **Setup environment:**

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```
3. **Launch analysis:**

   ```bash
   jupyter notebook
   ```

Follow the notebooks for end-to-end data workflows—from EDA to model evaluation.

## Future Work

* Integrate mood and anxiety metrics.
* Assess advanced classifiers (XGBoost, Neural Nets).
* Deploy real-time risk monitoring dashboards.

## References

1. Mental Health Lifestyle Dataset—Zenodo
2. WHO: Mental Health Fact Sheets
3. imbalanced‑learn SMOTE docs
4. Python & Scikit‑learn documentation
5. Tableau Community Resources
