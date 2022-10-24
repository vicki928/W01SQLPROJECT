# Final-Project-Transforming-and-Analyzing-Data-with-SQL

## Project/Goals
I had zero experience in coding before Bootcamp; my goal for this week's project is to use what I learned in class and try my best to answer all the questions. Try to follow the steps and requirements to finish the project on time.   


## Process

Step 1: Create the tables as required in Pgadmin. Assigned data types for each column. Assigned Primary Keys.

Step 2:  Review all the data in excel first to see what's on the table since I am more comfortable with excel. Find the relationships between each column. 

Step 3: Use queries in Pgadmin to make data more readable; for example, make all the reveune in millions, add missing values based on the data histories, and correct the mismatch between countries and cities. 

Step 4: deleted some columns that only have nulls; Use queries to show all the nulls comlums, deleted all the null columns to make database smaller, however bofore I delete the null columns, I made sure these columns were not valuable and would not affect the table after deleting it. 

Step 5: Analysis the relationships between columns, and make sure the data is accurate by running queries.  
		ex:  revenue = quantity sold * price 

Step 6: find all the duplicate and incorrect records by running queries and make sure to exclude the duplicate records when doing calculations. 
I also corrected the missing matching data. 

## Results


fullVisitorId	14223 Unique rows , 794 rows(id) used twice or more

channelGrouping	full data,  where all the visitor get the website link

time	time the visitor visited the website *** NOT SURE ABOUT THE UNIT OF TIME** HH:MM??? NOT SURE

country	Vistor's country, some unknow country,  correct country and city matching. 

city	Vistor's city, some unkown city 

totalTransactionRevenue	81 rows only 

transactions	81 rows only 

timeOnSite	9 rows only 

pageviews	full data - this is the full list of page views 

sessionQualityDim	has 1228 rows  with different values **NOT SURE MEANING***

date	full data - vistor visiting site date

visitId	14556 unique rows, 553 duplicates

type	full data - TYPE:( PAGE 14942 ROWS; EVENT 192 ROWS

productRefundAmount	no data - DEL. 

productQuantity	only has 4 rows that have value , divide by 1,000,000 round 2

productPrice	full data - this is the full list of product price, divide by 1,000,000 round 2

productRevenue	only has 4 rows that have value  ,divide by 1,000,000 round 2

productSKU	536 unique productsku,444 duppicates 

v2ProductName	full data - this is the full list of product name

v2ProductCategory	757 rows not set , This seems realted to pageTitle

productVariant	40 rows only has data  (size, clour, single option only)

currencyCode	change all to USD, it seems country and locaiton does not matter

itemQuantity	no data - DEL. 

itemRevenue	no data - DEL. 

transactionRevenue	only has 4 rows that have value   

transactionId	9 rows only 

pageTitle	1 NULL,  This is title of the v2ProductCategory

searchKeyword	no data - DEL. 

pagePathLevel1	full data - this is the path of the page

eCommerceAction_type	FULL DATA -  have different values,  ***NOT SURE MEANING*** 

eCommerceAction_step	FULL DATA -  have different values,  ***NOT SURE MEANING*** 

eCommerceAction_option	31 ROWS OF DATA - ***NOT SURE MEANING***

To answer the questions, I analyze each question first to locate which data I need. 
Choose the correct SQL commands to answer the questions.
After running the queries, analyze the query results to make sure they make sense 


## Challenges 
This database does not give any clear definations, therefore, it makes some cloumns are not very useful. For example, if the unit is given for the time cloumn on the all_seesions table, it will help me to analysis the relationship/result better for the visitor pucharcahse behavior. 

Also, some columns seem to need values added. There are 81 rows on transactions columns and only nine transaction ids. In the real world, each transaction needs to have one unique transaction id.



## Future Goals
Overall, for this project, I feel VERY overwhelmed and rewarding at the same time. i have learned a lot in one week.

We had to use many different tools to finish this project; however, during the lecture and after-class activities, it only had some very brief introductions on these concepts; It was very challenging for someone like me who has zero experience in coding.

If I had more time, I would review the whole week's lecture notes and in-class recordings before starting this assignment. That will help me to understand the material better for this project. 
Also, i will do a regression analysis on the data.

I hope to be more efficient with my coding in the future by doing more exercises. 


