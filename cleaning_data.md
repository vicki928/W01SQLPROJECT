## What issues will you address by cleaning the data?

On the all_sessions table. I wrote queries to find all the duplicate data, miss matching between countries and cities, and missing currency codes. Etc. The following table shows what I did for each column and the relationships between columns as labelled by different colours.

I deleted all the null columns on the table.

If I had more time on this project, I would divide the v2ProductCategory column into each sub-category and clean all the nulls for each column.


## Queries:
Below  provide the SQL queries you used to clean your data.

## BELOW ARE THE SOME Queries i used, I lost a lot of quiries i used because I did not save all the queries when cleaning the tables. I will make sure i save all the queries i create on my later projects. 

SELECT distinct fullVisitorId,channelGrouping,time,
    
    country,city,totalTransactionRevenue,transactions,
    
    timeOnSite,pageviews,sessionQualityDim,date,
   
    visitId,type,productRefundAmount,
   
    productQuantity,productPrice,
   
    productRevenue,productSKU,
   
    v2ProductName,v2ProductCategory,
   
    productVariant,currencyCode,
   
    itemQuantity,itemRevenue,
   
    transactionRevenue,transactionId,
   
    pageTitle,searchKeyword,pagePathLevel1,eCommerceAction_type,
   
    eCommerceAction_step,eCommerceAction_option
 
 FROM all_sessions

ORDER by visitid desc


## This is just one of the query i used to find duplicate data. I did one query for each column.


SELECT   productSKU, count(*)

FROM all_sessions 

GROUP BY productSKU

HAVING count(*) > 1

## UPDATE TABLE WITH MISMATCHING COUNTRY AND CITY


UPDATE all_sessions

SET country = 'United Kingdom'

where country = 'United States' 
	 AND city = 'London'

    ![](https://imgur.com/a/z7N5uMt.png)




