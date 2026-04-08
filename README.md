# Identify Customer Segments

An unsupervised learning project that applies PCA and KMeans clustering to German demographics data to identify customer segments for a mail-order company.

## Project Overview

This project analyzes demographics data for the general population of Germany alongside demographics data for customers of a mail-order company. Using unsupervised learning techniques, the goal is to identify segments of the population that best describe the core customer base, enabling more efficient targeting of marketing campaigns.

## Dataset

- **Udacity_AZDIAS_Subset.csv** — Demographics data for the general population of Germany (891,221 rows × 85 features)
- **Udacity_CUSTOMERS_Subset.csv** — Demographics data for customers of a mail-order company (191,652 rows × 85 features)
- **AZDIAS_Feature_Summary.csv** — Summary of feature attributes including type and missing value codes
- **Data_Dictionary.md** — Detailed descriptions of features and their values

## Methods

1. **Data Preprocessing** — Missing value re-encoding, column/row removal based on missing data thresholds, categorical re-encoding, and mixed-type feature engineering
2. **Feature Transformation** — Imputation (median), standardization (StandardScaler), and dimensionality reduction (PCA)
3. **Clustering** — KMeans clustering with elbow method for selecting the number of clusters
4. **Comparison** — Applying the same pipeline to customer data and comparing cluster distributions

## Key Results

- **Data Cleaning**: 6 columns with >20% missing data were dropped; 13 multi-level categorical features removed; ~111K rows with >10 missing values excluded. Final cleaned dataset: 780,153 rows × 64 features.
- **PCA**: 25 principal components selected, capturing 84.2% of total variance.
- **KMeans**: 10 clusters chosen via elbow method analysis.
- **Customer Segments**:
  - **Overrepresented** (target customers): Cluster 8 dominates — 49% of customers vs. 16% of the general population (ratio 2.99×). Clusters 9 (4.74× ratio) and 2 (1.65× ratio) are also overrepresented.
  - **Underrepresented** (unlikely customers): Clusters 7 (0.10× ratio), 5 (0.11× ratio), and 6 (0.15× ratio) are the least represented among customers.

## Requirements

- Python 3.13+
- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn
- jupyter

Install dependencies:

```bash
pip install -r requirements.txt
```

## Usage

```bash
jupyter notebook Identify_Customer_Segments.ipynb
```