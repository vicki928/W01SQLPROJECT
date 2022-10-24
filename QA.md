What are your risk areas? Identify and describe them.


There was no clear definition (explanation) in each column, so i had to make some assumptions. 
For example, on the all_sessions table, the totaltranscationreveune has 81 rows along with transactions. However, there are only 9 rows with numbers for the transactions column. In the real world, each transaction must have a unique ID. 

On the time column, it does not have a unit; If the unit is provided, we can find more information to decide if the time has any effect on the purchase; for example, when customer visit in the morning, do they intend to make a purchase? Or the most purchases happen in the afternoon or evening time? 

SessionQualityDim needs to be clarified. It has 1228 rows with different values but no clear definition of SessionQualityDim; therefore, this column could be more helpful in this table.

No clear defination on eCommerceAction_Type, eCommerceAction_step, and eCommerceAction_option.
eCommerceAction_Type and eCommerceAction_step have full set up of data, unknown defination
eCommerceAction_option has 31 rows of data with unknown defination. 



QA Process:
Describe your QA process and include the SQL queries used to execute it.

To ensure the totaltransctionrevenue data is accurate, I compared it with transactions cloum; they all have 81 rows. Therefore, I am more comfortable using this data to do calculations. 

Query used: 

Select totaltransactionrevenue, transactions
from all_sessions
where totaltransactionrevenue is not null 
		and transactions is not null

Product quantity and product revenue each have 4 rows of data since revenue = quantity * price, so I run the following query to ensure the data is correct. That confirms that product quantity, revenue, and price are accurate data with rounding. However, Transaction revenue does not make sense, so I only use this column to make calculations with further information. 

Select transactionrevenue, productquantity,productrevenue,productprice
from all_sessions
where transactionrevenue is not null 
		and productquantity is not null 
		and productrevenue is not null 

the answer is following:

"transactionrevenue"	"productquantity"	"productrevenue"	"productprice"
169.97	                    1	                58.66	            55.99
1015.48	                    50	                176.40	            3.50
1005.50	                    1	                   60.37	            59.99
200.00	                    1	                    120.00	            119.00








