# 📊  HR Analytics – Attrition, Performance & Satisfaction Analysis (PowerBI Capstone Project)

## 📌 Project Overview

This project is a complete **HR Analytics Dashboard ** developed in **Power BI**, covering three major workforce domains:

✅ Employee Attrition Analysis
✅ Employee Performance Analysis
✅ Employee Satisfaction Analysis

The dashboards provide a 360° view of employee behavior, engagement, and retention patterns, enabling HR teams and business leaders to make strategic workforce decisions.


## 🎯 Project Objectives

* Measure and monitor employee attrition rate
* Identify key factors driving employee turnover
* Analyze employee performance across departments, roles, gender, age, travel, and overtime
* Evaluate job satisfaction trends by demographics and work conditions
* Support HR decision-making with interactive KPIs and insights


## 📂 Dataset Information -->>>>

* **File Name:** : HR_Project_Power BI.csv
* **Source** : Kaggle (IBM HR Analytics dataset – modified)
* **Total Employees** : 1470

- <a href="https://github.com/dimple-shah-au13/HR-Attrition-Performance-Satisfaction-Analytics/blob/main/HR_Project_Power BI.csv">Dataset</a>

### Key Columns Included

* EmployeeID, Age, Gender, Department, JobRole
* MonthlyIncome, YearsAtCompany, TotalWorkingYears
* PerformanceRating, JobSatisfaction
* BusinessTravel, OverTime, DistanceFromHome
* Education, MaritalStatus, Attrition
* TrainingTimesLastYear

## 🛠 Tools & Technologies Used

* **Power BI Desktop**
* **Power Query (ETL & Data Cleaning)**
* **DAX Measures (KPIs & Calculations)**
* Interactive Slicers & Drill-through
* Data Visualization & Data Modeling


## 🔄 Data Cleaning & Transformation (Power Query)

Steps performed:
1. Removed duplicate records -- Duplicates were checked based on Employee Number.
2. Handled missing/null values
3. Converted data types (Date, Numeric, Text) -- Correct data types were assigned to prevent calculation errors.
4. Created Age Groups and Salary Slabs
5. Standardized categorical values


# 📊 Dashboard 1: Employee Attrition Analysis

## 🔑 Key Performance Indicators (KPIs)

* **Headcount:** 1470
* **Attrition Count:** 237
* **Attrition Rate:** 16.12%
* **Average Age:** 36.92
* **Average Salary:** 6.50K
* **Average Tenure:** 7.01 Years


## 📌 Creating New Calculated Columns

📌 Age Group Column :

    AgeGroup = 
    SWITCH(
        TRUE(),
        'HR_Project_Power BI'[Age] >= 18 && 'HR_Project_Power BI'[Age] <= 24, "18 - 24",
        'HR_Project_Power BI'[Age] >= 25 && 'HR_Project_Power BI'[Age] <= 34, "25 - 34",
        'HR_Project_Power BI'[Age] >= 35 && 'HR_Project_Power BI'[Age] <= 44, "35 - 44",
        'HR_Project_Power BI'[Age] >= 45 && 'HR_Project_Power BI'[Age] <= 54, "45 - 54",
        'HR_Project_Power BI'[Age] >= 55, "55+"
    )

📌 Salary Slab Column:

    SalarySlab = 
    SWITCH(
        TRUE(),
        'HR_Project_Power BI'[MonthlyIncome] < 5000, "Upto 5K",
        'HR_Project_Power BI'[MonthlyIncome] >= 5000 && 'HR_Project_Power BI'[MonthlyIncome] < 10000, "5k-10k",
        'HR_Project_Power BI'[MonthlyIncome] >= 10000 && 'HR_Project_Power BI'[MonthlyIncome] < 15000, "10k-15k",
        'HR_Project_Power BI'[MonthlyIncome] >= 15000, "15k+"
    )

📌 AttritionCount = IF('HR_Project_Power BI'[Attrition] = "Yes", 1,0) 


## 🧮 DAX Measures Used

📌 AttritionRate = SUM('HR_Project_Power BI'[AttritionCount])/SUM('HR_Project_Power BI'[EmployeeCount])


## 📈 Visual Insights

### Attrition by Gender
* Male attrition higher than female

### Attrition by Age Group
* Highest attrition in **25–34** age range

### Attrition by Education Field
* Life Sciences and Medical backgrounds show higher turnover

