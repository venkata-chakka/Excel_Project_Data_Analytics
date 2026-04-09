# Salary Analysis

## Introduction

I developed this dashboard to practice and master advanced Excel concepts, using real-world data to explore the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how that translates to higher pay.

### Questions to Analyze

To understand the data science job market, I asked the following:

1. **Do more skills get you better pay?**
2. **What’s the salary for data jobs in different regions?**
3. **What are the top skills of data professionals?**
4. **What’s the pay for the top 10 skills?**

### Excel Skills Used

The following Excel skills were utilized for analysis:

- **📊 Pivot Tables**
- **📈 Pivot Charts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**

### Data Jobs Dataset

The dataset used for this project contains real-world data science job information from 2023 -2025. The dataset is available via luke's [Excel course](https://www.lukebarousse.com/), which provides a foundation for analyzing data using Excel. 

It includes detailed information on:

- **👨‍💼 Job titles**
- **💰 Salaries**
- **📍 Locations**
- **🛠️ Skills**

## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 data_jobs_all

        <img width="228" height="307" alt="data_jobs_all_applied_steps" src="https://github.com/user-attachments/assets/aa411664-58ac-4eb5-9b4a-fa1a06139f01" />


    - 🛠️ data_job_skills

        <img width="236" height="308" alt="data_job_skills_applied_steps" src="https://github.com/user-attachments/assets/7e5614f3-9e6b-4a9d-8ec9-13e99af0950b" />

#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_all
      
<img width="1601" height="687" alt="load_data_jobs_all" src="https://github.com/user-attachments/assets/0e96ae3d-2a8d-4a1d-8d1a-3759ce3ffa98" />

       
    - 🛠️ data_job_skills
     
<img width="1899" height="638" alt="data_job_skills_load" src="https://github.com/user-attachments/assets/9e2fa28c-80a0-4ca8-aca2-8c6a6cc63f18" />

       
### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

  
<img width="821" height="522" alt="Screenshot 2026-04-09 123723" src="https://github.com/user-attachments/assets/3811ae38-fb6a-492b-ab01-2badb76e2b96" />


#### 🤔 So What

- This trend emphasizes the value of acquiring multiple relevant skills, particularly for individuals aiming for higher-paying roles.

## 2️⃣ What’s the salary for data jobs in different regions?

### 🧮 Skills: PivotTables & DAX

#### 📈Pivot Table

- 🔢 I created a PivotTable using the Data Model I created with Power Pivot.
- 📊 I moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
- 🧮 Then I added new measure to calculate the median salary for United States jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
    ```

#### 🧮 DAX

- To calculate the median year salary I used DAX.

    ```
    Median Salary := MEDIAN(data_jobs_all[salary_year_avg])
    ```

### 📊 Analysis

#### 💡 Insights

- 💼 Job roles like Senior Data Engineer and Data Scientist command higher median salaries both in the US and internationally, showcasing the global demand for high-level data expertise.
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs.

   <img width="1058" height="378" alt="Screenshot 2026-04-09 124547" src="https://github.com/user-attachments/assets/009702aa-e33f-4709-a3c9-c6832b02ec30" />


#### **🤔 So What**

- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    <img width="669" height="525" alt="Screenshot 2026-04-09 125526" src="https://github.com/user-attachments/assets/a7f60c42-ccfb-461d-bdc5-5be81376ec5e" />


#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

   
### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Tools like Excel and Tableau follows closely,alongside emerging cloud technologies like AWS.

<img width="584" height="396" alt="Screenshot 2026-04-09 130157" src="https://github.com/user-attachments/assets/1eb3571b-4176-45a0-a95b-3436572c0d75" />

#### 🤔So What

- Understanding prevalent skills in the industry not only helps professionals stay competitive but also guides training and educational programs to focus on the most impactful technologies.

## 4️⃣ What’s the pay of the top 10 skills?

### 📊 Skill: Advanced Charts (Pivot Chart)

#### 📈 PivotChart

- I created a combo PivotChart to plot median salary and skill likelihood (%) from my PivotTable.
    - 🪙 **Primary Axis:** Median Salary (as a Clustered Column)
    - 👍 **Secondary Axis:** Skill Likelihood (as a Line with Markers)
- To customize the chart, I added a title axis title, removed the lines (skill likelihood), and changed the markers to diamonds.

### 📊 Analysis

#### 💡Insights

- 💰 Specialized skills like Spark, AWS, and Azure command the highest median salaries despite being less common in job postings.

- 📉 Python and SQL are the most essential skills, offering both a high likelihood of being requested and strong median salaries above $120K.

- 📉 While visualization and office tools like Tableau, Power BI, and Excel are frequently required, they sit at the lower end of the salary spectrum compared to programming and cloud expertise.

    <img width="974" height="527" alt="Screenshot 2026-04-09 130928" src="https://github.com/user-attachments/assets/670435bf-9c90-428d-9c19-5f460a6643fd" />


### 🤔So What

- This chart highlights to maximize earning potential, professionals should prioritize mastering high-demand 'anchor' skills like Python and SQL while strategically specializing in niche cloud technologies like Spark and AWS to access the market's highest salary tiers.

## Conclusion

This project began with a simple question: What actually makes a job worth more in today’s market?  Using Excel’s advanced toolkit—from cleaning raw data in Power Query to building a relational Data Model, I was able to move beyond surface-level trends. I discovered that while tools like Excel and Power BI are foundational for entry, the real 'anchor' skills for long-term success are SQL and Python, which appeared in nearly 50% of the roles I analyzed. More importantly, I learned that the path to the highest salary tiers requires specializing in Cloud technologies like Spark and AWS. This project wasn't just about practicing technical functions, it was about learning how to turn raw information into a strategic career advantage.


