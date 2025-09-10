# IT Job Postings Database – Poland  


## Overview  
This project designs and implements a **relational database** for analyzing **IT job postings in Poland**. The dataset originates from **Kaggle’s European IT Job Postings**, which contains listings across multiple countries. We filtered and customized the dataset to focus on **Polish IT jobs posted in August 2022**.  

The database supports queries about **remote work availability, salary ranges, seniority levels, company size, and programming languages**. To ensure relevance, we excluded outdated technologies such as `.NET`.  

The database was developed as part of the **INST327: Database Design and Modeling** course at the University of Maryland.  

---

## Objectives  
1. Build a normalized relational database for **Polish IT job listings**.  
2. Provide support for queries on:  
   - Remote/hybrid positions  
   - Senior-level job postings  
   - Minimum salary thresholds  
   - Company size (min and max employees)  
   - Programming languages (excluding `.NET`)  
3. Implement **views and queries** to answer common hiring-related questions.  

---

## Database Design  

- **Logical Design**: Based on job postings filtered to Poland, August 2022.  
- **Physical Design**: 7 main tables, centered around the **Job** table.  
- **Entity Relationships**:  
  - Job → Company (many-to-one)  
  - Job → Location (many-to-one)  
  - Job ↔ Skills (many-to-many via Job_Skills)  
  - Job ↔ Contract Type (many-to-many via Job_Contract_Type)  

### Key Tables  
- **Job** – Job title, experience level, published date, remote option.  
- **Company** – Workplace type, company size, open-to-hire Ukrainians.  
- **Location** – City and country code.  
- **Skills** – Programming and technical skills required.  
- **Contract_Type** – Permanent, B2B, mandate, etc.  
- **Job_Contract_Type** – Links jobs with contract types and salary ranges.  
- **Job_Skills** – Links jobs with associated skills.  

---

## Queries & Views  

We created several SQL **views** to satisfy common use cases:contentReference[oaicite:0]{index=0}:contentReference[oaicite:1]{index=1}:  

1. **JobsOpentoUkrainians**  
   - Finds all jobs open to Ukrainian applicants, including job title, company, and contract type.  

2. **AvgSalariesByContract**  
   - Calculates average minimum and maximum salaries by contract type (B2B vs permanent).  

3. **CitiesWithAboveOneJobs**  
   - Lists cities that have more than one distinct IT job posting.  

4. **HighPayingJobsForUkrainians**  
   - Shows jobs open to Ukrainians with salaries above the global average.  

5. **LargerThanAvgMinCompaniesSize**  
   - Finds companies with a minimum size greater than the average.  

---

## Project Structure  

- **team_10_job_posting_logical.mwb** – MySQL Workbench ERD and schema design.  
- **annotated-team_10_job_posting_report.pdf** – Final project report (design, ethics, lessons learned).  
- **annotated-team_10_job_posting_backup.sql.pdf** – Full SQL dump of the database schema and sample data.  
- **annotated-Team_10_job_posting_queries.sql.pdf** – Query and view definitions.  
- **README.md** – Project documentation.  
