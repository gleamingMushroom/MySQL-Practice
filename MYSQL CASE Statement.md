### The SQL CASE Statement

The CASE statement goes through conditions and return a value when the first condition is met (like an IF-THEN-ELSE statement). So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause. If there is no ELSE part and no conditions are true, it returns NULL.  


>CASE Syntax

```sql
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```

>Example 1  

```sql
SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN "The quantity is greater than 30"
    WHEN Quantity = 30 THEN "The quantity is 30"
    ELSE "The quantity is under 30"
END
FROM OrderDetails;
```

>Example 2  

```sql
SELECT CustomerName, City, Country
FROM Customers
ORDER BY
(CASE
    WHEN City IS NULL THEN Country
    ELSE City
END);
```

>Question  

[Type of Triangle](https://www.hackerrank.com/challenges/what-type-of-triangle/problem)

Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

* __Equilateral__: It's a triangle with  sides of equal length.
* __Isosceles__: It's a triangle with  sides of equal length.
* __Scalene__: It's a triangle with  sides of differing lengths.
* __Not A Triangle__: The given values of A, B, and C don't form a triangle.

```sql
select 
    case 
    when A + B >= C and A + C >= B and B + C >= A then
        case 
        when A = B and B = C then "Equilateral" 
        when A = B or A = C or B = C then "Isosceles"
        when A <> B and B <> C and A <> C then "Scalene"
        end
    else "Not A Triangle"
    end 
from TRIANGLES;
```  

```sql
select 
    case 
    when A + B < C or B + C < A or C + A < B then "Not A Triangle"
    when A = B and b = C then "Equilateral"
    when A = B or B = C or C = A then "Isosceles"
    else "Scalene" 
    end
from Triangles;  
```
