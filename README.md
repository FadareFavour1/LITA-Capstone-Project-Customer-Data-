# LITA-Capstone-Project-Customer-Data-

## Contents
[Project Title](#Project-Title)

[Project Overview](#Project-Overview)

[Data Cleaning](#Data-Cleaning)

[Exploratory Data Analysis](#Exploratory-Data-Analysis)

[Data Visualization](#Data-Visualization)

[Conclusion](#Conclusion)



## Project Title
**Customer Data Analysis**
## Project Overview

### Introduction 
The Customer Data Analysis project aims to gain insights into customer behavior, subscription patterns, and revenue generation through a comprehensive examination of customer data. By analyzing various attributes such as customer demographics, subscription types, and financial contributions, this project seeks to identify trends, evaluate customer retention, and inform strategic business decisions.

### Objectives
1. Understand Customer Segmentation: Analyze customer data to identify distinct segments based on subscription types and regional distribution.
2. Analyze Subscription Lifecycles: Examine the relationship between subscription duration and revenue, and identify patterns related to subscription cancellations.
3. Identify Factors Influencing Churn: Investigate the reasons behind subscription cancellations and their impact on overall revenue.

### Data Description
The dataset comprises several key features that provide insights into customer characteristics and behaviors, including:
- CustomerId: Unique identifier for each customer.
- CustomerName: The name of the customer.
- Region: Geographic location of the customer.
- Subscription Type: The type of subscription plan selected by the customer.
- Subscription Start: The date when the customer's subscription commenced.
- Subscription End: The date when the customer's subscription ended (if applicable).
- Canceled: A flag indicating whether the subscription has been canceled.
- Revenue: Total revenue generated from the customer.
- Subscription Duration: The length of time the customer has been subscribed.

### Methodology
The project will employ data analysis techniques using tools such as Excel, SQL Server, and Power BI. The analysis will focus on key metrics such as average subscription duration and the most popular subscription type, providing a robust understanding of customer dynamics.

### Expected Outcomes
By the end of this project, we aim to deliver actionable insights that can guide marketing strategies, improve customer retention efforts, and ultimately enhance overall business performance.

## Data Cleaning 
Data cleaning is a crucial step in the data analysis process, ensuring that the dataset is accurate, consistent, and usable for analysis. In this project, several data cleaning techniques were employed to prepare the customer data for analysis.
1. **Validating Data Types:**
- Ensured that each feature was of the correct data type (e.g., Subscription Start and Subscription End as date types, Revenue as a numeric type).
- Converted data types as necessary to facilitate accurate calculations and analysis.

2. **Creating New Features:**
- Derived additional features such as Subscription Duration by calculating the difference between Subscription End and Subscription Start for relevant records.
- The formula used is `=(F2-E2)`

  Through these data cleaning steps, the dataset was transformed into a reliable foundation for further analysis, enabling accurate insights into customer behavior and subscription dynamics.
  
## Exploratory Data Analysis 
This section describes how we analyzed the customer data to uncover key trends in cancellations and revenue by region and subscription type. We used Excel, SQL, and Power BI to perform these analyses.

### Excel Analysis 
Excel was utilized for its robust data visualization and analytical capabilities. The following analyses were conducted:

**Descriptive Statistics:**
Using Excel functions such as SUM, AVERAGEIF, and SUMIF, we calculated key metrics including Average Subscription Duration and Finding the most popular subscription type

- Average Subscription Duration : The formula used for this was `=AVERAGE(I2:I75001)`
- Basic Subscription Type : THe formula used to find this was `=COUNTIF(D2:D75001,D2)`
- Premium Subscription type : This formula was used `=COUNTIF(D2:D75001,D3)`
- Standard Subscription type : This was the formula used `=COUNTIF(D2:D75001,D5)`

**Pivot Tables:**
To facilitate a deeper understanding of the Customer data, Pivot Tables were employed in Excel. A Pivot Table is a powerful tool that allows users to summarize and analyze large datasets interactively, enabling quick insights into data patterns and trends.

Several Pivot Tables were created to explore different dimensions of the sales data :

1. Cancellation Rates by Subscription Type:


![image](https://github.com/user-attachments/assets/cafe9614-f2c5-4efc-bf83-911237ebbf11)



- Purpose: This setup shows how many subscriptions of each type were canceled versus how many remained active, helping us to identify problematic subscription types.

2. Total Revenue by Region and Subscription Type:

![image](https://github.com/user-attachments/assets/1bbd696c-44f5-4140-bb31-23ec9a749b07)

- Purpose: This helps to identify which regions are generating the most revenue and which subscription types are most popular in those regions.

3. Average Subscription Duration by Subscription Type:

![image](https://github.com/user-attachments/assets/096bed7b-2dd6-4370-9d8f-6f967b6c345e)

- Purpose : This provides insight into which subscription types have longer durations, indicating higher customer satisfaction or engagement.

4. Trend Analysis Over Time:
   
![image](https://github.com/user-attachments/assets/d766f57a-2938-4683-aa50-c974373c8d64)

- Purpose : It helps to identify peak subscription months and any seasonality in subscriptions.

   This analysis will help to make data-driven decisions to enhance customer retention and improve revenue strategies

Analysis Performed in SQL
SQL was employed for more complex queries and data manipulations, leveraging its ability to handle large datasets efficiently. Key analyses performed included:

- Total Number Of Customers from each Region
  ```sql
    SELECT Region, COUNT(CustomerName)AS NumberofCustomers
    FROM [LITA Capstone CustomerData]
    GROUP BY Region

- Most Popular Subscription Type by the Number of Customers
  ```sql
    SELECT TOP 1 SubscriptionType,COUNT(CustomerName) as NumberofCustomer
    FROM [dbo].[LITA Capstone CustomerData]
    GROUP BY SubscriptionType
    ORDER BY NumberofCustomer

- Customers who Canceled and their Subscription within 6 months
  ```sql
  SELECT CustomerID,CustomerName,SubscriptionType,SubscriptionStart,SubscriptionEnd
  FROM [LITA Capstone CustomerData]
  WHERE Canceled = 1
  AND DATEDIFF(Day,SubscriptionStart,SubscriptionEnd)<= 180

- The Average Subscription Duration for all Customers
  ```sql
  SELECT avg(Datediff(Day,SubscriptionStart,SubscriptionEnd)) AS AverageSubscriptionDuration 
  FROM [LITA Capstone CustomerData]

- Customers with Subscription longer than 12 months
  ```sql
    SELECT CustomerID,CustomerName,SubscriptionType,SubscriptionStart,SubscriptionEnd
    FROM [LITA Capstone CustomerData]
    WHERE Datediff(Day,SubscriptionStart,SubscriptionEnd) > 365

- Total Revenue by Subscription Type
  ```sql
    SELECT SubscriptionType, Sum(Revenue) AS TotalRevenue from [LITA Capstone CustomerData]
    GROUP BY SubscriptionType

- The Top 3 Regions by Subscription Cancellation
  ```sql
    SELECT TOP 3 Region,Count(CustomerID) AS Top3CanceledSubscription
    FROM [LITA Capstone CustomerData]
    WHERE canceled = 1
    GROUP BY Region
    ORDER BY Top3CanceledSubscription

- Total Number Of Active and Canceled Subscription
  ```sql
    SELECT Canceled,Count(CustomerID) AS TotalSubscription
    FROM [LITA Capstone CustomerData]
    GROUP BY Canceled

 ## Data Visualization 
  Data visualization is essential for uncovering patterns and trends in customer data, especially when analyzing subscription behaviors. Using Power BI is a powerful choice for this, given its flexibility and advanced visualization options. 
Here are some of the Visualization done in Power BI
- Average Subscription Rate
  This was done by creating measure on Power BI, the formula used was
  
  `AverageSubscriptionDuration = AVERAGE(CustomerData[Subscription Duration])`

 ![Screenshot (50)](https://github.com/user-attachments/assets/6c7aaa7d-52c2-45b9-b85a-1650ac2be0ed)


- Cancellation Rates by Subscription Type
  
Visualization Type : Pie Chart

![Screenshot (51)](https://github.com/user-attachments/assets/a09ce953-05a3-400a-8645-abcd05e75d9f)

Purpose : This chart highlights which subscription types have the highest cancellation rates, helping identify areas where retention strategies are needed.
From this Chart Basic Subscription has the highest Subscription rate

- Sum of Revenue By Region
 
Visualization Type : Donut Chart

  ![Screenshot (52)](https://github.com/user-attachments/assets/f129dec6-373c-4c8a-8dbe-02afd2a59684)

Purpose : It helps us to Know the Region with the highest Revenue

- Number of Active and Canceled Subscription: Filter was used to Seperate the Active and Canceled Subscription

Visualization Type : Card


![Screenshot (54)](https://github.com/user-attachments/assets/1120da1c-5994-4fd4-8b40-31e5efea554c)


![Screenshot (53)](https://github.com/user-attachments/assets/0eb82ca7-daff-4dc0-a3be-fc92b5883fc2)

- Monthly Subscription Trends
 
Visualization Type : Line Chart

![Screenshot (55)](https://github.com/user-attachments/assets/e8dd0144-6c68-496b-9224-09fc10df4ab0)

Purpose : This time-based analysis reveals seasonality or trends in new subscriptions, helping predict demand cycles or identify high-growth periods.

- Active Subscription by Subscription Type

Visualization Type : Pie Chart

![Screenshot (56)](https://github.com/user-attachments/assets/7961e4a4-fc76-409c-85d8-7699d3283a2a)

- Revenue by Subscription Type
 
Visualization Type : Pie Chart

![Screenshot (57)](https://github.com/user-attachments/assets/1e66cfd4-f0e8-46f8-962d-dc58f86a0727)

Purpose : This helps us to Know the Subscription Type that generates the highest Revenue


## Conclusion

### Objective Recap
The primary objective of this analysis was to uncover insights into customer subscription patterns, with a focus on identifying regions with high cancellation rates, understanding revenue contributions by subscription type, and exploring subscription duration trends.


### Key Findings 
 **Revenue Distribution**:
   - Basic Subscription Type consistently generates the highest revenue across all regions
     
 **Subscription Duration**:    
   - Customers on Basic Subscription Type tend to have longer durations, durations.
     
 **Seasonal Trends**:
   - A noticeable spike in new subscriptions occurs in August year, suggesting a seasonal pattern that may align with marketing campaigns or product launches.

## Recommendations
Based on these findings, the following recommendations are suggested:
1. **Focus on High-Performing Subscription Types**:
   - Increase marketing efforts for Basic Subscription, particularly in high-revenue regions, to maximize its performance. Additionally, consider improving the offerings of Premium and Standard Subscription or replacing it if it does not meet customer needs.
2. **Enhance Subscription Duration**:
   - For Basic Subscription, explore initiatives to increase subscription duration, such as discounts for long-term commitments or added features to boost engagement.
3. **Leverage Seasonal Demand**:
   - Prepare marketing campaigns to coincide with the spike, potentially maximizing new subscriptions through promotions or limited-time offers.


This analysis provides valuable insights that can drive targeted strategies to improve customer retention, boost revenue, and enhance overall customer satisfaction.
