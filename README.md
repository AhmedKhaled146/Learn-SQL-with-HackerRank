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

### Weather Observation Station 7
**6. Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY LIKE '%a' 
   OR CITY LIKE '%e' 
   OR CITY LIKE '%i' 
   OR CITY LIKE '%o' 
   OR CITY LIKE '%u'
ORDER BY CITY;
```

### Weather Observation Station 8
**7. Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates.**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE (CITY LIKE 'A%a' OR CITY LIKE 'A%e' OR CITY LIKE 'A%i' OR CITY LIKE 'A%o' OR CITY LIKE 'A%u')
   OR (CITY LIKE 'E%a' OR CITY LIKE 'E%e' OR CITY LIKE 'E%i' OR CITY LIKE 'E%o' OR CITY LIKE 'E%u')
   OR (CITY LIKE 'I%a' OR CITY LIKE 'I%e' OR CITY LIKE 'I%i' OR CITY LIKE 'I%o' OR CITY LIKE 'I%u')
   OR (CITY LIKE 'O%a' OR CITY LIKE 'O%e' OR CITY LIKE 'O%i' OR CITY LIKE 'O%o' OR CITY LIKE 'O%u')
   OR (CITY LIKE 'U%a' OR CITY LIKE 'U%e' OR CITY LIKE 'U%i' OR CITY LIKE 'U%o' OR CITY LIKE 'U%u')
   OR (CITY LIKE 'a%a' OR CITY LIKE 'a%e' OR CITY LIKE 'a%i' OR CITY LIKE 'a%o' OR CITY LIKE 'a%u')
   OR (CITY LIKE 'e%a' OR CITY LIKE 'e%e' OR CITY LIKE 'e%i' OR CITY LIKE 'e%o' OR CITY LIKE 'e%u')
   OR (CITY LIKE 'i%a' OR CITY LIKE 'i%e' OR CITY LIKE 'i%i' OR CITY LIKE 'i%o' OR CITY LIKE 'i%u')
   OR (CITY LIKE 'o%a' OR CITY LIKE 'o%e' OR CITY LIKE 'o%i' OR CITY LIKE 'o%o' OR CITY LIKE 'o%u')
   OR (CITY LIKE 'u%a' OR CITY LIKE 'u%e' OR CITY LIKE 'u%i' OR CITY LIKE 'u%o' OR CITY LIKE 'u%u')
ORDER BY CITY;
```

### Weather Observation Station 9
**8. Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT LIKE 'A%'
  AND CITY NOT LIKE 'E%'
  AND CITY NOT LIKE 'I%'
  AND CITY NOT LIKE 'O%'
  AND CITY NOT LIKE 'U%'
  AND CITY NOT LIKE 'a%'
  AND CITY NOT LIKE 'e%'
  AND CITY NOT LIKE 'i%'
  AND CITY NOT LIKE 'o%'
  AND CITY NOT LIKE 'u%'
ORDER BY CITY;
```

### Weather Observation Station 10
**9. Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.**
```sql
SELECT DISTINCT CITY
FROM STATION
WHERE CITY NOT LIKE '%A'
  AND CITY NOT LIKE '%E'
  AND CITY NOT LIKE '%I'
  AND CITY NOT LIKE '%O'
  AND CITY NOT LIKE '%U'
  AND CITY NOT LIKE '%a'
  AND CITY NOT LIKE '%e'
  AND CITY NOT LIKE '%i'
  AND CITY NOT LIKE '%o'
  AND CITY NOT LIKE '%u'
ORDER BY CITY;
```

### Weather Observation Station 11
**10. Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels. Your result cannot contain duplicates.**
```sql

```

### Revising Aggregations - The Sum Function
**11.Query the total population of all cities in CITY where District is California.**
```sql
SELECT SUM(Population) FROM CITY WHERE District = 'California';
```

### Average Population
**12. Query the average population for all cities in CITY rounded down to the nearest integer.**
```sql
SELECT FLOOR(AVG(Population)) FROM CITY;
```

### African Cities
**13. Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'. Note: CITY.CountryCode and COUNTRY.Code are matching key columns**
```sql
SELECT Name FROM CITY WHERE CountryCode IN (SELECT Code FROM COUNTRY WHERE Continent = 'Africa');
```

### Average Population of Each Continent
**14. Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer. Note: CITY.CountryCode and COUNTRY.Code are matching key columns**
```sql
SELECT COUNTRY.Continent, FLOOR(AVG(CITY.Population)) AS AvgPopulation
FROM CITY
JOIN COUNTRY ON CITY.CountryCode = COUNTRY.Code
GROUP BY COUNTRY.Continent;
```

### Placements
**15. You are given three tables: Students, Friends and Packages. Students contains two columns: ID and Name. Friends contains two columns: ID and Friend_ID (ID of the ONLY best friend). Packages contains two columns: ID and Salary (offered salary in $ thousands per month).**
```sql
SELECT s.Name
FROM Students s
JOIN Friends f ON s.ID = f.ID
JOIN Packages p1 ON s.ID = p1.ID
JOIN Packages p2 ON f.Friend_ID = p2.ID
WHERE p2.Salary > p1.Salary
ORDER BY p2.Salary;
```
