### DSA-Project

### Project Title: Amazon Products Review Analysis
### Table of Contents

- [Introduction](#introduction)

- [Project Overview](#project-overview)

- [Data Sources](#data-sources)

- [About the Dataset](#about-the-dataset)

- [Tools Used](#tools-used)

- [Data Cleaning and Preparations](#data-cleaning-and-preparations)

- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis)

- [Data Analysis](#data-analysis)

- [Data Visualization](#data-visualization)
  
---
### Introduction
 In today's data-centric business landscape, informed decision-making is crucial. This project involves analyzing Amazon product reviews to uncover key trends and generate actionable insights that can inform product development, marketing strategies, and consumer engagement. The goal is to provide a roadmap for product improvements and drive sustainable growth.
 
 --- 
### Project Overview

This data analysis project aims to generate insights into Amazon product reviews. By analyzing the data, i seek to extract valuable information from product categories and reviews to inform business decision-making. The analysis will focus on key insights, including:

- Total number of products under each category
- Total number of reviews per category
- Average discount percentage by product category
- Product with the highest average ratings
- Total potential revenue
- Distribution of product ratings
- Product with the highest number of reviews
- Unique products per price range
- Products with fewer than 1000 reviews
- Product category with the highest discount
- Top 5 products in terms of ratings and number of reviews
- Product with 50% discount and more
- Relationship between rating and level of discount

These insights will enable us to tell compelling stories around the data, identify best performance, and make informed decisions to optimize operations, enhance product improvements, marketing strategies, and consumer engagement."

---
 ###  Data Sources
The primary source of the Data used here is Sales Data.Csv. This is an open source data that an be freely downloaded from an open source online such as kaggle or any other data repository site.
 
---
### About the Dataset

The dataset contains information scraped from Amazon product pages,It consists originally of 16 columns and 1465 rows which was modified further for the purpose of the analysis. The dataset include:

• Product details: name, category, price, discount, and ratings

• Customer engagement: user reviews, titles, and content

•Each row represents a unique product, with aggregated reviewer data stored as comma-separated values


- OrderID: Unique identifier for each order placed by a customer

- CustomerID: Unique identifier of each customer

- Product: Products sold by the store

- Region : Region of each customers

- OrderDate: Date the order was placed
 
- Quantity: Quantity ordered for each product

- Price Each: Price of each product
  
- Total Sales:Total sales gotten for each product
  
- Revenue: Revenue generated from the product sold
  
---
### Tools Used
- Microsoft Excel {Download Here}{https://www.microsoft.com}
  1. For Data Cleaning, 
  2. For Analysis
  3. For Data Visualization

 - Structured Query Language {SQL] for Quering of Data
  
- PowerBI for Dynamic and Interactive Data Visualization.

- GitHub for Portfolio Building

---
### Data Cleaning and Preparations.
In the initial phase of the Data cleaning and preparations, the following actions were performed; 
 1. Data Loading and Inspection
 2. Handling Missing Variables
 3. Data Cleaning and Formatting

---
### Exploratory Data Analysis (EDA)
EDA involved the exploration of Data to answer some questions about the Data in order to gain insights. The questions include:

1. What is the average discount percentage by product category?

2. How many products are listed under each category?

3. What is the total number of reviews per category?

4. Which products have the highest average ratings?

5. What is the average actual price vs the discounted price by category?

6. Which products have the highest number of reviews?

7. How many products have a discount of 50% or more?

8. What is the distribution of product ratings (e.g., how many products are rated 3.0,4.0, etc.)?

9. What is the total potential revenue (actual_price × rating_count) by category?

10. How does the rating relate to the level of discount?
    
11. How many products have fewer than 1,000 reviews?
    
12. Which categories have products with the highest discounts?
    
13. Identify the top 5 products in terms of rating and n

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
