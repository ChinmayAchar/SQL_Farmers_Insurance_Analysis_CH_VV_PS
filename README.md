🚜 Farmers Insurance Data Analysis (SQL)
Authors: Chinmay H R, Vishnu Vardhan Chedella, Preetham S 
Topic: Insurance Claim & Policy Analysis Tech Stack: SQL (Structured Query Language)

📊 Database Architecture
To understand the data flow, refer to the Entity Relationship Diagram (ERD) below. This illustrates how customers are linked to their policies, vehicles, and subsequent claims.

(Note: See the full ER Diagram in the project PDF).

📌 Project Overview
The goal of this project is to analyze a Farmers Insurance dataset to identify patterns in customer behavior, policy trends, and claim frequencies. By executing complex SQL queries, we extract actionable insights to assist in data-driven decision-making for insurance risk assessment and customer segmentation.

🗄️ Database Schema
The analysis is performed on a relational database consisting of five key tables:

Customers: Stores personal details (Name, Address, City, State, etc.).

Policy: Contains policy specifications (Policy Date, Limits, Deductibles, Premiums).

Claim: Records claim events (Claim Date, Amount, Status).

Drivers: Information on insured drivers (Age, Gender, Marital Status).

Car: Details of insured vehicles (VIN, Make, Model, Year).

💻 Sample Analysis: Top States by Claim Amount
One of the key business questions addressed is identifying which regions have the highest financial exposure. Below is the SQL logic used to retrieve the Top 3 States by total claim amount.

SQL

-- Query to find the top 3 states with the highest total claim amounts
SELECT
    C.State,
    SUM(CL.claim_amount) AS Total_Claim_Amount
FROM
    Customers C
JOIN
    Policy P ON C.Cust_id = P.Cust_id
JOIN
    Claim CL ON P.Policy_id = CL.Policy_id
GROUP BY
    C.State
ORDER BY
    Total_Claim_Amount DESC
LIMIT 3;
📉 Visualizing the Results
The query results can be visualized to quickly identify high-risk regions:

🛠️ SQL Techniques Used
This project demonstrates proficiency in the following SQL concepts:

Shutterstock

Joins: Using INNER JOIN and LEFT JOIN to combine data across the Customer, Policy, and Claim tables.

Aggregation: Utilizing COUNT, SUM, and AVG to summarize financial data.

Grouping & Sorting: Implementing GROUP BY and ORDER BY to rank data (as seen in the sample query above).

🚀 How to Run
Setup: Import the provided dataset script into your SQL environment (MySQL/PostgreSQL).

Execution: Run the SQL_Assg_Farmers_Insurance_Questions_Starter.sql file to generate the views and tables.

Analysis: Execute the individual queries to reproduce the insights found in the PDF report.
