# Introduction

📊 Dive into the data job market! Focusing on data analyst roles, this project explores 💰 top-paying jobs, 🔥 in-demand skills, and 📈 where high demand meets high salary in data analytics.

🔍 SQL queries? Check them out here: [project_sql folder](/project_sql/)

# Background

Data hails from Luke Barousse's [course](https://lukebarousse.com/sql). It's packed with insights on job titles, salaries, locations, and essential skills.

The questions I wanted to answer through my SQL queries were:

- What are the top-paying data analyst jobs?
- What skills are required for these top-paying jobs?
- What skills are most in demand for data analysts?
- Which skills are associated with higher salaries?
- What are the most optimal skills to learn?

# Tools I used

For my deep dive into the data analyst job market, I harnessed the power of several key tools:

- **SQL**: The backbone of my analysis, allowing me to query the database and unearth critical insights.
- **PostgreSQL**: The chosen database management system, ideal for handling the job posting data.
- **Visual Studio Code**: My go-to for database management and executing SQL queries.
- **Git & GitHub**: Essential for version control and sharing my SQL scripts and analysis, ensuring collaboration and project tracking.

# The analysis

Each query for this project aimed at investigating specific aspects of the data analyst job market. Here’s how I approached each question:

### 1. Top Paying Data Scientist Jobs

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
    job_title_short = 'Data Scientist' AND
    job_location = 'Anywhere' AND
    salary_year_avg IS NOT NULL
ORDER BY
    salary_year_avg DESC
LIMIT 10
```

Here's the breakdown of the top data scientist jobs worldwide in 2023:
Here are the key insights for Data Scientist roles in brief:

- **High Salaries**: Salaries range from $30,750 to $550,000, with higher pay for senior and specialized roles.
- **Top Skills**: Most in-demand skills are python, sql, machine learning, and R, reflecting the importance of programming, analytics, and data management.
- **Emerging Trends**: Skills like aws and data visualization are also crucial, indicating the need for cloud and communication expertise.
- **Industry Focus**: Roles are concentrated in finance, tech, and consultancy sectors, offering competitive salaries for expertise.

![Top paying roles](assets\10_most_common_skills_data_science.png)
_Bar graph visualizing top in-demand skills for Data Scientist wouldwide; ChatGPT generated this graph from my SQL query results_

# What I learned

Throughout this adventure, I've turbocharged my SQL toolkit with some serious firepower:

🧩 Complex Query Crafting: Mastered the art of advanced SQL, merging tables like a pro and wielding WITH clauses for ninja-level temp table maneuvers.
📊 Data Aggregation: Got cozy with GROUP BY and turned aggregate functions like COUNT() and AVG() into my data-summarizing sidekicks.
💡 Analytical Wizardry: Leveled up my real-world puzzle-solving skills, turning questions into actionable, insightful SQL queries.

# Conclusion

From the analysis, several general insights emerged:

1. **Salary Insights**:
   - Data Scientist positions have salaries ranging from $30,750 to $550,000, with the highest salaries associated with senior or specialized roles like "Staff Data Scientist."
   - The average salary for Data Scientist roles in this dataset is likely higher than other job categories, reflecting its high demand.
2. **Skills Demand**:
   - The most common skill for Data Scientist roles is "python", followed by "sql", indicating that programming and database management are critical.
   - Other frequently listed skills include "machine learning" and "R", showing the importance of analytical and statistical capabilities.
   - Skills like "aws" and "data visualization" are also prominent, emphasizing the role of cloud computing and communication of insights.
3. **Employer Trends**:
   - Many companies listing Data Scientist roles seem to be in the finance, tech, and consultancy sectors, often offering competitive salaries.
   - Some job listings may be tailored toward specific industries, such as finance or e-commerce, where specialized skills (e.g., "NLP" or "big data") might be emphasized.
4. **Conclusion**:
   - If one is aiming for a Data Scientist role, focusing on python, sql, machine learning, and cloud platforms (e.g., AWS) will align well with employer expectations.
   - Companies appear willing to pay premium salaries for senior Data Scientist roles, particularly if the candidate has a strong combination of technical and domain-specific skills.
