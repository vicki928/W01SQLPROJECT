Answer the following questions and provide the SQL queries used to find the answer.

    
**Question 1: Which cities and countries have the highest level of transaction revenues on the site?**


**SQL Queries:**

SELECT sum(totaltransactionrevenue) as total, 
		city, 
		country
FROM all_sessions 
		where totaltransactionrevenue is not null and city != 'N/A'
			group by city, country
			order by total desc



**Answer:**

1564.32	"San Francisco"	"United States"

992.23	"Sunnyvale"	"United States"

854.44	"Atlanta"	"United States"

608.00	"Palo Alto"	"United States"

602.00	"Tel Aviv-Yafo"	"Israel"

598.35	"New York"	"United States"

483.36	"Mountain View"	"United States"

479.48	"Los Angeles"	"United States"

449.52	"Chicago"	"United States"

358.00	"Sydney"	"Australia"

358.00	"Seattle"	"United States"

262.38	"San Jose"	"United States"

157.78	"Austin"	"United States"

157.00	"Nashville"	"United States"

103.77	"San Bruno"	"United States"

82.16	"Toronto"	"Canada"

38.98	"Houston"	"United States"

21.99	"Columbus"	"United States"

16.99	"Zurich"	"Switzerland"




**Question 2: What is the average number of products ordered from visitors in each city and country?**


SQL Queries:

SELECT round (avg(totaltransactionrevenue/productprice),2) as avg_prod_ordered, city,country
From all_sessions
	where city !='N/A'AND city !='(not set)'
	GROUP BY city,country
	order by avg_prod_ordered asc



Answer:

0.68	"Zurich"	"Switzerland"

1.05	"Nashville"	"United States"

1.16	"Columbus"	"United States"

1.46	"Mountain View"	"United States"

1.53	"Palo Alto"	"United States"

1.56	"Houston"	"United States"

1.60	"San Jose"	"United States"

3.01	"Sydney"	"Australia"

3.01	"Seattle"	"United States"

3.78	"New York"	"United States"

4.09	"San Francisco"	"United States"

4.11	"Toronto"	"Canada"

4.95	"Los Angeles"	"United States"

5.46	"San Bruno"	"United States"

5.81	"Austin"	"United States"

7.62	"Tel Aviv-Yafo"	"Israel"

16.73	"Chicago"	"United States"

36.09	"Atlanta"	"United States"

116.98	"Sunnyvale"	"United States"





**Question 3: Is there any pattern in the types (product categories) of products ordered from visitors in each city and country?**


SQL Queries:

SELECT count(*) as numOfProductPerCat, 
		v2productcategory, 
		city,
		country
FROM all_sessions
	where city !='N/A'AND city !='(not set)'
	GROUP BY v2productcategory,country, city
	order by  Country desc, numOfProductPerCat desc, city desc



Answer:

USA contributed the most to the revenue.People from the Bay area and New York in the USA spend the most on most categories; this may be related to their income level? 







**Question 4: What is the top-selling product from each city/country? Can we find any pattern worthy of noting in the products sold?**


SQL Queries:

Select distinct 

              all_sessions.v2productname, 
				all_sessions.country,
				all_sessions.city,
				round(sum (revenue/1000000), 2) as revenue
From (
	SELECT DISTINCT *
	FROM analytics
	Where Revenue is NOT NULL
	) as alt
	
Join all_sessions 
Using (fullvisitorid)
GROUP BY v2productname,country,city
Order by revenue desc 



Answer:  The top 10 selling products, They all in USA, However some without city names:

Straw Beach Mat   USA City(n/a) 9543.69

Android Wool Heather Cap Heather/Black  USA n/a 8983.53

Android Men's Vintage Tee  USA n/a 8930.55

Google Women's Fleece Hoodie USA n/a 8930.55

Google Women's Tee Purple  USA n/a 8930.55

YouTube Leatherette Notebook Combo  USA n/a 8930.55

7&quot; Dog Frisbee USA N/A 8850.43

Google Collapsible Pet Bowl USA N/A 8850.43

22 oz YouTube Bottle Infuser   USA San Bruno 3313.40

Nest® Cam Indoor Security Camera - USA Mountain View 1753.31









**Question 5: Can we summarize the impact of revenue generated from each city/country?**

SQL Queries: 

SELECT sum(totalTransactionRevenue) as rev , 
		city,
		country
FROM all_sessions
	where city !='N/A'AND city !='(not set)'AND totalTransactionRevenue is not NULL
	GROUP BY city,country
	order by country desc, city desc





Answer:USA contributed the most to the revenue.

"rev"	"city"	"country"

992.23	"Sunnyvale"	"United States"

358.00	"Seattle"	"United States"

262.38	"San Jose"	"United States"

1564.32	"San Francisco"	"United States"

103.77	"San Bruno"	"United States"

608.00	"Palo Alto"	"United States"

598.35	"New York"	"United States"

157.00	"Nashville"	"United States"

483.36	"Mountain View"	"United States"

479.48	"Los Angeles"	"United States"

38.98	"Houston"	"United States"

21.99	"Columbus"	"United States"

449.52	"Chicago"	"United States"

157.78	"Austin"	"United States"

854.44	"Atlanta"	"United States"

16.99	"Zurich"	"Switzerland"

602.00	"Tel Aviv-Yafo"	"Israel"

82.16	"Toronto"	"Canada"

358.00	"Sydney"	"Australia"







