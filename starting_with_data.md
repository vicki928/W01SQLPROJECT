Question 1: find all duplicate records

SQL Queries: 

Below is just one of the quries i used to find the duplicat records. i used the similar query to find other duplicate records

select count(distinct fullvisitorid), 
        
        fullvisitorid
        
        from all_sessions

group by fullvisitorid

having count(*)>1

Answer: 

Below are the duplicates from all_sessions table:

fullVisitorId	14223 Unique rows , 794 rows(id) used twice or more

visitId	14556 unique rows, 553 duplicates

productSKU	536 unique productsku,444 duppicates 



Question 2: find the total number of unique visitors (`fullVisitorID`)

SQL Queries: 

select count (distinct fullvisitorid ) as total_visitors

from all_sessions 

Answer:14223



Question 3: find the total number of unique visitors by referring sites

SQL Queries: 

Select count(distinct fullVisitorId), channelGrouping

    FROM all_sessions

    where channelGrouping = 'Referral'

    Group by channelGrouping

Answer: 2419


