# Excel Salary Dashboard

<img width="1781" height="700" alt="Screenshot 2026-04-08 093344" src="https://github.com/user-attachments/assets/2e678957-e2f8-48b3-b7e8-b6a1036b5480" />

## Introduction

I developed this dashboard to practice and master advanced Excel concepts, using real-world data to explore how job titles and locations influence salary trends in 
the data industry.

This project was inspired by my Excel course, providing a hands-on foundation in analyzing data with this powerful tool. 

### Dashboard File
My final dashboard is in [Salary_Dashboard.xlsx](Salary_Dashboard_2025.xlsx).

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📉 Charts**
- **🧮 Formulas and Functions**
- **❎ Data Validation**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2025. It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## Dashboard Build

### 📉 Charts

#### 📊 Data Science Job Salaries - Bar Chart

<img width="792" height="418" alt="Data Science job" src="https://github.com/user-attachments/assets/86f50a7d-9538-437c-9d9e-fb8796fc7e81" />


- 🛠️ **Excel Features:** Utilized bar chart feature (with formatted salary values) and optimized layout for clarity.
- 🎨 **Design Choice:** Horizontal bar chart for visual comparison of median salaries.
- 📉 **Data Organization:** Sorted job titles by descending salary for improved readability.
- 💡 **Insights Gained:** This enables quick identification of salary trends, noting that Senior roles and Engineers are higher-paying than Analyst roles.

#### 🗺️ Country Median Salaries - Map Chart

<img width="631" height="382" alt="Map_chart" src="https://github.com/user-attachments/assets/29360bc3-8fbd-46df-a5ff-3c6c33e11305" />


- 🛠️ **Excel Features:** Utilized Excel's map chart feature to plot median salaries globally.
- 🎨 **Design Choice:** Color-coded map to visually differentiate salary levels across regions.
- 📊 **Data Representation:** Plotted median salary for each country with available data.
- 👁️ **Visual Enhancement:** Improved readability and immediate understanding of geographic salary trends.
- 💡 **Insights Gained:** Enables quick grasp of global salary disparities and highlights high/low salary regions.

### 🧮 Formulas and Functions

#### 💰 Median Salary by Job Titles

```
=MEDIAN(
IF(
    (jobs[job_title_short]=A2)*
    (jobs[job_country]=country)*
    (jobs[salary_year_avg]<>0),
    (ISNUMBER(SEARCH(type,jobs[job_schedule_type])))*
    jobs[salary_year_avg]
)
)
```

- 🔍 **Multi-Criteria Filtering:** Checks job title, country, schedule type, and excludes blank salaries.
- 📊 **Array Formula:** Utilizes `MEDIAN()` function with nested `IF()` statement to analyze an array.
- 🎯 **Tailored Insights:** Provides specific salary information for job titles, regions, and schedule types.
- 🔢 **Formula Purpose:** This formula populates the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

<img width="264" height="208" alt="Median_salaries" src="https://github.com/user-attachments/assets/01892026-2a56-4c98-8db8-3e2dfa4525c8" />



#### ⏰ Count of Job Schedule Type

```
=FILTER(K2#,NOT(ISNUMBER((SEARCH("and",K2#))))*(K2#<>0))
```

- 🔍 **Unique List Generation:** This Excel formula employs the `FILTER()` function to exclude entries containing "and"  and omit zero values.
- 🔢 **Formula Purpose:** This formula populates the table below, which gives us a list of unique job schedule types.

🍽️ Background Table

<img width="256" height="125" alt="count of type" src="https://github.com/user-attachments/assets/9d6f375b-0bc3-40a0-a55f-d5ae099aa171" />


📉 Dashboard Implementation:

<img width="848" height="596" alt="Salary_dashboard_type" src="https://github.com/user-attachments/assets/6c8f2bd1-2162-4f31-beee-6bac4c7fd0bf" />


### ❎ Data Validation

#### 🔍 Filtered List

- 🔒 **Enhanced Data Validation:** Implementing the filtered list as a data validation rule under the `Job Title`, `Country`, and `Type` option in the Data tab ensures:
    - 🎯 User input is restricted to predefined, validated schedule types
    - 🚫 Incorrect or inconsistent entries are prevented
    - 👥 Overall usability of the dashboard is enhanced



## Conclusion

I built this project to transition from theoretical learning to practical application. Through this process, I mastered complex array formulas and dynamic 
filtering, while gaining a deeper understanding of how data can be visualized to tell a story about the modern job market. This project has solidified my Excel 
foundation and improved my ability to turn raw datasets into actionable career insights.
