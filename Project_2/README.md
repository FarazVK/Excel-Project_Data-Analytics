
# Project 2 Analysis

## Introduction

I’ve always been surprised by the lack of data exploring the most optimal jobs and skills in the data science market. I set out to understand what skills top employers request and how to land more pay.

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


## 1️⃣ Do more skills get you better pay?

### 🔍 Skill: Power Query (ETL)

#### 📥 Extract

- I first used Power Query to extract the original data (`data_salary_all.xlsx`) and create two queries:
    - 🗃️ First one with all the data jobs information.
    - 🔧 The second listing the skills for each job ID.

#### 🔄 Transform

- Then, I transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 data_jobs_all

        <img width="244" height="312" alt="2_Project_Analysis_Screenshot1" src="https://github.com/user-attachments/assets/ecb8ae34-f1c4-483c-a546-832a5f6be1bb" />


    - 🛠️ data_job_skills

        <img width="243" height="328" alt="2_Project_Analysis_Screenshot2" src="https://github.com/user-attachments/assets/af61f246-23fa-4945-95c8-ebc7accc4b91" />


#### 🔗 Load

- Finally, I loaded both transformed queries into the workbook, setting the foundation for my subsequent analysis.
    - 📊 data_jobs_all

        <img width="1916" height="649" alt="2_Project_Analysis_Screenshot3" src="https://github.com/user-attachments/assets/883bd47d-ded6-43f0-8600-3fa2e25727b9" />


    - 🛠️ data_job_skills

        <img width="1914" height="702" alt="2_Project_Analysis_Screenshot4" src="https://github.com/user-attachments/assets/7365e11b-3639-4b07-97f0-43cee29d9e81" />


### 📊 Analysis

#### 💡 Insights

- 📈 There is a positive correlation between the number of skills requested in job postings and the median salary, particularly in roles like Senior Data Engineer and Data Scientist.
- 💼 Roles that require fewer skills, like Business Analyst, tend to offer lower salaries, suggesting that more specialized skill sets command higher market value.

  <img width="874" height="537" alt="2_Project_Analysis_Chart1" src="https://github.com/user-attachments/assets/4f0de510-80cc-498a-b218-03d10220edc4" />


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
- 💰 The salary disparity between US and Non-US roles is particularly notable in high-tech jobs, which might be influenced by the concentration of tech industries in the US.

    <img width="1776" height="738" alt="2_Project_Analysis_Chart2" src="https://github.com/user-attachments/assets/4f4c374c-e98e-45ef-8106-a96b8c05d36d" />


- These salary insights are important for planning and salary negotiations, helping professionals and companies align their offers with market standards while considering geographical variations.

## 3️⃣ What are the top skills of data professionals?

### 🔧 Skill: Power Pivot

#### 💪 Power Pivot

- 🔗 I created a data model by integrating the `data_jobs_all` and `data_jobs_skills` tables into one model.
- 🧹 Since I had already cleaned the data using Power Query; Power Pivot created a relationship between these two tables.

#### 🔗 Data Model

- I created a relationship between my two tables using the `job_id` column.

    <img width="1788" height="1264" alt="2_Project_Analysis_Screenshot5" src="https://github.com/user-attachments/assets/8ed95808-b3f4-4e4e-9ddf-cb460bc8a180" />


#### 📃 Power Pivot Menu

- The Power Pivot menu was used to refine my data model and makes it easy to create measures.

    <img width="1918" height="742" alt="2_Project_Analysis_Screenshot6" src="https://github.com/user-attachments/assets/b528e2fd-8275-4267-bf1e-2baab362c935" />


### 📊Analysis

#### 💡Insights

- 💻 SQL and Python dominate as top skills in data-related jobs, reflecting their foundational role in data processing and analysis.
- ☁️ Emerging technologies like AWS and Azure also show significant presence, underlining the industry's shift towards cloud services and big data technologies.

    <img width="759" height="513" alt="2_Project_Analysis_Chart3" src="https://github.com/user-attachments/assets/964340a2-baf7-480c-8a69-e66266486fab" />



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

- 💰 Higher median salaries are associated with skills like Python, Oracle, and SQL, suggesting their critical role in high-paying tech jobs.
- 📉 Skills like PowerPoint and Word have the lowest median salaries and likelihood, indicating less specialization and demand in high-salary sectors.

    <img width="862" height="452" alt="2_Project_Analysis_Chart4" src="https://github.com/user-attachments/assets/183ea04e-b02f-4932-bc08-12774891d262" />



- This chart highlights the importance of investing time in learning high-value skills like Python and SQL, which are evidently tied to higher paying roles, especially for those looking to maximize their salary in the tech industry.

## Conclusion

I embarked on this Excel-based project to uncover valuable insights about the data science job market. Using a dataset I've curated from real-world job postings, I analyzed job titles, salaries, locations, and essential skills. By leveraging Excel features like Power Query, PivotTables, DAX, and charts, I discovered key correlations between multiple skills and higher salaries, particularly in Python, SQL, and cloud technologies. 

This project serves as a practical guide for data professionals and provides an overview of the skills needed for higher-paying roles.
