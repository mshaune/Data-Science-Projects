# Data Science Salary Dashboard (Excel)

An interactive Excel dashboard that lets users explore salaries for data jobs by **job title, country, and job type**, built from 32,000+ 2023 data job postings.

<img width="1780" height="877" alt="dashboard_screenshot" src="https://github.com/user-attachments/assets/3898f12a-58b5-4b84-9059-76049321d01c" />

## Overview

Job seekers often want to know what a role pays in a specific place and work arrangement. This dashboard answers that question: pick a job title, a country, and a job type (such as full-time or part-time), and the dashboard updates to show:

- **Median yearly salary** for the selected job
- **Number of job postings** that match the selection
- **Most common platform** where those jobs were posted
- **How the selected job compares** with other data job titles and job types
- **Median salary by country** on a map

## Dataset

- **Source:** Data job postings dataset (2023) provided in Luke Barousse's Excel for Data Analytics course
- **Size:** 32,672 job postings
- **Key fields used:** job title, country, job type, posting platform, and average yearly salary

## How I Built It

1. **Organized the data** in an Excel Table so formulas use structured references and update automatically.
2. **Built dynamic lists for the dropdowns** with `UNIQUE`, `SORT`, and `FILTER`, and removed combined job types (like "Full-time and Part-time") so the menu only shows clean choices.
3. **Added data validation dropdowns** for job title, country, and job type, and connected them to named ranges (`title`, `country`, `type`) so every calculation follows the user's selection.
4. **Calculated median salaries** with array formulas that combine `MEDIAN`, `IF`, `ISNUMBER`, and `SEARCH`, filtering on several conditions at once and excluding postings without a salary.
5. **Counted postings by platform** with `COUNTIFS`, then used `SORT` to find the most common one and `SUBSTITUTE` to clean up its label.
6. **Pulled results onto the dashboard** with `XLOOKUP`, including a "No Results" fallback.
7. **Built the charts:** bar charts that highlight the selected job title and job type using `IF` and `NA()`, and a map chart of median salary by country.
8. **Designed the layout** by aligning KPIs, layering charts, and centering the dropdowns so the dashboard is clear and presentable.

## Skills Used

- **Formulas:** `XLOOKUP`, `FILTER`, `SORT`, `UNIQUE`, `MEDIAN`, `IF`, `COUNTIFS`, `ISNUMBER`, `SEARCH`, `SUBSTITUTE`
- **Dynamic arrays and array formulas** with multiple conditions
- **Excel Tables, structured references, and named ranges**
- **Data validation** dropdowns driven by dynamic lists
- **Data visualization:** bar charts, map chart, KPI cards
- **Performance tuning and accuracy checks**

## Challenges and Solutions

- **Slow performance:** the platform calculation originally also looked at average hourly salary, which slowed the workbook down. I removed that piece so it only uses yearly salary, which made the dashboard run efficiently without changing the results it needs.
- **Accuracy:** I checked the dashboard's numbers as I built it and adjusted the median salary calculation so the values shown are accurate.
- **Presentation:** Excel doesn't automatically keep visuals aligned, so I spent time lining up KPIs, layering charts, and centering dropdowns to make the dashboard easy to read.

## Key Insights (United States, Full-time)

- Data Analyst roles have a median salary of about **$90,000**, while Senior Data Analyst roles rise to about **$110,000**.
- Senior Data Scientist roles have the highest median, about **$155,000**.
- **Indeed** is the most common platform for Data Analyst postings.

*Based on 2023 job postings that included a yearly salary.*

## What I Learned

Building this dashboard strengthened my skills in multi-condition array formulas and dynamic arrays, and showed me how much design and validation matter. A dashboard is only useful if the numbers are right and the layout makes them easy to understand.

## Acknowledgments

Built while following [Luke Barousse's](https://github.com/lukebarousse) Excel for Data Analytics course.
