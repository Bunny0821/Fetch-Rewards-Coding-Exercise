# **Fetch Rewards Coding Exercise - Analytics Engineer**

**Please read this section before executing the code or reading the project files.**

This project is designed to complete the Fetch Rewards Coding Exercise - Analytics Engineer task and requirements. All pipeline is included in the `Fetech_Jesper.ipynb`. The code implementation is done using Jupyter Notebook and Google BigQuery. The project consists of four parts:

## **Part 1: Review Existing Unstructured Data and Diagram a New Structured Relational Data Model**
In this section, I extracted the nested structure (`rewardsReceiptItemList`) from the Receipts Data Schema and created it as a fourth schema. This approach results in a more efficient database model design with higher query performance, avoiding performance bottlenecks. This is beneficial for environments with increasing data volumes as described in the problem context. The data model design diagram and all pipeline are included in the `Fetech_Jesper.ipynb` and can also be directly viewed in `Blank diagram (1).png`.

## **Part 2: Write Queries that Directly Answer Predetermined Questions from a Business Stakeholder**
This section uses PostgreSQL dialect and has been tested in the BigQuery environment. The two questions I addressed are:
1. When considering the average spend from receipts with `rewardsReceiptStatus` of ‘Accepted’ or ‘Rejected’, which is greater?
2. When considering the total number of items purchased from receipts with `rewardsReceiptStatus` of ‘Accepted’ or ‘Rejected’, which is greater?

Surprisingly, the data did not contain the 'ACCEPTED' status. In this part of the code, I split the original three JSON files into four DataFrames: `users`, `brands`, `receipts`, and `items`. These were then converted to CSV files and imported into Google Cloud for querying.

## **Part 3: Evaluate Data Quality Issues in the Data Provided**
My standard approach to data quality checks involves examining missing values, data distribution, time, data types, and business logic. All three JSON files (four DataFrames) have missing data, but not all missing values are critical. I believe the potential business value of this data lies in assessing the supply chain, Customer Lifetime Value (CLV), selecting partners, and adjusting sales strategies. Therefore, missing values related to these purposes are more important. Removing columns with unnecessary missing values can improve query efficiency. Notably, the 'ACCEPTED' status is very significant for supply chain evaluation. Although this column has no missing values, adding this status is necessary.

## **Part 4: Communicate with Stakeholders**
I summarized the exploration results of the data resources into an easy-to-understand email format and provided some database model optimization suggestions based on the CAP theorem.

## **Usage Instructions**
The project can be cloned using git commands. After cloning, place all files in the same directory and run them directly using Jupyter Notebook. Thank you for reading!
