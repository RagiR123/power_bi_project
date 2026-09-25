# power_bi_project
Superstore Business Intelligence & Customer Analytics Dashboard
An end-to-end Power BI business intelligence project built using the Kaggle Superstore dataset to demonstrate practical skills in data preparation, dimensional modeling, DAX, customer analytics, operational analysis, and interactive dashboard development.
The project transforms raw Superstore, People, and Returns datasets into a structured star-schema data model and an interactive multi-page Power BI report designed to answer key business questions across sales, profitability, products, customers, returns, and operational performance.

Project Objectives
The dashboard is designed to help business and BI stakeholders:
Monitor overall sales, profitability, customers, orders, and returns.
Identify high- and low-performing products and categories.
Analyze customer value, purchasing behavior, and retention risk.
Evaluate return patterns and operational efficiency.
Track sales and profit trends over time.
Analyze profitability across products, categories, states, regions, and shipping modes.
Segment customers using RFM (Recency, Frequency, Monetary) analysis.
Provide interactive drill-through analysis from high-level KPIs to individual product and order details.

Data Sources
The project uses three Kaggle Superstore datasets:
Superstore — transactional sales and order-level data.
People — regional/people information.
Returns — returned-order information.
The original flat files were imported into Power BI and transformed using Power Query.

Data Preparation & Power Query
The data preparation layer includes:
Data type correction and validation.
Locale-based date conversion for date fields.
Appropriate data types for numeric, categorical, and identifier fields.
Column removal and restructuring.
Creation of a Geography Key for geographic modeling.
Creation of Shipping Days using order and ship dates.
Left outer joins to incorporate return and people information into the appropriate dimension tables.
Separation of staging and analytical tables using Power Query references.
Disabled load for the initial staging datasets to keep the model focused on analytical tables.

Data Model
The report follows a star-schema architecture, with Fact Superstore serving as the central fact table.
Fact Table
Fact Superstore
Contains transactional metrics and keys including:
Order ID
Order Date
Ship Date
Ship Mode
Customer ID
Product ID
Sales
Quantity
Discount
Profit
Geography Key
Shipping Days

Dimension Tables
Dim Customer
Customer ID
Customer Name
Segment
Dim Product
Product ID
Product Name
Sub-Category
Category

Dim Order
Order ID
Order Date
Ship Date
Ship Mode
Customer ID
Returned

Dim Geography
Country
City
State
Postal Code
Region
Geography Key

Person
A dedicated Date Table is also used for time intelligence, containing year, quarter, month, month name, year-month, day, day name, and day number attributes.
The model uses one-to-many relationships from dimensions to the fact table, while the Customer RFM analysis is connected to the Customer dimension.

Customer RFM Analysis
A dedicated Customer RFM table was developed for customer segmentation and risk analysis.
The analysis includes:
Recency
Frequency
Monetary value
R, F, and M scores
RFM total score
RFM segment
At-risk flag
Customer ID
Last purchase date
Analysis date
This enables identification of customer groups such as high-value, loyal, inactive, and at-risk customers and provides a foundation for targeted customer analysis.

Dashboard Pages
1. Executive Summary
Provides a high-level overview of business performance.
KPIs:
Total Sales
Total Profit
Total Customers
Total Orders
Return Rate
Average Order Value

Interactive filters:
Year
Category
Region

Visual analysis:
Sales by State
Sales & Profit Trend
Profit by Sub-Category
Return Rate by Segment
Sales & Profit by Category

2. Product Performance
Analyzes product and category-level performance.
KPIs:
Total Sales
Total Products
Total Orders
Total Profit
Return Rate
Average Order Value

Analysis includes:
Sales and Profit by Category
Top 5 Products
Bottom 5 Products
Product performance matrix
Segment and Year filtering

A dedicated Product Details drill-through page provides deeper analysis for individual products.
Product Details KPIs:
Sales YoY %
Profit YoY %
Total Sales
Total Quantity
Total Orders
Average Order Value
Return Rate %
Average Selling Price
The page also uses field parameters to dynamically analyze product performance across dimensions such as:
Segment
City
Ship Mode
Region
Additional analysis includes:
Sales & Profit trends
Profitability by State
Product-level order details

3. Customer & Segment Analysis
Focuses on customer value, engagement, and risk.
KPIs:
Active Customers
Total Customers
Customer Revenue
Average Revenue per Customer
Repeat Customer %
At-Risk Customers
At-Risk Revenue
At-Risk Revenue %
Analysis includes:
Customer segment distribution
Revenue by RFM segment
Return risk by RFM segment
Return rate
Customer and segment-level detail matrix
This page combines traditional customer segmentation with RFM-based behavioral analysis to identify customer value and potential retention risks.

4. Returns & Operational Risk
Provides visibility into returns and shipping performance.
KPIs:
Total Orders
Returned Orders
Return Rate %
Returned Sales
Returned Profit
Average Shipping Days
On-Time Orders
On-Time Delivery Rate %
Analysis includes:
Monthly return trends
Return rate by region
Operational efficiency by shipping mode
Return rate by category
Year-based filtering

Interactive Reporting Features
The report incorporates several Power BI features to improve exploration and usability:
Slicers and cross-filtering
Drill-through analysis
Field parameters
Tooltips
Dynamic KPI calculations
Top/Bottom product analysis
Interactive matrices
Time-series analysis
Product-level order detail
RFM customer segmentation
A dedicated Product Performance Tooltip provides contextual information including:
Total Orders
Profit Margin %
Average Discount
Sales per Order
Top Sub-Category
Top Product
Product-level profitability and return metrics

DAX & Analytical Techniques
The project uses DAX to build reusable business metrics and analytical calculations, including functions and techniques such as:
CALCULATE
FILTER
SWITCH
DATEDIFF
RANKX
REMOVEFILTERS

Time-intelligence calculations
YoY analysis
Dynamic KPI calculations
Ranking analysis
Customer segmentation
RFM scoring
Return and operational metrics

Key Power BI Skills Demonstrated
Data Preparation
Power Query
Data cleansing
Data type management
Query referencing
M transformations
Merge operations

Data Modeling
Star schema
Fact and dimension design
Primary/foreign key concepts
One-to-many relationships
Date dimension
Model optimization through staging and analytical layers

DAX & Analytics
Measure development
Filter context
Time intelligence
Ranking
Dynamic calculations
RFM segmentation
KPI development

Visualization & Reporting
Executive dashboards
Drill-through pages
Tooltips
Field parameters
Interactive slicers

KPI cards
Trend analysis
top5/ bottom 5 product analysis

Business Value
The report provides a consolidated analytical view of the Superstore business, allowing stakeholders to move from executive-level performance monitoring to detailed product, customer, geographic, and operational analysis.
The combination of a structured star schema, reusable DAX measures, RFM customer segmentation, and interactive drill-through functionality demonstrates an end-to-end approach to building a business-ready Power BI analytical solution from raw data.

Tools & Technologies
Power BI Desktop
Power Query / M
DAX
Data Modeling
Star Schema

Outcome
This project demonstrates an end-to-end Data/BI Analyst workflow: transforming raw data, designing a dimensional model, developing analytical measures, applying customer segmentation techniques, and delivering an interactive business intelligence solution for decision support.
