# leetcode-sql-problems

# 1070. Product Sales Analysis III : [https://leetcode.com/problems/product-sales-analysis-iii/description/?envType=study-plan-v2&envId=top-sql-50](url)
My Solution : select s.product_id,s.year as first_year,s.quantity,s.price from sales s join (select product_id,min(year) as first_year from sales 
group by product_id) as first_sales 
on s.product_id=first_sales.product_id  and
s.year=first_sales.first_year;

# Approach 

First i did (group by) by product_id and applied aggregation min(year)to get the product_id which were sold earliest.

And then what i got the result from group by i considered this as 2nd table and joined with sales table to get the desired output.
