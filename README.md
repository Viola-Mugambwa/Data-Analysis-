# Data-Analysis-
## Data Analysis of Unemployment Rate by age from 2008 - 2024 
## Table of Contents.
- [Project Overview](#project-overview) 
- [Data Source](#data-source)
- [Tools](#tools)
- [Data cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Findings](#findings)
- [Observations](#observations)
- [Limitations](#limitations)
- [References](#references)



### Project Overview
The data analysis project aims to provide an overview  of unemploymentrate trends over a 17-year period, analyzed monthly across different age groups.

![PowerBI Dashboard](https://github.com/Viola-Mugambwa/Data-Analysis-/assets/171678539/2270add2-b2b5-42ca-abe2-42e673b56533)

### Data Source 
www.kaggledateset.com
### Tools
- Excel,Power Query /Data Cleaning 
- SQL Server /Minning & Data Analysis
- PowerBI /Creating Report
### Data Cleaning 
In the Intial data preparation the following were carried out;
- Data loading and inspection
- Handling Dupilicates and converting values to percentages.
- Dates Formatting and cleaning
### Exploratory Data Analysis
- Year with lowest & highest unemployment rate
- Month with the lowest & highest unemployment rate
- Age group with lowest & highest unemployment rate
## Findings
- Age group 45-54,registered the lowest unemployment rate while,age 16-19 registered the highest unemployment throughout the 17 year period.
- Looking at the months, July registered the lowest unemployment rate while March recorded the highest rates throughout the years.
- 2019 registered the lowest compared to 2011 that recorded the highest unemployment rate in the 17 year period.This analysis takes into account the years that recorded 12 months.

### Observations
- Overall data shows that unemployment rates continued to increase as the years  progressed for age of 16-19 to 20-24,which can be attributed to time in school ,high school, college and university. On the other hand, low unemployment rates registered in age group 45-54 & 55-64 is common perception that by this time or age one is set in their career and working towards retirement security.

### Limitations
- 2008 & 2024 recorded  (11 & 3 months) consequentively. This resulted in inconclusive data if the count of months was not taken into account. However, analysis by month was done to get an overall view of the unemployment rate throughout the 17 year period. Which resulted in March and February scoring highest among all the 17 years.  
### References
  - Cousera online/Data Analytics with excel
  - Edx online / Sql for Beginners
  - Alex the data analyst/ Data analysis with sql and excel bootcamp/ youtube
  - kenji explains / Data visualtions with PowerBI,Power query, pivort table, sql, data analysis with excel/youtube
  - chandoo/ Data cleaning, analysis, Pivort tables,excel visualisation/ youtube
  - Herdata /Creating Data analysis profile on Github/youtube
  
  

### Data Analysis
```sql
SELECT * From unemployment_rates;
SELECT DISTINCT(percentagerate)AS unemployment_rate From unemployment_rates;
SELECT DISTINCT(age) FROM unemployment_rates;
SELECT COUNT(DISTINCT year) FROM unemployment_rates;

SELECT COUNT(DISTINCT month) AS countofmonths, year FROM unemployment_rates
GROUP BY year
HAVING countofmonths =12
ORDER BY year;

SELECT age,
CASE
    WHEN age <=25 THEN 'adolescent'
    WHEN age BETWEEN 30 AND 40 THEN 'adult'
    WHEN age >40 ThEN 'old'
END AS Agebracket
FROM unemployment_rates;

SELECT year,
(SELECT ROUND(AVG percentagerate),2) FROM unemployment_rates)
FROM unemployment_rates;

SELECT SUM(percentagerate) As Sum_unemploymentrate,year FROM unemployment_rates
WHERE year IN ( '2024','2008')
GROUP BY year;




