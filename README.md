# Data Science Project: Web3 Trading Analysis

## Project Overview
This project analyzes the relationship between trader behavior and market sentiment using two key datasets:
1. **Bitcoin Market Sentiment Dataset** – Contains `Date` and `Classification` (Fear / Greed).
2. **Historical Trader Data from Hyperliquid** – Contains trader transactions, including `Account`, `Coin`, `Execution Price`, `Size`, `Side`, `Closed PnL`, `Leverage`, and other related fields.

The main objective is to understand how trading behavior (profitability, risk, volume, leverage) aligns with overall market sentiment and identify actionable insights for smarter trading strategies.

## Directory Structure
```
ds_<candidate_name>/
├── notebook_1.ipynb        # Main analysis and modeling notebook
├── notebook_2.ipynb        # Optional additional notebook (if any)
├── csv_files/              # Processed datasets
│   └── merged_data.csv
├── outputs/                # Visualizations and charts
│   └── *.png / *.jpg
├── ds_report.docx          # Detailed project report
└── README.md               # This file
```

## Setup Instructions
1. Clone or download the repository.
2. Open `notebook_1.ipynb` in Google Colab or Jupyter Notebook.
3. Ensure all required libraries are installed:
```bash
pip install pandas numpy matplotlib seaborn scikit-learn python-docx
```
4. Run each cell sequentially.

## Key Steps in the Project
1. **Data Preprocessing:**
   - Merged market sentiment and trader datasets.
   - Handled missing values.
   - Detected and imputed outliers using median values.
   - Encoded categorical features using one-hot encoding or label encoding.

2. **Exploratory Data Analysis (EDA) & Visualization:**
   - Identified key trends and patterns in trading data.
   - Visualized distributions of numerical and categorical variables.
   - Plotted relationships between trader behavior and market sentiment.

3. **Feature Engineering & Selection:**
   - Created relevant features for model training.
   - Dropped columns that could cause data leakage (e.g., `value`).

4. **Model Development:**
   - Train-test split.
   - Standardization of continuous numerical features (excluding Boolean and categorical columns).
   - Trained multiple models: Logistic Regression, Decision Tree Classifier (DTC), Random Forest Classifier (RFC).
   - Evaluated models using accuracy, precision, recall, F1-score, and confusion matrix.

5. **Insights & Observations:**
   - Logistic Regression performed poorly due to low linear separability.
   - Decision Tree and Random Forest achieved higher accuracies (~0.91), making them better choices.
   - Features like `Order ID`, `Size USD`, and trade directions were influential in predicting market sentiment.

## Conclusion
Based on the analysis:
- **Decision Tree Classifier** and **Random Forest Classifier** are recommended for predicting market sentiment due to high accuracy and ability to handle non-linear relationships.
- Standardization is necessary only for continuous numerical features.
- Categorical features with a large number of unique values (like `Coin`) can be dropped to simplify the model or encoded with caution.
- Visualizations and EDA provide insights into trading behavior, highlighting which features have more influence on market sentiment.

## Notes
- All code is executed in Google Colab, and all figures are saved in the `outputs` folder.
- The merged dataset is saved in `csv_files/merged_data.csv`.
- Detailed report is provided in `ds_report.docx`.

