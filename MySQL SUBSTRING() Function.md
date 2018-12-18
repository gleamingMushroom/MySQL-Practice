MySQL SUBSTRING() Function  

> __Syntax:__ SUBSTRING(string, start, length)  __OR:__  SUBSTRING(string FROM start FOR length)  

* [Question](https://www.hackerrank.com/challenges/the-pads/problem):

Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).  

* __Answer:__ 
```sql
SELECT concat(NAME,concat("(",substr(OCCUPATION,1,1),")")) 
FROM OCCUPATIONS ORDER BY NAME ASC;
```  


__Note:__ The _SUBSTR()_ and _MID()_ functions equals to the _SUBSTRING()_ function.


