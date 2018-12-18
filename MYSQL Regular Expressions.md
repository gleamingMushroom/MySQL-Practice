### MYSQL Regular Expressions

> Syntax: expr REGEXP pat

<br>  
  
Pattern	| What the pattern matches
------------ | -------------
^	| Beginning of string
$	| End of string
.	| Any single character
[...]	| Any character listed between the square brackets
[^...]	| Any character not listed between the square brackets
p1\|p2\|p3	| Alternation; matches any of the patterns p1, p2, or p3
\*	| Zero or more instances of preceding element
\+	| One or more instances of preceding element
{n}	n | instances of preceding element
{m,n}	| m through n instances of preceding element

  
<br>
### Examples:
<br>

  
The following MySQL statement will find the author’s name __beginning with ‘w’__. The ‘^’ is used to match the beginning of the name.


```
SELECT * FROM author 
WHERE aut_name REGEXP '^w';
```


The following statement will find the author’s name __beginning with ‘w’ exactly in lower case__, because for case sensitivity BINARY operator has been used. 

```
SELECT * FROM author 
WHERE aut_name REGEXP BINARY '^w'; 
```

The following statement will find the author’s name __ending with ‘on’__. The ‘$’ character have been used to match the ending of the name.

```
SELECT * 
FROM author 
WHERE aut_name REGEXP "on$" ;
```

The following statement will find the author’s name __containing a ‘t’__.

```
SELECT * 
FROM author 
WHERE aut_name REGEXP "t"; 
```

The following statement will find the author’s name __containing a ‘z’ or ‘v’ or ‘y’__.

```
SELECT * FROM author 
WHERE aut_name REGEXP "[zvy]";
```


The following statement will find the author’s name __containing characters from ‘x’ to ‘z’__.

```
SELECT * FROM author 
WHERE aut_name REGEXP "[x-z]";
```


The following statement will find the author’s name __containing exactly 12 characters__. Use ‘^’ and ‘$’ match the beginning and ending of the name and twelve instances of ‘.’ have been used for maintaining twelve characters.

```
SELECT * 
FROM author 
WHERE aut_name REGEXP '^............$'; 
```


The following statement will find the author’s name containing exactly 12 characters. Use ‘^’ and ‘$’ match the beginning and ending of the name and __‘{12}’ have been after ‘.’ for repeating ‘.’ twelve times__.

```
SELECT * FROM author
WHERE aut_name REGEXP '^.{12}$';
```

Query to find all the names starting with 'st' −

```
SELECT name FROM person_tbl WHERE name REGEXP '^st';
```

Query to find all the names ending with 'ok' −

```
SELECT name FROM person_tbl WHERE name REGEXP 'ok$';
```

Query to find all the names, which contain 'mar' −

```
SELECT name FROM person_tbl WHERE name REGEXP 'mar';
```

Query to find all the names starting with a vowel and ending with 'ok' −

```
SELECT name FROM person_tbl WHERE name REGEXP '^[aeiou]|ok$';
```
