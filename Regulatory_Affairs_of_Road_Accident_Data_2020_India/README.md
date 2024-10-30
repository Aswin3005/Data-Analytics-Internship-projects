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

After the analysis, the data is imported to the power bi for the visualization process. The power bi provides with wide range of charts and more it is user friendly.It supports complex data modeling, transformations, and relational mappings. Key aspects include data transformation using Power Query, data modeling with DAX,interactive visualizations, performance handling large datasets, seamless integration with other Microsoft services, and web-based accessibility for sharing reports and dashboards across the organization.

![Dashboard1](https://github.com/user-attachments/assets/31fc2c7b-5d72-45fb-8cf5-b2c2f492cc00)

From the analysis the total number of accidents are 9550
* From all the cities **Chennai** has the most number of count with **78459** and **Delhi** and **Jabalpur** as second and third places.
* The cause categories **Traffic Control,Junction,Traffic Violation,Weather** have the same count **173308** and **Road Features and Impacting Vehicle/Object** has **173284 and 122793.**
* The severity of the accident has the count as follows,
    * Minor injury has a count of 179898.
    * Greviously Injured has a count of 123183.
    * Persons Killed has a count of 81253.
* Under catergory **Weather** the count of the conditions are Sunny/Clear has **126904**, Rainy has **15421**, Foggy and Misty has **10326**, Hail/Sleet has **2193** and others are **126904.**
* The cause subcategory counts are more here are the topp 10 of them
  
    |Subcategory|Count|
    |-----------|-----|
    |Others|285305|
    |Sunny/Clear|126904|
    |Over|123013|
    |Straight Road|	104223|
    | Two Wheelers	|54356|
    | Uncontrolled	|50001|
    | T-Junction|	23555|
    | Pedestrian|	22189|
    | Staggered Junction|	18910|
    | Cars,Taxis,Vans and LMV |	17263|

## Recommendations

Focus on improving driving in fine weather conditions: As the majority of accidents occur during fine weather conditions, it may be worthwhile to explore ways to improve driver education and awareness during such conditions to help reduce the number of accidents.

Improve road infrastructure in areas with high accident rates: Given that certain geographic areas have higher accident rates, improving road infrastructure in those areas could help reduce the number of accidents.

## Conclusion

Overall, improving road safety requires a multi-faceted approach that involves education, infrastructure, and policy changes. These recommendations are a starting point for improving road safety and should be further explored and tailored to specific geographic areas and the types of accidents that occur.