### Attrition by Department
* Research & Development contributes the most attrition cases

### Attrition by Salary Slab
* Employees earning **Up to 5K** show the highest attrition

### Attrition by Business Travel
* Frequent travelers show increased attrition risk

### Attrition by Marital Status
* Single employees show the highest attrition percentage


# 📊 Dashboard 2: Employee Performance Analysis

## 🔑 Key Performance Indicators (KPIs)

* **Employees Count:** 1470
* **Average Working Years:** 11.28
* **Average Performance Rating:** 3.15
* **Average Salary:** 6.50K
* **Total Training Hours:** 4115


## 📌 Creating New Calculated Columns

📌 Satisfaction Category = 
SWITCH(
    TRUE(),
    'HR_Project_Power BI'[JobSatisfaction]  <= 2, "Low",
    'HR_Project_Power BI'[JobSatisfaction]  <= 3, "Medium",
    "High"
)

## 🧮 DAX Measures Used

📌 Performance Rating = AVERAGE('HR_Project_Power BI'[PerformanceRating])


## 📈 Visual Insights

### Performance Rating by Department
* Research & Development has the highest rating (3.16)

### Top 10 Job Roles by Performance
* Managerial and Research roles show strong performance

### Performance Rating by Gender
* Male and Female performance ratings are nearly equal

### Performance by Age Group
* Peak performance observed in mid-career employees (30–45)

### Performance vs Distance from Home
* Moderate distance employees show slightly higher performance

### Performance Rating by Satisfaction Category
* High satisfaction employees contribute most to strong ratings

### Performance by Overtime
* Employees working overtime show mixed performance outcomes


# 📊 Dashboard 3: Employee Satisfaction Analysis

## 🔑 Key Performance Indicators (KPIs)

* **Employees Count** : 1470
* **Average Job Satisfaction** : 2.73
* **Average Business Travel Score** : 2.09
* **Average Salary** : 6.50K
* **Total Training Hours** : 4K


## 📈 Visual Insights

### Job Satisfaction by Gender
* Female satisfaction slightly higher than male

### Top 10 Roles by Satisfaction
* Managers and Research roles report higher satisfaction

### Satisfaction by Distance & Department
* Employees living very near show improved satisfaction

### Satisfaction by Age Group
* Satisfaction peaks around age 30–40

### Training Hours by Satisfaction Category
* High satisfaction employees receive more training opportunities

### Satisfaction by Business Travel
* Travel_Rarely employees show highest satisfaction

### Satisfaction by Overtime
* Overtime employees show slightly reduced satisfaction


## 🎛 Dashboard Filters & Interactivity

* Department slicer
* Job Role slicer
* Business Travel filter
* Age Group filter
* Education Field filter

All visuals are cross-filtered for deep exploration.


## 📷 Dashboard Interaction -->>>>

- <a href="https://github.com/dimple-shah-au13/HR-Attrition-Performance-Satisfaction-Analytics/blob/main/HR%20Analysis%20Dashboard%20-%20Employee%20Attrition%20%26%20Performance.pbix">View HR Employee Analysis Dashboard</a>


## 📌 Business Recommendations

* Improve retention programs for employees aged 25–34
* Address attrition drivers in R&D department
* Provide salary growth opportunities for low-income employees
* Reduce excessive travel workload to enhance satisfaction
* Enhance training and career development for key job roles


## 🚀 How to Use This Project

1. Clone or download the repository
2. Open the Power BI (.pbix) file
3. Load dataset: **HR_Project_Power BI.csv**
4. Refresh the dashboard
5. Use slicers to explore workforce insights


## 📷 Dashboard Preview

Here’s a preview of the interactive dashboard:

![Dashboard Screenshot](Images/Employee%20Attrition%20Analysis.png)

![Dashboard Screenshot](Images/Employee%20Performance%20Analysis.png)

![Dashboard Screenshot](Images/Employee%20Satisfaction%20Analysis.png)


## 👤 Author

**Dimple Shah**
-  Data Analyst | Excel | Power BI | Tableau | SQL | Python | Business Intelligence Enthusiast


## GITHUB -->>>>

- <a href ="https://github.com/dimple-shah-au13/HR-Attrition-Performance-Satisfaction-Analytics/tree/main">GITHUB</a>


## ⭐ Support

If you found this project helpful, don’t forget to ⭐ star the repository on GitHub!
