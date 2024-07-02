# Credit-Card-Analysis
## PROJECT OBJECTIVE
To develop a comprehensive credit card weekly dashboard that provides real-time insights into key performance metrics and trends, enabling stakeholders to monitor and analyze credit card operations effectively.
This project aims to analyze weekly credit card transaction data coupled with customer information to achieve the following objectives:

•	Measure KPI’s : To measure and analyze various aspects of credit card data such as Revenue generated, transaction volume, Total Interest earned, Delinquency Rate, Customer Acquisition Cost, Customer Satisfaction score . By monitoring these KPIs, businesses can assess their performance, identify areas for improvement, and make data-driven decisions to drive growth and profitability.

•	Revenue Analysis by Quarter, Week, and Month: Conduct analysis of revenue generated from credit card transactions, segmented by quarters, weeks, and months. This analysis aims to uncover revenue trends, seasonality effects, and fluctuations in customer spending patterns over time.


•	Customer Spending Habits and Card Category Analysis: Explore customer spending behaviors and preferences across different card categories (eg, gold, platinum) and expenditure types (eg, Bills, Entertainment, travel). By analyzing transaction data, businesses can gain insights into customer demographics, purchasing preferences, and spending patterns.

•	Customer Analysis based on Different Metrics: Analyze Revenue based on different customer information metrics such as Educational level, Customer Job type, Income group. 

•	Week-on-Week Revenue Comparison: Perform week-on-week revenue comparisons to identify trends, anomalies, and deviations from expected revenue patterns. By analyzing week-on-week revenue fluctuations, businesses can detect seasonal trends, promotional effects, and emerging market dynamics. This analysis enables proactive decision-making and timely interventions to capitalize on revenue opportunities or mitigate risks.

## SOFTWARE USED

•	PostgreSQL

•	Power BI

## DATA UNDERSTANDING  

The dataset provides detailed information on credit card transactions along with associated customer details for a comprehensive analysis of spending behavior and transaction patterns over a specified period. The data is structured to enable in-depth insights into credit card usage, spending trends, and customer profiles.


      Source : Kaggle
      Datasets : 2
      File type : .csv
      Records : 10,293
      Data span : Jan 2023 - Dec 2023
  

## CREATING DATABASE

•	Crafting a data repository within the framework of PostgreSQL,

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/337fef4c-12e8-46a8-9f62-2f1b189bf585)

•	Building tables for both Transaction and Customer data within the database

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/daf2ed29-af1c-44b5-b97c-eb5d7c9d601c)

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/7c0e8507-1cf3-4285-a4ae-26ee85b2974a)

## IMPORTING DATA INTO DB

Bringing raw csv data into the PostgreSQL database by slotting it into the tables that have created.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/90a05ff1-ce19-4d6c-a606-c3d02f53ca90)


## CONNECTING DB WITH POWER BI

Linking PostgreSQL database directly to Power BI in order to easily visualize and analyze the data in real-time.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/7419e6ad-14d7-4efa-a865-38e6cad38fb8)

## DATA CLEANING & TRANSFORMATION

This involves cleaning the data to remove any inconsistencies, errors, or missing values, standardizing formats, and ensuring data integrity. Additionally, data is aggregated and transformed as needed to facilitate analysis and using DAX queries to calculate important metrics and KPI’s such as Total revenue, Total transactions, and Week-on-Week change in revenue, Average utilization ratio, Customer Acquisition cost etc,.. Once cleaned and structured, the prepared data will serve as the foundation for building Dashboard

In Power query editor,

•	Reviewing each column in both tables to get a good grasp of the data and understand its context within the domain. No missing values or inconsistencies were detected ensuring reliability and accuracy in the dataset. 

•	Introducing a comprehensive metric named Revenue, which consolidates Transaction Amount, Interest Earned, and Annual Fees Charged into a single aggregated column which helps in keeping an overview of the financial performance.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/e69e0d4b-99a2-4a0f-a467-bebc479cb4fa)

[ *Note*: The above formula is used due to limited info on credit card details. The actual formula to calculate total revenue for a credit card company involves summing up the revenue from various sources:
 Total Revenue = Interest Income + Annual Fee Revenue +  Transaction Fee Revenue + Late Fee Revenue + Interchange   Fee Revenue + Cash Advance Fee Revenue ]

•	Implementing a new column, ‘week_num’, which is extracted from the ‘week_start_date’ column that denotes the week number within the year, helps in sorting the columns chronologically.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/003dee47-4e48-4ac4-9b05-e5146230f899)

