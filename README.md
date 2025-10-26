The Banking Risk Analysis Project is a complete data analytics pipeline integrating MySQL, Python, and Power BI.  
It analyzes customer-level financial data to assess risk exposure, loan performance, and revenue potential, supporting data-driven decision-making in the banking domain.

The project demonstrates how to connect MySQL Workbench to Python (Jupyter Notebook) for data extraction, perform Exploratory Data Analysis (EDA), and visualize results using Power BI dashboards and automated PDF reports.

Objectives:

- Establish a MySQL-Python-Power BI data pipeline.
- Perform EDA on customer data to identify risk and performance patterns.
- Calculate "Processing Fees", "Total Loan", and "Total Deposit" using DAX and Python.
- Design an interactive "Power BI Dashboard" for decision-makers.
- Generate an analytical report.


Tech Stack:

Database - MySQL Workbench,ms excel
Programming - Python (pandas, numpy, matplotlib, seaborn) 
Data Visualization - Power BI 
Reporting - Power BI PDF Exports, MS Word 
Environment - Jupyter Notebook 
Version Control - Git & GitHub 

Database Integration (MySQL → Python → Power BI)

This project connects MySQL Workbench to Python to extract banking data dynamically, clean it, and forward it to Power BI for visualization.

Data Analysis Workflow

1️⃣ Data Extraction
Queried customer data from MySQL database (banking_case.customer).

Imported data into Python using mysql.connector.

2️⃣ Data Cleaning & Feature Engineering (Python)
Removed missing and inconsistent values.

Created Income Bands and Fee Structures.

Calculated Processing Fees dynamically.

3️⃣ Exploratory Data Analysis (EDA)
Correlation analysis of loan, deposit, and income.

Risk segmentation based on income bands.

Gender and nationality-based client behavior analysis.

Visualized patterns using seaborn and matplotlib.

KPI Definitions (Power BI DAX)
KPI	Formula	Description

Total Clients	DISTINCTCOUNT('customer'[Client ID])	Count of unique clients
Total Loan	SUM('customer'[Total Loan])	Overall loan exposure
Total Deposit	SUM('customer'[Total Deposit])	Total client deposits
Processing Fees	SWITCH(TRUE(), [Fee Structure]="High",0.05, [Fee Structure]="Mid",0.03, [Fee Structure]="Low",0.02)	Fee % by structure
Total Fees	SUMX('customer', [Total Loan] * [Processing Fees])	Total processing fee revenue

Power BI Dashboards
🔹 1. Loan Analysis Dashboard
Loan breakdown by Income Band, Gender, and Bank Type.

Highlights top-performing and high-risk clients.

🔹 2. Deposit Analysis Dashboard
Deposits segmented by Nationality, Occupation, and Age Group.

Liquidity and customer retention patterns visualized.

🔹 3. Summary Dashboard
Aggregated KPIs: Total Loan, Total Deposit, Processing Fees, Clients.

Provides an executive overview for management decisions.

Key Insights: 

Insight	Description
High-income clients	Show highest loan and credit card balances
Credit card balance	Strongly correlated with total loans
Private banks	Lead in total client base and lending exposure
Processing fees	Provide stable non-interest revenue
Loan-to-deposit ratio	Key metric for liquidity and risk

MySQL Database → Python EDA → Power BI Dashboard → Report Generation

"Turning raw financial data into actionable banking insights." 
