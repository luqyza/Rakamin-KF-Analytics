# Business Performance Analysis of Kimia Farma (2020-2023)

## Project Overview

This project analyzes the business performance of Kimia Farma from 2020 to 2023. The analysis incorporates data from key sources, including transaction records, inventory details, branch offices, and product catalogs. These datasets were processed using Google BigQuery to create a unified analytical table, enabling the generation of insights visualized through an interactive dashboard built in Google Looker Studio.

## Objective

The primary objective of this analysis is to evaluate key business metrics to support strategic decision-making. These metrics include:

 - Sales performance
 - Profit margins
 - Product trends
 - Branch-level efficiency

The insights derived aim to enhance operational effectiveness and improve overall business performance.

## Data Processing Workflow

The data processing involves the following steps:

### 1. Gross Profit Percentage Calculation

A gross profit percentage ("persentase_gross_laba") was calculated for each product based on price ranges to estimate profitability. This metric helps assess product-level contributions to overall financial performance.

### 2. Enrich Transactions with Product Data

Transaction data was combined with product details to compute critical financial metrics, including:

Net Sales: The effective revenue after applying discounts.

Net Profit: The gross profit derived from net sales.
Additional attributes, such as product names and customer transaction ratings, were also included.

### 3. Integrate Branch Data

Branch office details, including branch name, city, province, and branch ratings, were incorporated into the dataset to enable branch-level performance analysis.

### 4. Creation of the Final Analytical Table

The consolidated analytical table integrates transaction details, product attributes, branch information, and calculated financial metrics, forming the foundation for actionable insights.

## Repository Contents

This repository includes:

- SQL Query: The SQL code used to process the data and create the analytical table is stored in the `BigQuery`.

- Dashboard: The performance dashboard in Google Looker Studio, which visualizes the results of the analysis, is stored as `Dashboard`. The live version can be accessed at the following link:
[Kimia Farma Performance Dashboard](https://lookerstudio.google.com/s/gzx91N1egRM)

## Dashboard Features

The dashboard provides the following insights:

- Sales Trends and Profitability: Evaluate sales performance over time and identify key drivers of profit.

- Product Analysis: Analyze product-level performance, including top-performing and underperforming products.

- Branch Performance: Compare branch efficiency and revenue generation across different locations.

- Customer Behavior Insights: Understand customer purchase patterns and satisfaction levels through transaction ratings.

## Conclusion

This project delivers a comprehensive framework for analyzing Kimia Farma’s business performance. By leveraging advanced data processing and visualization tools, it provides actionable insights to inform strategic decisions and drive business growth.
