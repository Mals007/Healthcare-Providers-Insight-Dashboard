# Healthcare-Providers-Insight-Dashboard
 A dynamic healthcare dashboard featuring both dark and light mode options, along with interactive features and filtering capabilities
Healthcare Analytic Dashboard 

Dashboard link: https://app.powerbi.com/links/dnOsMsb0Of?ctid=7e2137dd-6ef9-46eb-974e-5086fd7cdd20&pbi_source=linkShare&bookmarkGuid=1510c2c2-2f63-4324-a556-b64224161765

Project Objective 
The objective of this project is to design and develop a comprehensive healthcare dashboard that enables healthcare providers, administrators, and decision-makers to effectively monitor, analyze, and manage key health metrics and operational data. This dashboard aims to enhance patient care, streamline operations, and support data-driven decision-making through the following specific goals 
Import data to Power BI 
1. Prepare csv file 
2. Import CSV file to Power BI 
3. Data cleaning 
4. Data Processing 

DAX Queries
1.	Total Billing Amount
Total Billing amount = [Total Medication cost]+[Total Treatment cost]+[Total Room Charge]
2.	Total Patients
Total Patients = DISTINCTCOUNT(visits[Patient ID])
3.	Total Room Charge
Total Room Charge = sumx(visits,
    visits[Room Charges(daily rate)]*visits[Admitted day])

4.	Length of Admitted days

Admitted day = DATEDIFF(
    visits[Admitted Date],
    visits[Discharge Date],DAY
)

5.	Out of Pocket Billing amount (Without Insurance)
Out-of-Pocket = [Total Billing amount]-[Total insurance coverage] 
6.	Percentage of Billing Amount by Procedure

% Procedure = 
divide(
    [Total Billing amount],
    (CALCULATE([Total Billing amount],
    ALL(procedures[Procedure])
    ))
)
7. Percentage of Billing Amount by Department

% department = 
divide(
    [Total Billing amount],
    (CALCULATE([Total Billing amount],
    ALL(departments[Department])
    ))
)

8.Average Billing Amount Per Visit
Average Billing amount per visit = 
divide(
    [Total Billing amount],
    [Total Patients]
)

9. Average Out of pocket = 
divide(
    [Out-of-Pocket],
    [Total Patients]
)


Project Insight
Overview
•	Total Billing Amount are 3.36 M
•	Total Patients are 4973
•	Total Out Of Pocket Billing is 1.13 M
•	Average Billing amount per Visit is 674.86 pound
•	Average out of pocket charge is  227.26 pound
•	Cardiology department contributes the highest to the billing amount 25.24%
•	X-Ray services contributes to the highest billing amount
•	The state Wales contributes highest to the billing amount



