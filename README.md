
📘 Depression & Student Behaviour Analysis – Tableau Project

This project analyzes a Student Depression Dataset using Tableau Desktop, with SQL used for preprocessing, data cleaning, and feature engineering.
The dashboard focuses on understanding how different factors — such as Academic Pressure, Sleep Duration, Financial Stress, Study Hours, and Study Satisfaction — influence student behavior and depression levels.

🧩 Project Overview

The objective of this project is to visualize and study different parameters that may contribute to student stress and depression.
Using Tableau, several worksheets and dashboards were created to analyze:

Academic Pressure vs Student Count

Financial Stress vs Student Count

Study Satisfaction vs Student Count

Sleep Duration vs Student Count

Study Hours vs Student Count

Overall Student Count Analysis Dashboard

This project showcases skills in:

✔ SQL Data Cleaning
✔ Feature Engineering
✔ Tableau Visualization
✔ Dashboard Design
✔ Analytical Interpretation

🗄️ 1. Dataset Description

The dataset contains information such as:

Age

Gender

Academic Pressure

Financial Stress

Sleep Duration

Study Hours

Study Satisfaction

Depression

Family History of Mental Illness

Dietary Habits

Have you ever had suicidal thoughts?

And other mental-health-related parameters

🔧 2. Data Preprocessing in SQL Server

Before importing the data into Tableau, the dataset was cleaned and modified in Microsoft SQL Server.

✔ Step 1 — Load Excel into SQL Server

The Excel file was uploaded into SQL Server using:

SQL Import Wizard

Selected table name: Depression Student Dataset

✔ Step 2 — Normalize Gender Column

Original values included Male and Female.
To make the dataset cleaner and standardize values, they were replaced with M and F.

UPDATE [dbo].[Depression Student Dataset]
SET Gender =
    CASE 
        WHEN Gender = 'Male' THEN 'M'
        WHEN Gender = 'Female' THEN 'F'
        ELSE Gender
    END;

✔ Step 3 — Create Age Group Column

Age ranges were categorized into groups (A1, A2, A3):

UPDATE [dbo].[Depression Student Dataset]
SET age_group =
CASE 
    WHEN Age BETWEEN 18 AND 24 THEN 'A1'
    WHEN Age BETWEEN 25 AND 30 THEN 'A2'
    ELSE 'A3'
END;

✔ Step 4 — Add an Index Column

An Index Column was added to uniquely identify each student row.

This index is later used in Tableau to calculate Student Count using:
CNT(Index Column) or CNTD(Index Column).

✔ Step 5 — Column Distribution Studied

Using SQL Server Column Profile, the distribution of:

Age

Gender

Academic Pressure

Sleep Duration

Study Hours

Financial Stress

was studied to understand the dataset before visualization.

🔗 3. Connecting Tableau to SQL Server

After preprocessing, Tableau Desktop was connected directly to Microsoft SQL Server:

Open Tableau Desktop

Select Microsoft SQL Server as data source

Enter:

Server name

Database name

Load the table Depression Student Dataset

Verify column types and import data

This allows live connection or extract mode.

📊 4. Tableau Visualizations (Worksheets)

The following visualizations were created — one factor at a time — to analyze its impact on Student Count (SC).

📌 Worksheet 1: Academic Pressure (AP) & Student Count (SC)

Fields Used:

Columns → Academic Pressure

Rows → CNT(Index Column)

Marks → Square

Labels → AP value & SC count

Insight:
Higher academic pressure tends to correspond with moderate student counts.

📌 Worksheet 2: Financial Stress (FS) & Student Count (SC)

Fields Used:

Columns → Financial Stress

Rows → CNT(Index Column)

Marks → Circle

Insight:
Students with medium to high financial stress show noticeable clustering.

📌 Worksheet 3: Study Satisfaction (SS) & Student Count (SC)

Fields Used:

Columns → Study Satisfaction

Rows → CNT(Index Column)

Marks → Bar (Automatic)

Insight:
Students who report high satisfaction show the highest count.

📌 Worksheet 4: Sleep Duration (SD) & Student Count (SC)

Fields Used:

Columns → Sleep Duration categories

Rows → CNTD(Index Column)

Marks → Pie

Insight:
Students sleeping less than 5 hours form a major group with high counts.

📌 Worksheet 5: Study Hours (SH) & Student Count (SC)

Fields Used:

Columns → Study Hours

Rows → CNT(Index Column)

Marks → Area Chart

Insight:
Study hours fluctuate significantly — peak at 10–12 hours.

🧮 5. Final Dashboard — Student Count Analysis

A combined dashboard was created that includes:

Sleep Duration vs SC

Study Hours vs SC

Study Satisfaction vs SC

Academic Pressure vs SC

Financial Stress vs SC

The dashboard provides a complete overview of behavior patterns.

🎯 Key Insights from Dashboard

Low sleep duration is a major contributor to increased stress.

Higher academic pressure groups have lower satisfaction levels.

Financial stress moderately affects student count.

Study hours above a certain threshold correlate with more stress patterns.

Overall, students with low satisfaction and high pressure show higher depression indicators.

🛠️ Tools Used

Microsoft SQL Server – Data cleaning & modification

Tableau Desktop – Data visualization & dashboard

Excel – Raw dataset source

🚀 How to Use This Project

Download the .twb or .hyper file.

Open in Tableau Desktop.

Ensure SQL Server connection is set or switch to Extract mode.

Explore individual worksheets for each factor.

View the final dashboard to understand multi-factor behavior.

⭐ Conclusion

This project demonstrates:

✔ Preprocessing data using SQL
✔ Adding new analytical fields (Index Column, Age Group)
✔ Building clean and separate worksheets
✔ Combining them into a structured dashboard
✔ Understanding patterns in student stress and depression
