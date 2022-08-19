1. Revising the Select Query I

SELECT * FROM CITY WHERE CountryCode='USA' AND POPULATION>100000;


2. Revising the Select Query II

SELECT NAME FROM CITY WHERE POPULATION>120000 AND COUNTRYCODE='USA';


3. Select All

SELECT * FROM CITY;


4. Select By ID

SELECT * FROM CITY WHERE ID=1661;


5. Japanese Cities' Attributes

SELECT * FROM CITY WHERE COUNTRYCODE='JPN';


6. Japanese Cities' Names

SELECT NAME FROM CITY WHERE COUNTRYCODE='JPN';


7. Weather Observation Station 1

SELECT CITY,STATE FROM STATION;


8. Weather Observation Station 3 -> return even ids

SELECT DISTINCT CITY FROM STATION WHERE MOD(ID,2)=0;


9. Weather Observation Station 4 -> return (no of cities - no of distinct cities)

SELECT (COUNT(CITY)-COUNT(DISTINCT CITY)) FROM STATION;


10. Weather Observation Station 5 -> return shortest & longest city names

SELECT DISTINCT CITY, LENGTH(CITY) FROM STATION ORDER BY LENGTH(CITY) ASC LIMIT 1;
SELECT DISTINCT CITY, LENGTH(CITY) FROM STATION ORDER BY LENGTH(CITY) DESC LIMIT 1;


11. Weather Observation Station 6 -> return city names starting with vowels

SELECT DISTINCT CITY FROM STATION WHERE 
CITY LIKE "a%" 
OR CITY LIKE "e%" 
OR CITY LIKE "i%" 
OR CITY LIKE "o%" 
OR CITY LIKE "u%";


12. Weather Observation Station 7 -> return city names ending with vowels

SELECT DISTINCT CITY FROM STATION WHERE
CITY LIKE "%a"
OR CITY LIKE "%e"
OR CITY LIKE "%i"
OR CITY LIKE "%o"
OR CITY LIKE "%u";


13. Weather Observation Station 8 -> return city names that start and end with vowels so there can be total 25 combinations as it can start and end with different vowels

-- Thus using Regex Expressions - ^ means starting with regex, $ means ending with regex
SELECT CITY FROM STATION WHERE 
CITY REGEXP '^[aeiou]' AND CITY REGEXP '[aeiou]$';


14. Weather Observation Station 9 -> return city whose names don't start with vowels

SELECT DISTINCT CITY FROM STATION WHERE NOT CITY REGEXP '^[aeiou]';


15. Weather Observation Station 10 -> return city whose names don't end with vowels

SELECT DISTINCT CITY FROM STATION WHERE NOT CITY REGEXP '[aeiou]$';
