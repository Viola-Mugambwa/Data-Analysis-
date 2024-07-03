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





