# Excel Salary Dashboard

![1_Salary_Dashboard.png](/Images/1_Salary_Dashboard_Final_Dashboard.gif)

## Introduction

This interactive Excel dashboard helps job seekers explore salary trends in data-related roles and understand how job title, location, and work type impact compensation.

Using real-world job data from 2023, I transformed raw data into clear visual insights that make salary comparisons simple and intuitive.

### Dashboard File
My final dashboard is in [1_Salary_Dashboard.xlsx](1_Salary_Dashboard.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Dataset Description

The dataset contains real-world data science job information from 2023, including:

- **Job titles**
- **Salaries**
- **Locations**
- **Skills**

This dataset was provided as part of my Excel learning journey and served as a strong foundation for building a practical analytical dashboard.



## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img src="/Images/1_Salary_Dashboard_Chart1.png" width="850" height="550" alt="Salary Dashboard Chart1">

#### Why this chart?
A horizontal bar chart makes salary comparisons between roles fast and intuitive.

#### Key Highlights:

- Clear ranking of job roles by median salary
- Easy identification of high-paying positions
- Shows how senior and engineering roles typically earn more than analyst roles

#### 🗺️ Country Median Salaries - Map Chart

![1_Salary_Dashboard_Chart2.png](/Images/1_Salary_Dashboard_Country_Map.gif)

This map visualizes median salaries across countries, making global trends easy to understand.

#### Key Insights:
- Reveals salary disparities between regions
- Highlights high-paying and lower-paying markets
- Helps users assess global job opportunities

### 🧮 Formulas and Functions

####  💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    (jobs[salary_year_avg]<>0),
    jobs[salary_year_avg]
)
)
```

What this does:
- Filters salaries by job title, country, and work type
- Excludes missing values
- Returns the median salary, giving a more realistic estimate than averages

📌 This drives the dynamic values displayed across the dashboard.

  Background Table

![1_Salary_Dashboard_Screenshot1.png](/Images/1_Salary_Dashboard_Screenshot1.png)

📉 Dashboard Implementation

<img src="/Images/1_Salary_Dashboard_Job_Title.png" width="400" height="500" alt="Salary Dashboard Title">

####  ⏰ Job Schedule Type Filtering

```
=FILTER(J2#,(NOT(ISNUMBER(SEARCH("and",J2#))+ISNUMBER(SEARCH(",",J2#))))*(J2#<>0))
```

Purpose:
- Creates a clean list of valid job schedule types
- Eliminates mixed or invalid entries
- Enables clean dropdown filters

  Background Table

![1_Salary_Dashboard_Type.png](/Images/1_Salary_Dashboard_Screenshot2.png)

📉 Dashboard Implementation:

<img src="/Images/1_Salary_Dashboard_Type.png" width="350" height="500" alt="Salary Dashboard Type">

### ❎ Data Validation

####  Filtered List

-  **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    -  User input is restricted to predefined, validated schedule types
    -  Incorrect or inconsistent entries are prevented
    -  Overall usability of the dashboard is enhanced

<img src="/Images/1_Salary_Dashboard_Data_Validation.gif" width="425" height="400" alt="Salary Dashboard Data Validation">

## Conclusion

This project demonstrates how Excel can be transformed from a spreadsheet tool into a powerful data analysis and visualization platform.

By combining charts, formulas, and data validation, I created a dashboard that allows users to:
- Explore salary trends
- Make informed career decisions
- Understand how geography and role type affect compensation

This project highlights my growing skills in data analysis, Excel automation, and dashboard design.
