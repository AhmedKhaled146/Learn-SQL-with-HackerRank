# Solve SQL With HackerRank

## Basic Select 

The CITY table is described as follows:
<br>
![alt text](sql-CITY.jpg)

> All the coming Question on this Table.
### Revising the Select Query I
**1. Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.**

```sql
SELECT * FROM CITY WHERE CountryCode = 'USA' AND Population > 100000;
```

### Revising the Select Query II
**2. Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.**

```sql
SELECT NAME FROM CITY WHERE CountryCode = 'USA' AND Population > 120000;
```

### Select All
**3. Query all columns (attributes) for every row in the CITY table.**

```sql
SELECT * FROM CITY;
```

### Select By ID
**4. Query all columns for a city in CITY with the ID 1661.**

```sql
SELECT * FROM CITY WHERE id = 1661;
```

### Japanese Cities' Attributes
**5. Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.**

```sql
SELECT * FROM CITY WHERE CountryCode = 'JPN';
```

### Japanese Cities' Name
**6. Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.**

```sql 
SELECT NAME FROM CITY WHERE CountryCode = 'JPN';
```


<hr>

![alt text](SQL-Station.jpg)

> All the coming Question on this Table.
### Weather Observation Station 1
**1. Query a list of CITY and STATE from the STATION table.**

```sql 
SELECT CITY, STATE FROM STATION;
```
### Weather Observation Station 3
**2. Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.**

```sql
SELECT DISTINCT CITY FROM STATION WHERE MOD(ID, 2) = 0;
```

### Weather Observation Station 4
**3. Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.**
```sql
SELECT 
    (COUNT(CITY) - COUNT(DISTINCT CITY)) AS difference
FROM 
    STATION;
```

### Weather Observation Station 5
**4. Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.**
```sql
SELECT CITY, LENGTH(CITY) AS LENGTH1
FROM STATION
ORDER BY LENGTH(CITY) ASC, CITY ASC
LIMIT 1;


SELECT CITY, LENGTH(CITY) AS LENGTH2
FROM STATION
ORDER BY LENGTH(CITY) DESC, CITY ASC
LIMIT 1;
```

### Weather Observation Station 6
**5. Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION. Your result cannot contain duplicates.**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY LIKE 'A%' 
   OR CITY LIKE 'E%' 
   OR CITY LIKE 'I%' 
   OR CITY LIKE 'O%' 
   OR CITY LIKE 'U%'
ORDER BY CITY;
```