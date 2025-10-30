# DEPI DATA ANALYSIS FINAL PROJECT
This is our final project where we take a deep dive in HR files to analyse for trends and performance metrics and gather key insights from the given data

# Team Members:
1- Fady Wagdy Naeem
2- Omar Reda Kassem
3- Omar Reda Kamel
4- Sarah Sameh Abdelazeem 
5- Mahmoud Ahmed Elsayed

# Files

The Given HR Folder from DEPI containing the following files:
-EducationLevel.csv
-Employee.csv
-PerformanceRating.csv
-RatingLevel.csv
-SatisfiedLevel.csv

## Description for each file

   ### Employee.csv
        EmployeeID                → Unique alphanumeric identifier for each employee.
        FirstName                 → Employee’s first name.
        LastName                  → Employee’s last name.
        Gender                    → Employee’s gender (Male, Female, etc.).
        Age                       → Employee’s age in years.
        BusinessTravel             → Frequency of business travel (No Travel, Some Travel, Frequent Travel).
        Department                → Department where the employee works (Sales, HR, R&D, etc.).
        DistanceFromHome (KM)     → Distance between home and office in kilometers.
        State                     → U.S. state abbreviation where the employee is located.
        Ethnicity                 → Ethnic background of the employee (White, Asian, Black, Hispanic, etc.).
        Education                 → Numeric code for education level (links to EducationLevel.csv).
        EducationField            → Field of study related to education (Life Sciences, Marketing, etc.).
        JobRole                   → Job title or position (Sales Executive, Research Scientist, etc.).
        MaritalStatus             → Marital status (Single, Married, Divorced).
        Salary                    → Annual salary in USD.
        StockOptionLevel          → Level of stock options awarded (0–3).
        OverTime                  → Indicates if the employee works overtime (Yes/No).
        HireDate                  → Date employee was hired (YYYY-MM-DD).
        Attrition                 → Whether the employee has left the company (Yes/No).
        YearsAtCompany            → Total years worked at the company.
        YearsInMostRecentRole     → Years in the most recent role.
        YearsSinceLastPromotion   → Years since the last promotion.
        YearsWithCurrManager      → Years with the current manager.

   ### PerformanceRating.csv
        PerformanceID                    → Unique ID for each performance review record.
        EmployeeID                       → Links to Employee.csv.
        ReviewDate                       → Date of review (MM/DD/YYYY).
        EnvironmentSatisfaction          → Satisfaction with work environment (1–5, links to SatisfiedLevel.csv).
        JobSatisfaction                  → Satisfaction with the job (1–5).
        RelationshipSatisfaction         → Satisfaction with workplace relationships (1–5).
        TrainingOpportunitiesWithinYear  → Number of training opportunities provided.
        TrainingOpportunitiesTaken       → Number of training sessions attended.
        WorkLifeBalance                  → Perception of work-life balance (1–5).
        SelfRating                       → Self-evaluation score (1–5).
        ManagerRating                    → Manager’s rating score (1–5).

   ### EducationLevel.csv
        EducationLevelID   → Numeric identifier for education level.
        EducationLevel     → Label for the education level.

        Example values:
            1 → No Formal Qualifications
            2 → High School
            3 → Bachelors
            4 → Masters
            5 → Doctorate

   ### SatisfiedLevel.csv
        SatisfactionID     → Numeric identifier for satisfaction level.
        SatisfactionLevel  → Text description of satisfaction level.

        Example values:
            1 → Very Dissatisfied
            2 → Dissatisfied
            3 → Neutral
            4 → Satisfied
            5 → Very Satisfied

   ### RatingLevel.csv
        RatingID     → Numeric identifier for performance rating (1–5).
        RatingLevel  → Text description of the rating label.

        Example values:
            1 → Unacceptable
            2 → Needs Improvement
            3 → Meets Expectations
            4 → Exceeds Expectations
            5 → Above and Beyond

##  UML Diagram
![UML Diagram](images/diagram.jpg)

--------

# EDA
## Overview
clean.py prepares the raw HR datasets for analysis by validating, normalizing, and exporting cleaned CSV files. Running the script produces cleaned datasets in the cleaned_data folder.
Purpose
- Normalize column names and datatypes. - Handle missing or inconsistent values (drop or impute based on rules). - Map numeric codes to human-readable labels using lookup files. - Produce reproducible, analysis-ready CSV files.
Expected inputs
The script expects the raw CSV files (as provided in the project) to be available in the input folder (project root or configured input path):
- Employee.csv - PerformanceRating.csv - EducationLevel.csv - SatisfiedLevel.csv - RatingLevel.csv
Outputs
- Cleaned CSV files saved to the cleaned_data folder (one cleaned file per input file). - Optional log messages printed to console or saved to a log file (depending on implementation).
Dependencies
- Python 3.8+ - pandas (for CSV I/O and transformations) - numpy (optional, for numeric operations) List additional packages in requirements.txt if used.
Main steps performed (high level)
- Load raw CSVs into DataFrame(s). - Standardize column names (trim, lowercase, replace spaces). - Convert date columns to datetime (e.g., HireDate, ReviewDate). - Convert numeric columns to appropriate numeric dtypes (ages, years, salary). - Map code fields using lookup files (e.g., Education → EducationLevel). - Normalize categorical values (e.g., OverTime: Yes/No). - Handle missing or invalid data (drop or impute, with consistent rules). - Save cleaned outputs to cleaned_data.
## Usage
install dependencies:
```
pip install -r requirements.txt
```
run the cleaning script:
```
python clean.py
```
The cleaned CSV files will be saved in the cleaned_data folder.

