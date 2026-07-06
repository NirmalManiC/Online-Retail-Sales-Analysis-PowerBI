Online Retail Sales Analysis - Excel & Power BI Project
This project takes a raw e-commerce transaction dataset, cleans it in Excel, and builds an interactive Power BI dashboard to analyze sales performance, product popularity, and customer behaviour for a UK based online gift retailer.

Project Overview
The Online Retail dataset contains around 541,000 transaction records from 1 December 2010 to 9 December 2011. The raw data was cleaned and prepared in Excel, then loaded into Power BI, where a star schema data model, DAX measures, and a three page interactive report were built to answer questions about sales trends, top products, and customer value.

Tools Used
•	Microsoft Excel - data cleaning, transformation and pivot tables
•	Power BI Desktop - data modelling, DAX measures, report building
•	Power BI Service - publishing the report online
•	UCI Machine Learning Repository - source of the raw dataset

Dataset
Source: Online Retail dataset, UCI Machine Learning Repository
Time period: 1 December 2010 - 9 December 2011
Rows after cleaning: 392,692 (from an original ~541,000 rows)
Grain: one row per product line item, per invoice

Columns
Column	Description
InvoiceNo	Unique transaction number. Numbers starting with C are cancelled orders.
StockCode	Unique product code.
Description	Product name.
Quantity	Units sold in the transaction line.
InvoiceDate	Date of the transaction.
UnitPrice	Price per unit, in GBP.
CustomerID	Unique customer number.
Country	Customer's country.
Sales	Quantity x UnitPrice, added during cleaning.
Year / Month Name / Quarter	Date breakdown columns added for reporting.

Project Structure
Online-Retail-Analysis/
|-- Online_Retail_Raw.xlsx          (original dataset)
|-- Online_Retail_Cleaned.xlsx       (cleaned dataset - Excel stage)
|-- OnlineRetail_PowerBI.pbix        (Power BI report file)
|-- Online_Retail_PowerBI_Report.pdf (exported dashboard, PDF)
|-- Online_Retail_Project_Document.docx  (full project write up)
|-- README.docx                      (this file)

Data Cleaning (Excel)
•	Removed around 132,000 rows with a blank Customer ID.
•	Removed duplicate rows.
•	Removed cancelled orders (invoice numbers starting with C) and negative quantities.
•	Standardized the InvoiceDate column and added Year, Month Name and Quarter columns.
•	Added a calculated Sales column (Quantity x UnitPrice).
•	Checked and corrected data types across key columns.
•	Built pivot tables to check totals before moving to Power BI.

Power BI Data Model
A star schema was built with one fact table and four dimension tables, joined on active one to many relationships:
•	FactSales - InvoiceNo, InvoiceDate, Quantity, UnitPrice, Sales, CustomerID, StockCode, Country
•	DimCustomer - CustomerID, Country
•	DimProduct - StockCode, Description
•	DimDate - Date, Month, Month Name, Quarter, Year
•	DimCountry - Country

DAX Measures
12 measures were built for the report, including Total Sales, Total Orders, Distinct Customers, Average Order Value, Sales per Customer, Monthly/Quarterly/YTD Sales, and % of Total Sales.
Report Pages
•	Sales Overview - KPI cards, monthly sales trend (with year to month drill down), country distribution, map
•	Product Analysis - top products by sales, product detail table, treemap
•	Customer Analysis - customers by country, KPI cards, top customers table

Interactivity
•	Slicers for Year, Country and Month Name on each page
•	Drill down on the monthly sales trend chart (Year to Month level)
•	Bookmarks: Sales Overview - Default, Product Analysis - Default, Customer Analysis - Default, UK 2011 Performance

Key Insights
•	Total sales for the period were about 9 million pounds, from around 19,000 orders and 5 million units sold.
•	The United Kingdom made up about 82% of total sales.
•	Paper Craft, Little Birdie and Regency Cakestand 3 Tier were the two top selling products by value.
•	A small group of customers generated a disproportionate share of total sales.

How to Use
•	Open OnlineRetail_PowerBI.pbix in Power BI Desktop.
•	Use the Year, Country and Month Name slicers on each page to filter the data.
•	Click a year on the Monthly Sales Trend chart and use the drill down arrow to view month level detail.
•	Use the Bookmarks pane to jump to a saved report view.

