# Project Alpha: Market Event & Equities Algorithmic Pipeline

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![SQL](https://img.shields.io/badge/SQL-Advanced-orange.svg)
![Machine Learning](https://img.shields.io/badge/Scikit--Learn-Model-yellow.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-Serving-green.svg)

## 📌 Overview
Project Alpha is an automated, end-to-end data pipeline designed to ingest, store, transform, and analyze financial market data. This project bridges the gap between raw data engineering and predictive analytics by extracting daily stock market data and financial news, engineering technical indicators and sentiment scores via SQL and Python, and serving predictive insights on asset volatility through a local API.

## 🏗️ Architecture & Data Flow
The pipeline is orchestrated to flow through four distinct phases:
1. **Ingestion:** Programmatic extraction of OHLCV (Open, High, Low, Close, Volume) data and news headlines using financial APIs.
2. **Storage & Transformation (ELT):** Raw data is loaded into a relational database. Advanced transformations, including rolling averages and window functions, are executed natively in SQL.
3. **Feature Engineering & Modeling:** Refined data is pulled into Python to calculate complex risk metrics (e.g., Sharpe Ratio) and train a classification model to predict daily price action.
4. **Serving Layer:** A FastAPI web server exposes an endpoint to serve "Buy/Sell/Hold" signals and current asset statistics to end-users.

```
financial_analytics_pipeline/
│
├── data/                  # Local storage for raw backups (CSVs)
├── database/              # Relational database files/scripts
├── sql_queries/           # Modular SQL scripts for transformations/views
├── notebooks/             # Scratchpad for exploratory data analysis (EDA)
├── src/                   # Main source code module
│   ├── ingestion.py       # API calls to market and news endpoints
│   ├── database_ops.py    # Python functions to execute SQL scripts 
│   ├── features.py        # Financial math and NLP sentiment calculations 
│   ├── modeling.py        # Training and backtesting the predictive model
│   └── api.py             # FastAPI server deployment
│
├── requirements.txt       # Project dependencies
└── main.py                # Main orchestration script
```

## 🚀 Quick Start & Installation

### 1. Clone the repository
```
bash
git clone https://github.com/yourusername/financial_analytics_pipeline.git
cd financial_analytics_pipeline
```

### 2. Set up a virtual environment
```
bash
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
pip install -r requirements.txt
```

### 3. Environment Variables
Create a `.env` file in the root directory and add your API keys:
```
ALPHA_VANTAGE_API_KEY=your_api_key_here
FINANCIAL_NEWS_API_KEY=your_api_key_here
DB_CONNECTION_STRING=sqlite:///database/market_data.db
```
### 4. Run the Pipeline
To execute the daily data pull, run the transformations, and update the model:
```
python main.py --update
```

To start the API server locally:
```
bash
uvicorn src.api:app --reload
```

## 📊 Core Technologies & Skills Demonstrated
* **Languages:** Python (Pandas, NumPy), SQL (DDL, DML, Window Functions, CTEs).
* **Data Engineering:** API Integration, ETL/ELT workflows, Relational Database Design.
* **Analytics & Math:** Time-series analysis, NLP sentiment scoring, Risk-adjusted return calculations (Sharpe Ratio).
* **Machine Learning:** Scikit-learn (Classification, Time-Series Cross-Validation).

## 👤 About the Author
**Tajinder Sharma** *Data Analyst | Analytics Engineer* Leveraging a foundational background in Computer Science and modern Data Analytics to build scalable data infrastructure and extract actionable business insights. Currently exploring opportunities in the Dallas, TX area.
* [LinkedIn](https://www.linkedin.com/in/tajsharma5/)


## 🔮 Future Enhancements
* Migrate orchestration from a standard Python script to **Apache Airflow**.
* Refactor SQL transformations using **dbt (Data Build Tool)** for improved modularity and testing.
* Migrate local database to a cloud data warehouse (e.g., Snowflake or BigQuery).
