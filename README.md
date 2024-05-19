# Solve SQL With HackerRank

The CITY table is described as follows:
![alt text](sql-CITY.jpg)

> All the coming Question on this Table.
### Revising the Select Query I
**1. Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.**

``` SELECT * FROM CITY WHERE CountryCode = 'USA' AND Population > 100000; ```

### Revising the Select Query II
**2. Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.**

``` SELECT NAME FROM CITY WHERE CountryCode = 'USA' AND Population > 120000; ```

### Select All
**3. Query all columns (attributes) for every row in the CITY table.**

``` SELECT * FROM CITY; ```

### Select By ID
**4. Query all columns for a city in CITY with the ID 1661.**

``` SELECT * FROM CITY WHERE id = 1661; ```

### Japanese Cities' Attributes
**5. Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.**

``` SELECT * FROM CITY WHERE CountryCode = 'JPN'; ```

### Japanese Cities' Name
**6. Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.**

``` SELECT NAME FROM CITY WHERE CountryCode = 'JPN'; ```

<hr>

![alt text](SQL-Station.jpg)


