
# HR Analytics Dashboard

### Dashboard Link: https://app.powerbi.com/groups/me/reports/5b582788-ddc0-42a6-9d7b-6d9cc42f0c29/9d2acde3052a7796f34f?experience=power-bi

## Problem Statement

This dashboard addresses the critical issue of employee attrition, which leads to increased costs and reduced organizational efficiency. By analyzing attrition trends across factors such as age group, salary, department, educational background, and job role, it helps organizations identify the underlying reasons for employees leaving. With these insights, companies can pinpoint areas for improvement, enhance workplace conditions, and implement effective retention strategies to boost employee satisfaction and reduce turnover rates.


### Steps followed 

- Step 1: Load data into Power BI Desktop, the dataset is a CSV file.
- Step 2: Open the Power Query Editor. Under the Data Preview section, in the View tab, check the "column distribution," "column quality," and "column profile" options.
- Step 3: Since the profile will be opened only for 1000 rows by default, you need to select "column profiling based on the entire dataset."
- Step 4: It was noted that all columns were free of errors and empty values, except for the "YearsWithCurrManager" column. As this column was not needed for analysis, it can be removed.
- Step 5: The EmpID column, serving as a primary key, must have UNIQUE and NOT NULL values. Any duplicates were removed using Power Query Editor.
- Step 6: In the report view, under the view tab, the theme was selected.
- Step 7: Since the data contains various key performance indicators(KPIs), Six card visualisations are added to showcase the numbers accordingly. Those cards represent Employee count, Attrition Count, Attrition Rate, Average Age, Average Salary & Average Years at Company. 
- Step 8: Visual filters (Slicers) were added for three fields named "Human Resources", "Research & Development" & "Sales".
- Step 9: A treemap is added to showcase hierarchical data based on gender category.
- Step 10: A donut chart is added to showcase the attrition based on the educational background of employees, A stacked bar chart is added to represent the attrition based on the salaries as well as based on different job roles in the company, A stacked column chart is added to represent the highest attrition in different age-groups, An area chart is also added to showcase attrition happening with employees years at company & lastly a matrix table is added to represent maximum attrition within job roles. While creating this visual, a field named "AttritionCount" was also added to the Values bucket.  
- Step 11: In the report view, under the insert tab, one text box is added to the canvas and the name of the dashboard is mentioned. 
- Step 12: A calculated column was created to count attrition by applying a filter on the "Yes" or "No" column, which was converted into 0s and 1s within the calculated column.

for creating a new column following DAX expression was written;
       
        AttritionCount = IF(HR_Analytics[Attrition]= "Yes", 1, 0)
        
Snap of a new calculated column,

![Snap 1](https://github.com/user-attachments/assets/deafe58f-47dc-43b8-ad61-ca3caf8cd2bb)
       
- Step 13: A new measure was created to find the attrition rate in the company.

Following DAX expression was written for the same,
        
        AttritionRate = DIVIDE(SUM(HR_Analytics[AttritionCount]),SUM(HR_Analytics[EmployeeCount]))
        
A card visual was used to represent the Attrition Rate.

![Snap 2](https://github.com/user-attachments/assets/eba2b390-634d-4985-a519-4c8a08fa9b8f)
 
 - Step 14: Based on the calculated column AttritionCount,
 
 A card visual is used to represent total count of employees who chose attrition.
 
 ![Snap 3](https://github.com/user-attachments/assets/458ed991-3005-4288-bdc3-a177861f88c0)
 
 - Step 15: The report was then published to Power BI Service.
 
 
![Publish_Message](https://github.com/user-attachments/assets/8ee79a15-7bd3-43c2-9090-c8838e0658c5)

# Snapshot of Dashboard (Power BI Service)

![Dashboard Snap](https://github.com/user-attachments/assets/91bf16db-eff2-40cc-b29e-28c199b13ef0)

 
 # Report Snapshot (Power BI DESKTOP)

![Report Snap](https://github.com/user-attachments/assets/90fd3a02-b6b5-4fde-bdf7-8a4665183c75)

# Insights

A single-page report was created on Power BI Desktop & it was then published to Power BI Service.

Following inferences can be drawn from the dashboard;

### [1] Attrition by Education

   No. of employees with **Life Science** background = 89 (37.55 %)

   No. of employees with **Medical** background = 63 (26.58 %)

   No. of employees with **Marketing** background = 35 (14.77 %)

   No. of employees with **Technical Degree** = 32 (13.5 %)

   No. of employees with **Human Resource** background = 7 (2.95%)

   **Others** = 11 (4.64%)


           thus, a higher number of employees are from a Life Sciences educational background.
           
### [2] Attrition by Salary

 Employees whose salaries range **Upto 5k** have the highest attrition count. i.e. a total of **163** employees which is even less than the average salary provided by the company i.e. 6.5k.  
  
  ### [3] Attrition by Years at Company
  Employees leaving the company after **1 year** of joining = 59
  
  Employees leaving the company after **5 years** of joining = 21

  Employees leaving the company after **10 years** of joining = 18

        thus, a maximum number of employees tend to leave the company after a year of joining.
  

 ### [4] Some other insights
 
 ### Department
 
 1.1) Human Resources has **6** Females and **5** Males opting for attrition.
 
 1.2) Research & Development has **38** Females and **88** Males opting for attrition.
 
 1.3) Sales has **35** Females and  **47** Males opting for attrition.
 
         thus, the maximum number of employees leaving are from the Research & Development field.
 
 ### Age Group
 
 2.1)  44 employees belong to the '18-25' age group.
 
 2.2)  116 employees belong to the '26-35' age group.
 
 2.3)  43 employees belong to the '36-45' age group.
 
 2.4)  26 employees belong to the '46-55' age group.

 2.5) 8 employees belong to '55+' age group.
 
         thus, the maximum employee count of attrition belongs to the '26-35' age group.
         





