# Telco Customer Churn Prediction

Machine learning project that predicts customer churn in the telecommunications sector and identifies the main churn drivers.

Built as the final project of the *Professional IT Business and Digitalization* course (M.Sc. Professional IT, HTW Berlin), January 2026.

## Overview

The notebook walks through the full workflow: exploratory data analysis, a leakage-safe preprocessing pipeline, three classification models and a business-oriented interpretation of the results.

| Stage | Details |
|---|---|
| EDA | Distribution and churn analysis of customer, contract and billing attributes |
| Preprocessing | Imputation, scaling and encoding inside Scikit-Learn `Pipeline`s |
| Models | Logistic Regression, Decision Tree (`max_depth=5`), Random Forest (`n_estimators=100`) |
| Evaluation | Accuracy scores plus confusion matrices, since accuracy alone can be misleading on imbalanced classes |

## Key points

- **No data leakage:** scaling and encoding are fitted on the training split only, via Scikit-Learn pipelines applied after the train/test split.
- **Overfitting control:** the Decision Tree depth is limited to 5.
- **Results:** Logistic Regression performed best (80.55% test accuracy), followed by Random Forest (80.34%) and Decision Tree (79.84%).
- **Class balance:** about 26% of customers churn, so the dataset is imbalanced.
- **Selected model:** Logistic Regression, for its high accuracy and interpretability.
- **Main finding:** customers on month-to-month contracts with short tenure are the most likely to churn.
- **Recommendation:** a targeted discount strategy to move monthly customers to 1-year contracts.

## Repository contents

| File | Description |
|---|---|
| `churn_analysis.ipynb` | Full analysis notebook with outputs |
| `final_project.pptx` | Presentation summarising the findings |

## Dataset

The data is the public **Telco Customer Churn** dataset and is not included in this repository.
Download it from Kaggle: https://www.kaggle.com/blastchar/telco-customer-churn
and save it as `telco_churn.csv` next to the notebook.

## How to run

```bash
python -m venv .venv
source .venv/bin/activate
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
jupyter notebook churn_analysis.ipynb
```

Then choose **Run All**.

## Author

Yigit Peker, HTW Berlin
