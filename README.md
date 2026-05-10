# Customer Shopping Behavior Analysis

A data analysis and machine learning project exploring customer shopping patterns and building predictive models from an e-commerce behavior dataset.

## Overview

This repository contains Jupyter notebooks and a CSV dataset for analyzing customer shopping behavior. The main notebook performs:

- data loading and validation
- exploratory data analysis (EDA)
- feature redundancy and leakage checks
- classification modeling for **Subscription Status**
- regression modeling for **Purchase Amount (USD)**
- interpretation of findings and dataset limitations

The work is based on the **Consumer Behavior and Shopping Habits Dataset** and focuses on demonstrating sound machine learning workflow inside a notebook environment.

## Repository Contents

- `Consumer_Shopping_Behavior_ML_Analysis.ipynb` — main end-to-end analysis notebook
- `E-Commerce Dataset ML_New.ipynb` — additional notebook version
- `E-Commerce Dataset_ML.ipynb` — earlier notebook version
- `shopping_behavior.csv` — dataset used for the analysis
- `README.md` — project documentation

## Project Goals

This project explores two predictive tasks:

1. **Classification:** predict whether a customer has a subscription (`Subscription Status`)
2. **Regression:** predict the customer `Purchase Amount (USD)`

It also investigates customer attributes such as age, gender, season, payment method, shipping type, purchase frequency, and product category.

## Dataset

**Dataset file:** `shopping_behavior.csv`  
**Rows:** 3,900  
**Columns:** 18  
**Type:** mixed numerical and categorical data

Example features include:

- Customer ID
- Age
- Gender
- Item Purchased
- Category
- Purchase Amount (USD)
- Location
- Size
- Color
- Season
- Review Rating
- Subscription Status
- Shipping Type
- Discount Applied
- Promo Code Used
- Previous Purchases
- Payment Method
- Frequency of Purchases

## Main Analysis Highlights

The main notebook includes:

- dataset structure inspection and type checks
- missing-value and duplicate analysis
- outlier detection using the IQR method
- distribution checks to assess data realism
- identification of redundant and leakage-prone features
- statistical testing for feature-target relationships
- visual exploration using plots and charts
- machine learning model building and evaluation

## What Was Missed in the Earlier Analysis

Compared with the earlier notebook versions, the newer analysis improves the project by covering several important points that were previously missing or not clearly addressed:

- **Data quality validation:** the new notebook explicitly checks for missing values, duplicate rows, and duplicate customer IDs before modeling.
- **Outlier inspection:** numerical features are reviewed with the IQR method and box plots instead of moving directly into modeling.
- **Dataset realism check:** the analysis now examines unusually uniform distributions and recognizes that the dataset may be synthetic or artificially regular.
- **Feature redundancy detection:** it identifies that `Promo Code Used` is identical to `Discount Applied` and removes that redundancy.
- **Leakage detection:** it recognizes that `Item Purchased` maps directly to `Category`, which would create target leakage if used improperly.
- **Statistical testing:** instead of relying only on visuals, the notebook now uses chi-square tests and Mann-Whitney U tests to assess which features actually relate to the target.
- **More honest interpretation:** the updated analysis does not present the dataset as fully realistic business data and instead discusses its limitations clearly.
- **Dual-task framing:** the notebook expands beyond a single prediction goal and separates the work into a classification task and a regression task.

## What I Learned from the New Analysis

The updated analysis leads to several important lessons:

- **Good ML starts with data checking, not modeling first.** Verifying missing data, duplicates, and suspicious patterns is essential before training any model.
- **High model performance can be misleading** when the dataset contains leakage, redundancy, or synthetic-like structure.
- **Feature engineering must include feature removal, not just feature creation.** Removing duplicated or leakage-prone columns improves the credibility of the workflow.
- **Statistical significance and practical usefulness are not always the same.** Some variables may look interesting visually but provide little real predictive value.
- **Gender is a dominant signal for subscription prediction in this dataset,** while many other features appear weak or non-significant.
- **Uniform distributions can be a warning sign** that a dataset may not reflect real-world consumer behavior.
- **Interpretability matters.** It is important not only to build models, but also to explain why certain features matter and where the data may be flawed.
- **A stronger project is one that acknowledges limitations honestly.** The new notebook is better because it explains where the analysis is strong and where the dataset is weak.

## Important Findings

From the notebook analysis:

- the dataset contains **3,900 records** and **18 columns**
- no missing values were found
- no duplicate rows were found
- some features show unusually uniform distributions, suggesting the dataset may be synthetic or highly regularized
- `Promo Code Used` duplicates `Discount Applied`
- `Item Purchased` maps directly to `Category`, so it can create target leakage in category-related modeling
- gender appears to be a very strong signal for subscription prediction in this dataset

## Technologies Used

- Python
- Jupyter Notebook
- pandas
- numpy
- matplotlib
- seaborn
- scikit-learn
- xgboost
- shap
- scipy

## How to Run

1. Clone the repository:

```bash
git clone https://github.com/Devikrishna545/Customer-Shopping-Behavior-Analysis.git
cd Customer-Shopping-Behavior-Analysis
```

2. Create and activate a virtual environment (optional):

```bash
python -m venv venv
source venv/bin/activate
```

On Windows:

```bash
venv\Scripts\activate
```

3. Install the required libraries:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost shap scipy jupyter
```

4. Launch Jupyter Notebook:

```bash
jupyter notebook
```

5. Open and run:

```text
Consumer_Shopping_Behavior_ML_Analysis.ipynb
```

## Suggested Project Structure

```text
Customer-Shopping-Behavior-Analysis/
├── Consumer_Shopping_Behavior_ML_Analysis.ipynb
├── E-Commerce Dataset ML_New.ipynb
├── E-Commerce Dataset_ML.ipynb
├── shopping_behavior.csv
└── README.md
```

## Use Cases

This project can be useful for:

- learning applied machine learning with tabular retail data
- practicing exploratory data analysis in Jupyter
- understanding feature leakage and dataset quality issues
- building customer behavior prediction workflows
- portfolio demonstration for data science and machine learning projects

## Limitations

The notebook explicitly notes that the dataset appears to have several synthetic-like characteristics, including highly uniform distributions. Because of that, results should be interpreted as a demonstration of workflow and methodology rather than a production-grade business model.

## Future Improvements

Possible next steps include:

- adding a `requirements.txt` file
- exporting plots or model artifacts to a results folder
- comparing more classification and regression models
- improving notebook organization and markdown explanations
- turning the notebook into a reusable Python pipeline or app

## Author

**Devikrishna545**  
GitHub: https://github.com/Devikrishna545

## Repository Link

https://github.com/Devikrishna545/Customer-Shopping-Behavior-Analysis
