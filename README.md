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
- Age group 45-54,registered the lowest unemployment rate, while age 16-19 registered the highest unemployment throughout the 17 year period.
- Looking at the months, July registered the lowest unemployment rate while March recorded the highest rates throughout the years.
- 2019 registered the lowest compared to 2011 that recorded the highest unemployment rate in the 17 year period.This analysis takes into account the years that recorded 12 months.

### Observations
- Overall unemployment rates  increase throughout the 17 year period among age group 16-19 to 20-24, can be attributed to time in school. On the other hand, low unemployment rates registered in age group 45-54 & 55-64 can be explained as the most known age group when one is set in their career and working towards retirement security.

### Limitations
- 2008 & 2024 recorded(11 & 3 months). This affected data analysis with inconclusive data results. However, analysis by month was done to get an overall view of the unemployment trend throughout the months. This resulted in March and February scoring highest across all the 17 year period  given that they were recorded in all the 17 years. 
### References
  - Cousera online/Data Analytics with excel
  - Edx online / Sql for Beginners
  - Alex the data analyst/ Data analysis with sql and excel bootcamp/ youtube
  - www.analystbuilder.com
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




