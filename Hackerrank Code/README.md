`1. Revising the Select Query I`

    SELECT * FROM CITY WHERE CountryCode='USA' AND POPULATION>100000;


`2. Revising the Select Query II`

    SELECT NAME FROM CITY WHERE POPULATION>120000 AND COUNTRYCODE='USA';


`3. Select All`

    SELECT * FROM CITY;


`4. Select By ID`

    SELECT * FROM CITY WHERE ID=1661;


`5. Japanese Cities' Attributes`

    SELECT * FROM CITY WHERE COUNTRYCODE='JPN';


`6. Japanese Cities' Names`

    SELECT NAME FROM CITY WHERE COUNTRYCODE='JPN';


`7. Weather Observation Station 1`

    SELECT CITY,STATE FROM STATION;


`8. Weather Observation Station 3 -> return even ids`

    SELECT DISTINCT CITY FROM STATION WHERE MOD(ID,2)=0;


`9. Weather Observation Station 4 -> return (no of cities - no of distinct cities)`

    SELECT (COUNT(CITY)-COUNT(DISTINCT CITY)) FROM STATION;


`10. Weather Observation Station 5 -> return shortest & longest city names`

     SELECT DISTINCT CITY, LENGTH(CITY) FROM STATION ORDER BY LENGTH(CITY) ASC LIMIT 1;
     SELECT DISTINCT CITY, LENGTH(CITY) FROM STATION ORDER BY LENGTH(CITY) DESC LIMIT 1;


11. `Weather Observation Station 6 -> return city names starting with vowels`

     SELECT DISTINCT CITY FROM STATION WHERE 
     CITY LIKE "a%" 
     OR CITY LIKE "e%" 
     OR CITY LIKE "i%" 
     OR CITY LIKE "o%" 
     OR CITY LIKE "u%";


12. `Weather Observation Station 7 -> return city names ending with vowels`

     SELECT DISTINCT CITY FROM STATION WHERE
     CITY LIKE "%a"
     OR CITY LIKE "%e"
     OR CITY LIKE "%i"
     OR CITY LIKE "%o"
     OR CITY LIKE "%u";


13. `Weather Observation Station 8 -> return city names that start and end with vowels so there can be total 25 combinations as it can start and end with different vowels`

     -- Thus using Regex Expressions - ^ means starting with regex, $ means ending with regex
     SELECT CITY FROM STATION WHERE 
     CITY REGEXP '^[aeiou]' AND CITY REGEXP '[aeiou]$';


14. `Weather Observation Station 9 -> return city whose names don't start with vowels`

     SELECT DISTINCT CITY FROM STATION WHERE NOT CITY REGEXP '^[aeiou]';


15. `Weather Observation Station 10 -> return city whose names don't end with vowels`

     SELECT DISTINCT CITY FROM STATION WHERE NOT CITY REGEXP '[aeiou]$';


16. `Weather Observation Station 11 -> return city whose names either don't start with vowels or don't end with vowels`

     SELECT DISTINCT CITY FROM STATION WHERE NOT CITY REGEXP '^[aeiou]' OR NOT CITY REGEXP '[aeiou]$';

17. `Weather Observation Station 12 -> return city whose names either don't start with vowels and don't end with vowels`

     SELECT DISTINCT CITY FROM STATION WHERE NOT CITY REGEXP '^[aeiou]' AND NOT CITY REGEXP '[aeiou]$';
     
18. `Higher Than 75 Marks -> return name of students who got more than 75 marks and order them by last 3 alphabets of name, secondary order them by id`
   
     -- RIGHT(colname,x) chooses x characters from right side/last of colname column values
     SELECT NAME FROM STUDENTS WHERE MARKS>75 ORDER BY RIGHT(NAME,3), ID;

19. `Employee Names -> return names of employees arranged in ascending order`

     SELECT NAME FROM EMPLOYEE ORDER BY NAME;
     
20. `Employee Salaries -> return employee names whose salary is more than 2000 per month and have worked for less than 10 months ordered in ascending format`

     SELECT NAME FROM EMPLOYEE WHERE SALARY>2000 AND MONTHS<10 ORDER BY EMPLOYEE_ID;
     
21. `Population Census -> join tables city and country and find sum of population of all cities where continent is 'Asia'`

     SELECT SUM(CITY.POPULATION) FROM CITY JOIN COUNTRY
     ON CITY.COUNTRYCODE=COUNTRY.CODE
     WHERE CONTINENT='ASIA';
   
22.  `African Cities -> join tables city and country and find city names where continent is 'Africa'`

      SELECT CITY.NAME FROM CITY JOIN COUNTRY
      ON CITY.COUNTRYCODE=COUNTRY.CODE
      WHERE CONTINENT='AFRICA';
     
23. `Average Population of Each Continent -> join tables city and country and find name of all continents and their respective average city population`

     -- GROUP BY is used to group rows into summary rows like finding sum/count/average
     SELECT COUNTRY.CONTINENT, FLOOR(AVG(CITY.POPULATION)) FROM CITY JOIN COUNTRY
     ON CITY.COUNTRYCODE=COUNTRY.CODE 
     GROUP BY COUNTRY.CONTINENT;
     
24. `The Report ->  join tables students and grades and find students with >8 grade and student names with <8 grade will be replaced by NULL`

     SELECT IF(GRADE<8,NULL,NAME),GRADE,MARKS 
     FROM STUDENTS JOIN GRADES
     WHERE STUDENTS.MARKS BETWEEN GRADES.MIN_MARK AND GRADES.MAX_MARK
     ORDER BY GRADE DESC, NAME ASC;
     
25. 
