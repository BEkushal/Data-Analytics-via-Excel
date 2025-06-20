# Data Science Jobs Salary Dashboard via Excel

![DS_Dashboard_demo](https://github.com/user-attachments/assets/75c7c22f-40f4-4a60-a504-6d2914764437)

## 📝 Introduction

This Excel salary dashboard was created as part of my learning journey in data analysis. It helps users especially job seekers explore salary trends across job titles, countries, and job types to make informed career decisions.

The dataset includes job roles, salaries, locations, and required skills structured and visualized in a dynamic dashboard.

This project was built by following an excellent Excel course on [YouTube](https://www.youtube.com/watch?v=pCJ15nGFgVg&list=PLiSt4_1tGhCl0X8AqTebvIIHxQ_hgl5j8) I completed the entire course, recreating and understanding each component from the ground up. The dashboard represents my first complete Excel project, showcasing skills in understanding worksheet features, navigation, formula logic, charting, and interactivity.

### 📁 Dashboard File
The Dashboard [click here](Project_1_DS_Jobs_Dashboard/Dashboard_&_Dataset) has the dataset in the hidden sheet named "Jobs_data".

### 🛠️ Excel Skills Demonstrated

- **📉 Charts** – Bar & Map visuals for salary insights.
- **🧮 Formulas** and Functions – Including array logic & conditional formatting.
- **❎ Data Validation** – Clean dropdown filters for user input.
- **🔐 Sheet Protection** – Prevents editing errors while keeping interactivity intact.

### 📂 Dataset Overview

The dataset represents real-world data-related jobs from 2023 and contains key fields like:

- **👨‍💼 Job Titles**
- **💰 Average Yearly Salaries**
- **📍 Countries**
- **🛠️ Required Skills**

## 🧱 Dashboard Build Breakdown

### 📉 Charts

#### 📊 Median Salary by Job Title - Bar Chart

![DS_Jobs_Title_Vs_MedSal_Bar_Chart](https://github.com/user-attachments/assets/dd36d401-9e94-4cd2-adda-8b4b5546f98b)

- Horizontal bar chart showing median salary per job title, sorted in descending order.
- Insights 💡: Engineer roles (e.g., Data Engineer, ML Engineer, Cloud Engineer, Software Engineer) command higher pay than non-senior analyst roles (e.g., Data Analyst, Business Analyst), reflecting industry demand for engineering-heavy roles.

#### 🌍 Median Salary by Country – Map Chart

![DS_DBoard_Map_chart_demo](https://github.com/user-attachments/assets/537e42b8-34f7-408f-b091-b581302818ef)

- Map chart visualizing median salaries globally using color gradients.
- Insight 💡: Highlights salary disparities based on role diversity — countries like the US, with a wide variety of roles, may show lower median salaries, while others like Russia, with fewer but high-paying roles, show higher median salaries.

### 🧮 Key Formulas Used

#### 💰 Median Salary (Multi-Criteria)

```
=MEDIAN(
    IF(
        (Jobs_TB[job_title_short]=J3)*
        (Jobs_TB[salary_year_avg]<>"")*
        (Jobs_TB[job_country]=country)*
        (ISNUMBER(SEARCH(type,Jobs_TB[job_schedule_type]))),
        Jobs_TB[salary_year_avg]
    )
)
```

- Calculates salary median for a selected combination of job title, country, and schedule type.
- Excludes blanks and invalid salary values.
- Fills the table below, returning the median salary based on job title, country, and type specified.

🍽️ Background Table

![DS_Jobs_Title_Reference_table](https://github.com/user-attachments/assets/954121ca-6d96-4e92-8530-f113aedb9709)

📉 Dashboard Implementation

![DS_Jobs_Job_Title_MedSal_KPI](https://github.com/user-attachments/assets/0edd0bcc-ad2e-44f2-a6ef-fcf1691998d5)

#### ⏰ Job Schedule Type Filter

```
=FILTER(W3#,NOT(ISNUMBER(SEARCH("and",W3#))+ISNUMBER(SEARCH(",",W3#)))*(W3#<>0))
```
- Filters out values containing "and" or commas, along with exclusion of zero values.
- Fills the table below, giving a desired list of unique job schedule types ensuring compactness.

🍽️ Background Table

![DS_Jobs_Type_Reference_table](https://github.com/user-attachments/assets/c837b75b-b950-4bb2-ace6-89829f33bc38)

📉 Dashboard Implementation

![DS_Jobs_Type_Count_KPI](https://github.com/user-attachments/assets/f0b07724-02fc-42cb-b5ac-c8d30fa8ff31)

#### 🎯 Visual Highlight Logic (Bar Chart)

- Used `IF` logic in support tables to conditionally **dim** or **highlight** bars based on selected filters.
- **Selected bars** appear in bold color, while **non-selected bars** appear faded allowing users to focus without losing context

#### 📋 Background Tables (Support Tables)

The dashboard is powered by structured support tables located on a separate hidden sheet named "Data_Validation":

- Feed dynamic values to visuals like bar charts, map charts, and KPI elements.
- Enable interactivity using formulas like `XLOOKUP`,`IF` and array logic.
- Provide cleaned, filtered lists for dropdowns.
- Centralize all data prep, ensuring a scalable and maintainable structure.
- The KPI-like visual on the dashboard is powered using:
    - Data validation
    - Cell referencing
    - `XLOOKUP` pulling matching values based on selected filters.

### ❎ Data Validation & Interactivity

#### 🔍 Filtered Dropdowns

- Dropdowns for Job `Title`, `Country`, and `Job Schedule Type`.
- Sourced from filtered lists in support tables.
- Prevents invalid inputs and improves user experience.

![DS_DBoard_Data_Validation_demo](https://github.com/user-attachments/assets/7c57275a-d827-4aa5-8354-c6c8b21cdda6)

#### 🔐 Worksheet Protection

- The Dashboard sheet is protected to prevent accidental edits.
- Only Data Validation cells (dropdowns) are unlocked to allow user input.
- This setup ensures users can interact with the dashboard safely without breaking its structure.

### ✅ Conclusion

This project sharpened my Excel skills while delivering a dashboard that helps users make rational, data-driven decisions in their job search. It blends interactive visuals, smart filtering, and clean design, reinforcing key concepts like dynamic filtering, data validation, and visual storytelling.

### 🙌 Acknowledgement

Special thanks to Luke Barousse [Youtube](www.youtube.com/@LukeBarousse) and his channel for sharing this excellent Excel course and dashboard project for free on on YouTube. The course was clear, structured, and highly practical.





