# Job Posting Analysis

## Project Objective
This project focuses on cleaning and preparing a dataset of job postings for analysis. The dataset includes messy text and inconsistent financial formats (e.g., salary ranges and revenue estimates). The goal was to clean the dataset in a thoughtful, structured way that maintains the original intent of the data while making it ready for exploration and modeling.

## What's in the Dataset?
- `Job Title`
- `Company Name`
- `Location`
- `Salary Estimate`
- `Revenue`
- `Employment Type`
- `Industry`
- `Company Size`
- `Job Description`

## Thought Process & Cleaning Approach
I decided to clean the dataset **column by column** instead of applying bulk transformations. This allowed me to tailor my approach to the unique structure and inconsistencies of each column.

### Salary Estimate Column
- Parsed salary strings like `'75-131'` into separate `min_salary`, `max_salary`, and `avg_salary`
- Removed any unwanted characters (like `$`, `K`, or `/yr`)
- Converted values into consistent numerical formats

### Employment Type, Industry, and Other Categorical Fields
- Cleaned for consistent formatting (e.g replaced non-applicable values ('Unknown', -1) with NaN, and after cleaning, I filled NaN back to 'Unknown' for readability.)
- Handled nulls and standard inconsistencies
- Converted all text columns to lowercase, stripped white spaces, and replaced multiple spaces with single ones for consistency

### Revenue Column
So I mapped them to a new, simplified category system:

- 'Less than $1 million (USD)': 'Under $1M'
- '$1 to $5 million (USD)': '$1M–$5M'
- '$5 to $10 million (USD)': '$5M–$10M'
- '$10 to $25 million (USD)': '$10M–$25M'
- '$25 to $50 million (USD)': '$25M–$50M'
- '$50 to $100 million (USD)': '$50M–$100M'
- '$100 to $500 million (USD)': '$100M–$500M'
- '$500 million to $1 billion (USD)': '$500M–$1B'
- '$1 to $2 billion (USD)': '$1B–$2B'
- '$2 to $5 billion (USD)': '$2B–$5B'
- '$5 to $10 billion (USD)': '$5B–$10B'
- '$10+ billion (USD)': 'Over $10B'
- 'Unknown / Non-Applicable': 'Unknown'
- '-1': 'Unknown'

This was more meaningful for analysis based on business scale.

## Insights You Can Extract
- Top-paying job titles in data roles
- Salary patterns by company size, revenue, or location
- Common employment types and industry distributions
- Clean, analysis-ready dataset for dashboards or modeling

## Tools Used
- Python (Pandas, NumPy)
- Jupyter Notebook

## Next Steps
- Create visualizations (e.g., salary distribution, job count by state)
- Build dashboards (Power BI or Tableau)

