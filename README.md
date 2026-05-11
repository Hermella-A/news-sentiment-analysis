# News Sentiment Analysis

## Setup
1. Clone the repository  
   `git clone https://github.com/Hermella-A/news-sentiment-analysis.git`
2. Create a virtual environment  
   `python -m venv venv`
3. Activate it  
   `venv\Scripts\activate` (Windows) or `source venv/bin/activate` (macOS/Linux)
4. Install dependencies  
   `pip install -r requirements.txt`
5. Download TextBlob data  
   `python -m textblob.download_corpora`

## Task 1 – Exploratory Data Analysis (EDA)
- **Notebook:** `eda_analysis.ipynb`
- **What it does:** Loads and cleans the FNSPID news dataset, analyses headline lengths, top publishers, news volume over time, and most common keywords. Includes visualisations (histograms, bar charts, time‑series plots).
- **Key findings:** Average headline length 71 characters; top publishers are Benzinga and Paul Quintaro; news spikes in 2015‑2016 and early 2020; top keywords include "alcoa", "market", "stocks".

## Task 2 – Technical Indicators & Financial Metrics
- **Notebook:** `technical_indicators.ipynb`
- **What it does:** Loads AAPL stock data (2020‑2024) and computes:
  - Simple & Exponential Moving Averages (SMA, EMA)
  - Relative Strength Index (RSI)
  - MACD (Moving Average Convergence Divergence)
  - Financial metrics: annual return, volatility, Sharpe ratio
- **Libraries used:** TA‑Lib (for indicators), PyNance (attempted), `yfinance`, `pandas`, `matplotlib`.
- **Results:** The notebook shows all indicator plots and prints financial metrics (e.g., annual return ~29.9%, volatility ~33.6%, Sharpe ratio ~0.89).

## Task 3 – Correlation between News Sentiment and Stock Returns
- **Notebook:** `correlation_analysis.ipynb`
- **What it does:** 
  - Aligns news publication dates to the next trading day.
  - Computes sentiment polarity using TextBlob.
  - Aggregates daily sentiment per stock (e.g., AA – Alcoa).
  - Calculates daily stock returns.
  - Performs Pearson correlation and visualises results with a scatter plot and a bar chart.
- **Key finding:** A weak negative correlation (≈ -0.29) that is not statistically significant (p > 0.05), indicating sentiment alone is not a reliable predictor for this stock.
- **Limitations:** Small overlapping sample, no time‑lag analysis, other confounding factors.

## Repository Structure
├── .github/workflows/ # CI/CD pipeline
├── notebooks/ # All Jupyter notebooks
├── data/raw/ # CSV files (ignored by Git)
├── src/ # Source code (future)
├── tests/ # Unit tests
├── scripts/ # Utility scripts
├── .gitignore
├── requirements.txt
└── README.md


## Branches
- `main` – complete project (all tasks)
- `task-1` – EDA notebook only
- `task-2` – technical indicators notebook only
- `task-3` – correlation analysis notebook only