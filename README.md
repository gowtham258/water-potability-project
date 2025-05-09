# water-potability-project
creating interactive dashboards and visualitions 
Project Title

Water Potability Analysis & Dashboard

Introduction

This project performs a comprehensive Exploratory Data Analysis (EDA) on water quality parameters to determine factors affecting water potability. It includes data cleaning, statistical testing, and interactive visualizations to help stakeholders understand which factors (like pH, hardness, solids, etc.) most strongly correlate with safe drinking water.

Project Type

Fullstack (Data Processing + Visualization App)

Deployed App

Frontend (Streamlit): https://drive.google.com/drive/folders/1LjRzJDlSS23pdAw_0m5Li68q45Udnvss?usp=sharing

Backend (SQL Database): https://drive.google.com/file/d/1i04HyvuiUxEnInTyYs_yV6Wdy6fWjexi/view?usp=sharing

Directory Structure

water-potability-project/
├─ data/                    # raw and cleaned CSV files
│  ├─ water_potability.csv
│  └─ water_potability_clean.csv
├─ backend/                 # SQL scripts and ETL code
│  ├─ create_tables.sql
│  └─ load_data.py
├─ frontend/                # Streamlit app
│  ├─ app.py
│  └─ requirements.txt
└─ README.md

Video Walkthrough of the Project

https://drive.google.com/file/d/1yuzsnhqUtlvqAZP3p560CbBVmKVyOeOt/view?usp=sharing

Video Walkthrough of the Codebase

https://drive.google.com/file/d/1qXU3vY62UGjyA9zGhwYTE-3luivK2kjC/view?usp=sharing

Features

Data Cleaning: Median imputation for missing values, duplicate removal, optional outlier filtering.

EDA Visualizations: Histograms, KDE plots, correlation heatmaps, boxplots.

Statistical Analysis: Pearson correlations, hypothesis testing (t‑tests) between potable and non‑potable samples.

Interactive Dashboard: Select parameters, view distribution comparisons, and correlation metrics.

SQL Integration: Cleaned data is loaded into a SQL database for querying and reporting.

Design Decisions & Assumptions

Median Imputation: Chosen for robustness against outliers in water-quality metrics.

IQR Outlier Removal (Optional): To focus on typical ranges, extremes are filtered based on the 1.5×IQR rule.

Streamlit Frontend: Provides rapid development and interactive filtering capabilities.

No Time/Region Data: Trend analyses focus on parameter correlations in absence of temporal or spatial metadata.

Installation & Getting Started

Set up a virtual environment

python3 -m venv venv
source venv/bin/activate

Install dependencies

pip install -r frontend/requirements.txt
pip install pandas numpy scipy matplotlib seaborn scikit-learn sqlalchemy

Database Setup (PostgreSQL / MySQL)

# create_tables.sql contains DDL
psql -U user -d waterdb -f backend/create_tables.sql
python backend/load_data.py --db-url postgresql://user:pass@host:port/waterdb

Run the dashboard

streamlit run frontend/app.py

Usage

View overall distributions of each water-quality parameter.

Select a feature to compare potable vs. non-potable histograms.

Inspect correlation metrics in bar charts and heatmaps.

Run hypothesis tests to evaluate statistical significance of differences.

Credentials

APIs Used

No external APIs are required; all analysis is performed on local CSV and SQL data.

API Endpoints

(If you extended this with a REST backend)

GET  /api/potability       # returns potability statistics
GET  /api/features         # returns feature distributions
POST /api/hypothesis       # runs t-test for specified feature

Technology Stack

Python: pandas, numpy, scipy, scikit-learn

Visualization: Matplotlib, Seaborn, Streamlit

Database: PostgreSQL / MySQL (via SQLAlchemy)

Dev Tools: Git, Docker (optional containerization)

