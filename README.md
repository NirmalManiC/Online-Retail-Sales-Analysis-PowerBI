# Online Retail Sales Analysis – Excel & Power BI Project

## Project Overview

This project analyzes a large e-commerce transaction dataset using Microsoft Excel and Power BI. The raw dataset was cleaned and transformed in Excel and then loaded into Power BI to build an interactive sales analytics dashboard.

The dashboard is designed to analyze sales performance, identify top-performing products and markets, and understand customer purchasing behaviour for a UK-based online gift retailer.

The project demonstrates an end-to-end data analytics workflow involving data cleaning, transformation, data modelling, DAX calculations, interactive visualization, and business insight generation.

---

## Project Objective

The main objectives of this project are to:

- Clean and transform raw online retail transaction data.
- Prepare an analysis-ready dataset using Microsoft Excel.
- Build a star schema data model in Power BI.
- Create DAX measures for key business metrics.
- Analyze overall sales performance and sales trends.
- Identify top-selling products.
- Analyze customer purchasing behaviour.
- Compare sales performance across countries.
- Build an interactive Power BI dashboard using slicers, drill-downs, and bookmarks.
- Generate meaningful business insights to support data-driven decision-making.

---

## Tools & Technologies Used

| Tool / Technology | Purpose |
|---|---|
| Microsoft Excel | Data cleaning, transformation, calculated fields, and Pivot Tables |
| Power BI Desktop | Data modelling, DAX calculations, and dashboard development |
| Power BI Service | Publishing and accessing the Power BI report online |
| UCI Machine Learning Repository | Source of the Online Retail dataset |

---

## Dataset Information

The project uses the **Online Retail dataset** from the UCI Machine Learning Repository.

| Dataset Detail | Information |
|---|---|
| Dataset | Online Retail |
| Domain | Retail / E-commerce / Sales Analytics |
| Source | UCI Machine Learning Repository |
| Time Period | 1 December 2010 – 9 December 2011 |
| Original Records | Approximately 541,000 rows |
| Records After Cleaning | 392,692 rows |
| Data Grain | One row per product line item per invoice |

The dataset contains transactional data from a UK-based online retailer selling gift items to customers across multiple countries.

---

## Dataset Columns

| Column | Description |
|---|---|
| InvoiceNo | Unique transaction number. Invoice numbers starting with `C` represent cancelled orders |
| StockCode | Unique product code |
| Description | Product name or description |
| Quantity | Number of units sold in the transaction |
| InvoiceDate | Date and time of the transaction |
| UnitPrice | Price per unit in GBP |
| CustomerID | Unique customer identifier |
| Country | Customer's country |
| Sales | Calculated as Quantity × UnitPrice |
| Year | Year extracted from InvoiceDate |
| Month Name | Month extracted from InvoiceDate |
| Quarter | Quarter derived from InvoiceDate |

---

## Data Cleaning and Transformation – Excel

The raw dataset was cleaned and transformed using Microsoft Excel before being loaded into Power BI.

The following preprocessing tasks were performed:

- Removed approximately 132,000 records with blank Customer IDs.
- Removed duplicate records.
- Removed cancelled transactions where InvoiceNo starts with `C`.
- Removed records containing negative quantities.
- Standardized the InvoiceDate column.
- Verified and corrected data types for key columns.
- Created the `Sales` calculated column using:

`Sales = Quantity × UnitPrice`

- Created the `Year` column for yearly analysis.
- Created the `Month Name` column for monthly analysis.
- Created the `Quarter` column for quarterly analysis.
- Applied filtering and sorting to validate the dataset.
- Created Pivot Tables to summarize and verify key totals before loading the dataset into Power BI.

After completing the data cleaning process, the final cleaned dataset contained **392,692 records**.

---

## Power BI Data Model

A **Star Schema** data model was implemented in Power BI.

The model contains one central fact table and four dimension tables.

### Fact Table

**FactSales**

The FactSales table contains transactional sales data:

- InvoiceNo
- InvoiceDate
- Quantity
- UnitPrice
- Sales
- CustomerID
- StockCode
- Country

### Dimension Tables

**DimCustomer**

- CustomerID
- Country

**DimProduct**

- StockCode
- Description

**DimDate**

- Date
- Month
- Month Name
- Quarter
- Year

**DimCountry**

- Country

The dimension tables are connected to the FactSales table using active **one-to-many relationships**.

This star schema improves data organization, reporting performance, and analytical flexibility.

---

## DAX Measures

A total of **12 DAX measures** were created to calculate key business metrics and support dashboard analysis.

The measures include:

- Total Sales
- Total Orders
- Total Quantity
- Distinct Customers
- Average Order Value
- Sales per Customer
- Monthly Sales
- Quarterly Sales
- Year-to-Date Sales
- Previous Period Sales
- Sales Growth Percentage
- Percentage of Total Sales

These DAX measures provide dynamic calculations based on slicers, filters, and report interactions.

---

## Power BI Dashboard

The final Power BI report contains **three interactive report pages**.

