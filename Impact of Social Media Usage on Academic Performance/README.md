# Impact of Social Media Usage on Academic Performance
> *I analyzed 4,500 students and built a Power BI dashboard showing how extreme users of social media platforms score 0.73 GPA lower than light users, proving that hours spent on social media usage and duration of sleep - not the platform being used - hurt grades, so parents and schools know what to fix .*

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


 


**Context:** Students spend hours daily on social media, schools and parents worry it is hurting grades and affecting their academic performance - but it was not clear if the problem was the various apps being used, the hours spent, or the timing. 

**Problem Statement:** Does social media usage affect academic performance, and if so, is it the platform, the amount of time, or late-night use and sleep loss that matters most?

**Approach:** I analyzed 4,500 students in Excel & Power BI, grouped them into Light, Moderate, Heavy, and Extreme users, and built a 3-page interactive Power BI dashboard comparing GPA by usage, sleep duration, platform, academic level, and late-night use.

**Outcome:** Majority of students who use social media a lot got lower grades. Light users got 3.72 GPA, Extreme users got 2.99 GPA - that's a 0.73 difference. The app didn't matter, all apps are about the same in GPA. What mattered is how many hours spent and how much sleep was lost.

---

## 2. Objectives


- **Primary Objective:** To find out if the amount of time a student spends on social media is linked to how well they perform in school (GPA), and where the problem becomes more common.
- **Secondary Objective 1:** To find out how students are distributed across Light, Moderate, Heavy, and Extreme use, and how GPA changes as daily usage increases.
- **Secondary Objective 2:** To find how sleep is linked to both social media use and grades - do heavy users sleep less, and do students who sleep well score better?
- **Secondary Objective 3:** To find out if stress and mental wellbeing change the relationship between social media and grades, and if the choice of platform (Instagram, Tiktok, etc.) affects grades on its own - or if total time is what matters, so we can identify which group or groups need attention most.

---

## 3. Project Scope & Tools

### Scope




| Dimension | Details |
|-----------|---------|
| **In Scope** |4,500 students aged 15-26 (High School, Undergraduate, Postgraduate). 16 columns: Students ID, Age, Gender, Academic Level, Primary Platform, Daily Usage Hours, Weekend Extra Hours, Device Type, Late-Night Usage, Sleep Duration, Sleep Quality Score, Social Comparison Frequency, Perceived Stress Score, Mental Health Index, GPA (0-4), and Overall Impact (Beneficial / Neutral / Negative - self-reported). Plus 3 derived columns created for analysis: Usage Category, Sleep Category, Total Weekly Usage Hours. Analysis of GPA by usage, sleep, platform, academic level, late-night use, and overall impact.|
| **Out of Scope** |Proving causation - this is a one-time survey, so it shows association, not that social media causes lower grades. Predicting future grades, tracking students over time, and analyzing what students actually do on each app (chatting vs studying vs entertainment) were excluded because that data was not collected.|
| **Time Period** |One-time survey / cross-sectional snapshot. No date range in the dataset itself.|
| **Granularity** |Row-level: 1 row = 1 student. All analysis is aggregated from student-level records into groups - Usage Category (Light / Moderate / Heavy / Extreme), Sleep Category, Platform, and Academic Level.|

### Tools & Technologies


| Category | Tool(s) Used |
|----------|-------------|
| Data Storage |CSV files, Excel (.xlsx)|
| Data Processing |Excel|
| Analysis |Excel|
| Visualization |Power BI|
| Version Control |Git, GitHub|
| Documentation |Markdown, GitHub README|
| Other |None|

---

## 4. Repository Structure


[telco-customer-churn]/

│
├── data/

│   ├── raw/                  # Social_media_impact_on_life.csv - Original, unmodified source data, never edited

│   ├── processed/            # Social_media_impact_on_life_cleaned-dataset.xlsx - Cleaned and transformed data

│   └── external/             # (none was used in this project)

│
├── notebooks/                # (not used - analysis was in Excel)

│
├── scripts/                  # (not used - cleaning was in Excel)

├── queries/                  # (not used - no SQL in this project)

│
├── reports/                  # Telco Customer Churn Dashboard.pdf - Final outputs: PDFs, slide decks, Word docs

│
├── visuals/                  # telco home-page.png, telco dasboard-overview.png - Exported charts, dashboard screenshots, ERD diagrams

│
├── docs/                     # (not used)

