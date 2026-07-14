E-COMMERCE DATASET CLEANING AND VISUALIZATION DOCUMENTATION
Author: Ibeh Doris Chinelo 
Dataset: Online Retail Transaction Records
 Date: July, 2026.

OBJECTIVE
To explore the e-commerce transaction data, perform data cleaning to handle missing and invalid values, create new features for analysis, and uncover insights through exploratory data analysis and visualization. The aim is to understand sales performance, customer behavior, product performance, and geographic revenue patterns.

DATASET OVERVIEW
The e-commerce dataset contains online retail transaction records from 1 Dec 2010 to 9 Dec 2011. Each row represents a product transaction and includes details such as InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, and Country. The original dataset had 541,909 rows and 8 columns.

LIBRARIES USED: pandas, matplotlib.pyplot, seaborn

DATA CLEANING PROCESS
The dataset was first loaded into Python using pandas. The file did not load properly with the default encoding, so it was loaded using encoding='latin1'. After loading the data, I checked the structure of the dataset, viewed the first few rows, checked the number of rows and columns, reviewed the data types, and identified missing values.

STEPS	ROWS	COLUMNS	ACTION TAKEN
Raw Dataset (Before cleaning)	It contained 541,909	It contained 8	Loaded Online Retail .csv with latin1 encoding.
Missing Values	541,909	8	Filled missing Description and CustomerID with "Unknown"
Invalid Data Removal	530,104	8	Removed rows where UnitPrice <= 0 or Quantity <= 0
Feature Engineering	530,104	13	Created Revenue, Year, Month, Day, MonthName
Final Clean Dataset	530,104	13	Dataset used for EDA and visualization

NEW COLUMNS ADDED
 Revenue = Quantity * UnitPrice. 
Year, Month, Day, MonthName = Extracted from InvoiceDate for trend analysis
NOTE: No rows were dropped due to missing values. Only ∼2.2% of rows were removed due to invalid transactions.
METRIC	VALUE TOTAL
Revenue	£9,747,747.93
Unique Customers	4,372
Unique Products	4,070
Countries Served	38
Avg Order Value	£376.36

VISUALIZATIONS CREATED
The following visualizations were created for the e-commerce dataset:
1.	Top 10 products by quantity sold 
2.	Top 10 countries by total revenue 
3.	Monthly revenue trend 
4.	Top 10 Most Purchased Products by Invoice Count
5.	Top 5 customer by total spend

KEY FINDINGS
 1. Top-selling products are dominated by a few high-demand decorative items, with one product significantly leading in quantity sold, product like WHITE HANGING HEART T-LIGHT HOLDER ranked 1st, followed by REGENCY CAKESTAND 3 TIER and JUMBO BAG RED RETROSPOT. This indicates strong customer preference patterns, creating opportunities for better inventory planning and targeted marketing strategies.
2. The United Kingdom overwhelmingly dominates revenue, contributing far more than all other countries combined. Other countries like Netherlands, EIRE, and Germany contribute relatively small and similar amounts, indicating low market penetration outside the UK.
