# CECILIA_ANU-CAPSTONE-PROJECT
### SALES DATA ANALYSIS & CUSTOMER DATA PROJECT 

## Table of Contents
1. [Overview](#overview)
2. [Data Sources](#data-sources)
3. [Tools_Used](#tools_used)
4. [Data Integration](#data-integration)
5. [Experimental Data Analysis](#experimental-data-analysis)
6. [Data Analysis](#data-analysis)
7. [Data Visualizations](#data-visualizations)
8. [Conclusion](#conclusion)
   
### 1. Overview
---
This Data Analysis project aims to gererate insight into the sales performance of a Sales transaction from different categories. The goal is to deliver an interactive and visually appealing dashboard that helps stakeholders easily understand sales performance across various dimensions, and also to Provide Insight into the Revenune, and different other summaries contained within the data. The objective of this project is to create an automated, dynamic reporting system using Power BI that pulls data from Microsoft SQL Server and Excel. The reporting solution enables users to explore and monitor key metrics with interactive dashboards, saving time on manual report creation and improving access to real-time data insights..

### 2. Data Source
---
The Primary sourcs of Data here is Salesdata.csv and this is an open source that can was given to work with by the Incubators hub, tagged capstone project Dataset.

- Built a Power BI dashboard to visualize sales data, focusing on metrics like total sales, product performance, and regional breakdowns.
- Incorporate findings from Excel and SQL analyses to ensure a comprehensive view of the data.
- Enable users to interact with the dashboard and drill down into specific data points.

### 3. Tools Used 
---

Excel: Used for initial data preparation, stakeholder data submission, and certain manual calculations
  1.  For Data cleanig (www.microsoft.com)
     -*Excel File: Use the *Get Data option to connect to the Excel file. Select the relevant tables or sheets that contain summarized sales data, such as total sales, regional breakdowns, and monthly sales
      
- -Microsoft SQL Server:r(For Quering and Analysis) As the primary data source for structured storage and query processing.
  2. *Connect to Data Sources*:
  - *SQL Server Data: Use *Get Data > SQL Server to connect to the SQL Server database and import key tables. Enter your SQL Server credentials and select tables with insights like top-performing products, sales by region, and customer data.
- *Performance Optimization*: Consider indexing columns like TransactionDate, ProductID, and Region to improve query performance.
- *Data Validation*: it Ensure the data loaded in SQL Server matches the source file.
- *Customizations*: it Adapt queries to reflect your data structure or analysis needs.
    
- Power BI: For data visualization and dashboarding.
- *Power BI Desktop*: We used Power BI Desktop application for building the dashboard.
 3. *Basic Power BI Knowledge*: Familiarity with Power BI visualizations, data modeling, and DAX.
  
-Github for Portfolio Building 
-The Documentation of all we have to dis on the project in detailed format and also creating an avenue for your work to be viewed and seen by other people

### 4. Data Integration (ETL Process)
---

Extract, Transform, Load (ETL):
Extraction: Data is extracted from SQL Server using SQL queries to fetch relevant tables, views, and stored procedures.
Transformation:
SQL Procedures: Preprocessing in SQL Server using stored procedures to join tables, filter records, and aggregate data.
Power Query: Additional transformations performed within Power BI to handle specific calculations, data reshaping, and data type adjustments.
Load: Transformed data is loaded into Power BI’s data model for analysis and visualization.
At the initail phase of the Data cleaning and preparations , certains operations were performed
Data Loading and Inspection 
Handling Missing Variables 
Handling Balnk Spaces in the proces of loading the salesdata.csv into the SQL 
Data Cleaning and categorization 


### 5. Experimental Data Analysis
---
EDA involves the exploring of the Data to answer some questions about the Data such as;

-What is the total sales for each product category.
-Whats the sales transactions for each region. 
-How to find the highest-selling product by total sales value.
-How to Calculate total revenue per product.
-How to calculate the monthly sales totals for the current year. 
-How to find top 5 customers by total purchase amount.
-How to calculate the percentage of total sales by each region
-How to identify products with no sales in the last quarter.


### 6. Data Analysis 
---
This is where we include some basic line of code or queries;

```SQL
CREATE DATABASE LITA_ANUOLU_db
---CREATE DATABASE LITAANUOLUDB;

SELECT * FROM SalesDataCsv;

select Product, sum(Total_sales) as Total_sales
from [dbo].[SalesDataCsv]
Group by product 

select Region,count(Total_sales) as Number_of_sales
from [dbo].[SalesDataCsv]
Group by Region
```

```SQL
---Customer Segmentation
select*from [dbo].[CustomerDataCsv]

---Total Customers by Region
select Region, count(customerName) as Number_of_Customers
from [dbo].[CustomerDataCsv]![Uploading ANU EXCEL CUSTOMER DATA 2.jpg…]()

Group by Region 
```
```SQL
---Total number of cancelled subscription
SELECT 
    CASE 
        WHEN SubscriptionEnd IS NULL THEN 'Active'
        ELSE 'Canceled'
    END AS Subscriptiontype,
    COUNT(CustomerID) AS Total_Subscriptions
FROM [dbo].[CustomerDataCsv]
GROUP BY 
    CASE 
        WHEN SubscriptionEnd IS NULL THEN 'Active'
        ELSE 'Canceled'
    END;
```

*Data Validation*:
   - Review data in Power BI to ensure that imported figures match Excel and SQL outputs
### Dashboard Components
 *Sales by Month Line Chart*:
   - Add a Line Chart to show monthly sales trends over time.
   - Drag Transaction Date to the X-axis and SalesAmount to the Y-axis, and format to display month-over-month performance.

#### Regional Breakdown
1. *Regional Sales Map*:
   - Use a Map visualization to display sales by region geographically.
   - Drag Region to the location field and Total Sales to size or color, depending on the preferred visualization.

2. *Region Comparison Column Chart*:
   - Use a Clustered Column Chart to compare sales by region.
   - Place Region on the X-axis and Total Sales on the Y-axis for a clear comparison.

-. Interactivity Features

This allow the users to drill down and filter data:
- *Slicers*:
  - Add slicers for fields like Product Category, Region, and Time Period to allow users to filter views.
- *Drill-Throughs*:
  - Enable drill-through functionality to allow users to click on specific data points (e.g., region or product) and view details.
- *Tooltips*:
  - Customize tooltips to show extra data when hovering over visual elements (e.g., show percentage contribution or customer insights on region breakdowns).

### 7. Data Visualization
---
### The SQL screenshots for SAles Data Execution 
![AC Q1](https://github.com/user-attachments/assets/aa093450-0e29-46b7-af30-a3ba1a102b75)
![AC Q2](https://github.com/user-attachments/assets/3a9d53a3-4b8c-474c-8fe2-b8da1a20a411)
![AC Q3](https://github.com/user-attachments/assets/2fd37967-fce6-4835-a022-eeff78489d8d)
![AC Q4](https://github.com/user-attachments/assets/24223dcc-17be-42a5-bc1b-52c44a6634b0)
![AC Q5](https://github.com/user-attachments/assets/361f1b70-338b-480b-ad99-bbeef0dbf99f)
![AC Q6](https://github.com/user-attachments/assets/353aa62b-62be-41bc-b0bb-48d7d993dbb1)
![AC Q7](https://github.com/user-attachments/assets/e28a32b8-a98e-495f-a331-2bbea6dfdc01)
![AC Q8](https://github.com/user-attachments/assets/e97366a0-582b-405e-a798-7df90eacb8ed)

### The SQL Screenshots for Customer Data Execution

![CD A1](https://github.com/user-attachments/assets/5176e819-7efe-4545-94fd-3d60dfbeb777)
![CD A2](https://github.com/user-attachments/assets/cdbca658-9b78-4122-81bf-761ddfc1cc78)
![CD A3](https://github.com/user-attachments/assets/cb7c2dca-8119-4948-bc69-eae577cb4896)
![CD A4](https://github.com/user-attachments/assets/34b45f95-9997-4cea-954d-852edda2428c)
![CD A5](https://github.com/user-attachments/assets/b3de820f-4c8c-42dd-bd30-95e1eb3b365a)
![CD A6](https://github.com/user-attachments/assets/e63ed469-f5dc-4efb-abb2-c48866e47256)
![CD A7](https://github.com/user-attachments/assets/4101d9cf-7860-4b93-a24e-4911950af4ce)
![CD A8](https://github.com/user-attachments/assets/4776ff57-6041-44de-8a9c-1d89dc2393f1)
![CD A9](https://github.com/user-attachments/assets/f37eec58-086a-4c37-acc4-2dfac0ae6bab)

### The Power BI screenshots
![ANU PAGE 1](https://github.com/user-attachments/assets/b681253f-4951-4794-91df-a29647fa8620)
![CECILIA LITA PBI PAGE 2](https://github.com/user-attachments/assets/fd4c707e-17e3-46df-ba54-b15e6fd846d2)

### The Excel Screenshots and Graphs
![EXCEL GRAGH CUST DATA](https://github.com/user-attachments/assets/a11b0fa6-6105-4f93-bd6c-d3c05662af8b)
![EXCEL CUST DATA](https://github.com/user-attachments/assets/5a0a6bcb-50a6-4990-bca4-a541fdfb0c91)
![CECILIA LITA PBI PAGE 2](https://github.com/user-attachments/assets/9b692870-47f7-4a57-bb53-0df31864eb24)
![ANU PAGE 1](https://github.com/user-attachments/assets/ebb2238e-04ae-4ab5-9ce5-fef2afbc11a0)
![SALES DATA SUMMARY EXCEL](https://github.com/user-attachments/assets/3109076e-4cb8-44b8-b671-bc80bb7b29b4)
![EXCEL GRAPH](https://github.com/user-attachments/assets/71d990c3-25e7-405b-8224-82673d62d3aa)


### 8. Conclusion
"This project offers a comprehensive solution to Sales Data.csv by utilizing (https://www.microsoft.com), (https://www.microsoft.com/power-bi),(https://www.microsoft.com/sqlserver) With the steps provided,i have a complete setup and a good understanding of how to use [Cecilia_Anu-Capstone-Project] effectively."

Benefits and Impact:
"By implementing the project i could attempt and conveninetly work on the project given. It enhances my development process and provides a solid foundation for further enhancements."

Encourage Feedback and Contributions:i am open to users to contribute to my project, report issues, or suggest improvements. Link to the (https://github.com/Cecilia-Mercy/CECILIA_ANU-CAPSTONE-PROJECT/edit/main/README).


"Thank you for using [(https://github.com/Cecilia-Mercy/CECILIA_ANU-CAPSTONE-PROJECT/edit/main/README.md)] and being part of our community! We look forward to seeing how you make the most of it."
