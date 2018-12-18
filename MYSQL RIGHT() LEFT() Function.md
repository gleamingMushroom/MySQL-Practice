MySQL RIGHT() Function

> Syntax RIGHT(string, number_of_chars)  

__Example:__ 

Extract 5 characters from a string (starting from left), output __"SQL T"__:
```
SELECT LEFT("SQL Tutorial is cool", 5) AS ExtractString;
```

__Q:__ Query the __Name__ of any student in __STUDENTS__ who scored higher than __75 Marks__. Order your output by the last three characters of each name. If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.), secondary sort them by ascending ID.  

__A:__  

```sql
select Name from STUDENTS where Marks > 75 order by right(Name, 3), ID asc;
```  


