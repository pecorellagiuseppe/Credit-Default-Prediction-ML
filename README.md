# Credit Default Prediction Using Machine Learning

### A Cross-Country Comparative Analysis

## Project Overview

This project investigates the application of Machine Learning techniques to credit default prediction across three countries: **Italy, Poland, and Kazakhstan**.

The main objective is to evaluate the predictive performance of different classification algorithms and assess their ability to generalize across different economic environments.

Three models are compared:

- Logistic Regression
- Random Forest
- XGBoost

The analysis focuses on both within-country predictive accuracy and cross-country model transferability.

## Dataset

The dataset contains **17,500 observations** and 16 original variables, including:

- **Borrower characteristics:** Age, employment status, annual income
- **Credit information:** Credit history, previous defaults, loan amount, loan duration
- **Financial indicators:** Debt-to-income ratio
- **Macroeconomic indicators:** GDP per capita, inflation, interest rates, government debt-to-GDP ratio

The target variable is `default`, indicating whether a borrower defaults on a loan.

## Methodology

The analysis follows these main steps:

1. **Data preprocessing:** Missing-value handling, correlation analysis, categorical encoding, numerical scaling and logarithmic transformations.
2. **Model development:** Implementation of Logistic Regression, Random Forest and XGBoost.
3. **Within-country evaluation:** Training and testing models separately for each country using stratified 80/20 splits.
4. **Cross-country generalization:** Training models on one country and evaluating their predictive performance on other countries.
5. **Performance comparison:** Evaluating ROC-AUC, Precision-Recall AUC and Brier Score, alongside probability calibration and overfitting diagnostics.

## Results

### Average Within-Country Performance

| Model | Mean ROC-AUC |
|---|---|
| Logistic Regression | 0.8697 |
| XGBoost | 0.8682 |
| Random Forest | 0.8647 |

### Cross-Country Generalization

| Model | Mean Cross-Country ROC-AUC |
|---|---|
| Logistic Regression | 0.8512 |
| Random Forest | 0.8413 |
| XGBoost | 0.8357 |

## Key Findings

- Logistic Regression achieved the highest average within-country ROC-AUC.
- Logistic Regression also demonstrated the strongest cross-country generalization.
- Random Forest achieved particularly strong performance in Italy, with a ROC-AUC of 0.9250.
- Tree-based models showed greater evidence of overfitting in some countries, particularly Poland.
- Greater model complexity did not consistently translate into better predictive performance.

These findings highlight the importance of evaluating model robustness and transferability when developing credit risk prediction systems.

## Technologies Used

- Python
- Pandas and NumPy
- Scikit-learn
- XGBoost
- Matplotlib and Seaborn
- Jupyter Notebook / Google Colab

## Repository Contents

- `credit_default_analysis.ipynb` — Complete Python analysis, model development, evaluation and visualizations.
- `credit_default_dataset_cleaned.csv` — Dataset used in the analysis.
- `README.md` — Project documentation.

## How to Run

1. Download or clone this repository.
2. Install the required Python libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn` and `xgboost`.
3. Open `credit_default_analysis.ipynb` in Jupyter Notebook or Google Colab.
4. Ensure `credit_default_dataset_cleaned.csv` is available in the notebook's working directory.
5. Execute the notebook cells in order.

## Conclusion

The project demonstrates that relatively simple statistical models can remain competitive with more complex Machine Learning algorithms in credit risk prediction.

In particular, Logistic Regression showed strong predictive performance and greater stability across the countries examined, highlighting the importance of model generalization in financial risk management.