•	Introducing a new column, ‘Age group’, designed to categorize customers in ‘customer_age’ column into age buckets using ‘SWITCH’ function. By segmenting customers based on age, this addition helps in the analytical process, enabling to uncover trends and patterns more effectively. 

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/2974ee2a-2892-4250-a24c-57d5a46ce961)

•	Introducing the ‘Income group‘ column, used to categorizes customers based on their income levels using ‘SWITCH’ function that helps in analysis. By segmenting customers into income groups, we can gain deeper insights into their purchasing behaviors, preferences, and profitability.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/ae1cb02b-0706-4a7e-b45e-a2ce377632ce)

•	Created DAX queries to measure the total revenue generated from credit card transactions within the current week and also within the previous week using CALCULATE function in order to find the Week-on-Week change in revenue.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/489859d2-9b0f-446a-b946-dcbba67cbc13)


![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/41875883-a0b5-414e-895c-11f461a42b1d)

•	Calculate Week-on-Week Change in Revenue using DIVIDE function, this measure calculates the percentage change in revenue from the previous week to the current week. It computes the difference between the current week revenue and the previous week revenue, then divides it by the previous week revenue.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/7fe94860-8397-422c-a633-b3fdc56bee54)

•	Created a KPI, Total Customer Acquisition Cost(CAC) which  refers to the total cost a company incurs to acquire a new customer. It's a critical metric for businesses, including credit card companies, as it helps in evaluating the efficiency and effectiveness of their marketing and sales efforts.

•	Created a new metric, Average Utilization ratio(AU Ratio) which refers to the average percentage of credit card limits that are being used by cardholders. It's an important metric for credit card issuers to understand how much of their available credit card limits are being utilized by customers.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/82c7de94-8871-44cb-aea1-64b1ac950f3d)

•	Created a new measure Delinquency Rate, A delinquent account in the context of credit card companies refers to an account on which the cardholder has failed to make the minimum required payment by the due date specified in the credit card agreement. When an account becomes delinquent, it can lead to various consequences such as late fees, increased interest rates, negative impact on credit scores, and potentially collections efforts by the credit card issuer.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/d351074b-8821-4d2a-966b-077e18ffded7)

## UPDATED WEEKLY DATA IN SQL DB

Seamlessly integrated the new week's (week-53) financial and customer data into the PostgreSQL database ensuring the analytics reflect the most current trends and patterns.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/040e19ab-c8ef-4adc-bb6f-f7f4bcac9451)

Real-Time Insights: Refreshed Power BI dashboards to provide stakeholders with up-to-the-last week insights, empowering data-driven decision-making.

## BUILDING DASHBOARDS

### Dashboard 1 : Credit Card Financial Report

Check out my [Dashboard](https://app.powerbi.com/view?r=eyJrIjoiNjUwNzdiNTUtZWUzZS00MGY5LWE1NjItNzQyY2NkZDE5MWM0IiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9&pageName=ReportSection)

Key Features:

•	KPI Monitoring: Tracks essential KPIs related to credit card usage and financial performance.

•	Revenue Analysis by Timeframe: Quarterly, monthly, and weekly revenue breakdowns for detailed trend analysis.

•	Revenue Analysis by Demographics: Segmentation of revenue based on Age groups for targeted insights.

•	Revenue Analysis by Expenditure Type: Provides insights into revenue share by expenditure type, allowing understanding of spending habits and preferences.

•	Revenue Analysis by Card Attributes: Breakdown of revenue by card category and card use type to understand usage patterns.

•	Interactive Filters: Weekly date filters, card category filters, gender filters etc,. for customized analysis.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/6327d3b6-b6c7-4cab-989c-ff68bf890d05)

### Dashboard 2 : Credit Card Customer Report

