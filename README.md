# Home-Sales-Analysis-with-Spark
![Home sales](https://gvwire.s3.us-west-1.amazonaws.com/wp-content/uploads/2022/08/18101901/Home-Sales-Decline_1280X720.jpg)
## Introduction
In this project, I'll use your knowledge of SparkSQL to determine key metrics about home sales data.

## Instruction
Please navigate to `Starter_Code` folder and select `Home_Sales.ipynb` to see the code I've written for this project.

## Installation
The following dependecies were installed for this project:
`import findspark`\
`from pyspark.sql import SparkSession`\
`import time`\
`from pyspark.sql.functions import month, year`

Please ensure you have the following libraries pre-installed:
1) `pip install findspark`
2) `pip install pandas`

## Data extraction
The original dataset contains home sales data and has the following attributes:
![Alt text](<Screenshot 2024-01-09 at 3.41.00 pm.png>)

## Querying the dataframe
Specifically, I wanted to query the data to answer the following questions:
1) What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.

![Alt text](<Screenshot 2024-01-09 at 3.44.31 pm.png>)

2) What is the average price of a home for each year it was built that has three bedrooms and three bathrooms? 

![Alt text](<Screenshot 2024-01-09 at 3.44.59 pm.png>)

3) What is the average price of a home for each year that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? 

![Alt text](<Screenshot 2024-01-09 at 3.45.27 pm.png>)

4) What is the "view" rating for homes costing more than or equal to $350,000? Determine the run time for this query.
![Alt text](<Screenshot 2024-01-09 at 3.45.48 pm.png>)

Using the cached data, I re-ran the query that filters out the view ratings with an average price of greater than or equal to $350,000 and determined the runtime and compare it to uncached runtime. I discovered that the runtime was reduced to 0.73 secs, down from 1.08 secs using the uncached data. 

![Alt text](<Screenshot 2024-01-09 at 3.47.14 pm.png>)

Next, I partitioned by the "date_built" field on the formatted parquet home sales data and determined the runtime and compare it to uncached runtime. The runtime actually decreased from 0.73 to 0.60 secs using the partitioned data.

![Alt text](<Screenshot 2024-01-09 at 3.52.01 pm.png>)


