# Data-Warehousing-Business-Intelligence
Data Warehouse and Business Intelligence for Contoso Retail (ETL, Dimensional Modeling, Power BI, Tableau)

## Objective
- Developed Multi-Dimensional data model (STAR Schema) and enhanced it to meet growing requirements. 
- Created a centralized data warehouse, pipelining retail data from diverse data sources using Talend Implemented Slowly Changing         Dimensions, Rejection codes, and Performance tuning on a dataset with 48 million rows. 
- Built interactive dashboards to convey stories of retail sales and customer segmentation using Tableau and PowerBI.

## Overview
This project involves a retail company that sells a variety of products to people and to businesses across a variety of sales channels.

The Retail Company would like to:
Create a data warehouse (DW) from its various systems of record (SORs)
Create BI applications that enable analysis of business performance

The DW will store (facts) in the following subject areas:
Sales
Inventory
Sales Quotas
Strategy Plans

### Retail
The categories of products sold:
Audio
TV and Video
Computers
Cameras and camcorders 
Cell phones
Music, Movies and Audio Books
Games and Toys
Home Appliances
The Retail Company would like to:
Create a data warehouse (DW) from its various systems of record (SORs)
Create BI applications that enable analysis of business performance

### Observations in SOR
- Different unique key for product’s table across all SORs e.g. ProductID, BrandID, ProductLabel
- Length of the values were different across SORs
- Data type for dates in the CSV and TXT files are not constant.

### Data Profiling
- Changed the SOR Load and Update dates from TIMESTAMP to DATE for Oracle and PostgreSQL to load SOR_LOADDATE
- Converted data type values for DATES to DATE data type across all the CSVs and Text input files
- For SCDs DimProductPrice and DimProductCost we had to use SOR dimproduct (MySQL) as a bridge between input file price_cny_step_1_of_4   and DIMPRODUCT
- Converted all the possible columns in the target metadata from Big Decimal to INT
- Data Type csv contains all the column’s data type which we kept constant across all the SORs and Target table depending upon the
  size of data
- Had to append zeros and trimmed values in the for joining product tables

### Reject Codes and Error Handling
- Reject Codes are used to catch bad data,missing values or invalid data present in the facts rejects
- Reject Reasons help you understand the bad data in detail
- Handled null values using Relation.ISNULL function and applied code 99 if nulls are found

![image](https://user-images.githubusercontent.com/47194856/78525513-61a90f00-77a5-11ea-93aa-b8d5f61ce4c3.png)

### Currency Conversion
![image](https://user-images.githubusercontent.com/47194856/78525619-b0ef3f80-77a5-11ea-9a6e-bcbd3b38c9ab.png)

### Talend Job Summary
![image](https://user-images.githubusercontent.com/47194856/78523693-9a45ea00-779f-11ea-81af-46a1504c88b7.png)

### Master Job Screenshot
![image](https://user-images.githubusercontent.com/47194856/78523800-edb83800-779f-11ea-93a1-639e9c4f00ea.png)

### BI PowerBI Visualizations

### Online Sales Analysis
![image](https://user-images.githubusercontent.com/47194856/78524554-4a1c5700-77a2-11ea-8ee6-452b966cdd39.png)

### Overall Sales Analysis
![image](https://user-images.githubusercontent.com/47194856/78524642-8059d680-77a2-11ea-9fe9-881a55bbb752.png)

### Reject Analysis
![image](https://user-images.githubusercontent.com/47194856/78524713-bbf4a080-77a2-11ea-9550-12f009a33ef1.png)

### Sales Quota & Strategy Analysis
![image](https://user-images.githubusercontent.com/47194856/78524749-e5adc780-77a2-11ea-95bd-32b1e58ee3df.png)


## BI Talend Visualizations
![image](https://user-images.githubusercontent.com/47194856/78524163-2c022700-77a1-11ea-9baf-78670b17ecc0.png)

![image](https://user-images.githubusercontent.com/47194856/78524411-e1cd7580-77a1-11ea-951c-8b1ca72dd477.png)

![image](https://user-images.githubusercontent.com/47194856/78524458-032e6180-77a2-11ea-8c5a-1070b72ff39a.png)

## Authors
Uthsav Shetty

Sheetal Shekar

Praful Badami