Check out my [Dashboard](https://app.powerbi.com/view?r=eyJrIjoiNjUwNzdiNTUtZWUzZS00MGY5LWE1NjItNzQyY2NkZDE5MWM0IiwidCI6ImRmODY3OWNkLWE4MGUtNDVkOC05OWFjLWM4M2VkN2ZmOTVhMCJ9&pageName=ReportSection)

Key Features:

•	KPI Monitoring: Tracks and displays key performance indicators (KPIs) related to credit card usage and revenue.

•	Week-on-Week Revenue Change: Provides a comparative analysis of revenue changes on a weekly basis, allowing for trend identification and forecasting.

•	Demographic Impact Analysis: Analyzes the impact of revenue on customer demographics based on gender, including educational level, job type, marital status, and income group, facilitating targeted marketing strategies.

•	Top 5 States Contribution: Identifies the top five states contributing to overall revenue, enabling focused marketing efforts and regional strategy development.

•	Interactive Filters: Includes filters such as weekly dates and card categories, enhancing user experience and allowing for customized data exploration.

•	Tree Maps: Utilizes tree maps for visual representation of data, aiding in the intuitive interpretation of revenue distribution across different categories and demographics.

![image](https://github.com/lkh-pranav/Credit-Card-Analysis/assets/165638568/1560937d-2291-4f11-b685-1aeb27c937ac)

## INSIGHTS

### WoW Insights (Week-53)

Revenue Growth: The company's revenue increased by 28.8% compared to the previous week.

Customer Growth: The number of active customers has increased by 12.80% compared to the previous week.

Transaction Count: The total transaction count for the current week increased by 3.39% compared to the previous week.

Transaction Amount: The total transaction amount for the current week has increased by 35% compared to the previous week.


### Overview YTD

Overall Revenue: The total revenue generated from credit card transactions for the analyzed period is $57 million.

Overall Interest Earned: The total interest earned from credit card transactions during the reporting period is $8 million.

Cost-to-Revenue Ratio: The customer acquisition cost represents approximately 1.74% of the total revenue generated. This cost reflects the investment made by the company to attract new customers.

Overall Activation Rate: The overall activation rate for the credit card portfolio over the specified period is 57.5%, indicating the proportion of issued credit cards that have been activated by customers.

Overall Delinquency Rate: The overall delinquency rate for the credit card portfolio is 6.06% indicating that, on average, approximately 6 out of every 100 accounts have payments that are past due.

Average Utilization Ratio: The average utilization ratio for the credit card portfolio was approximately 13.47% which provides insights into how much of the available credit customers are using on average.

Average Customer Satisfaction Score: The average customer satisfaction score for the credit card company is 3.19 out of 5 indicates a moderate level of satisfaction among customers, reflecting their overall perception of the services and products offered by the company.

### Customer Spending and Transaction Patterns

Customer Age Group and Revenue Generation: Customers aged 40 to 50 contribute the highest revenue which is about 43.7% ($25M). This age group typically has higher spending capacity and engages in a variety of transactions, including higher-value purchases.

Credit Card Contribution: A significant portion of the total transaction volume is driven by the Blue and Silver credit cards. Together, these two card types account for 93% of the overall transactions, underscoring their popularity and high usage among customers.

Transaction Method: The swipe method remains the most popular choice among customers, accounting for 66.9% of all transactions. This indicates a preference for convenience and speed in completing transactions.

Spending Categories: Analysis of spending patterns shows that customers primarily use their credit cards for essential expenses such as bill payments (24.7%), entertainment (17.3%), and fuel (16.9%). Additionally, grocery shopping (15.4%), food (14.8%), and travel (10.6%) also constitute significant portions of the transaction volume.

### Customer Demographics:

Revenue Contribution by Gender: Analysis of the revenue contribution by gender reveals that male customers are the leading contributors to the total transaction revenue.

•	Male Customers: Contributed 54.4% to the total revenue($31M).

•	Female Customers: Contributed 45.6% to the total revenue($26M).

Top 3 States Contribution: The analysis of credit card transactions reveals that the top three states, Texas (TX), New York (NY), and California (CA), collectively account for a significant portion which is about 68% of the total transaction amount.

Educational Level: Customers with a graduate degree have a higher propensity to spend and contribute significantly to the credit card company's revenue (40.3%). This demographic typically has higher income levels and spending capacity.

Job Type: Businessmen, characterized by their professional status and likely higher income, contribute a substantial portion of the total revenue (31.3%). Their spending patterns may include business-related expenses and high-value transactions.

Income Level: Customers with high income levels have a greater ability to spend on credit cards, contributing nearly half of the total revenue (49%). They may engage in luxury spending, travel, and other high-ticket purchases.

Marital Status: Married customers contribute the highest revenue (50.6%), suggesting stable financial situations and potentially higher household spending.

Personal Loan Status: Customers who do not have a personal loan contribute the most revenue for the credit card company, accounting for 87.42% of total revenue indicates that customers without personal loans may rely more on credit cards for various expenses, leading to higher transaction volumes and revenue generation.



