# MTN_Nigeria_Customer_Churn_Analysis
A data-driven investigation into customer churn across MTN Nigeria's subscriber base in Q1 2025. Using a three-stage pipeline of SQL, Python, and Power BI, this project identifies the primary drivers of churn, quantifies the revenue impact, builds a churn prediction model, and delivers actionable retention recommendations.

**Key finding: 29.16% churn rate has cost ₦58M in lost revenue —
with ₦83M more at risk from 493 medium-risk active customers.**

## Dataset Overview
| Field | Detail |
|---|---|
| **Records** | 974 customer entries |
| **States** | 36 Nigerian states including FCT |
| **Period** | Q1 2025 |
| **Device Types** | Mobile SIM Card, Broadband MiFi, 4G Router, 5G Broadband Router |
| **Source** | MTN Nigeria Customer Churn Dataset (Kaggle — synthetic) |

## Key Columns in the Dataset
| Column | Description |
|---|---|
| **Customer_ID** | Unique customer identifier |
| **MTN_Device** | Device type purchased |
| **Subscription_Plan** | MTN data plan name |
| **Unit_Price** | Plan cost in Nigerian Naira |
| **Data_Usage** | Estimated data consumption in GB |
| **Number_of_Times_Purchased** | Purchase frequency within the month |
| **Total_Revenue** | Unit Price × Number of Purchases |
| **Satisfaction_Rate** | Customer satisfaction score (0–5) |
| **Customer_Tenure_in_months** | Subscription length in months |
| **Customer_Churn_Status** | Yes (churned) or No (active) |
| **Reasons_for_Churn** | Churn reason for departed customers |
| **State** | Nigerian state of residence |
| **Age** | Customer age (16–80) |
| **Gender** | Male or Female |

## Tools Used
| Tool | Purpose | Stage |
|---|---|---|
| **MySQL** | 8 analytical queries — churn rate, device, reasons, revenue, age | Stage 1 |
| **Python (pandas, seaborn, scikit-learn)** | EDA, feature engineering, churn prediction model | Stage 2 |
| **Microsoft Power BI** | DAX measures, 4-page interactive dashboard | Stage 3 |
| **DAX** | Custom KPI and risk measures | Stage 3 |

## Data Cleaning & Preparation
**SQL Stage:**
- Confirmed 29.16% overall churn rate across 974 customers
- Identified Mobile SIM Card as highest churn device at 31.23%
- Quantified ₦58M revenue lost to churn
- Ranked churn reasons — High Call Tariffs leads at 19.01%

**Python Stage:**
- Verified zero missing values in key analytical columns
- Engineered 6 new features:
  - **`Age_Group`** — 5 demographic bands
  - **`Tenure_Group`** — 5 subscription length categories
  - **`Churn_Binary` — 1/0 encoding for model training
  - **`Revenue_Per_Purchase`** — spending efficiency metric
  - **`Churn_Probability`** — ML model score per customer (0–1)
  - **`Churn_Risk_Category`** — Low / Medium / High classification
- Trained Logistic Regression and Decision Tree classifiers
- Exported enriched dataset for Power BI

## Key Questions & Analysis
1. What is the overall churn rate and how much revenue has been lost?
2. Which device types and subscription plans have the highest churn?
3. What are the primary reasons customers are leaving MTN?
4. Which states generate the most revenue and which have the most churned customers?
5. Which age group is most at risk of churning?
6. Does satisfaction rate predict churn behaviour?
7. Which active customers are most likely to churn next?
8. How much revenue is currently at risk from medium-risk customers?

## Key Insights
- **29.16% churn rate** — 284 customers lost, ₦58M revenue gone
- **₦83M more at risk** — 493 medium-risk customers identified by ML model
- **Pricing drives 37% of churn** — High Call Tariffs + Competitor Offers combined
- **200GB plan: 45.16% churn** — highest churn rate of any subscription plan
- **36-45 age group most at risk** — 36.57% churn rate, highest demographic
- **Satisfaction does not prevent churn** — 5-star customers churn at the highest rate
- **5G Router is the golden segment** — highest revenue, lowest churn probability
- **Better Offers from Competitors causes most revenue damage** — ₦14M lost

## Recommendations
1. Launch pricing competitiveness review — pricing drives 37% of all departures
2. Proactive retention campaign for 493 medium-risk customers — protect ₦83M before it is lost
3. Redesign the 200GB Broadband Plan — 45% churn rate requires structural intervention

## Limitations
The dataset is synthetically generated for educational purposes and does not represent actual MTN Nigeria customer data, meaning findings cannot be directly applied to real business decisions without validation against live records. The churn prediction model is trained on 974 records which limits its statistical robustness and generalisation capability.

## Dashboard / Visualization
The Power BI dashboard contains 4 report pages:

| Page | Focus |
|---|---|
| Customer Overview | KPIs, active vs churned donut, customers by state/device/gender/age |
| Churn Analysis | Churn rate by device/age/plan, reasons bar, satisfaction vs churn probability |
| Revenue Analysis | Revenue by state/device/plan/month, revenue lost by churn reason |
| Risk Intelligence | Churn probability by device/plan/state, risk matrix, ₦83M at risk |

## Project Structure
```text
├── data/
│   ├── mtn_customers.csv
│   └── mtn_customers_enriched.csv
├── sql/
│   └── mtn_analysis_queries.sql
├── notebooks/
│   └── mtn_churn_analysis.ipynb
├── dashboard/
│   └── mtn_churn_dashboard.pbix
├── report/
│   └── MTN_Nigeria_Churn_Analysis.pptx
├── screenshots/
│   ├── customer_overview.png
│   ├── churn_analysis.png
│   ├── revenue_analysis.png
│   └── risk_intelligence.png
└── README.md
```

## About me
Afodunrinbi Samad Akinkunmi

I am a Certified Data Analyst with a strong passion for transforming raw data into meaningful insights that support informed decision-making. My work focuses on exploring datasets, identifying patterns, and communicating findings in a clear and impactful way. I enjoy approaching problems analytically, breaking them down into structured steps, and uncovering the story behind the data. Beyond data analysis, I am actively expanding towards becoming a Data Scientist, with an interest in building predictive modeling and advanced analytics.

Data Analyst| ML | Excel | Power BI | Python | SQL | Figma

Connect With Me On - [LinkedIn](https://www.linkedin.com/in/akinkunmiafod) | [Medium](https://medium.com/@afodunrinbikunmi) | Gmail: afodunrinbikunmi@gmail.com
