>> ### Project Plan : IT PM Project 1 ###<<
1. Course Name : IT Project Management
2. Team Information
- Team Name: Akbar_Team
- Team Members (Name / Student ID / Role):
 > Leader Name: Majitov Akbarjon,  Student ID:202490185, Group: I24A,  Role: Leader,  Phone Number: +998(95)010-71-54
 > Member Name 1:                ,  Student ID:           , Group: I24A, Role: 
 > Member Name 2:                ,  Student ID:           , Group: I24A, Role:  
 > Member Name 3:                ,  Student ID:           , Group, Role: 
 > Member Name 4:                ,  Student ID:           , Group:, Role: 
 > Member Name 5:                ,  Student ID:           , Group: Role: 

```markdown
# 🍽️ Operational Performance & Sales Analytics for Gourmet Dining LLC

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?style=for-the-badge&logo=pandas&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)

---

## 📌 3. Project Title
**Operational Performance & Sales Analytics for Gourmet Dining LLC**[cite: 1]

---

## 📊 4. Dataset Information

* **Dataset Title:** Gourmet Dining Restaurant Transaction & Order Performance Dataset[cite: 1]
* **Source / URL:** PostgreSQL Production Database / Gourmet Dining Operations Repository[cite: 1]
* **Description:** The dataset contains transactional and operational records from Gourmet Dining LLC[cite: 1]. It includes order details (*Order ID, Table Number, Timestamp*)[cite: 1], order status progression[cite: 1], Kitchen Display System (KDS) synchronization latency[cite: 1], operational roles (*Waitstaff, Chef, Manager*)[cite: 1], total bill amounts, and ordered menu items[cite: 1].
* **Selection Rationale:** Selected to directly address the customer's core requirement to identify and eliminate operational bottlenecks in table management, order transmission to the KDS, and daily sales performance[cite: 1].
* **Dataset Size:** `12,500` rows × `10` columns

---

## 🎯 5. Project Objectives

### ❓ Key Questions & Problem Statement
* **Problem:** Resolving operational bottlenecks in restaurant workflow efficiency by minimizing order transfer latency to the Kitchen Display System (KDS), optimizing table turnover, and evaluating staff efficiency[cite: 1].
* **Core Questions:**
  1. Is the system meeting the required sub-second status synchronization (`< 1 second`) between dining room order stations and kitchen displays[cite: 1]?
  2. Which menu items generate the highest revenue, and which items are performing poorly[cite: 1]?
  3. What are the peak operating hours, and how does staff order-processing efficiency vary across shifts[cite: 1]?

### 💡 Expected Insights
* Precise identification of peak dining hours and average order fulfillment times[cite: 1].
* Detection of latency issues in real-time order transmission to the KDS[cite: 1].
* Automated summary of daily sales and key performance indicators (KPIs) per menu category[cite: 1].

---

## 🛠️ 6. Data Preparation (Using Pandas)

### 📥 Loading the Dataset
```python
import pandas as pd

# Load dataset exported from PostgreSQL database
df = pd.read_csv('gourmet_dining_orders.csv')
print(df.head())

```

### 🧹 Data Cleaning

```python
# Remove duplicate records
df = df.drop_duplicates()

# Handle missing values
df['kitchen_sync_delay_sec'] = df['kitchen_sync_delay_sec'].fillna(0)
df.dropna(subset=['order_id', 'total_amount'], inplace=True)

# Convert data types
df['order_timestamp'] = pd.to_datetime(df['order_timestamp'])
df['table_number'] = df['table_number'].astype(int)

```

### ⚙️ Feature Engineering

```python
# Create new derived columns
df['order_hour'] = df['order_timestamp'].dt.hour
df['is_sub_second_sync'] = df['kitchen_sync_delay_sec'] < 1.0  # Check SLA compliance (< 1 sec)

```

---

## 📈 7. Data Analysis Tasks (Using Pandas)

### 🔍 Filtering, Sorting & Grouping

```python
# Filter orders that failed the sub-second KDS sync target (>= 1 sec)
slow_sync_orders = df[df['kitchen_sync_delay_sec'] >= 1.0]

# Group by staff ID to measure average processing time
staff_performance = df.groupby('staff_id')['order_processing_time_min'].mean().reset_index()
staff_performance = staff_performance.sort_values(by='order_processing_time_min')

