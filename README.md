# Introduction
Dive into the data job market! Focusing on data analyst roles, this project explores: 
- top-paying jobs
- in-demand skills
- where high demand meets high salary 

SQL Queries: [project_sql folder](/project_sql/)
# Background
Driven by a quest to navigate the data analyst job market more effectively, this project was born from a desire to pinpoint top-paid and in-demand skills, streamlining others work to find optimal jobs.

Data from [here](https://www.lukebarousse.com/sql), insights on job titles, salaries, locations and essential skills.

## The questions I wanted to answer with my SQL queries:

1. What are the top-paying jobs for my role?
2. What are the skills required for these top-paying roles?
3. What are the most in-demand skills for my role?
4. What are the top skills based on salary for my role?
5. What are the most optimal skills to learn?

# Tools I used
For my analysis I used several key tools:
- **SQL**: The backbone of my analysis, allowing me to query the database and find insights
- **PostgreSQL**: The chosen database managment system, ideal for handling the job posting data
- **Visual Studio Code**: My go-to for executing SQL queries
- **Git & Github**: version control and sharing my SQL scripts and analysis
# The Analysis
Each query for this project aimed at investigating specific aspects of the data analyst job market. Here's how I approched each question:
### 1. Top Paying Data Analyst Jobs
To identify the highest-paying roles, I filtered data analyst positions by average yearly salary and location, focusing on remote jobs. This query highlights the high paying opportunities in the field.

```sql
SELECT 
    job_id,
    job_title,
    job_location,
    job_schedule_type,
    salary_year_avg,
    job_posted_date,
    name AS company_name
FROM 
    job_postings_fact
LEFT JOIN company_dim ON job_postings_fact.company_id = company_dim.company_id
WHERE
    job_title_short = 'Data Analyst' AND 
    job_location = 'Anywhere' AND
    salary_year_avg IS NOT NULL
ORDER BY
    salary_year_avg DESC
LIMIT 10
```
# What I Learned

# Conclusions