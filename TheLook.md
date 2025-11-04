## Unlocking Lending Insights: TheLook Fintech

**Project description:** This was the capstone project for the Google Cloud Analytics Certificate. This project was designed to help the treasury department of a hypothetical company (TheLook Fintech) analyze key metrics such as cash flow, loan purpose, and borrower location. 
A report and interactive dashboard were developed focusing on the key metrics to aid the Treasury Department in making decisions on issuing a loan. This would be an impactful project, providing valuable insights to inform lending decisions, mitigate risk, and tailor financial offerings. 

### 1. The Report

First, I analyzed the data available in the Fintech dataset using BigQuery. I then joined a CSV table with state and region information to the Fintech dataset, using an INNER JOIN on state. It is important to know the region of each loan, since many loans in one region carries a risk of many loans defaulting at once.
Finally, I concluded the report by creating a table identifying the number of loans issued by day and year. 

<img src="images/Fintech_Table.png?raw=true"/>

### 2. The Dashboard

An interactive dashboard was created using Looker and LookML to allow the treasury department to access key performance metrics. Most importantly, the dashboard includes a single-value visualization of the total amount of outstanding loans. It is highlighted in red in the screenshot below because the amount of outstanding loans is above the threshold set by the Treasury Department. 
The dashboard also includes a pie chart detailing amount of loans of a particular status compared to the total, a bar chart showing the states with the most outstandings loans, and a table of the top 10 customers with the highest income. 
As the table is interactive, users can click on particular values to filter the dashboard. 

<img src="images/TheLook_Fintech.png?raw=true"/>
