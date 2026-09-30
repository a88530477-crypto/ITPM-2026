<div align="center">

# 🍽️ Gourmet Dining LLC
## Operational Performance & Sales Analytics

### 📊 IT Project Management — Project 1

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9%2B-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=for-the-badge&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/Status-Completed-2EA44F?style=for-the-badge" alt="Status"/>
</p>

<p>
  <strong>📈 Data-driven analysis of restaurant operations, sales performance, KDS synchronization and staff efficiency.</strong>
</p>

<p>
  <a href="#-team-information">Team</a> •
  <a href="#-project-overview">Overview</a> •
  <a href="#-dataset-information">Dataset</a> •
  <a href="#-objectives">Objectives</a> •
  <a href="#-data-preparation">Data</a> •
  <a href="#-analysis">Analysis</a> •
  <a href="#-key-results">Results</a> •
  <a href="#-timeline">Timeline</a>
</p>

</div>



# 📋 Table of Contents

- [👥 Team Information](#-team-information)
- [📌 Project Overview](#-project-overview)
- [📊 Dataset Information](#-dataset-information)
- [🎯 Project Objectives](#-project-objectives)
- [🛠️ Data Preparation](#️-data-preparation)
- [📈 Data Analysis](#-data-analysis)
- [🔍 Key Results](#-key-results)
- [📊 KPI Dashboard](#-kpi-dashboard)
- [💼 Business Impact](#-business-impact)
- [🔄 Project Workflow](#-project-workflow)
- [🧰 Technology Stack](#-technology-stack)
- [📅 Project Timeline](#-project-timeline)
- [🎓 Project Outcomes](#-project-outcomes)
- [📝 Conclusion](#-conclusion)
- [📚 References](#-references)
- [📎 Appendix](#-appendix)
- [🚀 Future Improvements](#-future-improvements)


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
> 👥 **Team:** Akbar_Team


# 📌 Project Overview

**Gourmet Dining LLC** is a restaurant operations analytics project focused on understanding and improving the efficiency of daily restaurant workflows.

The project uses transactional and operational data to investigate:

- 🍽️ Restaurant order performance
- ⚡ Kitchen Display System (KDS) synchronization
- 🕒 Order processing time
- 👨‍🍳 Staff performance
- 💰 Menu item revenue
- 📊 Peak operating hours
- 🔄 Table and order workflow efficiency

The main objective is to transform raw restaurant transaction data into **actionable business insights** using **Python, Pandas and PostgreSQL**.


# 🎯 Project Objectives

The project focuses on three major operational areas:


┌─────────────────────────────────────────────────────────┐
│                 GOURMET DINING ANALYTICS                │
├─────────────────────────────────────────────────────────┤
│                                                         │
│   ⚡ KDS PERFORMANCE                                    │
│   └── Reduce order synchronization latency              │
│                                                         │
│   🍽️ OPERATIONAL EFFICIENCY                            │
│   └── Improve order processing & table turnover         │
│                                                         │
│   💰 SALES PERFORMANCE                                  │
│   └── Identify high-performing products & peak hours    │
│                                                         │
└─────────────────────────────────────────────────────────┘


 # ❓ Key Questions

 ### 1️⃣ KDS Synchronization

 > Is the system meeting the required **sub-second synchronization target (\< 1 second)** between dining room order stations and kitchen displays?

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
| --- | --- |
| 🗄️ Source | PostgreSQL Production Database |
| 📦 Records | **12,500 rows** |
| 📊 Columns | **10 columns** |
| 🏢 Organization | Gourmet Dining LLC |
| 🐘 Database | PostgreSQL |
| 🐍 Analysis | Python + Pandas |

### Dataset Contains

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
| --- | --- |
| ⚡ KDS | Synchronization latency and SLA compliance |
| 🕒 Operations | Average order fulfillment time |
| 📈 Sales | Revenue by item and category |
| 🍽️ Demand | Peak operating hours |
| 👥 Staff | Order-processing performance |
| 📊 Management | Daily operational KPIs |
| 🚨 Bottlenecks | Areas requiring optimization |


 # 🛠️ Data Preparation

 ## 1\. 📥 Loading the Dataset

import pandas as pd

# Load dataset exported from PostgreSQL
df = pd.read_csv("gourmet_dining_orders.csv")

print(df.head())
print(df.info())


 ## 2\. 🧹 Data Cleaning

 The dataset was cleaned to improve analytical reliability.

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
```

 ### 🧹 Data Cleaning Workflow

Raw Data
   │
   ▼
Remove Duplicates
   │
   ▼
Handle Missing Values
   │
   ▼
Validate Required Fields
   │
   ▼
Convert Data Types
   │
   ▼
Clean Analytical Dataset


 # ⚙️ Feature Engineering

 Additional analytical features were created from the original dataset.

# Extract order hour
df["order_hour"] = df["order_timestamp"].dt.hour

# Check SLA compliance
df["is_sub_second_sync"] = (
    df["kitchen_sync_delay_sec"] < 1.0
)

 ### 📌 Created Features

 | Feature | Purpose |
| --- | --- |
| `order_hour` | Identify peak operating hours |
| `is_sub_second_sync` | Measure KDS SLA compliance |


 # 📈 Data Analysis

 ## ⚡ KDS Synchronization Analysis

 Orders exceeding the 1-second target are identified using:

slow_sync_orders = df[
    df["kitchen_sync_delay_sec"] >= 1.0
]

print(slow_sync_orders)


 ## 👥 Staff Performance Analysis

 Average order processing time is calculated for each staff member:

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


 # 🍕 Menu Performance Analysis

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

 ### 📊 Metrics

 - 💰 Total revenue
- 🧾 Number of orders
- 🍕 Item popularity
- 📈 Revenue contribution
- 📊 Menu category performance


 # 🕐 Peak Hours Analysis

 Order timestamps are transformed into hourly data:

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


 # 📑 Pivot Table Analysis

 Revenue can be analyzed by operating hour and menu category.

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
              ┌────┬────┬────┬────┐
              │ A  │ B  │ C  │ D  │
┌─────────────┼────┼────┼────┼────┤
│ 12:00       │ $  │ $  │ $  │ $  │
│ 13:00       │ $  │ $  │ $  │ $  │
│ 14:00       │ $  │ $  │ $  │ $  │
│ 19:00       │ $  │ $  │ $  │ $  │
│ 20:00       │ $  │ $  │ $  │ $  │
└─────────────┴────┴────┴────┴────┘
             ORDER HOUR


 # 🎯 KPI Evaluation

 ## ⚡ KDS SLA Compliance

sub_sec_percentage = (
    df["is_sub_second_sync"].mean() * 100
)

print(
    f"Percentage of orders synchronized "
    f"in < 1 second: {sub_sec_percentage:.2f}%"
)

 ### KPI Formula

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

SLA TARGET
< 1.0 sec

┌──────────────────────────────────────────┐
│██████████████████████████████████████░░░│
│                 96.4%                    │
└──────────────────────────────────────────┘


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

 | 📌 KPI | 🎯 Target | 📈 Actual | Status |
| --- | --- | --- | --- |
| ⚡ KDS Sync Latency | `< 1.0 sec` | **0.42 sec** | 🟢 Passed |
| ⏱️ Order Processing Time | `< 15 min` | **11.8 min** | 🟢 Passed |
| 💰 Daily Sales Export | Automated | **Implemented** | 🟢 Passed |
| 📦 Dataset Size | — | **12,500 rows** | 🔵 Analyzed |
| 🐍 Data Analysis | Pandas | **Completed** | 🟢 Done |


 # 💼 Business Impact

 ## 👥 Staff Planning

 Peak-hour information can support better allocation of:

 - Waitstaff
- Chefs
- Managers
- Order-processing resources


 ## ⚡ KDS Optimization

 Identifying synchronization delays can help investigate:

 - Network latency
- Database performance
- Server synchronization
- Order transmission workflow


 ## 🍕 Menu Management

 Revenue analysis can help management understand:

 - High-performing products
- Low-performing products
- Category revenue
- Customer demand patterns


 ## 📊 Management Reporting

 The project supports automated reporting of:

 - Daily revenue
- Order volume
- Average synchronization delay
- Menu performance
- Operational KPIs


 # 🔄 Project Workflow
                    ┌──────────────────┐
                    │ PostgreSQL Data  │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Data Extraction  │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Data Cleaning    │
                    │     Pandas       │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Feature          │
                    │ Engineering      │
                    └────────┬─────────┘
                             │
                             ▼
                    ┌──────────────────┐
                    │ Data Analysis    │
                    │     Pandas       │
                    └────────┬─────────┘
                             │
              ┌──────────────┼──────────────┐
              ▼              ▼              ▼
        ⚡ KDS SLA       🍕 Sales       👥 Staff
          Analysis       Analysis       Analysis
              │              │              │
              └──────────────┼──────────────┘
                             ▼
                    ┌──────────────────┐
                    │ Business Insights│
                    └──────────────────┘


 # 🧰 Technology Stack

 | Technology | Purpose |
| --- | --- |
| 🐍 **Python 3.9+** | Data analysis |
| 🐼 **Pandas** | Data manipulation & analytics |
| 🐘 **PostgreSQL** | Transaction database |
| 📊 **Pivot Tables** | Multi-dimensional analysis |
| 🕐 **Datetime** | Time-based analysis |
| 📈 **KPI Analytics** | Performance measurement |


 # 📅 Project Timeline

 | Week | Date | Activities | Status |
| --- | --- | --- | --- |
| **Week 1** | 07 Sep – 13 Sep | Dataset search, PostgreSQL export setup, project planning | ✅ |
| **Week 2** | 14 Sep – 20 Sep | Data cleaning, missing values, timestamp preparation | ✅ |
| **Week 3** | 21 Sep – 27 Sep | Pandas analysis, KDS performance, visualization | ✅ |
| **Week 4** | 28 Sep – 04 Oct | KPI aggregation, validation and interpretation | ✅ |
| **Week 5** | 05 Oct – 13 Oct | Final report and presentation preparation | ✅ |
| 🎓 **Final Presentation** | **14 Oct** | Project presentation | 🎯 |


 # 🎓 Project Outcomes

 ## 🧠 Key Learnings

 The project provided practical experience in connecting:


Business Requirements
        ↓
Database Data
        ↓
Data Cleaning
        ↓
Data Analysis
        ↓
KPI Calculation
        ↓
Business Insights


 ### Main Learning Areas

 - Understanding business requirements and SLAs
- Working with relational database exports
- Transforming PostgreSQL data into Pandas DataFrames
- Cleaning transactional data
- Performing group-by analysis
- Creating pivot tables
- Working with datetime data
- Calculating operational KPIs
- Translating analytical results into business insights


 # 🐍 Pandas Skills Developed

 ### 🔹 Data Manipulation

df.drop_duplicates()
df.dropna()
df.groupby()
df.sort_values()


 ### 🔹 Data Transformation


pd.to_datetime()
df.astype()
df.dt.hour


 ### 🔹 Analytical Operations


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


 ### Example Output

 | Date | Total Revenue | Total Orders | Avg. Sync Delay |
| --- | --- | --- | --- |
| 2025-09-07 | — | — | — |
| 2025-09-08 | — | — | — |
| 2025-09-09 | — | — | — |



 # 📝 Conclusion

 The **Operational Performance & Sales Analytics for Gourmet Dining LLC** project demonstrates how data analytics can be applied to restaurant operations to identify workflow bottlenecks and measure operational performance.

 The analysis focuses on three central areas:

 > ⚡ **KDS synchronization**\
>  🍽️ **Operational efficiency**\
>  💰 **Sales performance**

 Based on the project analysis:

 - ⚡ **96.4%** of orders achieved sub-second KDS synchronization.
- ⏱️ Reported average KDS latency was **0.42 seconds**.
- 🕒 Average order processing time was **11.8 minutes**.
- 🍽️ Major demand periods were identified during **13:00–15:00** and **19:00–22:00**.
- 🍕 The top **20% of menu items** accounted for more than **65% of total sales revenue**.

 The project demonstrates the complete process of transforming raw transactional data into structured KPIs and operational insights using **PostgreSQL and Pandas**.



 # 📚 References

 ### 🗄️ Dataset

 **Gourmet Dining LLC Production Database**

 - PostgreSQL schema
- Restaurant transaction records
- Operational transaction logs

 ### 📖 Documentation

 - Pandas Documentation
- PostgreSQL Documentation



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
| Records | \< 1 sec | \< 15 min | Top 20% Items |

\</div\>


 \<div align="center"\> # 🍽️ Gourmet Dining LLC

 ### Turning Restaurant Data Into Operational Insights

 **IT Project Management — Project 1**

 \<br\> 🐍 **Python** • 🐼 **Pandas** • 🐘 **PostgreSQL**

 \<br\> ⭐ **Thank you for visiting our project!**

 \</div\> \`\`\`
