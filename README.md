# DSC148_Project

## Data

Download `application_train.csv` from the Kaggle Home Credit Default Risk
competition and place it in the project root:
[https://www.kaggle.com/competitions/home-credit-default-risk/data](https://www.kaggle.com/code/shivamb/homecreditrisk-extensive-eda-baseline-0-772/input)

## Pipeline

The notebooks must be run **in order**, because each one consumes the output
of the previous step.

| Step | Notebook | Input(s) | Output(s) |
|------|----------|----------|-----------|
| 1 | `cleaning_home_credit.ipynb` | `application_train.csv` | `application_train_clean.csv` |
| 2 | `eda_home_credit_fairness.ipynb` | `application_train.csv` | figures (EDA) |
| 3 | `feature_engineering_home_credit.ipynb` | `application_train_clean.csv` | `application_train_features.csv`, `feature_manifest.json` |
| 4 | `modeling_audit_home_credit.ipynb` | `application_train_features.csv`, `feature_manifest.json` | results |

### Run order

1. **Cleaning** — run first. Produces the cleaned dataset used by feature engineering.
2. **EDA** — reads the original `application_train.csv` directly (independent of cleaning; can be run any time after the data is downloaded).
3. **Feature engineering** — requires `application_train_clean.csv` from step 1.
4. **Modelling** — requires `application_train_features.csv` and `feature_manifest.json` from step 3.

All intermediate files should be stored in the directory containing the corresponding notebook.
