# Data4Tech_Challenge
Analyzing data from Tech Careers Report (Landing.jobs' survey 2021).

## Basic Overview

The goal of this project is to analyze data from Landing.Jobs' survey 2021 by taking advantage of Statistics tools, Machine Learning and Data Visualization. 

## Analysis outcomes

- [PowerBI dashboard](https://app.powerbi.com/view?r=eyJrIjoiZWY1MjBiYTMtNjIyMC00OTBkLWFiZjAtYWZmMmE4NzNkOGJjIiwidCI6ImEyZjBjZGU1LWUzMjItNGQ0ZC05NTAyLTllZTM2ZjIzMDU5OSJ9&pageName=ReportSectionb8e092a827d1d903e246)
- [Jupyter Notebook](https://github.com/isabelmarcolino/Data4Tech_Challenge/blob/main/Landing%20Jobs%20Data%20Challenge%20Isabel%20Marcolino.ipynb)

## Analysis methodology
The analysis was performed using Jupyter Notebook with Python for mainly apply both Statistic and Machine Learning tools and Microsoft PowerBI for some Data Visualization.

**Statistic**

- Pearson's Correlation Coefficient
- Boxplot  analysis

**Machine Learning**

- Association Rules
- K-Means Clustering

**Data Visualization**

- Radar Chart
- Distribution Tree
- Bar charts
- Geographic Map
- Area Chart


## Female representativity (Gender vs Job Role)

The Tech roles with less than 10% of female representativity are: CTO, Solutions Architect, DevOps Engineer, SysAdmin Engineer, Mobile Apps Developer and Full-Stack Developer. While, the Tech roles with more of female representativity (> 20%) are: Business Application, Data Scientist/Data Engineer, Project Manager, Quality Assurance/Testing, Scrum Master, UX/UI Designer.

![image](https://user-images.githubusercontent.com/42064695/114468031-c1b96900-9be2-11eb-8e7f-bda62bc3fa84.png)

## Varibles correlation

Pearson's correlation coefficient is the test statistics that measures the statistical relationship or association, between two continuous variables. It is known as the best method of measuring the association between variables of interest because it is based on the method of covariance. In order to understand better our results, correlation coeficient is in the range from -1 to 1: negative coeficients show that there is a negative correlation (when one increases, the other one decreases); positive coeficients indicate that there is a positive correlation (both increase or decrease together); when the coeficient is 0, it means that there is not a linear correlation.

I performed the encoder of the categotical varibles in order to process the analysis.
``` python
encoder= ce.OrdinalEncoder(cols=['Working_Experience'],return_df=True,mapping=[
    {'col':'Working_Experience','mapping':{'No working experience':0,'Less than 1 year':1,
                                           'Between 1 - 3 years':2, 'Between 3 - 6 years':3, 'Between 6 - 9 years':4, 
                                           'More than 9 years':5}}])
```

The outcome is a symmetrical heatmap that indicates a positive correlation (increase and decrease together) between the salary's average and Working Experience, English Level, Age and Salary Fairness. Also, a slightly positive correlation with remote work opinion and changing job next 6 months was observed.

![image](https://user-images.githubusercontent.com/42064695/114471650-e3b5ea00-9be8-11eb-9c56-cb461d2998ac.png)

## Relation between Remote working and Changing jobs next 6 months

Remote work opinion has a slightly positive correlation with changing job next 6 months. But checking the type of working (Remote_Working_Current category - full remote, flexible or full office) in more details, we can conclude that around 43% of people who work full time in office are more likely to change job next 6 months. However, people who always work remotly or flexible (regardless the Covid) correspond to 27%. For this analysis, we have selected people who have chosen levels 5 and 4 in the changing jobs next 6 months category.

![image](https://user-images.githubusercontent.com/42064695/114473866-f7634f80-9bec-11eb-8b4e-6f2f7598c590.png)

The conclusion of correlation analysis is that companies that provide fairness salaries tend to keep their talents; 2. Workers who have flexibility to work remotely are less likely to change jobs next months.

## Boxplot analysis

### Type of organization vs Salary Fairness

We can see that workers from Unicorn and Startups present the higher median, which means that they scored theirs salary fairness higher than workers from other companies. It's interesting note that the category Unicorn has data less spreaded.

![image](https://user-images.githubusercontent.com/42064695/114472592-6ab79200-9bea-11eb-9bd3-f728764c5cc0.png)

### Type of organization vs Changing Jobs

Workers from Unicorn companies present the smallest median. So, we are able to say that Unicorn companies' workers are less likely to changing jobs, and they feel fairness of theirs salaries. Important note that Scale-up has the highest average salary.

![image](https://user-images.githubusercontent.com/42064695/114472676-9c305d80-9bea-11eb-9904-51be3a3be579.png)

### Boxplot analysis conclusion
Unicorn companies tend to provide higher and fairness salaries.

## Salary vs English Level

English level influences salary average. Here is an example: in average, people with no working experience but fluent in English has almost the same salary of someone with 3-6 years of experience but with an elementary English level.

![image](https://user-images.githubusercontent.com/42064695/114474289-cfc0b700-9bed-11eb-9d0b-1a27b8a43078.png)

