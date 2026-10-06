<div align="center">

# 🍽️ Gourmet Dining LLC
## Operational Performance & Sales Analytics

### 📊 IT Project Management — Project 1

<p>
  <img src="https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/Status-Completed-2EA44F?style=for-the-badge" alt="Status"/>
</p>

<p>
  <strong>📈 Data-driven analysis of restaurant operations, sales performance, KDS synchronization, and staff efficiency.</strong>
</p>

<p>
  <a href="#-team-information">Team</a> •
  <a href="#-project-overview">Overview</a> •
  <a href="#-dataset-information">Dataset</a> •
  <a href="#-project-objectives">Objectives</a> •
  <a href="#-data-preparation">Data</a> •
  <a href="#-data-analysis">Analysis</a> •
  <a href="#-key-results">Results</a> •
  <a href="#-kpi-dashboard">KPIs</a> •
  <a href="#-project-timeline">Timeline</a>
</p>

</div>



# 📋 Table of Contents

- [👥 Team Information](#-team-information)
- [📌 Project Overview](#-project-overview)
- [🎯 Project Objectives](#-project-objectives)
- [❓ Key Questions](#-key-questions)
- [📊 Dataset Information](#-dataset-information)
- [💡 Expected Insights](#-expected-insights)
- [🛠️ Data Preparation](#️-data-preparation)
- [📈 Data Analysis](#-data-analysis)
- [🎯 KPI Evaluation](#-kpi-evaluation)
- [🔍 Key Results](#-key-results)
- [📊 KPI Dashboard](#-kpi-dashboard)
- [💼 Business Impact](#-business-impact)
- [🔄 Project Workflow](#-project-workflow)
- [🧰 Technology Stack](#-technology-stack)
- [📅 Project Timeline](#-project-timeline)
- [🎓 Project Outcomes](#-project-outcomes)
- [🐍 Pandas Skills Developed](#-pandas-skills-developed)
- [📊 Automated Executive Report](#-automated-executive-report)
- [📝 Conclusion](#-conclusion)
- [📚 References](#-references)
- [📎 Appendix](#-appendix)
- [🚀 Future Improvements](#-future-improvements)
- [⭐ Project Highlights](#-project-highlights)



# 👥 Team Information

| 👤 Member | 🆔 Student ID | 🎓 Group | 💼 Role | 📞 Contact |
|---|---|---|---|---|
| **Majitov Akbarjon** | `202490185` | `I24A` | 👑 Team Leader | `+998 (95) 010-71-54` |
| Member 1 | — | `I24A` | — | — |
| Member 2 | — | `I24A` | — | — |
| Member 3 | — | `I24A` | — | — |
| Member 4 | — | `I24A` | — | — |
| Member 5 | — | `I24A` | — | — |

> 🏫 **Course:** IT Project Management
> 📚 **Project:** Project 1
> 👥 **Team:** BOOST



# 📌 Project Overview

**Gourmet Dining LLC** is a restaurant operations analytics project focused on understanding and improving the efficiency of daily restaurant workflows.

The project uses transactional and operational data to investigate:

- 🍽️ Restaurant order performance
- ⚡ Kitchen Display System (KDS) synchronization
- 🕒 Order processing time
- 👨‍🍳 Staff performance
- 💰 Menu item revenue
- 📊 Peak operating hours
- 🔄 Order workflow efficiency

### 🎯 Main Goal

> Transform raw restaurant transaction data into actionable insights that can support operational efficiency, KDS performance, and sales management.



# 🎯 Project Objectives

The project focuses on three major operational areas.

<div align="center">

<table>
<tr>

<td align="center" width="33%">

## ⚡ KDS PERFORMANCE

### Reduce Synchronization Latency

Improve communication between restaurant order stations and the Kitchen Display System.

</td>

<td align="center" width="33%">

## 🍽️ OPERATIONAL EFFICIENCY

### Improve Order Processing

Analyze order processing time, workflow efficiency, and staff performance.

</td>

<td align="center" width="33%">

## 💰 SALES PERFORMANCE

### Analyze Revenue & Demand

Identify high-performing menu items, sales patterns, and peak operating hours.

</td>

</tr>
</table>

</div>

### 📌 Key Objectives

- ⚡ **KDS Performance** — measure synchronization latency and SLA compliance.
- 🍽️ **Operational Efficiency** — analyze order processing time and staff performance.
- 💰 **Sales Performance** — identify revenue-generating menu items and categories.
- 🕐 **Peak Hours** — determine periods of highest restaurant demand.
- 📊 **KPI Monitoring** — create measurable indicators for management.



# ❓ Key Questions

### 1️⃣ KDS Synchronization

> Is the system meeting the required **sub-second synchronization target (< 1 second)** between dining room order stations and kitchen displays?

### 2️⃣ Menu Performance

> Which menu items generate the highest revenue, and which items have lower sales performance?

### 3️⃣ Peak Operating Hours

> What are the peak operating hours of the restaurant?

### 4️⃣ Staff Efficiency

> How does order-processing efficiency vary across staff members and shifts?



# 📊 Dataset Information

## 📁 Dataset

**Gourmet Dining Restaurant Transaction & Order Performance Dataset**

| Property | Description |
|---|---|
| 🗄️ Source | PostgreSQL Production Database |
| 📦 Records | **12,500 rows** |
| 📊 Columns | **10 columns** |
| 🏢 Organization | Gourmet Dining LLC |
| 🐘 Database | PostgreSQL |
| 🐍 Analysis | Python + Pandas |

### 📋 Dataset Contains

The dataset includes:

- 🆔 Order ID
- 🪑 Table Number
- 🕐 Order Timestamp
- 📌 Order Status
- ⚡ KDS Synchronization Latency
- 👨‍🍳 Staff Information
- 💵 Total Bill Amount
- 🍕 Menu Items
- 📂 Menu Categories
- ⏱️ Order Processing Time



# 💡 Expected Insights

The analysis is designed to provide:

| Area | Expected Insight |
|---|---|
| ⚡ KDS | Synchronization latency and SLA compliance |
| 🕒 Operations | Average order fulfillment time |
| 📈 Sales | Revenue by item and category |
| 🍽️ Demand | Peak operating hours |
| 👥 Staff | Order-processing performance |
| 📊 Management | Daily operational KPIs |
| 🚨 Bottlenecks | Areas requiring optimization |



# 🛠️ Data Preparation

## 1. 📥 Loading the Dataset


import pandas as pd

# Load dataset exported from PostgreSQL
df = pd.read_csv("gourmet_dining_orders.csv")

print(df.head())
print(df.info())




 ## 2\. 🧹 Data Cleaning

 The dataset was cleaned to improve data quality and analytical reliability.

 ### 🧹 Cleaning Process


# Remove duplicate records
df = df.drop_duplicates()

# Handle missing KDS synchronization values
df["kitchen_sync_delay_sec"] = (
    df["kitchen_sync_delay_sec"].fillna(0)
)

# Remove records without required identifiers
df.dropna(
    subset=["order_id", "total_amount"],
    inplace=True
)

# Convert timestamp to datetime
df["order_timestamp"] = pd.to_datetime(
    df["order_timestamp"]
)

# Convert table number to integer
df["table_number"] = df["table_number"].astype(int)



### 🔄 Data Cleaning Workflow

mermaid
flowchart TD
    A["📥 Raw Data"] --> B["🔄 Remove Duplicates"]
    B --> C["🧹 Handle Missing Values"]
    C --> D["✅ Validate Required Data"]
    D --> E["🔧 Convert Data Types"]
    E --> F["📊 Clean Analytical Data"]


 # ⚙️ Feature Engineering

 Additional analytical features were created from the cleaned dataset to support deeper operational analysis.

 ### 🔧 Feature Engineering Process


        Clean Analytical Data
                  │
                  ▼
       ┌─────────────────────┐
       │ Extract Order Hour  │
       │ from Timestamp      │
       └──────────┬──────────┘
                  │
                  ▼
       ┌─────────────────────┐
       │ Calculate KDS SLA   │
       │ Compliance          │
       └──────────┬──────────┘
                  │
                  ▼
       ┌─────────────────────┐
       │ Create Analytical   │
       │ Features            │
       └──────────┬──────────┘
                  │
                  ▼
          📊 Analysis-Ready Data


 ### 🧮 Feature Creation


# Extract order hour
df["order_hour"] = df["order_timestamp"].dt.hour

# Check SLA compliance
df["is_sub_second_sync"] = (
    df["kitchen_sync_delay_sec"] < 1.0
)


 ### 📌 Created Features

 | Feature | Description | Purpose |
| --- | --- | --- |
| `order_hour` | Hour extracted from `order_timestamp` | 🕐 Identify peak operating hours |
| `is_sub_second_sync` | Boolean indicator for sync time below 1 second | ⚡ Measure KDS SLA compliance |



 # 📈 Data Analysis

 ## ⚡ KDS Synchronization Analysis

 Orders exceeding the 1-second synchronization target are identified using:


slow_sync_orders = df[
    df["kitchen_sync_delay_sec"] >= 1.0
]

print(slow_sync_orders)


 ### 🎯 Analysis Objective

 The goal is to identify orders that did not meet the required:

 > **KDS synchronization target: \< 1 second**



 ## 👥 Staff Performance Analysis

 Average order processing time is calculated for each staff member.


staff_performance = (
    df.groupby("staff_id")[
        "order_processing_time_min"
    ]
    .mean()
    .reset_index()
)

staff_performance = staff_performance.sort_values(
    by="order_processing_time_min"
)

print(staff_performance)


 ### 📊 Performance Metrics

 - ⏱️ Average order processing time
- 👥 Orders handled by staff
- 📈 Processing efficiency
- 🕐 Shift performance



 # 🍕 Menu Performance Analysis

 Menu performance is analyzed by calculating total revenue and order volume for each item.


item_analytics = (
    df.groupby("item_name")
    .agg(
        total_sales=("total_amount", "sum"),
        orders_count=("order_id", "count")
    )
    .sort_values(
        by="total_sales",
        ascending=False
    )
)

print(item_analytics.head(10))


 ### 📊 Menu Metrics

 | Metric | Description |
| --- | --- |
| 💰 Total Revenue | Revenue generated by each menu item |
| 🧾 Order Count | Number of orders containing the item |
| 🍕 Item Popularity | Demand based on order volume |
| 📈 Revenue Contribution | Item contribution to total sales |
| 📊 Category Performance | Revenue by menu category |



 # 🕐 Peak Hours Analysis

 Order timestamps are transformed into hourly data to identify periods of high restaurant demand.


hourly_orders = (
    df.groupby("order_hour")
    .agg(
        total_orders=("order_id", "count"),
        total_revenue=("total_amount", "sum")
    )
    .sort_values(
        by="total_orders",
        ascending=False
    )
)

print(hourly_orders)


 ### 🕒 Analysis Focus

 The analysis evaluates:

 - 🍽️ Number of orders per hour
- 💰 Revenue per hour
- 📈 Demand patterns
- 🕐 Peak operating periods



 # 📑 Pivot Table Analysis

 Revenue is analyzed across operating hours and menu categories using a Pandas pivot table.


sales_pivot = pd.pivot_table(
    df,
    values="total_amount",
    index="order_hour",
    columns="menu_category",
    aggfunc="sum",
    fill_value=0
)

print(sales_pivot)


 ### 📊 Analytical Structure


                         MENU CATEGORY
                 ┌────────┬────────┬────────┬────────┐
                 │   A    │   B    │   C    │   D    │
┌────────────────┼────────┼────────┼────────┼────────┤
│ 12:00          │   $    │   $    │   $    │   $    │
│ 13:00          │   $    │   $    │   $    │   $    │
│ 14:00          │   $    │   $    │   $    │   $    │
│ 19:00          │   $    │   $    │   $    │   $    │
│ 20:00          │   $    │   $    │   $    │   $    │
└────────────────┴────────┴────────┴────────┴────────┘

                       ORDER HOUR




 # 🎯 KPI Evaluation

 ## ⚡ KDS SLA Compliance

 The percentage of orders synchronized in less than one second is calculated as follows:


sub_sec_percentage = (
    df["is_sub_second_sync"].mean() * 100
)

print(
    f"Percentage of orders synchronized "
    f"in < 1 second: {sub_sec_percentage:.2f}%"
)


 ### 📐 KPI Formula

 $$
SLA\ Compliance =
\frac{\text{Orders with Sync Time < 1 sec}}
{\text{Total Orders}}
\times 100
$$



 # 🔍 Key Results

 > 📌 The following figures represent the results stated in the project analysis.

 ## ⚡ KDS Synchronization

 ### **96.4%**

 of analyzed orders were synchronized with the Kitchen Display System in under **1 second**.


KDS SLA TARGET
< 1.0 second

┌──────────────────────────────────────────┐
│██████████████████████████████████████░░░│
│                  96.4%                   │
└──────────────────────────────────────────┘


 ### 📊 Reported Average Latency

 **0.42 seconds**



 ## 🕒 Peak Operating Hours

 ### 🍽️ Lunch

 **13:00 – 15:00**

 ### 🌙 Dinner

 **19:00 – 22:00**

 These periods represent the main operating windows requiring careful staffing and workflow planning.



 ## 🍕 Menu Performance

 The analysis indicates that approximately:

 ### **Top 20% of menu items → 65%+ of total sales revenue**

 This indicates that a relatively small group of menu items contributes a large share of overall sales revenue.



 # 📊 KPI Dashboard

 \<div align="center"\> | 📌 KPI | 🎯 Target | 📈 Actual | Status |
| --- | --- | --- | --- |
| ⚡ KDS Sync Latency | `< 1.0 sec` | **0.42 sec** | 🟢 Passed |
| ⏱️ Order Processing Time | `< 15 min` | **11.8 min** | 🟢 Passed |
| 💰 Daily Sales Export | Automated | **Implemented** | 🟢 Passed |
| 📦 Dataset Size | — | **12,500 rows** | 🔵 Analyzed |
| 🐍 Data Analysis | Pandas | **Completed** | 🟢 Done |

\</div\>


 # 💼 Business Impact

 ## 👥 Staff Planning

 Peak-hour information can support better allocation of:

 - 👨‍🍳 Chefs
- 🧑‍💼 Waitstaff
- 👔 Managers
- 📋 Order-processing resources



 ## ⚡ KDS Optimization

 Identifying synchronization delays can help investigate:

 - 🌐 Network latency
- 🗄️ Database performance
- 🔄 Server synchronization
- 📡 Order transmission workflow



 ## 🍕 Menu Management

 Revenue analysis can help management understand:

 - ⭐ High-performing products
- 📉 Lower-performing products
- 📂 Category revenue
- 📈 Customer demand patterns



 ## 📊 Management Reporting

 The project supports automated reporting of:

 - 💰 Daily revenue
- 🧾 Order volume
- ⚡ Average synchronization delay
- 🍕 Menu performance
- 📊 Operational KPIs



 # 🔄 Project Workflow


                 ┌──────────────────────┐
                 │   🐘 PostgreSQL DB   │
                 │      Raw Data        │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │   📥 Data Export     │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │   🧹 Data Cleaning   │
                 │       Pandas         │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │ ⚙️ Feature           │
                 │    Engineering       │
                 └──────────┬───────────┘
                            │
                            ▼
                 ┌──────────────────────┐
                 │   📈 Data Analysis   │
                 │       Pandas         │
                 └──────────┬───────────┘
                            │
             ┌──────────────┼──────────────┐
             ▼              ▼              ▼
       ┌──────────┐   ┌──────────┐   ┌──────────┐
       │ ⚡ KDS   │   │ 🍕 Sales │   │ 👥 Staff │
       │ Analysis │   │ Analysis │   │ Analysis │
       └────┬─────┘   └────┬─────┘   └────┬─────┘
            │              │              │
            └──────────────┼──────────────┘
                           ▼
                 ┌──────────────────────┐
                 │  💡 Business Insights│
                 └──────────────────────┘




 # 🧰 Technology Stack

 \<div align="center"\> | Technology | Purpose |
| --- | --- |
| 🐍 **Python 3.9+** | Data analysis |
| 🐼 **Pandas** | Data manipulation & analytics |
| 🐘 **PostgreSQL** | Transaction database |
| 📊 **Pivot Tables** | Multi-dimensional analysis |
| 🕐 **Datetime** | Time-based analysis |
| 📈 **KPI Analytics** | Performance measurement |

\</div\>


 # 📅 Project Timeline

 | Week | Date | Activities | Status |
| --- | --- | --- | --- |
| **Week 1** | 07 Sep – 13 Sep | Dataset search, PostgreSQL export setup, project planning | ✅ Completed |
| **Week 2** | 14 Sep – 20 Sep | Data cleaning, missing values, timestamp preparation | ✅ Completed |
| **Week 3** | 21 Sep – 27 Sep | Pandas analysis, KDS performance, visualization | ✅ Completed |
| **Week 4** | 28 Sep – 04 Oct | KPI aggregation, validation and interpretation | ✅ Completed |
| **Week 5** | 05 Oct – 13 Oct | Final report and presentation preparation | ✅ Completed |
| 🎓 **Final Presentation** | **14 Oct** | Project presentation | 🎯 |



 # 🎓 Project Outcomes

 ## 🧠 Key Learnings

 The project provided practical experience in connecting business requirements with data analysis.


Business Requirements
        │
        ▼
Database Data
        │
        ▼
Data Cleaning
        │
        ▼
Data Analysis
        │
        ▼
KPI Calculation
        │
        ▼
Business Insights


 ### 📚 Main Learning Areas

 - 🎯 Understanding business requirements and SLAs
- 🗄️ Working with relational database exports
- 🐘 Transforming PostgreSQL data into Pandas DataFrames
- 🧹 Cleaning transactional data
- 📊 Performing group-by analysis
- 📑 Creating pivot tables
- 🕐 Working with datetime data
- 📈 Calculating operational KPIs
- 💡 Translating analytical results into business insights



 # 🐍 Pandas Skills Developed

 ## 🔹 Data Manipulation


df.drop_duplicates()
df.dropna()
df.groupby()
df.sort_values()


 ## 🔹 Data Transformation


pd.to_datetime()
df.astype()
df["order_timestamp"].dt.hour


 ## 🔹 Analytical Operations


df.groupby()
pd.pivot_table()
.agg()
.mean()
.sum()
.count()




 # 📊 Automated Executive Report

 The project includes a function for generating a daily management summary.


def generate_daily_report(dataframe):
    """
    Generate an aggregated daily executive
    summary report for management.
    """

    summary = dataframe.groupby("order_date").agg(
        total_revenue=("total_amount", "sum"),
        total_orders=("order_id", "nunique"),
        avg_sync_delay=(
            "kitchen_sync_delay_sec",
            "mean"
        )
    )

    return summary


 ### 📋 Example Output

 | Date | Total Revenue | Total Orders | Avg. Sync Delay |
| --- | --- | --- | --- |
| 2025-09-07 | — | — | — |
| 2025-09-08 | — | — | — |
| 2025-09-09 | — | — | — |



 # 📝 Conclusion

 The **Operational Performance & Sales Analytics for Gourmet Dining LLC** project demonstrates how data analytics can be applied to restaurant operations to identify workflow bottlenecks and measure operational performance.

 The analysis focuses on three central areas:

 > ⚡ **KDS Synchronization**\
>  🍽️ **Operational Efficiency**\
>  💰 **Sales Performance**

 ### 📌 Main Findings

 - ⚡ **96.4%** of analyzed orders achieved sub-second KDS synchronization.
- ⏱️ Reported average KDS latency was **0.42 seconds**.
- 🕒 Average order processing time was **11.8 minutes**.
- 🍽️ Major demand periods were identified during **13:00–15:00** and **19:00–22:00**.
- 🍕 The top **20% of menu items** accounted for more than **65% of total sales revenue**.

 Overall, the project demonstrates the complete process of transforming raw transactional data into structured KPIs and operational insights using **PostgreSQL, Python, and Pandas**.



 # 📚 References

 ## 🗄️ Dataset

 **Gourmet Dining LLC Production Database**

 - PostgreSQL schema
- Restaurant transaction records
- Operational transaction logs

 ## 📖 Documentation

 - [🐼 Pandas Documentation](<https://pandas.pydata.org/docs/>)
- [🐘 PostgreSQL Documentation](<https://www.postgresql.org/docs/>)



 # 📎 Appendix

 ## 📁 Recommended Project Structure


Gourmet-Dining-Analytics/
│
├── 📄 README.md
│
├── 📂 data/
│   └── gourmet_dining_orders.csv
│
├── 📂 notebooks/
│   └── restaurant_analysis.ipynb
│
├── 📂 src/
│   ├── data_cleaning.py
│   ├── analysis.py
│   └── reporting.py
│
├── 📂 reports/
│   └── final_report.pdf
│
├── 📂 visualizations/
│   ├── sales_by_hour.png
│   ├── menu_performance.png
│   └── kds_latency.png
│
└── 📄 requirements.txt




 # 🚀 Future Improvements

 Possible future extensions include:

 - 📊 Interactive dashboard using Power BI or Tableau
- 🔔 Real-time KDS latency monitoring
- 🤖 Automated anomaly detection
- 📈 Sales forecasting
- 👥 Advanced staff scheduling analytics
- 🗺️ Table utilization heatmaps
- ☁️ Cloud-based data pipeline
- 📱 Real-time management dashboard



 # ⭐ Project Highlights

 \<div align="center"\> | 📊 Dataset | ⚡ KDS SLA | 🕒 Avg. Processing | 🍕 Revenue Concentration |
| --- | --- | --- | --- |
| **12,500** | **96.4%** | **11.8 min** | **65%+** |
| Records | `< 1 sec` | `< 15 min` | Top 20% Items |

\</div\>


 \<div align="center"\> # 🍽️ Gourmet Dining LLC

 ### Turning Restaurant Data Into Operational Insights

 **IT Project Management — Project 1**

 🐍 **Python** • 🐼 **Pandas** • 🐘 **PostgreSQL**



 ⭐ **Thank you for visiting our project!**

 \</div\> \`\`\` 


- ✅ Все ссылки оформлены нормально для GitHub.
- ✅ Код стал копируемым и подсвечивается синтаксисом Python.
- ✅ Финальная часть README теперь выглядит как полноценная презентационная страница проекта.
