# Telco Customer Churn Analysis
> *I analyzed 7,032 telecom customers and built an interactive dashboard that uncovers why 26.6% of customers churned, representing $2.8m in lifetime revenue. So the company can target high-risk month-to-month and Fiber optic customers early and retain revenue.*

---

## ⚙️ Project Type Flags


- [x] Exploratory Data Analysis (EDA)
- [ ] SQL Analysis / Querying
- [x] Dashboard / Data Visualization
- [ ] Data Pipeline / ETL
- [ ] Predictive Modelling / Machine Learning
- [x] Data Cleaning / Wrangling
- [x] End-to-End (multiple of the above)
- [ ] Other: ___________

---

## Table of Contents
1. [Project Overview](#1-project-overview)
2. [Objectives](#2-objectives)
3. [Project Scope & Tools](#3-project-scope--tools)
4. [Repository Structure](#4-repository-structure)
5. [Data Workflow](#5-data-workflow)
6. [Data Model & Schema](#6-data-model--schema)
7. [ERD - Entity Relationship Diagram](#7-erd--entity-relationship-diagram) *(SQL projects)*
8. [Analysis & Metrics](#8-analysis--metrics)
9. [Key Insights](#9-key-insights)
10. [Recommendations](#10-recommendations)
11. [Assumptions & Limitations](#11-assumptions--limitations)
12. [Future Enhancements](#12-future-enhancements)
13. [Deliverables](#13-deliverables)
14. [Author](#14-author)

---

## 1. Project Overview


 


**Context:** A telecom company was losing a large number of its customers but did not know which category of customers were leaving, why they were leaving, or how much revenue was being lost. I used the Telco Customer Churn dataset with 7,032 customers to investigate the problem. 

**Problem Statement:** Which customer segments have the highest churn rate, and what factors - contract type, internet service, payment method, and monthly charges - are driving customers to leave?

**Approach:** I cleaned the dataset in Power BI by removing 11 rows with missing TotalCharges. I then built an interactive Power BI dashboard with KPIs and breakdowns by contract, tenure, internet service, payment method, and monthly charges, with slicers for Contract and InternetService. 

**Outcome:** I found a 26.6% churn rate - 1,869 out of 7,032 customers left, costing an estimated $2,862,927 in lost revenue. Month-to-month customers churned at 42.7% vs only 2,8% for two-year contracts customers, and Fiber optic customers at 61.3% vs 27.8% for DSL. New customers in their first 12 months were the most at-risk group.

---

## 2. Objectives


- **Primary Objective:** To identify which customers are churning, why they are leaving, and how much lifetime revenue is being lost, so the company can reduce churn and retain revenue.
- **Secondary Objective 1:** To measure the overall churn rate and the total lifetime revenue represented by churned customers.
- **Secondary Objective 2:** To find the customer segments with the highest churn risk - by contract type, internet service, tenure, payment method, and monthly charges.
- **Secondary Objective 3:** To build an interactive Power BI dashboard that lets managers filter by Contract and InternetService to explore churn patterns and take actions.

---

## 3. Project Scope & Tools

### Scope




| Dimension | Details |
|-----------|---------|
| **In Scope** |Telco Customer Churn dataset from Kaggle. 7,032 customers after cleaning. Analysis of churn by contract type, internet service, tenure group, payment method, and monthly charges. KPIs: Total Customers, Churned Customers, Churn Rate, and TotalCharges of churned customers. Interactive dashboard with Contract and InternetService slicers.|
| **Out of Scope** |No churn prediction / machine learning model - this is descriptive analysis, not predictive. No customer names, call logs, network quality, or customer satisfaction data - they were not in the dataset. No causal claim that Fiber optic causes churn, only that it is associated with higher churn.|
| **Time Period** |No calendar dates in the dataset. It is a cross-sectional snapshot of customers. Tenure ranges from 0 to 72 months with the company.|
| **Granularity** |One row = one customer. All analysis is at customer level, then aggregated by segment.|

### Tools & Technologies


| Category | Tool(s) Used |
|----------|-------------|
| Data Storage |CSV files, Excel (.xlsx)|
| Data Processing |Excel|
| Analysis |Excel, Power BI DAX measures|
| Visualization |Power BI|
| Version Control |Git, GitHub|
| Documentation |Markdown, GitHub README|
| Other |None|

---

## 4. Repository Structure

```




## 5. Data Workflow

[Data Source(s)]
      ↓
[Ingestion / Collection Method]
      ↓
[Cleaning & Transformation]
      ↓
[Analysis / Modelling / Querying]
      ↓
[Output / Visualisation / Reporting]
```

1. **Source:** Superstore Sales Dataset (CSV file, 2.3MB), gotten from Kaggle.com.
2. **Ingestion:** I loaded the CSV file into Excel for cleaning, then imported into Power BI Desktop.
3. **Cleaning:** I checked for duplicates, missing values and errors. None was found (dataset was already cleaned).
4. **Transformation:** In Power BI, I created measures for Total Sales, Total Profit, Profit Margin, and Avg Discount.
5. **Analysis:** I compared sales and profit by Year, Category, and Region. I also analyzed Top 10 profit-making vs Top 10 loss-making products, and checked Discount vs Profit to see how discounts affect profit.
6. **Output:** A 2-page interactive Power BI dashboard - Page 1 is the Cover Page, Page 2 is the main dashboard with KPI cards, slicers, charts, and Top 10 / Bottom 10 tables. Screenshots are saved in the `visuals/` folder. 

---

## 6. Analysis & Metrics

### Analytical Approach

This was an exploratory, descriptive analysis. I did not test a fixed hypothesis. I started with business questions - which categories, regions, and products drive sales and profit, and how discounts affect profit - then I explored the data in Power BI to find patterns and answer those questions with charts.

### Key Metrics Defined

| Metric | Plain-Language Definition | Why It Matters |
|--------|--------------------------|----------------|
| `Total Sales` | Total money from all orders | Shows overall size of the business |
| `Total Profit` | Sales minus costs across all orders | Shows if business is actually making money |
| `Profit Margin` | Total Profit divided by Total Sales | Shows how much profit business keep from every $1 of sales |

### Methods Used

- Descriptive analysis: Summed sales, profit, and orders by Year, Category, Region, and Product
- Visual comparison: Used line charts, bar charts, and donut charts in Power BI to compare groups over time
- Ranking: Ranked Top 10 profit-making vs Top 10 loss-making products to find winners and losers
- Correlation check: Compared Discount vs Profit to see if higher discounts are linked to lower profit

---

## 7. Key Insights

**Insight 1: Technology drives the business, Furniture drags profit**

Technology is the top-performing product category for both sales and profit. Furniture has high sales but lower profit, which suggests high costs or heavy discounts are eating its profit.

**Insight 2: The West region carries the business**

The West region leads with $108.42k in profit, which is 37.9% of total profit. It outperforms East, Central, and South. The business should protect and grow the West while investigating why Central and South are lagging.

**Insight 3: Discounts are hurting profit**

Products with high discounts, especially in Furniture and Office Supplies, appear in the Top 10 loss-making products list. This suggests that higher discounts are linked to lower profit, and some discounts are too high.

**Insight 4: A few products make most of the profit, a few lose most of it**

Profit is not spread evenly. The Top 10 profit-making products drive a large share of the $286.40k total profit, while the Top 10 loss-making products pull it down. Focusing on the winners and fixing or stopping the losers would improve the overall 12.5% profit margin.

---

## 8. Recommendations


| Priority | Recommendation | Based On | Suggested Owner |
|----------|---------------|----------|-----------------|
| High | Review and cap discounts on Furniture and Office Supplies, especially for products in the Top 10 loss-making list. Do not give high discounts without approval | Insight 3 - Discounts are hurting profit | Sales Manager |
| Medium | Protect and grow the West region, and push Technology products more in Central and South to copy what is working in the West | Insight 1 and 2 - Technology leads, West carries the business | Regional / Marketing Manager |
| Low | Review the Top 10 loss-making products and track Profit Margin monthly in Power BI, so the team can see early if discounts are eating profit again | Insight 4 - A few products lose most of the profit, margin is only 12,5% | Data Analyst / Product Manager |

---

## 9. Assumptions & Limitations

### Assumptions
- The data in the Superstore file is correct and complete. I treated Sales, Profit, Discount, and Dates as given without being able to verify them with the real company.
- Profit is calculated as Sales minus Cost. I accepted the Profit column as given and did not recalculate costs.
- The analysis focuses on 2014-2017 sales data in the file. I assumed this period is enough to show sales and profit trends.

### Limitations
- The dataset does not include customer age, customer feedback, or marketing costs. So I could not analyze why customers chose a product or how much was spent on advertising to get them.
- The dataset does not include stock levels or delivery costs. So I could not analyze if loss-making products were caused by stock or shipping issues.
- This project looks like past sales only. It does not predict future sales or customer behaviour.
- The data is from one sample store dataset, not a real life company. So the results may not apply to all retail businesses.


---

## 10. Author

**Okafor Chimezie Paul**

Aspiring Data Analyst - Power BI & Excel

- 🔗 https://www.linkedin.com/in/okafor-chimezie-805952415?utm_source=share_via&utm_content=profile&utm_medium=member_android
- 💼 [Portfolio or GitHub profile URL]
- 📧 ochimezie522@gmail.com

---

*Last updated: November 2026*

