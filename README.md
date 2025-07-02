# DSA-Project-.-Amazon-Product-Review-Analysis-
This project aim at analysing product and customer review data to generate insights that can guide product improvements, marketing strategies and customer engagement.

---
### Exploratory Data Analysis (EDA)
EDA involved the exploration of Data to answer some questions about the Data in order to gain insights. The questions are categorized into two, which are: Sales Analysis and Product Analysis.
#### Sales Analysis
- What is the total sales per product ? 
- What is the total sales per month?
- What is the total sales per region?
- What is the revenue by region?
#### Product Analysis
- Which product sold the most?
- Which product are top sellers?
- What is the average sales per product?

---
### Data Analysis
This is where i include some basic lines of code or queries or even some of the DAX functions used during the analysis.These include
- SQL Queries
```SQL
SELECT* FROM [dbo].[Sales Data]
```
- To Retrieve Total Sales for each Product category
```SQL
SELECT Product, SUM (Total_Sales) as Sales_Per_State FROM [dbo].[Sales Data]
GROUP By Product
```
- To Find the Number of Sales Transaction in each Region
```SQL
SELECT Region, SUM(Total_Sales) as Sales_Transaction FROM [dbo].[Sales Data]
GROUP By Region
 ```
 - To Find the Highest Selling Product by Total Sales Value
```SQL
SELECT Product, SUM (Total_Sales) as Total_Sales FROM [dbo].[Sales Data]
GROUP By Product
Order By Total_Sales DESC
```
- To Calculate Total Revenue by Product
```SQL
SELECT Product, SUM (Revenue) as Total_Revenue FROM [dbo].[Sales Data]
GROUP By Product
```
- To Order Month Column
```SQL
ALTER TABLE [dbo].[Sales Data]
ADD Order_Month Nvarchar(50)
```
```SQL
UPDATE [dbo].[Sales Data]
SET Order_Month = DATENAME(month, OrderDate)
```
```SQL
ALTER TABLE [dbo].[Sales Data]
ADD Order_Year INT
```
```SQL
Update [dbo].[Sales Data]
SET Order_Year = Year (OrderDate)
```
- Monthly Sales For The Current Year
```SQL
SELECT  Order_Month, SUM (Total_Sales) AS Monthly_Sales FROM [dbo].[Sales Data]
WHERE Order_Year=2024
GROUP By Order_Month
```

---
### Data Visualization

#### Microsoft Excel Data Visualization