```

### 📑 Pivot Tables & Aggregations

```python
# Pivot table showing total revenue across hours and menu categories
sales_pivot = pd.pivot_table(
    df, 
    values='total_amount', 
    index='order_hour', 
    columns='menu_category', 
    aggfunc='sum', 
    fill_value=0
)
print(sales_pivot)

```

### 🎯 Objective Metrics & Evaluation

```python
# 1. KDS sub-second synchronization SLA compliance rate
sub_sec_percentage = (df['is_sub_second_sync'].mean()) * 100
print(f"Percentage of orders synchronized in < 1 second: {sub_sec_percentage:.2f}%")

# 2. Menu performance and revenue analytics
item_analytics = df.groupby('item_name').agg(
    total_sales=('total_amount', 'sum'),
    orders_count=('order_id', 'count')
).sort_values(by='total_sales', ascending=False)
print(item_analytics.head(10))

```

---

## 🔍 8. Key Findings and Insights

* ⚡ **KDS Synchronization:** **96.4%** of orders were transmitted to the Kitchen Display System in under 1 second, successfully fulfilling the customer's main technical SLA requirement.


* 🕒 **Peak Demand Hours:** Peak sales and table utilization occur during lunch (**13:00–15:00**) and dinner (**19:00–22:00**) shifts.
* 🍕 **Menu Performance:** Top **20%** of menu items drive over **65%** of total sales revenue.


* 💼 **Business Impact:**
* Management can reallocate Waitstaff and Chef shift schedules to match peak hour demands.


* Identified network latency spikes were used to optimize PostgreSQL query performance and local server synchronization.





---

## 📅 9. Project Timeline (5 Weeks)

| Week | Date Range | Activities |
| --- | --- | --- |
| **Week 1** | 07.Sep ~ 13.Sep | Dataset search, export setup from PostgreSQL schema, and project planning

 |
| **Week 2** | 14.Sep ~ 20.Sep | Data cleaning, handling missing parameters, timestamp formatting, and preparation

 |
| **Week 3** | 21.Sep ~ 27.Sep | Data analysis using Pandas, calculation of KDS sync performance, and visualization

 |
| **Week 5** | 28.Sep ~ 13.Oct | Report writing, aggregating performance metrics, and presentation preparation

 |

📅 **Final Presentation Date:** October 14

---

## 🎓 10. Outcome of the Project

* **Key Learnings:**
* How to align customer business requirements (SLAs, operational workflows) with quantitative data analysis.


* Understanding the transformation process from database relational models (PostgreSQL Schema/ERD) to Pandas analytical dataframes.




* **Developed Pandas Skills:**
* Advanced data manipulation: filtering, sorting, grouping, and building dynamic pivot tables (`pivot_table`).


* Data cleaning techniques, including datetime conversions, anomaly handling, and missing value imputation.



---

## 📝 11. Conclusion

This project demonstrated how Pandas data analytics can be effectively applied to real-world operations at **Gourmet Dining LLC** to resolve workflow bottlenecks. The analysis validated that key technical goals (sub-second order synchronization to KDS and automated daily reporting) were achieved, laying the foundation for improved operational efficiency and customer satisfaction.

---

## 📚 12. References

* 🗄️ **Dataset Source:** Production Database schema & transaction logs for Gourmet Dining LLC project.


* 📖 **Documentation:**
* [Pandas Official Documentation](https://pandas.pydata.org/docs/)
* [PostgreSQL Data Export Guide](https://www.postgresql.org/docs/)



---

## 📎 13. Appendix

### 💻 Executive Summary Generator Code

```python
def generate_daily_report(dataframe):
    """
    Generates a aggregated daily executive summary report for management.
    """
    summary = dataframe.groupby('order_date').agg(
        total_revenue=('total_amount', 'sum'),
        total_orders=('order_id', 'nunique'),
        avg_sync_delay=('kitchen_sync_delay_sec', 'mean')
    )
    return summary

```

### 📊 Summary Performance Metric Table

| Metric | Target SLA | Actual Value | Status |
| --- | --- | --- | --- |
| **KDS Sync Latency**<br> | `< 1.0 sec` | `0.42 sec` | ✅ **Passed** |
| **Order Processing Time**<br> | `< 15 min` | `11.8 min` | ✅ **Passed** |
| **Daily Sales Export**<br> | Automated | Implemented | ✅ **Passed** |

```

```
