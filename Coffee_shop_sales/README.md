# COFFEE SHOP SALES

## Project introduction:
This project improves the coffee shop's analytical capabilities by utilizing an Excel dashboard for sales information. The goal of analyzing transaction data is to get important insights regarding customer behavior, product popularity, sales patterns, and operational efficiencies. The purpose is to optimize inventory management, improve decision-making processes, and find possible cross-selling opportunities.
## Tool used:
Microsoft Excel 

Excel is a powerful tool that Data Analysts use to transform raw data into actionable insights, aiding decision-making and business success. Analysts play a detective-like role, identifying patterns and interpreting trends to convey complex data in a straightforward manner.

## Steps involved:
* Data cleaning
* Data analysis
* Data visualization

### Data cleaning:
It is crucial that the data should be clean for the analysis
* First the duplicate values should be removed,there were no duplicate values found.
* Secondly the date and time format was changed for the further use, In money column currency format was changed to dollar sign with two decimal values.
* Irrelevant data was checked and removed the card column.
* Add more columns like **Revenue,Month,Month name,Weekday,Weekday name,Hour,Temp transaction id**

Revenue is taken from the money column

For month```Month = MONTH(A2)```

For Month name```Month name = TEXT(A2,"mmmm")```

For Weekday```Weekday = WEEKDAY(A2,2)```

For Weekday name```Weekday name = TEXT(A2,"dddd")```

For Hour```Hour = HOUR(B2)```

Temp transaction is to find the total count of orders

![Clean](https://github.com/user-attachments/assets/433a4cb0-24ab-49db-bdd3-988c6d09a8b0)

### Data analysis

In this step of data analysis, Pivot tables are used to generate some useful insights. Through the new columns added, Created pivot tables from them. Created total of six pivot tables which show the following insights:
* Revenue by month
* Number of transaction by **day of the week**
* Number of transaction by **Hour of the day**
* Number of transaction by **Product Category** and **Revenue**
* Revenue by **Product category**
* Transaction type

![table](https://github.com/user-attachments/assets/67d9943b-dac2-4f13-a419-9323a725b4b8)
      
From the pivot tables created charts are compelled with the slicer for further navigation. To present the charts in a more appealing way for the user to understand the insights that have been obtained from the analysis.

![charts](https://github.com/user-attachments/assets/01bf15e4-8043-4469-aa5e-b851568d5ae1)
