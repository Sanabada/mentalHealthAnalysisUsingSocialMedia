# mentalHealthAnalysisUsingSocialMedia
A data visualization project for mental health analysis using social media impact and behavioural patterns

# Mental Health Risk Prediction Using Social Media and Behavioral Patterns

## Project Overview

This repository contains the code, data processing steps, machine learning models, and visualizations developed for predicting mental health risk levels based on social media usage and behavioral factors. The project leverages exploratory data analysis (EDA), feature engineering, and two classification models—Logistic Regression and Random Forest—to identify individuals at risk of mental health challenges. Interactive dashboards built in Tableau and Power BI accompany the analysis for deeper insights and real-time monitoring. citeturn0file0

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
* Provide interactive visual insights via Tableau and Power BI dashboards. citeturn0file0

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

The data were uniformly sampled across demographics to ensure balanced feature distributions, but the target class (`risk_flag`) remained imbalanced. citeturn0file0

## Methodology

### Data Preprocessing

* Cleaned and standardized column names
* Handled missing values and duplicates
* Formatted categorical fields (e.g., stress levels)

### Exploratory Data Analysis

1. **Univariate Analysis:** Histograms and count plots for age, social media usage, sleep duration (buckets: <6 h, 6–8 h, >8 h), and stress levels.
2. **Bivariate/Multivariate Analysis:** Box plots, scatter plots with LOWESS curves, and correlation analysis revealed minimal global linear correlations due to uniform sampling.
3. **Risk Funnel Analysis:** Applied incremental filtering rules (stress = high, sleep < 6, social media > 4, low activity, long work hours, lifestyle vices) to trace a health-risk cascade from \~3.8% core cases down to individuals already consulting professionals. citeturn0file0

### Feature Engineering

* Created a domain-driven binary target variable `risk_flag` based on composite behavioral thresholds.
* Ensured objective, consistent labeling for supervised learning. citeturn0file0

### Modeling

1. **SMOTE:** Applied to training set (70:30 split) to balance classes.
2. **Logistic Regression:** Achieved 88.31% test accuracy and 93% recall on the at-risk class (prioritized sensitivity).
3. **Random Forest:** Achieved 94.15% accuracy but only 52% recall for at-risk individuals (trade-off favored Logistic Regression).

**Final Model:** Logistic Regression with SMOTE was selected for its high recall in healthcare contexts where missing a risky individual is costlier than false positives. citeturn0file0

## Results

* **At-risk detection rate:** \~3.8% of the population flagged.
* **Logistic Regression Recall (at-risk):** 93%
* **Random Forest Recall (at-risk):** 52%

## Dashboards and Visualizations

Interactive dashboards are available via Tableau:

* [Country Map Overview](https://public.tableau.com/app/profile/sai.chaitanya.munagala/viz/MentalHealthAnalysis_17466541122880/COUNTRYMAP)
* [Occupation vs. Social Media Hours](https://public.tableau.com/app/profile/sai.chaitanya.munagala/viz/MentalHealthAnalysis-OccupationandSocialMediaHours/OCCUPATION-SOCIALMEDIAHOURS)
* [Risk Insights Dashboard 1](https://public.tableau.com/app/profile/kapil.reddy8547/viz/IMPACTOFSOCIALMEDIAONMENTALHEALTHRISKINSIGHTS/Dashboard3)
* [Risk Insights Dashboard 2](https://public.tableau.com/app/profile/kapil.reddy8547/viz/IMPACTOFSOCIALMEDIAONMENTALHEALTHRISKINSIGHTS/Dashboard2) citeturn0file0

## Installation and Usage

1. Clone this repository:

   ```bash
   git clone https://github.com/<username>/mental-health-risk-prediction.git
   cd mental-health-risk-prediction
   ```
2. Create a virtual environment and install dependencies:

   ```bash
   python3 -m venv venv
   source venv/bin/activate
   pip install -r requirements.txt
   ```
3. Run Jupyter Notebook to explore the analysis:

   ```bash
   jupyter notebook
   ```
4. Follow the notebooks for EDA, preprocessing, modeling, and visualization steps.

## Future Work

* Incorporate additional features such as anxiety scores and mood indicators.
* Experiment with advanced algorithms (e.g., XGBoost, Neural Networks).
* Validate models on real-world, dynamic datasets.
* Develop real-time monitoring dashboards for proactive intervention.

## References

1. Mental Health Lifestyle Dataset: [https://zenodo.org/records/14838680](https://zenodo.org/records/14838680)
2. WHO Mental Health Overview: [https://www.who.int/news-room/fact-sheets/detail/mental-health-strengthening-our-response](https://www.who.int/news-room/fact-sheets/detail/mental-health-strengthening-our-response)
3. imbalanced-learn SMOTE Documentation: [https://imbalanced-learn.org/stable/over\_sampling.html](https://imbalanced-learn.org/stable/over_sampling.html)
4. Python Libraries Documentation: [https://www.python.org/doc/](https://www.python.org/doc/)
5. Tableau Community: [https://community.tableau.com/](https://community.tableau.com/)


This is combined project using Tableau, powerBI and python for Data Analysis proess.
