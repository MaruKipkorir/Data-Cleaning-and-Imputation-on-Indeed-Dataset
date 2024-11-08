# Data Cleaning and Imputation on Indeed Dataset

## Overview

This project explores and analyzes salary data from job listings in the Data Science and AI fields. The dataset contains job titles, locations, summaries, and salaries. The primary goal is to clean and prepare the salary data for further analysis, and visualize the distribution of salaries across various job titles.

## Dataset

The dataset contains the following columns:
- **title**: The job title.
- **location**: The job location.
- **summary**: A brief description of the job.
- **salary**: The salary offered for the position.

The dataset has 1080 entries, but the **salary** column contains a significant number of missing values, with only 230 valid salary records.  
The dataset can be found here: https://www.kaggle.com/datasets/srivnaman/data-science-and-ai-jobs-indeed

## Data Cleaning and Preprocessing

### 1. Title Standardization
To standardize job titles:
- Converted all titles to lowercase.
- Removed leading and trailing whitespaces.
- Mapped specific keywords in titles to standard job categories, such as "Data Scientist", "Data Analyst", "Developer", and "AI/ML" using fuzzy matching for titles like "machine learning" and "software engineer".

### 2. Salary Data Cleaning
The salary data contained inconsistencies and missing values. The following steps were taken:
- Removed unwanted characters (e.g., 'a year', '₹', commas).
- Converted salary ranges (e.g., "50000 60000") into their midpoint.
- Converted salaries mentioned in monthly, daily, or hourly formats into yearly salary figures for consistency.

### 3. Imputation of Missing Salary Values
Due to the high percentage of missing salary data, median imputation was used:
- First, missing salaries were filled using the median salary of the respective job title.
- For remaining missing values (i.e., titles with no salary data), the overall median salary was used as a fallback.

### 4. Data Visualization
Visualized the salary distribution for each job title using a box plot to provide insights into the variability of salaries across different titles.

## Key Insights

- **High Missing Data**: A large percentage of salary values were missing, making it difficult to draw accurate conclusions about the salary distribution.
- **Median Imputation**: Imputing with the median may not be an ideal solution due to the high number of missing values in certain titles. The imputed data may not be representative of the true salary distribution for those roles.
- **Salary Distribution**: After cleaning and imputing the missing salary values, the distribution of salaries shifted significantly, particularly for titles with no available salary data.

## Conclusion

While the data cleaning and imputation steps were necessary to fill in missing salary values, the resulting salary distribution may not be fully representative of the true data. Further investigation and alternate imputation techniques (such as using machine learning models or additional data) might be necessary for more accurate analysis.

## Future Work

- Investigate alternative methods for imputation.
- Explore relationships between job location and salary.


