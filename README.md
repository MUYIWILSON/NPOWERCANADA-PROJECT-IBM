# NPOWERCANADA-PROJECT-IBM
Comprehensive Project Summary: 

Stack Overflow Developer Survey Analysis

**Problem Statement:**

The primary objective of this project was to analyze the Stack Overflow Developer Survey dataset to identify key trends and relationships within the global developer community. Specifically, the analysis aimed to explore how factors such as professional coding experience, employment type, educational background, job role, and geographical location influence job satisfaction and technology preferences.

**Project Steps and Key Findings:**
1. **Data Loading and Initial Inspection:**
The dataset, sourced from the Stack Overflow Developer Survey, was loaded into a Pandas DataFrame. Initial inspection revealed a rich set of features covering various aspects of developers' professional lives.
The display.max_columns option was set to None to ensure all columns were visible during inspection.

**2. Data Cleaning and Preprocessing (Handling Missing Data):**

Identification: Missing values were identified in critical columns: Employment (0%), JobSat (55.49%), and RemoteWork (16.25%).
Strategy:
Rows with missing JobSat values were dropped due to the high percentage of missing data and its criticality for job satisfaction analysis, ensuring the integrity of the satisfaction metrics.
Missing values in Employment and RemoteWork were filled with 'Unknown' to retain data and explicitly mark unknown preferences.
Simplification of Employment: The Employment column was simplified into broader categories (e.g., 'Employed, Full-time', 'Independent Contractor', 'Student', 'Multiple Employment Types') to enhance readability and interpretability for cross-tabulation and visualization.

**3. Analysis of Experience and Job Satisfaction (YearsCodePro vs. JobSat):**

YearsCodePro was converted to a numeric type, and rows with missing values were dropped for this specific analysis.
Finding: Job satisfaction generally increases with professional coding experience. Developers with 21-50 years and 11-20 years of experience reported a median JobSat of 8.0, while those with 1-5 years and 6-10 years of experience reported 7.0. The 'Less than 1 year' category showed NaN median JobSat, likely due to insufficient data or variations in satisfaction for very new professionals.
Visualization: A bar plot visually confirmed this trend, showing higher median job satisfaction for more experienced developers.

**4. Visualization of Overall Job Satisfaction Distribution:**

Finding: A count plot of the JobSat column provided an overall distribution of job satisfaction levels among the respondents, highlighting the most common satisfaction scores.

**5. Analyzing Remote Work Preferences by Employment Type and Job Role:**

Overall Distribution: A count plot showed the overall distribution of 'Remote', 'Hybrid', and 'In-person' work preferences among respondents.
By Simplified Employment Type:
Cross-tabulation and a normalized stacked bar chart revealed proportions of remote work preferences across simplified employment categories.
Finding: Different employment types exhibit distinct remote work patterns. For example, 'Independent Contractor' roles might show a higher proportion of 'Remote' work, while 'Employed, Full-time' may have a mix of 'Remote', 'Hybrid', and 'In-person' preferences.
By Job Role (DevType):
The DevType column was processed by splitting multiple job roles into individual entries.
Cross-tabulation and a normalized stacked bar chart illustrated the distribution of remote work preferences across various developer types.
Finding: Specific job roles show varying inclinations towards remote work. Roles like 'Blockchain Developer', 'Cloud infrastructure engineer', 'Data engineer', and 'Developer, AI' tend to have higher proportions of 'Remote' workers compared to roles like 'Hardware Engineer' or 'Embedded applications developer', which might require more in-person interaction.

**6. Analyzing Programming Language Trends by Region:**

The LanguageHaveWorkedWith column was processed to extract individual languages and associate them with their respective countries.
Focus Regions: The analysis focused on 'United States of America', 'Germany', and 'India'.
Finding: While core languages like JavaScript, Python, HTML/CSS, and SQL consistently appeared in the top 10 across all selected countries, regional variations were also present. For instance, PowerShell was notably popular in the USA, C had a strong showing in Germany, and PHP ranked highly in India, reflecting regional technology ecosystems and demands.
Visualization: A heatmap effectively displayed the popularity (count of mentions) of the top 10 languages for each country, allowing for quick cross-country comparisons.

**7. Correlation between Years of Experience and Job Satisfaction (YearsCodePro vs. JobSatPoints_**1):****

Finding: A scatter plot between YearsCodePro and JobSatPoints_1 (an individual job satisfaction score component) was generated. This visualization helped to visually inspect for any direct linear or non-linear correlation. While a direct correlation might not always be strong, it supports the earlier finding that increased experience generally aligns with higher satisfaction.

**8. Educational Background vs. Employment Type (EdLevel vs. Employment_Category_Simplified):**
**Finding**:
A cross-tabulation and normalized stacked bar chart demonstrated the relationship between educational levels and simplified employment categories. This indicated how different educational paths (e.g., Bachelor's, Master's, Ph.D., self-taught) tend to lead to specific employment statuses (e.g., full-time, part-time, independent contractor).

**9. Saving the Modified Dataset:**


The final modified DataFrame, incorporating cleaned data and new categorical columns, was saved as modified_survey_data.csv for future use.
**Insights:**

**Experience-Satisfaction Link:** 
Experienced developers generally report higher job satisfaction, suggesting career progression and mastery contribute positively to contentment.

**Flexibility is Key**:

Remote and hybrid work models are prevalent, especially in roles that are less hardware-dependent or require significant independent work. Employment types like independent contractors often leverage this flexibility.
Global Core, Regional Flavor: Certain programming languages form a global core skill set, while others gain prominence in specific regions due to historical context, industry focus, or educational emphasis.
Education's Role: Educational background strongly influences employment types, indicating clear career trajectories linked to different levels of formal education.

**Recommendations:**

**Talent Management**: Companies should consider tailored retention strategies for less experienced developers to address potential lower job satisfaction and provide clear career progression paths.

**Workplace Strategy:** 
Organizations should continue to offer flexible work options where feasible, aligning with the observed preferences, particularly for roles that can effectively operate remotely.

**Educational Programs**:
Curricula for aspiring developers should strike a balance between globally popular languages and regional demands to enhance employability. Programs could also emphasize soft skills and problem-solving, which contribute to job satisfaction.

**Recruitment:**
Recruitment strategies should acknowledge the diverse educational backgrounds and job roles within the tech industry, targeting candidates based on their specific skill sets rather than solely on traditional academic credentials.

**Further Analysis:**
Quantify the exact proportions and statistical significance of observed relationships (e.g., correlation coefficients for experience vs. satisfaction, chi-squared tests for categorical relationships) to provide more robust, data-driven recommendations.
