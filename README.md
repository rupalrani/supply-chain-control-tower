# 📦 Supply Chain Control Tower Dashboard

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)

> Supply chains fail customers most visibly when deliveries arrive late. This project builds a control tower dashboard that turns raw order and shipment data into a single, clear view of delivery performance — using the DataCo Smart Supply Chain dataset (180,519 orders, 5 global markets).

---

## ⚠️ Current Status

This project is a **complete, working research framework** — not yet a full-dataset result. Here's exactly what that means:

| Component | Status |
|-----------|--------|
| Research design, methodology, KPI definitions | ✅ Complete |
| Literature review (22 PRISMA-tracked sources, all verified; 69 total citations in the full paper) | ✅ Complete |
| Excel formula engine (KPIs, Pareto, control limits) | ✅ Built and tested |
| Formula engine validated on illustrative sample (24 orders) | ✅ Done |
| **Full DataCo dataset (180,519 orders) run** | ⏳ Not yet executed |
| **Predictive model (logistic regression) evaluated on real data** | ⏳ Not yet executed |

The companion workbook and report are explicit about this throughout — KPI cells are formula-linked so that running the full DataCo extract through the same pipeline updates every result automatically. The 24-row sample exists to prove the formula logic works, not to claim a finished result. The honest next step is documented in the report's own "Further Work" section: pull the full Mendeley/Kaggle extract, run the cleaning protocol, and let the engine recompute on real numbers.

---

## 📌 Overview

The project asks: **what drives late delivery, and can high-risk orders be flagged before dispatch?** It works through four analytical layers — descriptive KPIs, diagnostic segmentation (Pareto + control limits), a baseline predictive classifier, and a five-view Power BI/Tableau dashboard — all grounded in a literature review spanning the bullwhip effect, supply chain visibility, control tower architecture, and India's national logistics policy context.

A key methodological decision worth highlighting: the DataCo dataset ships with a pre-computed "late delivery risk" flag. This project deliberately **excludes that flag as a model feature**, since it appears to be derived from the same fields used to define the prediction target — using it would cause target leakage and produce inflated, meaningless accuracy. This kind of leakage check is exactly the sort of thing that separates a real analysis from a naively-built one.

---

## 🔍 Methodology

```
1. Data Cleaning & Star Schema
   └── Parse dates, derive delay (actual − scheduled), build OTIF flag, separate cancellations

2. Descriptive Layer
   ├── Headline KPIs: OTIF rate, late delivery rate, order cycle time, fill rate, perfect order proxy
   └── Breakdown by region, category, shipping mode, customer segment

3. Diagnostic Layer
   ├── Pareto analysis — isolates the few drivers behind most late orders
   └── Statistical process control limits — separates true exceptions from normal variation

4. Predictive Layer
   ├── Baseline logistic regression: shipping mode, market, category, scheduled days, order value
   ├── Provided "late delivery risk" flag explicitly excluded (target leakage control)
   └── Target: precision > 0.70, recall > 0.65 on held-out test set (not yet evaluated on full data)

5. Dashboard (Power BI / Tableau)
   └── Five linked views: Executive Overview, Regional Performance, Category Performance,
       Exception Monitor, Predictive Risk
```

---

## 📁 Repository Structure

```
supply-chain-control-tower/
│
├── README.md
├── LICENSE
│
├── workbook/
│   └── Project1_Research_Workbook.xlsx   # 12-sheet workbook: search log, PRISMA, formula
│                                          # engine (illustrative sample), references
│
├── report/
│   ├── Supply_Chain_Control_Tower_Research_Package.docx  # Full paper (~11,800 words):
│   │                                                       # abstract, 10-part lit review,
│   │                                                       # methodology, results, limitations,
│   │                                                       # 69-source APA 7 reference list,
│   │                                                       # publication upgrade plan
│   └── Project1_Supply_Chain_Control_Tower.docx          # Condensed interview-prep version
│
└── data/raw/
    └── README.md                          # Dataset sourcing instructions
```

---

## 🗃️ Data Source

This project uses the **DataCo Smart Supply Chain Dataset** (Constante, Silva & Pereira, 2019):

🔗 **Kaggle:** [DataCo SMART Supply Chain for Big Data Analysis](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)
🔗 **Mendeley Data (original, DOI-citable, no login required):** [10.17632/8gx2fvg2k6.5](https://data.mendeley.com/datasets/8gx2fvg2k6/5)

180,519 order/shipment records, 53 fields, covering 5 global markets (LATAM, Europe, Pacific Asia, USCA, Africa).

---

## 📐 KPI Formula Library

A sample of the Excel formula engine already built and tested in the workbook:

| KPI | Formula Logic |
|-----|---------------|
| Late delivery rate | `Late orders / Delivered base` |
| OTIF rate | `Orders meeting both on-time AND in-full / Total delivered` |
| Average delay (days) | `AVERAGE(real days − scheduled days)` across delivered orders |
| Fill rate | `Quantity delivered / Quantity ordered` |
| Sales at risk | `SUMIF(status = "Late delivery", sales)` |

---

## 📚 Literature Review Highlights

The review spans global, national (India), state, and local evidence levels:

- **Established evidence:** information distortion produces the bullwhip effect (Lee, Padmanabhan & Whang, 1997); visibility supports supply chain agility (Barratt & Oke, 2007; Brusset, 2016)
- **National context:** India's National Logistics Policy targets cutting logistics cost from ~13–14% to 7.5–8% of GDP (DPIIT, 2022); India rose from rank 54 to rank 38 on the World Bank Logistics Performance Index between 2014 and 2023
- **Methodology grounding:** control tower architecture (Trzuskawska-Grzesinska, 2017), dashboard design principles (Few, 2013), target leakage avoidance (Hazen, Boone, Ezell & Jones-Farmer, 2014)

Full reference list (69 sources, APA 7) in `report/Supply_Chain_Control_Tower_Research_Package.docx`.

---

## ⚠️ Limitations

1. **Historic data** — DataCo covers 2015–2018; any "real-time" framing should be understood as near-real-time on a refreshed extract, not a live feed
2. **Provided risk label excluded** from modelling to avoid target leakage — this is a deliberate methodological choice, not an oversight
3. **Illustrative sample only** — current workbook results (41% late delivery rate, 54.5% OTIF on a 24-order sample) are formula demonstrations, not full-dataset findings
4. **Cost proxies** — "sales at risk" approximates but does not equal actual financial cost of delay

---

## 🚀 Next Steps (Documented in the Report)

1. Pull the full 180,519-row DataCo extract from Mendeley
2. Run the 12-step cleaning protocol already logged in the workbook
3. Let the formula engine recompute all KPIs automatically on real data
4. Train and evaluate the logistic regression classifier on a proper train/test split
5. Build the Power BI dashboard on the real, cleaned dataset

---

## 👩‍💻 About

**Project 1 of 5** in a data analytics portfolio built during BSc Analytics & Sustainability Studies at TISS Mumbai. Methodology mirrors the MIS dashboard and data-cleaning work done during the Aajeevika Bureau internship.

📫 [rupalrani2303@gmail.com](mailto:rupalrani2303@gmail.com) · [LinkedIn](https://www.linkedin.com/in/rupal-rani-a23b36257) · [GitHub](https://github.com/rupalrani)
