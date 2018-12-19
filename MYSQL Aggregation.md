> FLOOR() Function  

The FLOOR() function returns the largest integer value that is smaller than or equal to a number.  

```sql
# Return 25:
SELECT FLOOR(25.75) AS FloorValue;
```  


> CEILING() Function  

The CEILING() function returns the smallest integer value that is larger than or equal to a number.

```sql
# Return 26:
SELECT CEILING(25.75) AS CeilValue;
```  

> MySQL ROUND() Function  

The MySQL ROUND() function rounds a number to a specified number of decimal places.  

```sql
# Return 235.42:
SELECT ROUND(235.415, 2) AS RoundValue;
```  

```sql
# Return 236
SELECT ROUND(235.5);
```
