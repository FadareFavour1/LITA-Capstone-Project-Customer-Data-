# LITA-Capstone-Project-Customer-Data-

## Contents
[Project Title](#Project-Title)

[Project Overview](#Project-Overview)

[Data Cleaning](#Data-Cleaning)

[Exploratory Data Analysis](#Exploratory-Data-Analysis)



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

Cancellation Rates by Subscription Type:

[image](https://github.com/user-attachments/assets/28d259bc-f552-4b55-aca8-541bdefeeef8)



Analysis Performed in SQL
SQL was employed for more complex queries and data manipulations, leveraging its ability to handle large datasets efficiently. Key analyses performed included:



   



 
  
