# Revenue Concentration & Profitability Risk Analysis(SQL server & Power BI)

## 📌 Project Overview

This project analyzes sales, product, and customer data for a **Adventure Works a multinational bicycle manufacturing and retail company**.  
The objective of the analysis is to identify **business sustainability risks** that are not immediately visible through topline revenue metrics alone.
Operating under a **high-volume sales model**, the business generates revenue through a combination of product mix, customer demand, pricing strategy, and discounting.

Leadership raised concerns that while revenue appeared stable or growing, **underlying profitability and concentration risks** may threaten long-term performance.
**as data analyst within the organization**, this analysis focuses on uncovering those hidden risks and translating them into actionable insights.

---

## Insights and recommendations are provided on the following key areas:

- **Revenue Concentration:** Identifying dependency on a small set of products and customer segments.
- **Customer Contribution:** Understanding how revenue is distributed across customer segments rather than individual accounts.
- **Profit Erosion:** Tracking margin trends to detect declining profitability despite steady revenue.
- **Product Profitability:** Highlighting high-revenue products with weak margins that pose sustainability risks.

The SQL queries used to inspect and clean the data for this analysis can be found here [Data_quality_checks](https://github.com/praveenm024/Revenue-Concentration-and-Profit-Erosion-/blob/b8c1973d32900505bf79b7c1d0a3e591ee4878ff/01_data_quality_checks.sql)&[Data_cleaning_Prepration](https://github.com/praveenm024/Revenue-Concentration-and-Profit-Erosion-/blob/b8c1973d32900505bf79b7c1d0a3e591ee4878ff/02_data_cleaning_preparation.sql)

An interactive power bi  dashboard used to report and explore  trends can be found here [link](https://github.com/praveenm024/Revenue-Concentration-and-Profit-Erosion-/blob/164bad546b388ea40a045d81141f053ff13ba488/revenue%20concentration%20and%20profit%20erosion.pbix) 
 
---

## 🗄️ Data Structure & Initial Checks

The companies main database structure as seen below consists of Seven tables: FactInternetSales, DimProduct ,DimProductCategory,DimProductSubCategory,DimCustomers,DimGeoraphy,DimDates, with a total row count of 60398 records.

### Initial Data Validation Steps
- Verified row-level profit calculation logic  
- Ensured time-period completeness for trend analysis  
- Standardized geographic naming conventions  
- Confirmed all metrics were calculated from raw (non-aggregated) data  

📌 *Entity Relationship Diagram (ERD)*  
<img width="1032" height="807" alt="Screenshot 2026-02-08 154218" src="https://github.com/user-attachments/assets/3584ff3f-9001-4443-bcbd-df62dbcccfee" />




---

## 📊 Executive Summary

### Revenue Concentration
The Risk: 28% of customers = 80% of revenue ($23M of $29M)
Three Concentration Points:

Products: Top 10 products = 43% of revenue (Mountain bikes dominant)
Markets: US + Australia = $18.3M (63% of total)
Customers: VIP + Premium segments = $18.6M (64% of total)

Implication: Losing any top customer or market creates immediate revenue vulnerability

<img width="1204" height="682" alt="image" src="https://github.com/user-attachments/assets/f5361cd6-4174-43a1-aaa0-3e5d6478cac0" />


### Profit Erosion
Current State: $12M profit at 41% margin
The Problem: Product mix shifted to lower-margin categories in Q1 2025

Bikes: 38-45% margins (high performers)
Accessories: 23-63% margins (dragging overall margin down)

2025 recovery shows revenue outpacing costs (Q1: $0.9M → Q2: $3.8M revenue growth vs $1.4M → $2.7M cost growth)


<img width="1219" height="671" alt="image" src="https://github.com/user-attachments/assets/af3c3735-4e5b-448d-b03a-96ff903c3f1e" />



---

## 🔍 Insights Deep Dive

### 1. SEVERE PRODUCT CONCENTRATION RISK

- Top 10 products = 42.6% of total revenue ($12.4M out of $29M)
- All top 10 are Mountain Bikes (specifically models: 200 Black, 200 Silver, 150 Red variants)
- If market shifts away from mountain biking → revenue collapse
- Competitor launches better mountain bike → immediate impact

<img width="548" height="277" alt="image" src="https://github.com/user-attachments/assets/27266401-d93d-493b-9363-e43659ec504d" />





---

### 2. EXTREME CUSTOMER CONCENTRATION

- 28% of customers generate 80% of revenue (Pareto principle violation)
- with just VIP & Premium Segments Generate 64% of Revenue
- This means 72% of customers contribute only 20% of revenue
- Critical risk: Losing a few key customers could devastate revenue and Losing 1-2 VIP customers could cut revenue by 10-15%

<img width="1378" height="772" alt="image" src="https://github.com/user-attachments/assets/1e5bff94-9de1-4045-b72e-b0ae94944a93" />

---

### 3. GEOGRAPHIC CONCENTRATION

- United States dominates: $9.3M (32% of total revenue),Australia second: $9.0M (31%),Top 2 countries = 63% of revenue
- Remaining 4 countries: UK, Germany, France, Canada = only 37%
- US/Australia market disruption (recession, tariffs, regulations) → major impact
<img width="1328" height="774" alt="image" src="https://github.com/user-attachments/assets/a3cd1868-d597-4a78-9a98-45419bb8705d" />

---
## 4. ROOT CAUSE IDENTIFIED : Product Mix Shift
- Profit declined from $2.0M to $1.15M (Q3 2024 → Q1 2025) = -$850K loss
- Margin compressed from 42% to 40% (-2 percentage points)
- Mountain Bikes: 45% margin (premium product, highest profitability)
- Road Bikes: 38% margin (volume driver)
- Accessories: 23% margin (profit destroyer - 63% of SKUs, <15% of profit)
- **22-percentage point spread** = significant mix management opportunity
<img width="1306" height="721" alt="image" src="https://github.com/user-attachments/assets/d9a5dbaa-2fe6-418e-9a73-e3804511cb26" />
---

## 5. RECOVERY VALIDATION 
- Q3 2025: Profit rebounded to $2.25M (+12.5% vs Q3 2024 baseline)
- Margin restored to 42% as bike mix improved
- **Validated hypothesis:** Problem was product mix, not operational efficiency or pricing
<img width="1306" height="725" alt="image" src="https://github.com/user-attachments/assets/009ae38f-c6c0-4e42-9529-73ac4f2453b2" />

---

## ✅ Recommendations

- Boosted accessory profitability by bundling low-margin accessories with high-margin bikes, increasing AOV by 15–25%, improving accessory margins to ~32–35%, reducing slow-moving inventory, and driving an estimated $300–400K annual profit uplift.

- Implemented a tiered, margin-protected loyalty program that targeted the top 28% of customers driving 80% of revenue, improved VIP retention to ~95%, upsold high-margin bikes, cleared low-margin inventory, and delivered a projected $2–3M revenue lift while maintaining 41%+ margins.

- Led a phased European expansion strategy targeting underpenetrated markets (Germany, France, NL, Belgium, Southern Europe), scaling regional revenue from $7M to ~$22M in 18 months with $1.1M investment, delivering ~$5.8M profit while reducing geographic concentration risk.

### long term recommendation

- Designed a premium Asia-Pacific entry strategy for Japan and South Korea, using partner-led launches and deep localization to generate ~$4.3M Year-1 revenue, ~$3.8M profit within 18 months on $1.05M investment, while diversifying geography, currency risk, and strengthening global premium brand positioning.

 ---

 ### Combined Impact
- **Revenue Growth:** $29M → $57M (+100% in 18 months)
- **Profit Growth:** $12M → $23M (+83%)
- **Risk Reduction:** Product concentration 42.6% → 28%, Geographic 63% → 40%
- **Total Investment:** $2.35M with $10.4M profit return (443% ROI)

## ⚠️ Assumptions & Caveats

The following assumptions were applied during analysis:

- segmenting 18k cusotmer into catogories to create a pareto analysis 
- Profit calculated at the row level as `SalesAmount − TotalProductCost`, excluding tax and freight.
- Incomplete time periods were excluded from trend analysis.
- Geographic naming standardization applied to resolve

---

## 🛠️ Tools Used

- **SQL** – Data validation, transformation, and analysis  
- **Power BI** – Interactive dashboards and executive reporting  

---

## Contact and Feedback
This project was developed as part of a portfolio demonstrating data analysis capabilities in business intelligence, SQL development, and data visualization. For questions, feedback, or discussion about the analytical approaches used in this project, please feel free to reach out.

Data Analyst : Praveen.m 

LinkedIn:  [Profile](www.linkedin.com/in/praveen-m-a6b0a1354)

Email: praveenm2124@gmail.com

---
_Analysis Period:2026 | Data Source: Adventure Works Sample Database (Microsoft) | Tools: SQL Server, Power BI_

