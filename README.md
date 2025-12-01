📊 Sales Performance Dashboard – Power BI (B2B Hardware Company | 2017 Analysis)

This project presents an interactive Sales Performance Dashboard built in Power BI for a B2B computer hardware company to analyze 2017 sales performance.
The dashboard consolidates previously fragmented reports and provides a single source of truth for revenue, sales pipeline outcomes, regional trends, agent productivity, and customer lifecycle insights.

🚀 Project Overview

The sales leadership team lacked unified visibility across:

Regions (Headquarters, North, South, West)

Sales teams & individual agents

Product-level profitability

Customer segmentation & retention

Year-over-year comparisons

This dashboard solves that problem by integrating multiple datasets into a robust analytical model, enabling real-time decision-making, performance optimization, and revenue forecasting.

🧭 1. Business Problem

Leadership struggled with:

Disconnected spreadsheets and inconsistent KPIs

No clear visibility into YTD vs previous year performance

Difficulty pinpointing where performance dropped

Lack of insights into customer retention, agent productivity, and regional efficiency

No single platform to observe conversion funnels or lost opportunities

This created reactive decision-making and delayed interventions in declining regions/products.

🎯 2. Project Goal

Design a Power BI dashboard that:

Consolidates all 2017 sales data

Tracks Revenue, Units Sold, AOV, CLV, Conversion Rates

Visualizes regional & team-level performance

Segments customers by size, industry, region, and purchase behaviour

Measures quarterly trends & identifies growth drop-off points

Provides actionable insights for leadership to improve sales efficiency

🛠️ 3. Data Preparation (Power Query – M Language)
Key Steps
Step	Activities Performed
Data Extraction	Imported CSV files (Accounts, Sales Pipeline, Products, Sales Teams, Dates)
Cleaning	Removed duplicates, fixed data types, replaced nulls
Feature Engineering	Added Company Size, Client Segments, Continents
Date Table (M Query)	Built custom Date dimension (2016–2017)
Validation	Removed inconsistencies in product naming & agent mapping
🧩 4. Data Modelling (Star Schema)
Fact Table

sales_pipeline

Dimension Tables

accounts

sales_team

products

date

sales_funnel

🔷 Star Schema Diagram
         accounts           products          sales_team
             |                 |                  |
             |                 |                  |
             ---------------------------------------
                           sales_pipeline
                                 |
                                 |
                                date

⭐ Key DAX Measures
Measure	Purpose
Conversion Rate	Secured Deals / Total Deals
Avg Purchase Value	SUM(close_value) / Secured Deals
Client Lifetime	First vs Last engagement date difference
CLV (Lifetime Value)	Purchase Frequency × Avg Purchase Value × Avg Lifespan
Avg Cycle Time	Days between engagement & closure
Revenue Growth	(Current – Previous) / Previous
📈 5. Dashboard Features & Visuals
a) Company-Level KPIs

Total Sales: $9.48M

Units Sold: 3,988

YTD vs Previous Year Comparison

Quarterly Trend Chart: Highlights 44.48% drop in Q4

Product Mix Treemap

b) Regional Performance Analysis
Region	Highlight
North Zone	Highest revenue: $3.36M
Headquarters	Highest monthly order volume: 1531 units
South Zone	Highest Average Purchase Value: $2.67K
Americas	85% of customers, 95% from US
c) Sales Team & Agent Insights

Melvin’s team → $2.1M (highest-performing)

Dustin’s team → $1.0M

Rocco’s team → outperforms Cara (nearly double revenue)

Agents with fewer orders but high basket values → under-utilized opportunities

Avg sales cycle of 40–48 days shows optimal performance zone

d) Customer Segmentation & Retention

85 customers, 64 are Silver-tier

Industry dominance:

Retail: 753

Technology: 642

Large enterprises = 80.2% of revenue

Retention stable but drops sharply in Month 12

CLV Avg: $116K

Customer lifetime ~ 380 days

🔍 6. Key Insights Generated
📉 1. Revenue Drop in Q4

Q2 strongest ($3M)

Q4 saw a 44.48% decline (Nov–Dec being worst performing months)

🌍 2. Regional Opportunities

West region drives most revenue

South region has strongest purchase value → ideal for cross-selling

Headquarters brings highest order frequency

👥 3. Sales Team Dynamics

Performance gaps exist within same region

Conversion rate alone isn’t the best metric → order volume & AOV matter more

Certain agents high-value but low-frequency → targeted coaching potential

🧿 4. Customer Behaviour Patterns

Heavy reliance on US large enterprises

Small & medium businesses under-penetrated

Loyalty drops at year-end → indicates engagement gaps

🏆 7. Business Impact

The dashboard shifted leadership decisions from reactive → proactive.

✔ Resource Optimization

Reallocated efforts to high-potential regions like South for upselling.

✔ Enhanced Sales Coaching

Identified agents needing:

AOV improvement

More client follow-ups

Shorter cycle times

✔ Improved Customer Retention

Insights helped design:

Renewal offers

Personalized outreach

Tier upgrade strategies (towards Platinum)

✔ Forecasting & Strategy Planning

Dashboard allowed:

Monthly and quarterly forecasting

Target-setting per team

Monitoring real-time KPIs

📂 8. Project Files & Schema Documentation
Datasets Used
1. Accounts.csv (85 rows)

Key fields:

Company Size

Continent

Sector

Revenue

Client Segments (Bronze/Silver/Gold/Platinum)

Retention metrics

2. Date.csv (438 rows)

Year, Month, Day, Quarter

YTD flag

Used for time intelligence functions

3. Products.csv (7 rows)

Product

Series (GTX/MG)

Sales Price

4. Sales_Funnel.csv

Lead

Interaction

Secured

5. Sales_pipeline.csv (8800 rows)

Contains:

Opportunity details

Stage (Lost / Secured)

Close value

Product

Agent

Dates

6. sales_team.csv (35 rows)

Sales agent

Manager

Region

🔢 9. Important DAX Measures Reference
Client Lifetime Calculation
Client Lifetime = 
DATEDIFF(
    MIN(sales_pipeline[engage_date]),
    MAX(sales_pipeline[engage_date]),
    DAY
)

Conversion Rate
Conversion Rate = 
DIVIDE([Secured], COUNTROWS(sales_pipeline), 0)

Avg Purchase Value
Avg Purchase Value = 
SUM(sales_pipeline[close_value]) / [Secured]

Client Retention
Client_Retention = 
DIVIDE([Retained_Clients], [Prev_Month_Clients], 0)

🖥️ 10. How to Use This Dashboard

Load all CSVs into Power BI

Apply transformations in Power Query

Set up star schema in Model View

Create DAX measures for KPIs

Build visuals:

KPI Cards

Funnel chart

Treemap

Decomposition Tree

Line charts

Donut charts

Agent comparison matrix

Enable slicers:

Region

Product

Customer segment

Sales team

🌟 11. Final Outcomes

Using this dashboard, leadership can now:

View consolidated metrics in seconds

Detect weakness in regions or products early

Improve agent performance with data-driven coaching

Identify high-value and at-risk customers

Benchmark quarter-over-quarter growth

Boost retention and loyalty programs

This project demonstrates strong skills in Power BI, M Query, DAX, Data Modeling, KPI Engineering, and Business Analytics.

📬 12. Contact

For suggestions, collaborations, or feedback:

Developer: Darrsheni Sapovadia
Role: Data Analyst & AI Engineer
Location: Navi Mumbai, India
