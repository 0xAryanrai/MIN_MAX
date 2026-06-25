# Customer Segmentation – Data Preprocessing for K-Means Clustering

This notebook works with a customer dataset (`Assessment-III.csv`) to clean, explore, and prepare the data for K-Means clustering. It covers exploratory data analysis, missing value imputation, and feature scaling.

## Dataset

`Assessment-III.csv` contains the following customer attributes:

| Column | Description |
|---|---|
| `customer_id` | Unique identifier for each customer |
| `age` | Customer age |
| `annual_income_usd` | Annual income in USD |
| `spending_score` | Spending score |
| `website_visits_per_month` | Number of website visits per month |
| `avg_purchase_value_usd` | Average purchase value in USD |
| `days_since_last_purchase` | Days since the customer's last purchase |

## What This Notebook Does

1. **Load data** – Reads the CSV into a pandas DataFrame.
2. **Initial inspection** – `df.head()` and `df.isnull().sum()` to preview the data and check for missing values.
3. **Exploratory Data Analysis (EDA)**
   - `sns.pairplot()` to visualize relationships between all numeric features.
   - KDE plots for `age`, `annual_income_usd`, `website_visits_per_month`, `avg_purchase_value_usd`, and `days_since_last_purchase` to inspect distribution shape (skewed vs. normal).
   - A histogram of `age`.
4. **Missing value imputation** – Based on the distribution shape observed in EDA:
   - **Median** imputation for skewed features: `age`, `annual_income_usd`, `avg_purchase_value_usd`.
   - **Mean** imputation for normally distributed features: `website_visits_per_month`, `days_since_last_purchase`.
5. **Feature scaling** – A custom `min_max()` function rescales `age`, `annual_income_usd`, `spending_score`, `website_visits_per_month`, `avg_purchase_value_usd`, and `days_since_last_purchase` to a [0, 1] range.

## Status

⚠️ This notebook currently covers **EDA and preprocessing only**. The final cell stubs out a `k_mean()` function, but the K-Means clustering implementation itself (choosing K, fitting the model, assigning/interpreting clusters) is **not yet written**.

## Requirements

```
numpy
pandas
seaborn
matplotlib
```

## How to Run

1. Place `Assessment-III.csv` in the same directory as the notebook.
2. Install dependencies: `pip install numpy pandas seaborn matplotlib`
3. Run the cells in order (top to bottom).

## Next Steps

- Implement K-Means clustering on the scaled features (e.g., using `sklearn.cluster.KMeans`).
- Use the elbow method or silhouette score to choose an appropriate number of clusters (K).
- Visualize and interpret the resulting customer segments.
