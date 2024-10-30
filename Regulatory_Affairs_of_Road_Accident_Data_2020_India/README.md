# Regulatory Affairs of Road Accident Data 2020 India

## Project introduction

In this project, we will be analyzing data related to road accidents, which can be utilized to study accident-prone conditions and also helps understand the factors that influence road fatalities. The data includes information about accidents, such as the number of vehicles involved, severity of the accident, and the location and Cause of the accident.

## Tools used

**Microsoft Excel**

Excel is a powerful tool that Data Analysts use to transform raw data into actionable insights, aiding decision-making and business success. Analysts play a detective-like role, identifying patterns and interpreting trends to convey complex data in a straightforward manner.

**SQL**

SQL (Structured Query Language) is a powerful tool used in data analysis for querying and manipulating data stored in relational databases. It enables data analysts to access and extract data. SQL allows analysts to retrieve data from different tables within a database, making it accessible for analysis.

**Microsoft PowerBI**

Microsoft Power BI is a business analytics tool that can be used for data analysis to help users visualize data and gain insights. Power BI is designed to be used by business professionals with varying levels of data knowledge. Power BI Data Analysts design, develop, and deploy business analytics dashboards using Power BI.

## Steps involved

* Data cleaning
* Data analysis
* Data visualization

### Data cleaning

It is crucial for the data to be clean for the analysis
* Checked for duplicate values, there is no duplicate values found.
* Checked for relevant data in each column, the count column has some decimal values, round the values with ```=ROUND(E2,0)```
* Channged some irrelevant fields in cause subcategory column to others.
* Checked the data contained only relevant data for the analysis.
* Divided the data into further tables based on the cause category for visualization purpose.

 ![clean1](https://github.com/user-attachments/assets/a865da43-f4f1-4bfe-b217-fc079db3762c)


 ### Data analysis

 Using MySQL the cleaned data is imported for analysis

 --Check the data
 ```sql
SELECT*FROM
road_accident;
```

--Total nuber of accidents
```sql
SELECT COUNT(ID) AS total_accidents
FROM road_accident;
```

--The city with most count
```sql
SELECT cities,SUM(Count)
FROM road_accident
GROUP BY Cities
order by sum(Count)desc
limit 3;
```

--The category with most count
```sql
SELECT Cause_category,SUM(Count)
FROM road_accident
GROUP BY Cause_category
order by sum(Count)desc;
```

--The severity of the accident
```sql
SELECT Outcome_of_Incident,SUM(Count)
FROM road_accident
GROUP BY Outcome_of_Incident
order by sum(Count)desc;
```

--The accidents happened in weather conditions
```sql
SELECT Cause_Subcategory,SUM(Count)
FROM road_accident
where cause_category='weather'
GROUP BY Cause_Subcategory
order by sum(Count)desc;
```

--The count of subcategory of accidents
```sql
SELECT Cause_Subcategory,SUM(Count)
FROM road_accident
GROUP BY Cause_Subcategory
order by sum(Count)desc
limit 10;
```

### Data visualization

After the analysis, the data is imported to the power bi for the visualization process. The power bi provides with wide range of charts and more it is user friendly,
