# Amazon Clothing Sales — EDA & Insights (2024–2025)

**Exploratory Data Analysis of Amazon clothing sales (2024–2025) to identify patterns in pricing, returns, delivery, and customer behavior.**
Dataset: 25,000+ purchase-level records collected from publicly available Amazon product listings and seller pages (scraped ethically, no PII included).


## Table of contents

* [Project overview](#project-overview)
* [Repository structure](#repository-structure)
* [Reproducibility (clone & run)](#reproducibility-clone--run)
* [About the data](#about-the-data)
* [Data quality & cleaning](#data-quality--cleaning)
* [Feature engineering](#feature-engineering)
* [Key findings](#key-findings)
* [Hypotheses & results](#hypotheses--results)
* [Requirements](#requirements)
* [Next steps](#next-steps)
* [Contact](#contact)


## Project overview

This repository contains an end-to-end EDA of Amazon clothing sales across 2024–2025.
The project focuses on converting raw transactional data into **actionable insights** that can inform:

* **Pricing strategy** — understanding discount effectiveness and price sensitivity
* **Operational efficiency** — delivery times, returns, and payment method patterns
* **Customer behavior** — regional preferences, age group patterns, and repeat buyers
* **Revenue drivers** — identifying top categories, brands, and customer segments

By combining data cleaning, feature engineering, visualization, and hypothesis testing, the notebook provides a structured workflow from raw CSVs to business recommendations.


## Repository structure

```
Amazon Sales Analysis/
├─ Data/
│  ├─ Raw_Data.csv
│  └─ Cleaned_Data.csv
├─ NoteBook/
│  └─ Amazon Clothing Sales Analysis.ipynb
├─ requirements.txt
└─ README.md
```


## Reproducibility (clone & run)

To replicate the analysis locally:

```bash
git clone https://github.com/MutafAkram223/Amazon-Clothing-Sales-2025-Analysis.git
cd "Amazon Sales Analysis"

python -m venv venv
source venv/bin/activate   # macOS/Linux
venv\Scripts\Activate.ps1  # Windows

pip install -r requirements.txt
jupyter notebook "NoteBook/Amazon Clothing Sales Analysis.ipynb"
```

Run all cells top-to-bottom. If you only want results, skip directly to the *Findings & Hypotheses* sections inside the notebook.


## About the data

* **Volume:** \~25,000 purchase-level transactions
* **Scope:** Clothing purchases across Men, Women, Kids, and Baby categories
* **Key attributes (sample):** price, discount, final price, payment method, review rating, delivery days, return flag, region, customer demographics
* **Ethics:** Scraped from public listings, aggregated at transaction level, with no personally identifiable information (PII).


## Data quality & cleaning

* **Missing values (\~5%)**: handled via imputation

  * Numerical → mean
  * Categorical → mode
* **Duplicates:** none found after integrity checks
* **Price/discount inconsistencies:** \~300 rows corrected or flagged
* **Outliers:** clipped conservatively (e.g., unrealistic delivery days)
* **Documentation:** all rules, thresholds, and corrections logged in notebook


## Feature engineering

Several new fields were created to enable richer analysis:

* **Order attributes** — month, year, weekday
* **Discount metrics** — discount amount, unit price
* **Delivery performance** — fast vs slow (≤3 days threshold)
* **Customer-level aggregates** — total spend, total orders, average rating given, return rate

These engineered variables were critical in identifying **seasonality, pricing sensitivity, and customer behavior** patterns.


## Key findings

> All supported by charts/tables inside the notebook.

1. **Seasonality:** Sales volume lowest in February, peaking in March.
2. **Revenue drivers:** Kids category and Nike are the strongest contributors to revenue.
3. **Discount paradox:** Deep discounts (25%+) increase quantity but reduce average revenue, highlighting margin concerns.
4. **Returns:** Zara experiences higher returns; gift card payments have the highest return rates; male customers slightly more likely to return items.
5. **Regional differences:** North East has the highest Average Order Value (AOV); Midwest faces elevated return rates.
6. **Delivery patterns:** Average delivery \~5 days. Returns spike around 5 days delivery time, while customer ratings show no clear decline with longer delivery.
7. **Price sensitivity:** Weak linear correlation between discounts and units sold — category-specific effects dominate.


## Hypotheses & results

1. **Higher discounts → higher sales & returns**
   *Not supported overall.* Weak correlation with sales/returns at aggregate level.

2. **Longer delivery times → lower ratings & higher returns**
   *Partially supported.* Returns increase up to \~5 days, but ratings remain stable.

3. **Region impacts return behavior**
   *Supported.* Midwest shows higher return rates, North East lower.

4. **Certain age groups spend more (AOV)**
   *Supported.* 18–24 year olds recorded the highest average order values.

5. **Premium brands → lower return rates**
   *Not supported.* Return rates did not significantly differ between premium and non-premium brands.


## Requirements

Minimal dependencies used for analysis:

```
pandas
numpy
matplotlib
seaborn
scipy
statsmodels
jupyter
```

For strict reproducibility, pin versions via `pip freeze > requirements.txt`.


## Next steps

* **Profitability modeling** — simulate discount impacts on profit margins.
* **Returns management** — investigate Midwest and gift card–related returns.
* **Retention strategy** — target campaigns to one-time buyers with tailored offers.
* **Discount optimization** — evaluate category- or brand-specific thresholds for discounting.


## Contact

* **Author:** Mutaf Akram
* **LinkedIn:** [linkedin.com/in/mutafakram](https://www.linkedin.com/in/mutafakram/)
  

nto a 1–2 page README** (just essentials for recruiters/managers), or keep it this medium-detailed version (balanced for both recruiters + technical peers)?