│
├── project_metadata.yml      # (not used)

└── README.md                 # You are here





---

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


1. **Source:** WA_Fn-UseC_-Telco-Customer-Churn.csv from Kaggle. 7,043 rows, 21 columns.
2. **Ingestion:** I loaded the CSV file into Power BI Desktop via Get Data > Text/CSV.
3. **Cleaning:** I removed 11 rows with blank TotalCharges in Power Query. 7,043 -> 7,032 rows. Checked for duplicates, missing values and errors.
4. **Transformation:** I created DAX measures in Power BI: Total Customers, Churned Customers, Churned Rate %, and Revenue Lost then added a conditional column for Tenure, where tenure was categorized in groups of 0-12 months, 12-24 months, and 24+ months. I also created a calculated column in Power BI for MonthlyCharges, breaking it down into categories ($0-35, $36-70, $71-100, $100+). 
5. **Analysis:** Descriptive analysis in Power BI - churn by Contract, Tenure, Payment Method, Internet Service and Monthly Charges. No Python or SQL used.
6. **Output:** A 2-page interactive Power BI dashboard. Screenshots in `visuals/` folder.

---

## 6. Analysis & Metrics

### Analytical Approach

This was an exploratory, descriptive analysis. I did not test a formal hypothesis or build a prediction model. I explored patterns in the data to answer: who is churning, and what do churned customers have in common?

### Key Metrics Defined

| Metric | Plain-Language Definition | Why It Matters |
|--------|--------------------------|----------------|
| `Total Customers` | Count of all customers after cleaning = 7,032 | Shows the total customers in the file after cleaning |
| `Churned Customers` | Count where churn = Yes = 1,869 | Shows how many customers were lost |
| `Churn Rate %` | Churned Customers / Total Customers = 26.5% | Main KPI - answers how bad is churn? |
| `Revenue Lost` | Sum of TotalCharges for churned customers | shows total lifetime money lost from customers that left |

### Methods Used

- Segmentation / grouping by Contract, Tenure, Payment Method, Internet Service, and Monthly Charges 
- Comparison of churn rate across groups using charts
- Visual exploration in Power BI to spot patterns 
---

## 7. Key Insights

**Insight 1: Month-to-month contracts churn the most**

Customers on Month-to-month contracts have a much higher churn rate than those on One-year or Two-year contracts. This suggests customers with no long-term commitment leave easily.

**Insight 2: New customers leave early**

Customers with low tenure (0-12 months) churn more than long-term customers. This suggests the first year is the riskiest period.

**Insight 3: Electronic check users churn more**

Customers who pay with Electronic check have a higher churn rate than those who pay with Credit card, Bank transfer, or Mailed check. This suggests payment experience or customer type plays a role.

**Insight 4: Fiber Optic + higher Monthly Charges = higher churn**

Customers with Fiber Optic internet and higher MonthlyCharges churn more than DSL customers. This suggests price and service value may be pushing customers away.

---

## 8. Recommendations


| Priority | Recommendation | Based On | Suggested Owner |
|----------|---------------|----------|-----------------|
| High | Offer discount / incentive to move Month-to-month customers to One-year or Two-year contracts | Insight 1 | Retention Team |
| Medium | Create a welcome / onboarding program for new customers in first 12 months | Insight 2 | Customer Success Team |
| Low | Review Fiber Optic pricing and service quality, offer bundle or support check-in | Insight 4 | Product / Pricing Team |

---

## 9. Assumptions & Limitations

### Assumptions
- Churn = Yes means the customer has left and will not return.
- The data is a snapshot in time and represents the full customer base at that time.
- TotalCharges and MonthlyCharges are recorded correctly, except the 11 blank rows which were removed during cleaning.

### Limitations
- No date column, so we cannot see if churn is getting better or worse over time.
- No reason for churn (e.g. price, service, competitor), so we can show who churns, not why they churn.
- No prediction model was built, so we cannot predict which current customer will churn next.
- The data is from one telecom company, so findings may not apply to other companies.


---

## 10. Author

**Okafor Chimezie Paul**

Aspiring Data Analyst - Power BI & Excel

- 🔗 https://www.linkedin.com/in/okafor-chimezie-805952415?utm_source=share_via&utm_content=profile&utm_medium=member_android
- 💼 [Portfolio or GitHub profile URL]
- 📧 ochimezie522@gmail.com

---

*Last updated: November 2026*

