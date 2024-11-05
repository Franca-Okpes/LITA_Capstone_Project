# LITA_Capstone_Project

## Project Title: Sales Performance Analysis for a Retail Store 

[Project Overview](#project-overview)


[Data Sources](#data-sources)


[Tools Used](#tools-used)


[Data Cleaning and Preparations](#data-cleaning-and-preparations)


[Exploratory Data Analysis (EDA)](exploratory-data-analysis-eda)


[Data Analysis](#data-analysis)


[Data Visualization](#data-visualization)


### Project Overview
---
This repository contains an analysis of retail store sales performance. The project explores sales data to identify key insights, including top-selling products, regional performance, and monthly sales trends. The goal is to create an interactive Power BI dashboard that effectively visualizes these findings.

### Data Sources
---
 The primary source of Data used here is a DataSale.xlsx which is an open source Data that can be freely downleaded from an open source online such as Kaggleor FRED or any other Data repository site.

### Tools Used
---
The tools used in analysing the Dataset from the retail shop are
-  Microsoft Excel [Download Here](https://www.microsoft.com)
   1.  For Data cleaning
   2.  For Analysis
   3.  For Data Visualization

-  SQL Structure Query [Download Here](https://www.microsoft.com/en-us/evalcenter/download-sql-server-2019)
   1. SQL Structure Query Language for Quering Data
  
-  Power Bi [Download Here](https://www.microsoft.com/en-US/download/details.aspx?id=58494)
   1. Power Bi for visualization of the analysis carried out on Microsoft Excel and SQL
  
-   Github for Portfolio Building

  ### Data Cleaning and Preparations
---
 In the initial phase of Data cleaning and preparation, I performed the following action;
1. Data Importation and Inspection
2. Handling missing variables
3.   Data Cleaning and Formatting
    
 ### Exploratory Data Analysis (EDA)
 ---
 Exploratory Data Analysis (EDA) helps uncover insights by addressing key questions such as:
 -   Which product is the top seller?
 -   How does performance vary across regions?
 -   What are the monthly sales trends?
 -   What is the total revenue?
 -   How much revenue does each product generate annually?

### Data Analysis
---
This is the section I included my basic lines of code or queries or even some of the DAX (Data Analysis Expression) ecpressions used during the analysis; 
- Eg

  ```SQL
  SELECT
  Product,
    SUM(revenue) as total_sales 
FROM [dbo].[LITA+Capstone+SalesDataset]
GROUP BY Product
ORDER BY Product
  ```SQL
  
 ```SQL
SELECT
product,
sum (revenue) as highest_selling_product
from[dbo].[LITA+Capstone+SalesDataset]
group by product
order by 2 desc
 ```

```SQL
SELECT 
    region,
    SUM(revenue) AS region_revenue,
    CAST(
        (SUM (revenue) * 100.0) / 
        (SELECT SUM(revenue) FROM [dbo].[LITA+Capstone+SalesDataset])
    AS DECIMAL(10,2)
	)AS revenue_percentage
	FROM [dbo].[LITA+Capstone+SalesDataset]
GROUP BY region
ORDER BY revenue_percentage DESC;
```

```EXCEL
=AVERAGEIF(C:C, "shirt",H:H)
```
```EXCEL
TOTAL REVENUE
=F2*G2
```

### Data Visualization
---

![Pie-chart Logo](https://github.com/user-attachments/assets/8f0387f8-25f0-4257-99da-419063691e4c)


![Line chart for monthly sales trend](https://github.com/user-attachments/assets/56eb6a4e-f69d-486c-ac79-58aba3f7277d)


![Line chart showing customer purchase](https://github.com/user-attachments/assets/ea30022c-083c-45ad-91d3-bc95f5ccf3e4)
