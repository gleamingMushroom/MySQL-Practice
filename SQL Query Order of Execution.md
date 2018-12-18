### SQL Query Order of Execution  


ORDER | CLAUSE
------------ | -------------
1 | From
2 | Where
3 | Group By
4 | Having
5 | Select
6 | Order By
7 | Limit  



> FROM  

SQL's __from__ clause selects and joins your tables and is the first executed part of a query. 
This means that __in queries with joins, the join is the first thing to happen__.   

> WHERE  

The where clause is used to __limit the now-joined data__ by the values in your table's columns.  

One frequent "gotcha" in SQL is trying to use a where statement to filter aggregations, which will violate the rules of SQL's order of execution. This is because when the where statement is being evaluated, the group by statement has yet to be executed and aggregate values are unknown. Thus, the following query will fail:

```sql
select
 country
, sum(area)
from
 countries
where
 sum(area) > 1000
group by
 1
```  

But it can be solved using the having clause  

> GROUP BY  

Group by __X__ means put all those with the same value for __X__ in the same row.  

Group by __X, Y__ put all those with the same values for both __X__ and __Y__ in the same row.  

> HAVING  

The having clause is used in SQL to perform the same function as the where clause, but with aggregate values.  

__[Window Functions]__  

If you are using any window functions, they will be calculated immediately after the having clause.   

> SELECT  

The select statement is where you finally specify the values and aggregations remaining in the data set after the grouping and pruning have occurred. The execution will be almost complete at this point, with only orders and limits left to specify.  


[SQL Query Order of Execution](https://www.periscopedata.com/blog/sql-query-order-of-operations)
