# Superstore Sales Analysis
> *I analyzed 9,994 order lines across 5,009 unique orders from 2014 to 2017, built an interactive Power BI dashboard tracking sales, profit and margin, and solved why profit did not match sales by exposing that Furniture returns the lowest profit of the three product categories and losses are concentrated in Tables, which matters because it shows exactly where to fix pricing and discounting to protect profit.*

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


 


**Context:** Superstore is a US retail company selling Furniture, Office Supplies, and Technology across 4 regions. Sales were growing from 2014 to 2017, but management was concerned that profit was not matching sales, so they needed a clear view of where money was being made and lost. 

**Problem Statement:** With total sales of $2.3m but a profit margin of only 12.5%, where is Superstore losing profit, and is discounting helping or hurting performance?

**Approach:** I analyzed 9,994 order lines across 5,009 unique orders from 2014 to 2017, validated the data for duplicates and missing values, then built an interactive dashboard to track sales, profit, margin, and discount by category, region, and year using DAX measures.

**Outcome:** I built a 2-page Power BI dashboard covering 9,994 orders from 2014 to 2017, showing $2.3m in total sales, $286.40k in total profit, and a 12.5% profit margin. The dashboard shows that profit is uneven: Technology drives the highest profit while Furniture returns the lowest profit of the three product categories, and the West region leads with $108.42k (37.9% of profit) while Central is lowest at $39.71k (13.9% of profit). It also shows that high discount reduces profit, with the biggest losses concentrated in Tables, including BoxOffice By Design Rectangular Table and Balt Solid Wood Round Tables. 

---

## 2. Objectives


- **Primary Objective:** To find where Superstore makes and loses money, and explain why profit of $286.40k did not match sales of $2.3m from 2014 to 2017.
- **Secondary Objective 1:** To measure performance by Category, Region, and Country to identify the highest and lowest profit products and locations.
- **Secondary Objective 2:** To test the effect of Discount on Profit and find out if high discounts are increasing sales but reducing profit.
- **Secondary Objective 3:** To build a Power BI Overview and Details dashboard that a manager can read in 5 seconds to make pricing and discount decisions.


---

## 3. Project Scope & Tools

### Scope




| Dimension | Details |
|-----------|---------|
| **In Scope** |Superstore sales data from the US market, covering all 4 regions (West, East, Central, South), all 3 segments (Consumer, Corporate, Home Office), and all 3 product categories (Technology, Furniture, Office Supplies)|
| **Out of Scope** |Customer names, returns, and shipping logistics were excluded because they were not needed to answer the core question: why profit did not match sales. No forecasting or price optimization modelling.|
| **Time Period** |3rd January 2014 to 30th December 2017 (4 years of order data)|
| **Granularity** |One row = one order line (one product in one order). 9,994 order lines in total.|

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
[superstore-sales-analysis]/

## Overview
This project analyzes Superstore sales data to understand sales performance, profitability, customer trends, and presents the findings in an interactive Power BI dashboard.

## Business Questions
- Which products and categories drive the most sales and profit?
- Which regions are sales performing best?
- How do sales trend over time?

## Tools Used
- Power BI - Dashboard & Visualization
- Excel - Data Cleaning and Validation
- GitHub - Project Documentation

## Key Insights
- Technology is the top-performing product category
- The West region leads in sales and generates the highest profit
- Sales grew steadily from 2014 to 2017, with the strongest growth in 2016 to 2017

## Files
- `data/` - Raw sales data
- `dashboard/` - Power BI file (.pbix) & dashboard PDF
- `visuals/` - Dashboard screenshots

## How to View Dashboard File
1. Open the `dashboard/` folder
2. Download the `.pbix` file
3. Open it in Power BI Desktop


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
- The data in the Superstore file is correct and complete. I treated Sales, Profit, Discount, and Dates as given without being able to verify them with real the company.
- Profit is calculated as Sales minus Cost. I accepted the Profit column as given and did not recalculate costs.
- The analysis focuses on 2014-2017 sales data in the file. I assumed this period is enough to show sales and profit trends.

### Limitations
- The dataset does not include customer age, customer feedback, or marketing costs. So I could not analyze why customers buy or how much it costs to get them.
- The dataset does not include stock levels or delivery costs. So I could not analyze if loss-making products were caused by stock or shipping issues.
- This project looks like past sales only. It does not predict future sales or customer behaviour.
- The data is from one sample store dataset, not a real life company. So the results may not apply to all retail businesses.


---

## 14. Author

**Okafor Chimezie Paul**

Aspiring Data Analyst - Power BI & Excel

- 🔗 [LinkedIn URL]
- 💼 [Portfolio or GitHub profile URL]
- 📧 [Email - optional]

---

*Last updated: November 2026*