### 1. Sales Overview

The Sales Overview page provides a high-level view of overall business performance.

Visualizations include:

- Total Sales KPI Card
- Total Orders KPI Card
- Distinct Customers KPI Card
- Total Quantity KPI Card
- Monthly Sales Trend
- Sales by Country
- Country Sales Distribution
- Geographic Sales Map

The Monthly Sales Trend supports **Year-to-Month drill-down analysis**.

---

### 2. Product Analysis

The Product Analysis page focuses on product-level sales performance.

Visualizations include:

- Top Products by Sales
- Product Sales Detail Table
- Product Sales Contribution Treemap
- Product-level sales comparison

This page helps identify high-performing products and understand product contribution to overall revenue.

---

### 3. Customer Analysis

The Customer Analysis page analyzes customer purchasing behaviour and customer value.

Visualizations include:

- Distinct Customer KPI
- Sales per Customer KPI
- Customers by Country
- Top Customers by Sales
- Customer Sales Detail Table

This page helps identify high-value customers and understand customer concentration across countries.

---

## Dashboard Interactivity

The Power BI dashboard includes multiple interactive features to improve the user experience.

### Slicers

The following slicers are available:

- Year
- Country
- Month Name

These slicers allow users to dynamically filter dashboard data.

### Drill-Down

The Monthly Sales Trend visualization supports drill-down from:

`Year → Month`

This allows users to analyze monthly sales performance within a selected year.

### Bookmarks

The following bookmarks were created:

- Sales Overview – Default
- Product Analysis – Default
- Customer Analysis – Default
- UK 2011 Performance

Bookmarks allow users to quickly navigate to predefined analytical views.

---

## Key Business Insights

The dashboard analysis identified several important business insights.

### Sales Performance

- Total sales during the analyzed period were approximately **£9 million**.
- Approximately **19,000 orders** were processed.
- Around **5 million units** were sold.
- Approximately **4,000 unique customers** placed orders.
- The average order value was approximately **£480**.

### Country Analysis

- The **United Kingdom contributed approximately 82% of total sales**.
- The Netherlands, Ireland, Germany, and France were among the other important markets.
- The high dependency on UK sales indicates potential opportunities for international market expansion.

### Product Analysis

- **Paper Craft, Little Birdie** was one of the highest-selling products by sales value.
- **Regency Cakestand 3 Tier** was also among the top-performing products.
- Several high-performing products were low-priced, high-volume items.
- Product sales were concentrated among a group of popular products.

### Customer Analysis

- A relatively small group of customers generated a significant proportion of total sales.
- The business depends heavily on high-value customers.
- These customers may represent wholesale or bulk purchasers.
- Customer retention strategies should focus on protecting relationships with high-value customers.

---

## Analytical Insights

### Descriptive Analysis

The dashboard provides a summary of historical business performance.

Key findings include:

- Approximately £9 million in total sales.
- Around 19,000 orders.
- Approximately 5 million units sold.
- Around 4,000 unique customers.
- The United Kingdom generated the majority of total sales.

### Diagnostic Analysis

The analysis identified several factors influencing business performance:

- Sales are highly concentrated in the United Kingdom.
- The business has limited sales contribution from several international markets.
- High-volume products contribute significantly to overall sales.
- A small number of customers contribute a large proportion of total revenue.
- The apparent sales decline in December 2011 is caused by the dataset ending on 9 December 2011 and should not automatically be interpreted as an actual business decline.

### Predictive Analysis

The current dashboard focuses primarily on descriptive and diagnostic analytics.

Future improvements could include:

- Sales forecasting.
- Customer purchase prediction.
- Product demand forecasting.
- Customer churn analysis.
- Seasonal trend forecasting.

Power BI forecasting functionality could be applied to the monthly sales trend to estimate future sales performance.

### Prescriptive Analysis

Based on the dashboard findings, the following business actions are recommended:

- Develop retention strategies for high-value customers.
- Expand sales efforts in markets such as Germany, France, and Australia.
- Increase marketing activities in countries with growth potential.
- Maintain sufficient inventory for high-volume products.
- Bundle popular products with slower-selling products.
- Use targeted promotions to increase average order value.
- Continuously monitor monthly sales trends and customer concentration.

---

## Project Structure

```text
Online-Retail-Sales-Analysis-PowerBI/
│
├── DA-V8 Mini Project Guidelines.pdf
│
├── OnlineRetail_PowerBI.pbix
│
├── OnlineRetail_PowerBI_README.docx
│
├── OnlineRetail_PowerBI_live_dashboard_export.pdf
│
├── Online_Retail_Cleaned.zip
│
├── Online_Retail_Excel_Project_Document.docx
│
├── Online_Retail_PowerBI_Project_Screenshots.docx
│
├── Online_Retail_Project_Document.pdf
│
├── Power BI Project Document Template.docx
│
├── Step_By_Sytep_Guide_Excel_Process_Project_Online_Retail.docx
│
├── Task3_PowerBI_Complete_Step_Step_Guide.docx
│
└── README.md
