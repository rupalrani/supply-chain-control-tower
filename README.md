# 📦 Supply Chain Control Tower Dashboard

> End-to-end supply chain analytics platform with late-delivery prediction (AUC 0.81) across 180,519 orders in 5 global markets — backed by a 12,000-word research report and 72-source APA 7 bibliography.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

---

## 📌 Overview

This project builds a full **Supply Chain Control Tower** using the DataCo Smart Supply Chain dataset — a real-world logistics dataset capturing order flows across Europe, Latin America, Pacific Asia, USCA, and Africa.

The project spans the complete analytics lifecycle: raw data ingestion → SQL-based cleaning → Python EDA → machine learning → Power BI dashboard. A complementary academic paper (~12,000 words) documents findings in publication-ready format with 72 APA 7 references.

---

## 🏆 Key Results

| Metric | Value |
|--------|-------|
| Dataset size | 180,519 orders across 5 global markets |
| Late-delivery prediction AUC | **0.81** (best model) |
| Feature importance (top predictor) | Shipping mode + order region |
| Report length | ~12,000 words |
| References | 72 (APA 7 format) |
| Excel workbook | 12 analytical sheets |

---

## 🔍 Methodology

```
1. Data Ingestion & SQL Cleaning
   └── Standardised 180K+ records; handled nulls, duplicates, type mismatches

2. Exploratory Data Analysis (Python)
   ├── Order-to-delivery timeline analysis by market & product category
   ├── Revenue trends and geographic distribution
   └── Late-delivery rate decomposition by region, mode, and SKU

3. Predictive Modelling
   ├── Features: shipping mode, region, product category, order volume, lead time
   ├── Models tested: Logistic Regression, Random Forest, XGBoost
   └── Best model: AUC 0.81 (XGBoost)

4. Dashboard & Reporting
   ├── Interactive Power BI Control Tower dashboard
   ├── 12-sheet Excel research workbook
   └── Academic report (~12,000 words, 72 APA 7 references)
```

---

## 📁 Repository Structure

```
supply-chain-control-tower/
│
├── README.md
├── requirements.txt
│
├── scripts/
│   ├── 01_data_cleaning.py          # ETL and data standardisation
│   ├── 02_eda.py                    # Exploratory data analysis
│   ├── 03_predictive_model.py       # ML pipeline (feature engineering → model → evaluation)
│   └── sql_queries.sql              # MySQL queries for data extraction and aggregation
│
├── data/
│   └── README.md                    # Data source info and download instructions
│
└── outputs/
    └── README.md                    # Dashboard screenshots and key visualisations
```

---

## 🚀 Getting Started

### Prerequisites
```bash
pip install -r requirements.txt
```

### Data
This project uses the **DataCo Smart Supply Chain Dataset** (Fabian Constante, Fernando Silva & António Pereira, Instituto Politécnico de Leiria):

🔗 **Kaggle:** [DataCo SMART Supply Chain for Big Data Analysis](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)  
🔗 **Mendeley Data (no login required):** [DataCo Supply Chain Dataset — Mendeley](https://data.mendeley.com/datasets/8gx2fvg2k6/5)

Download `DataCoSupplyChainDataset.csv` and place it in the `data/` folder.

### Run the Analysis
```bash
# Step 1: Clean and prepare data
python scripts/01_data_cleaning.py

# Step 2: Exploratory analysis
python scripts/02_eda.py

# Step 3: Train and evaluate predictive model
python scripts/03_predictive_model.py
```

---

## 📊 Outputs

- **Power BI Dashboard** — Interactive control tower with KPI cards, delivery heatmaps, and regional drilldowns
- **Research Report** — ~12,000-word academic paper with literature review, methodology, and policy implications
- **Excel Workbook** — 12-sheet structured workbook covering data profile, EDA, model summary, and reference analysis

---

## 🗃️ Data Source

| Source | Description |
|--------|-------------|
| DataCo Smart Supply Chain Dataset (Mendeley / Kaggle) | 180,519 order records; 53 features; clothing, sports & electronics across 5 global markets |

---

## 👩‍💻 About

Developed as **Portfolio Project 1** — part of an end-to-end analytics portfolio built during BS Analytics & Sustainability Studies at TISS Mumbai.

📫 [rupalrani2303@gmail.com](mailto:rupalrani2303@gmail.com) · [LinkedIn](https://www.linkedin.com/in/rupal-rani-a23b36257) · [GitHub](https://github.com/rupalrani)
