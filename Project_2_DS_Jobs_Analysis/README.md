# Project 2 - 📈 Excel Salary Analysis – Data Job Skills & Pay Insights

## 📝 Introduction

As a current job seeker in the data space, I built this Excel-based project to answer key questions that matter most to professionals:
- 👉 What skills are in demand?
- 👉 How many skills are typically required per role?
- 👉 Which ones are must-haves?

This project dives deep into 2023 data job postings to help aspiring and active data professionals understand skill expectations, role requirements, and compensation trends, making it easier to strategically upskill.

### 🔍 Key Questions Explored

1. **Are more skills linked to better pay?**
2. **How does India's salary compare to other regions?**
3. **Which skills are most in demand?**
4. **Which skills drive the highest pay?**

### 🛠️ Excel Skills Demonstrated

- **📊 PivotTables & PivotCharts**
- **🧮 DAX (Data Analysis Expressions)**
- **🔍 Power Query**
- **💪 Power Pivot**
- **📈 Data Modeling & Relationships**

### 📂 Dataset Overview

2023 dataset from real-world job postings covering:

- **👨‍💼 Job Titles**
- **💰 Average Salaries**
- **📍 Countries (Focus: India)**
- **🛠️ Required Skills**

## 🔍 Analysis & Insights

### 1️⃣ Are More Skills Linked to Better Pay?

- Approach: Used **Power Query** as an **ETL** tool to extract the original data (`data_salary_all.xlsx`) creating two queries:
    - First one with all the data jobs information.
    - Second, listing the skills for each job ID.
  - Transform: transformed each query by changing column types, removing unnecessary columns, cleaning text to eliminate specific words, and trimming excess whitespace.
    - 📊 all_data_jobs
  
        ![all_data_jobs_applied_steps](https://github.com/user-attachments/assets/442ae434-72cd-48ff-89f6-3e147622cbd1)
      
    - 🛠️ all_data_job_skills
  
        ![all_data_jobs_skills_applied_steps](https://github.com/user-attachments/assets/b1ad20ac-641b-437f-912b-6627f02cf3a4)
  
  - Load: loaded both transformed queries into the workbook, setting the base for further analysis.
    - 📊 all_data_jobs
   
        ![all_data_jobs_PQE](https://github.com/user-attachments/assets/b40f9049-df6e-474d-87e5-5528cbb04bb6)
  
    - 🛠️ all_data_job_skills
  
        ![all_data_jobs_skills_PQE](https://github.com/user-attachments/assets/04756f7c-2a17-46b4-a75f-de8abfc39e25)

- Insights 💡: Roles with more skills, like **Data Engineer" and **Data Scientist** indicating a positive correlation between skills and salary.

    ![Skills_Vs_Med_Sal_Analysis](https://github.com/user-attachments/assets/3a3c2602-108a-451a-a8f3-d3efb51829d2)

- 🎯 Takeaway: **More relevant skills = higher earning potential**

### 2️⃣ India vs Global Salary Comparison

- Approach: set up a PivotTable using the Data Model created with Power Pivot.
  - moved the `job_title_short` to the rows area and `salary_year_avg` into the values area.
  - added new measure to calculate the median salary for India jobs.
    ```
    =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "India")
    ```
    - Used DAX calculate the median year salary (other than India)
      ```
      =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] <> "India")
      ```
    - Used DAX calculate the median year salary (US)
      ```
      =CALCULATE(
        MEDIAN(data_jobs_all[salary_year_avg]),
        data_jobs_all[job_country] = "United States")
      ```

- Insights 💡:
  - India's median is lower than both US and other countries.
  - Business Analyst is the lowest-paid among all roles in India.
  - **Data Engineer** Job offers higher median salary.

    ![MedSal_India_Vs_NonIndia_Vs_US_Comparison](https://github.com/user-attachments/assets/0d4095b3-7f02-4874-88e3-91253b9e757e)

- 🎯 Takeaway: **Global context matters, job seekers in India must balance expectations and explore upskilling paths to boost competitiveness.**

### 3️⃣ Most In-Demand Skills

- Approach: Linked `all_data_jobs` and `all_data_jobs_skills` queries via Power Pivot.
  - created a **data model** by relating `job_id` column from both the queries.

    ![data_model](https://github.com/user-attachments/assets/4275df1c-b307-41ce-a7d8-0173009f89da)

  - **power pivot menu** was used to create measures for desired analysis.
 
    ![power_pivot_1](https://github.com/user-attachments/assets/44b9caae-ac37-4072-93aa-b1173d3283f5)

    ![power_pivot_2](https://github.com/user-attachments/assets/e1c22042-43ec-47e0-9a4a-ac111f63a685)

- Insights 💡: 
  - SQL and Python dominate across the board.
  - In India, Apache Spark appears in the top 3.
  - Cloud skills like AWS are increasingly reflecting industry trends toward cloud and automation.
 
    ![skill_share](https://github.com/user-attachments/assets/f5dae8e1-059d-431a-a9c5-f968914c8e31)

- Takeaway 🎯: **Knowing which skills are most in demand helps professionals prioritize learning and stay market-relevant.**

### 4️⃣ What’s the Pay for Top 10 Skills?

- Approach: Created combo PivotCharts to show salary vs. skill share (%).
  - Clustered column for salary, line with markers for skill frequency.
  - Customized formatting for clean visual comparisons. 

  ![skill_share_Vs_Med_Sal](https://github.com/user-attachments/assets/7c066cd9-300a-4ea9-a689-4f6ba587431a)

- Insights 💡:
  - High-paying skills include Python, Oracle, SQL, Spark(in India).
  - ower-paying ones like PowerPoint offer less return in technical roles.

Takeaway 🎯: Focusing on high-impact technical skills like **Python** and **SQL** is key for maximizing salary in data roles.

### ✅ Conclusion

This project uncovered how skill specialization and location influence salary in data roles. Through advanced Excel tools like Power Query, Power Pivot, and DAX, I analyzed job trends that help data professionals make smart, evidence-based career decisions.

### 🙌 Acknowledgement

Special thanks to **Luke Barousse** [YouTube](www.youtube.com/@LukeBarousse) for the free Excel course that inspired this project. Their structured teaching and practical datasets helped bridge the gap between learning and real-world application.

