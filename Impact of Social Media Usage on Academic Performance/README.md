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
| Analysis |Power BI|
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

│   ├── processed/            # Social_media_impact_on_life_cleaned.xlsx - Cleaned and transformed data

│   └── external/             # (none was used in this project)

│
├── notebooks/                # (not used - analysis was in Power BI)

│
├── scripts/                  # (not used - cleaning was in Excel)

├── queries/                  # (not used - no SQL in this project)

│
├── reports/                  # Impact of Social Media Usage on Academic Performance Dashboard.pdf - Final outputs: PDFs, slide decks, Word docs

│
├── visuals/                  # impact home-page.png, impact dashboard-overview.png, impact statistics-analysis.png - Exported charts, dashboard screenshots, ERD diagrams

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


1. **Source:** Social_media_impact_on_life.csv from Kaggle. 4,500 rows, 16 columns.
2. **Ingestion:** I loaded the CSV file into Excel for cleaning, then into Power BI for analysis and dashboarding.
3. **Cleaning:** I checked for duplicates (none was found). Filled 46 missing Perceived Stress Scores and 85 missing GPAs with the median value. I also checked for errors (none was found).
4. **Transformation:** I created 3 derived columns in Excel: Usage Category (Light / Moderate / Heavy / Extreme from Daily Usage Hours), Sleep Category (from Sleep Duration Hours), and Total Weekly Usage Hours (Daily Usage Hours * 7 + Weekend Extra Hours * 2).
5. **Analysis:** Descriptive statistics, group comparison by usage, sleep, platform, academic level, and overall impact. Correlation analysis between usage, sleep and GPA.
6. **Output:** A 3-page interactive Power BI dashboard (Overview, Statistics Analysis, KPIs).

---

## 6. Analysis & Metrics

### Analytical Approach

This was an exploratory analysis. I did not start with one hypothesis to prove. I explored the data to find patterns: first described the students (how much they use social media, how they sleep, their GPA), then compared groups (light vs extreme users, late-night vs non-late-night, platform vs platform), and then checked which factors moved together with GPA and Sleep using Correlation.

### Key Metrics Defined

| Metric | Plain-Language Definition | Why It Matters |
|--------|--------------------------|----------------|
| `Avg Daily Usage Hours` | Average hours a student uses social media on a normal day | It is the main behaviour we are testing - if higher daily use is linked to lower GPA and less sleep |
| `Total Weekly Usage Hours` | Daily Usage Hours * 7 + Weekend Extra Hours * 2 | Gives the full weekly load, not just one day |
| `Avg GPA` | Average Academic Performance GPA, on a 0-4 scale | The main academic outcome we are trying to explain |
| `Avg Sleep Duration` | Average hours a student sleeps per night | Shows if heavy and extreme use is eating into sleep |

### Methods Used

- Descriptive statistics: Averages, counts, and percentages to describe the 4,500 students.
- Group comparison: I compared GPA and sleep across Usage Category, Platform, Academic Level, Late-Night Use, and Overall Impact.
- Correlation analysis: I checked how strongly usage moves with GPA and sleep.
- Visual analysis: Bar, donut, and scatter charts in Power BI to spot 6-hour tipping point.

---

## 7. Key Insights

**Insight 1: The 6-hour tipping point**

GPA stays fairly stable at 0-5 hours of daily use (around 3.2 - 3.4), but drops sharply after 6 hours - down to around 2.5 - 2.6 for mainly Extreme users (9h+). This suggests 6 hours is the threshold where social media starts to seriously hurt academic performance.

**Insight 2: It is not the app - it is how much you use it**

There is no detectable difference in GPA by platform - YouTube, TikTok, Instagram, LinkedIn, X, Snapchat, and Reddit all average 3.42 - 3.43. The difference is in usage category: light users average 3.72, Moderate 3.58, Heavy 3.36, and Extreme users 2.99. So grades do not drop because of which app students use, it drops because of how long they use it.

**Insight 3: Late-night use hurts sleep even more**

Students who use social media late at night sleep less and have lower sleep quality and lower GPA than non late-night users with similar total usage. When students use it also matters, not just how long.

**Insight 4: Students know it - but still do it**

Most students who reported their overall impact as "Negative" were Heavy / Extreme users, while Light users mostly reported "Beneficial" or "Neutral". Students are aware of the harm, which means awareness alone is not enough - they need practical limits and support.

---

## 8. Recommendations


| Priority | Recommendation | Based On | Suggested Owner |
|----------|---------------|----------|-----------------|
| High | Promote a "No Late-Night Scroll" rule - no social media 1 hour before bed, plus sleep hygiene workshops in hostels / homes | Insight 3 | School Health / Counselling Unit + Parents |
| Medium | Focus interventions on time spent, not banning specific apps - since all platforms average the same GPA (3.42 - 3.43) | Insight 2 | School Management / Teachers + Parents
| Low | Add termly check-ins and peer support for Heavy / Extreme Users - self-help groups, counselling, and study support, since awareness alone is not changing behaviour | Insight 4 | Counselling Unit + Students Mentors |

---

## 9. Assumptions & Limitations

### Assumptions
- I assumed students reported their daily usage hours, sleep hours, GPA, stress, and mental health truthfully, as I could not verify them against school records or screen-time logs.
- I assumed GPA on a 0-4 scale means the same thing for High School, Undergraduate, and Postgraduate students, to allow comparison across academic levels.
- I assumed the Daily Usage Hours and Sleep Duration reported are for a normal / typical day, not only exam periods, holidays, or weekends when habits change a lot.

### Limitations
- The data shows usage moves together with GPA and sleep, but it cannot prove heavy/extreme social media use causes low GPA.
- The dataset is cross-sectional (one point in time for 4,500 students). We cannot see how a student's grades change as their usage changes over time.
- Usage hours, sleep, and mental health are self-reported and may be under or over-reported.


---

## 10. Author

**Okafor Chimezie Paul**

Aspiring Data Analyst - Power BI & Excel

- 🔗 https://www.linkedin.com/in/okafor-chimezie-805952415?utm_source=share_via&utm_content=profile&utm_medium=member_android
- 💼 [Portfolio or GitHub profile URL]
- 📧 ochimezie522@gmail.com

---

*Last updated: November 2026*

