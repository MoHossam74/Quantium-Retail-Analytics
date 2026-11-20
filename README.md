# Quantium Retail Customer Analytics

> Customer segmentation and store-trial uplift testing on 12 months of chip-category transaction data (Jul 2018 - Jun 2019).

## 📋 Project Overview
The project is split into two main tasks, plus a final report for the Category Manager:

**Task 1: Data Preparation and Customer Analytics**
* Cleaned and merged transaction and customer datasets (264,836 -> 249,667 transaction lines)
* Performed exploratory data analysis (EDA) on chip category sales
* Segmented customers by life stage and premium / mainstream / budget classification
* Identified purchasing behaviour trends across customer segments to support category strategy recommendations

**Task 2: Experimentation and Uplift Testing**
* Selected control stores comparable to trial stores (77, 86, 88) using correlation and magnitude-distance metrics
* Assessed the impact of the store trial on sales performance
* Compared trial vs. control store metrics (total sales, customer numbers, transactions) over the trial period
* Drew conclusions on whether the trial layout drove measurable uplift, including robustness and placebo checks

**Task 3: Business Report**
* 11-slide presentation and Excel workbook for a non-technical Category Manager, using the Pyramid Principle (answer first)

## 🛠️ Tech Stack
* **Python** (pandas, numpy, matplotlib, seaborn) for data cleaning, EDA and visualization
* **SciPy** for t-tests and confidence intervals
* **Jupyter Notebook** for the analysis walkthrough
* **openpyxl / pptxgenjs** to build the Excel workbook and PowerPoint deck

## 📁 Project Structure
```
├── data/
│   ├── raw/                # QVI_transaction_data.xlsx, QVI_purchase_behaviour.csv
│   └── processed/          # results.json and result tables
├── notebooks/              # quantium_retail_analytics.ipynb (Task 1 & Task 2)
├── images/                 # charts exported from the notebook
├── reports/
│   ├── QVI_Category_Manager_Presentation.pptx   # 11-slide business presentation
│   └── QVI_supporting_analysis.xlsx             # KPIs, segments, products, store & statistical tests
├── src/                    # scripts that build the workbook and deck
├── requirements.txt
└── README.md
```

## 📊 Key Findings
**Customers and products**
* Sales are steady at about $150K a month, so growth must come from frequency and mix, not seasonality.
* Families are 26% of customers but 35% of sales (about 9 packs each vs 4.5 for young singles/couples).
* Mainstream Young Singles/Couples is the largest customer group (7,930) and buys least often, yet pays the most per pack ($4.06 vs $3.69, statistically significant). One extra pack per customer is worth about $32K (1.8% of sales), as simple arithmetic rather than a forecast.
* Kettle is 21% of sales; revenue leaders are 330-380g bags.

**Store trial**
* Matched each trial store to a control using pre-trial correlation and size similarity on sales, customers and transactions, then scaled controls to the trial store's size.
* Trial stores beat their controls (sales +27.5%, +11.2%, +14.2% for stores 77, 86, 88), but the result is **not statistically conclusive**: no whole-period test reached p < 0.05.
* A placebo test on 60 untouched stores showed that 23% produce at least one "significant" month by chance, and store 77's result flips with a different control.
* Conclusion: promising, not proven. Extend the trial (more stores, 6+ months) before rollout; store 86 is the strongest candidate.

## 🎯 Skills Demonstrated
* Data wrangling and cleaning with Python
* Exploratory data analysis and customer segmentation
* A/B-style experimental design (trial vs. control store selection)
* Statistical significance testing (t-tests, confidence intervals) and robustness checks
* Translating data findings into commercial recommendations for a non-technical audience

## 📄 Report
The business presentation (`reports/QVI_Category_Manager_Presentation.pptx`)  cover the full analysis, methodology and recommendations.



## ⚠️ Assumptions
Trial stores (77, 86, 88) and trial dates (Feb-Apr 2019) come from the project brief, not from the data files. Analysis uses revenue only (no margin data).

## Acknowledgements
Task structure and business context are provided by Quantium's virtual internship. Dataset is from that programme.
