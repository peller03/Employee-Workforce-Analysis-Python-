# Employee-Workforce-Analysis-Python-
----

### Project Overview

This project analyzes employee workforce data using Python to uncover insights related to retention, compensation, demographics, departmental performance, and overall workforce stability. Using the Pandas, NumPy, Matplotlib, and Seaborn libraries, the analysis transforms raw HR data into clear insights that support data-driven decision-making in employee management, recruitment, compensation planning, and retention strategy.
The project focuses on understanding turnover trends, demographic distribution, salary patterns, tenure behavior, and job-level dynamics across departments and locations.

### Data Source

The dataset was downloaded from Maven Analytics, containing:

- Employee information

- Performance metrics

- Salary and compensation data

- Department & job role details

- Data dictionary

It includes 7,500+ employee records across multiple HR fields.

### Tools & Libraries Used

```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```

- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Seaborn

```python
df = pd.read_csv(r"C:\Users\ADMIN\Desktop\TDI_Python\capstodata.csv")

df.head()
```


### Data Cleaning & Preparation

Data preprocessing was performed using Pandas to ensure accuracy and consistency:

- Handled Missing column 
```python
#This drop the 'Gendr.1' column with empty value

df.drop(columns=["Gender.1"], inplace=True)
```

- Removed duplicates with df.drop_duplicates()

- Converted date fields (Hire_Date and Exit_Date) to datetime
- Checked missing values in all fields
  
- Created Employment_Status (Active or Inactive)

- Standardized text fields (department names, company info, job roles)

- Optimized data types for efficiency and accuracy

These steps ensured the dataset was structured, clean, and reliable for analysis.


### Exploratory Data Analysis (EDA)
#### Business Question 1: What is the demographic structure of the workforce?
```python
# Age distribution
plt.figure(figsize=(10,4))
sns.histplot(df['Age'].dropna(), bins=20, kde=True, color='skyblue')
plt.title('Distribution of Employee Age')
plt.show()

# Gender count
plt.figure(figsize=(10,4))
sns.countplot(x='Gender', hue='Gender', data=df, palette='Set2', legend=True)
plt.title('Gender Distribution')
plt.show()

# Job level count
plt.figure(figsize=(10,4))
sns.countplot(x='Job_Level', hue='Job_Level', data=df, palette='pastel', legend=True)
plt.title('Job Level Distribution')
plt.show()
```
![1](https://github.com/user-attachments/assets/b625b2e6-7abb-4f49-9246-af54c5e316ae)
![2](https://github.com/user-attachments/assets/a2846cbc-bc10-4afb-ba76-a7d105638c64)
 

- Workforce is mostly aged 25–40, indicating a young to mid-career workforce
  

- Males dominate the workforce, representing nearly two-thirds

- Most employees fall into Entry and Associate job levels


### Business Question 2: Which departments have the highest turnover?

![3](https://github.com/user-attachments/assets/04758206-1b1f-4810-acfc-898e6148126e)


- HR experiences the highest turnover (~0.20)

- Logistics/Warehousing and Marketing follow closely

- IT and Finance show the lowest turnover, indicating stability

### Business Question 3: How does salary vary by department and job role?

 
 
![4](https://github.com/user-attachments/assets/c30c4236-a7ee-42bf-badc-8399b272ad80)
![5](https://github.com/user-attachments/assets/955023f5-a509-4327-8909-2adde2cbb993)
![6](https://github.com/user-attachments/assets/a517cf12-c9e6-4123-9e7c-f80a9a2653a3)


- IT earns the highest average salary (~$25,000)

- Customer Service earns the lowest (~$18,000)

- Executive and Senior Manager roles command significantly higher compensation

- Entry and Associate earn below $30,000

### Business Q5: Does location influence retention (tenure)?

Tenure is consistent across locations (5.3–5.5 years)

Location has minimal impact on employee retention
### Business Question 4: What is the correlation between job level, age, and salary?

![7](https://github.com/user-attachments/assets/847c7c8d-aa5a-481a-87ee-f9af21365e16)
 

- Job level shows a strong positive correlation with salary (0.49)

- Age has no meaningful correlation with salary or job level

- Salary progression is driven by job level, not age

### Business Question 5: Does location influence retention (tenure)?

![8](https://github.com/user-attachments/assets/51adf587-8d3c-40d1-b129-1b3fb72ec59e)


- Tenure is consistent across locations (5.3–5.5 years)

- Location has minimal impact on employee retention


### Data Analysis Summary

The Python script examines:

   - Employee demographics

   - Turnover by department & location

   - Salary by job level & department

   - Tenure & employment status

   - Job level vs salary correlation

   - Workforce diversity & representation

### Python File Reference 

All cleaning steps, EDA, and visualizations are contained in your Jupyter Notebook:

#### Click to direct you [`Pelumi_Capstone.ipynb`](Pelumi_Capstone.ipynb)

### Results / Findings

- Workforce is dominated by young and entry-level employees

- HR and Logistics/Warehousing suffer the highest turnover

- Job level is the strongest driver of salary variation

- Salary inequalities exist across job roles and departments

- Retention rates are stable across geographic locations

- Minimal representation in senior leadership roles

- Salary distribution reveals progression gaps between levels


### Recommendations

1. Implement Targeted Retention Programs:
Focus on departments with high turnover (HR, Logistics, Marketing).

2. Strengthen Career Development Pathways:
Increase promotion opportunities and leadership programs.

3. Conduct Regular Compensation Reviews:
Resolve salary disparities and align compensation with job responsibilities.

4. Promote Diversity & Inclusion:
Increase representation in senior positions.

5. Conduct Regular Employee Engagement Surveys:
Monitor satisfaction and identify early signs of disengagement.
