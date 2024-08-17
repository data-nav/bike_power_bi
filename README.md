

# Pallmall Bikes Performance Analysis (2021-2022)

This project provides a comprehensive analysis of Pallmall Bikes' performance over two years (2021 and 2022). By integrating data from multiple sources and utilizing SQL for data preparation, we've developed an interactive Power BI dashboard that highlights key performance indicators (KPIs), trends, and revenue analysis.

## Project Overview

The goal of this project is to deliver a detailed analysis of Pallmall Bikes' business performance. The analysis includes:
- **Interactive Dashboard**: A dynamic Power BI dashboard featuring essential KPIs.
- **SQL Queries**: SQL scripts used for calculating revenue and order metrics.
- **Data Visualization**: A variety of charts, including donut and funnel charts, for enhanced insights.
- **Performance Analysis**: Identification of best and worst sellers to optimize business strategies.
- **Trend Analysis**: Visualization of daily and monthly trends to support better decision-making.
- **Data Preparation**: Data enhancement with custom columns and DAX functions.

## Highlights

- **📊 Interactive Dashboard**: A user-friendly Power BI dashboard showcasing essential KPIs.
- **🛠️ SQL Queries**: Efficient SQL queries used for calculating revenue and order metrics.
- **📈 Data Visualization**: Use of diverse chart types for meaningful insights, including donut and funnel charts.
- **🔍 Performance Analysis**: Analysis of best and worst-selling products to refine business strategies.
- **📅 Trend Analysis**: Visualization of daily and monthly trends to facilitate informed decision-making.
- **⚙️ Data Preparation**: Data modification and enhancement through custom columns and DAX functions.
- **📚 Comprehensive Learning**: Suitable for beginners and intermediates to develop practical skills.

## Key Insights

- **✅ Data Integration**: Combining SQL and Power BI provides a holistic view of business performance.
- **📈 Trend Visualization**: Daily and monthly trends offer valuable insights into sales performance and customer behavior.
- **🧩 Custom Calculations**: Adding custom columns like total revenue and quantity simplifies data analysis.
- **💡 Visual Storytelling**: Effective chart and KPI usage enables clear communication of data findings to stakeholders.
- **🔄 Interactive Filters**: Interactive dashboard features allow users to explore data dynamically.

## Data Sources

The data for this analysis was sourced from two CSV files containing revenue reports for 2021 and 2022. These files were imported into MSSQL Server for further processing.

## SQL Query

The following SQL query was used to combine data and calculate the necessary metrics:

```sql
WITH cte AS (
    SELECT * FROM bike_share_yr_0
    UNION ALL
    SELECT * FROM bike_share_yr_1
)
SELECT
    dteday,
    season,
    a.yr,
    weekday,
    hr,
    rider_type,
    riders,
    price,
    COGS,
    riders * price AS revenue,
    riders * price - COGS AS profit
FROM cte a
LEFT JOIN cost_table b ON a.yr = b.yr;
```

## Dashboard Features

### Key Performance Indicators (KPIs)

- **Total Profit**: $10.45M
- **Total Revenue**: $15M
- **Total Riders**: 3M

### Visualizations

- **KPI Over Time**: A line and bar chart showing riders, average profit, and average revenue over time.
- **Profit Margin and Sum of Profit**: A donut chart highlighting the profit margin.
- **Sum of Riders by Rider Type**: A donut chart illustrating the distribution of registered and casual riders.
- **Sum of Revenue by Season**: A bar chart displaying revenue across different seasons.
- **Hourly Revenue**: A heatmap representing revenue distribution across different hours.

