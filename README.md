Project Overview
This project aims to provide a detailed analysis of Pallmall Bikes' performance over two years
(2021 and 2022). By integrating data from multiple sources and using SQL for data preparation,
we've created an interactive and insightful Power BI dashboard that highlights key performance
indicators (KPIs), trends, and revenue analysis.
Highlights
● 📊Interactive Dashboard: A dynamic Power BI dashboard with essential KPIs.
● 🛠️SQL Queries: SQL queries for calculating revenue and order metrics.
● 📈Data Visualization: Various charts, including donut and funnel charts, for insights.
● 🔍Performance Analysis: Analyze best and worst sellers to optimize business
strategies.
● 📅Trend Analysis: Visualize daily and monthly trends for better decision-making.
● ⚙️Data Preparation: Modify and enhance data with custom columns and DAX
functions.
● 📚Comprehensive Learning: Aimed at beginners and intermediates for practical skills
development.
Key Insights
● ✅Data Integration: Combining SQL and Power BI enhances analytical capabilities,
offering a complete view of business performance.📊
● 📈Trend Visualization: Daily and monthly trends provide crucial insights into sales
performance and customer behavior.📅
● 🧩Custom Calculations: Adding custom columns like total revenue and quantity
streamlines data analysis.🔢
● 💡Visual Storytelling: Effective use of charts and KPIs helps communicate data
findings clearly to stakeholders.📉
● 🔄Interactive Filters: Interactive features in dashboards allow users to explore data
dynamically.
Data Sources
The data for this analysis comes from two CSV files containing revenue reports for 2021 and
2022. These were exported into MSSQL Server for further processing.
SQL Query
The following SQL query was used to combine and calculate the necessary metrics:
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
LEFT JOIN cost_table b ON a.yr = b.yr
Dashboard Features
Key Performance Indicators (KPIs)
● Total Profit: $10.45M
● Total Revenue: $15M
● Total Riders: 3M
Visualizations
● KPI Over Time: A line and bar chart showing riders, average profit, and average
revenue over time.
● Profit Margin and Sum of Profit: A donut chart highlighting the profit margin.
● Sum of Riders by Rider Type: A donut chart showing the distribution of registered and
casual riders.
● Sum of Revenue by Season: A bar chart displaying revenue across different seasons.
● Hourly Revenue: A heatmap representing revenue distribution across different hours.
