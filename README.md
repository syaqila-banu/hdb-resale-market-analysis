# Singapore HDB Resale Market Analysis

My first data analytics portfolio project, exploring Singapore's HDB resale market through data cleaning, exploratory analysis, statistical comparisons, and machine learning.

## Project Overview

This project analyses resale flat transactions in Singapore to understand how flat characteristics and location relate to resale prices. It also compares two regression models to evaluate how accurately resale prices can be predicted using selected property features.

The analysis uses resale transaction data registered from January 2017 onwards and aims to turn raw data into useful market insights.

## Objectives

- Explore and clean Singapore HDB resale transaction data.
- Analyse resale price patterns across towns, flat types, floor area, storey ranges, and remaining lease.
- Examine relationships between property characteristics and resale prices.
- Build and evaluate regression models for resale price prediction.
- Compare model performance using appropriate evaluation metrics.

## Dataset

The project uses the official Singapore HDB resale flat prices dataset published on data.gov.sg, covering transactions registered from January 2017 onwards.

- **Source:** [Resale flat prices based on registration date from Jan-2017 onwards](https://data.gov.sg/datasets/d_8b84c4ee58e3cfc0ece0d773c8ca6abc/view)
- **Records analysed:** 240,807 transactions
- **Target variable:** Resale price
- **Selected predictors:** Floor area, remaining lease, storey range, flat type, and town

The dataset was cleaned and prepared before analysis. A price-per-square-metre variable was also derived for market comparisons.

## Tools and Technologies

- **Python** — Data analysis and machine learning
- **Pandas and NumPy** — Data manipulation and numerical calculations
- **Matplotlib and Seaborn** — Data visualisation
- **Scikit-learn** — Data preprocessing, regression modelling, and model evaluation
- **Jupyter Notebook in VS Code** — Analysis and documentation
- **Git and GitHub** — Version control and project hosting

## Key Findings

The exploratory and market analyses revealed several patterns in Singapore's HDB resale market:

- **Rising resale prices:** The monthly median resale price increased from approximately $405,000 in January 2017 to $640,000 in the latest period analysed, an increase of approximately 58%.
- **Floor area and resale price:** Floor area had a moderate positive correlation with resale price (approximately 0.563).
- **Remaining lease:** Remaining lease had a positive correlation with resale price (approximately 0.300) in the analysed dataset.
- **Differences across towns:** Median resale prices and prices per square metre varied across towns, reflecting differences in location and the types of flats transacted.
- **Flat type:** Resale prices differed substantially across flat types, with larger flat categories generally having higher median transaction prices.

These findings describe patterns and associations in the transaction data; they do not establish that any single factor directly causes a change in resale price.

## Machine Learning Results

Two regression models were evaluated on a held-out test set using the same five predictors and an 80:20 train-test split.

| Evaluation Metric | Multiple Linear Regression | Random Forest |
|---|---:|---:|
| Mean Absolute Error (MAE) | $94,051.74 | $47,504.78 |
| Root Mean Squared Error (RMSE) | $115,857.76 | $69,414.86 |
| R² Score | 0.6362 | 0.8694 |

The Random Forest model outperformed Multiple Linear Regression across all three evaluation metrics.

- **MAE decreased by approximately 49.5%.**
- **RMSE decreased by approximately 40.1%.**
- **R² increased from 0.6362 to 0.8694.**

Feature-importance analysis identified floor area and remaining lease as the most important individual predictors in the fitted Random Forest model.

The results suggest that Random Forest captured nonlinear patterns and interactions that the linear model may not have represented as effectively. Performance is based on the selected test set and may differ on future transactions or under changing market conditions.

## Project Structure

```text
hdb-resale-market-analysis/
├── data/
│   └── hdb_resale_cleaned.csv
├── notebooks/
│   ├── 01_hdb_data_exploration.ipynb
│   ├── 02_hdb_market_analysis.ipynb
│   └── 03_hdb_price_prediction.ipynb
└── README.md
```

### Notebook Guide

| Notebook | Description |
|---|---|
| `01_hdb_data_exploration.ipynb` | Data acquisition, cleaning, quality checks, and exploratory data analysis |
| `02_hdb_market_analysis.ipynb` | Price drivers, comparisons across towns and flat types, and Multiple Linear Regression |
| `03_hdb_price_prediction.ipynb` | Random Forest regression, model comparison, and feature-importance analysis |

## Limitations and Future Improvements

Although the project provides useful insights into HDB resale transactions, several limitations should be considered:

- **Limited predictors:** The models do not include every factor that may influence resale prices, such as proximity to MRT stations, nearby amenities, renovation condition, or broader economic conditions.
- **Random train-test split:** The evaluation does not directly measure how accurately the models would predict future transactions under changing market conditions.
- **Interpretation:** Correlations and feature-importance scores indicate patterns in the data, not causal relationships.
- **Model improvement:** Further work could explore hyperparameter tuning, cross-validation, and time-based validation.
- **Additional features:** Future versions could incorporate location-based variables and broader market indicators to improve predictive performance.

## Author

This project was developed as part of my data analytics portfolio to demonstrate practical skills in data preparation, exploratory analysis, visualisation, and machine learning.