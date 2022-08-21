`1757. Recyclable and Low Fat Products`

       SELECT PRODUCT_ID FROM PRODUCTS WHERE LOW_FATS='Y' AND RECYCLABLE='Y';

`175. Combine Two Tables`

      # left join as left table-person is 
      SELECT PERSON.firstname, PERSON.lastname, ADDRESS.city, ADDRESS.state 
      FROM PERSON LEFT JOIN ADDRESS
      ON PERSON.PERSONID=ADDRESS.PERSONID

`181. Employees Earning More Than Their Managers` 
     
     SELECT E1.NAME AS EMPLOYEE
     FROM EMPLOYEE AS E1 JOIN EMPLOYEE AS E2
     ON E1.MANAGERID=E2.ID
     WHERE E1.SALARY>E2.SALARY;
     
`182. Duplicate Emails`
     
     SELECT EMAIL AS Email FROM PERSON
     GROUP BY EMAIL
     HAVING COUNT(EMAIL)>1;
     
`183. Customers Who Never Order`

     SELECT CUSTOMERS.NAME AS Customers FROM CUSTOMERS
     WHERE CUSTOMERS.ID NOT IN (SELECT ORDERS.CUSTOMERID FROM ORDERS);
     
`511. Game Play Analysis I`

     SELECT PLAYER_ID, MIN(EVENT_DATE) AS FIRST_LOGIN 
     FROM ACTIVITY
     GROUP BY PLAYER_ID;

`1741. Find Total Time Spent by Each Employee`

     SELECT EVENT_DAY AS day, EMP_ID AS emp_id, SUM(OUT_TIME-IN_TIME) AS total_time FROM EMPLOYEES
     GROUP BY EMP_ID,DAY;
     
`1693. Daily Leads and Partners`

     SELECT DISTINCT DATE_ID AS date_id, MAKE_NAME AS make_name, COUNT(DISTINCT(LEAD_ID)) AS unique_leads, COUNT(DISTINCT(PARTNER_ID)) AS unique_partners
     FROM DAILYSALES
     GROUP BY DATE_ID,MAKE_NAME;
     
`1587. Bank Account Summary II`

     SELECT USERS.NAME, SUM(TRANSACTIONS.AMOUNT) AS BALANCE
     FROM USERS JOIN TRANSACTIONS
     ON USERS.ACCOUNT=TRANSACTIONS.ACCOUNT
     GROUP BY TRANSACTIONS.ACCOUNT HAVING SUM(TRANSACTIONS.AMOUNT)>10000
     
`1965. Employees With Missing Information`

     --UNION is used to combine results of 2 or more select statements, columns must have similar data and must be in similar order
     --this part means entire employees and common part of salaries & employees so NULL values of salaries are missing information
     SELECT EMPLOYEES.EMPLOYEE_ID 
     FROM EMPLOYEES LEFT JOIN SALARIES
     ON EMPLOYEES.EMPLOYEE_ID=SALARIES.EMPLOYEE_ID
     WHERE SALARIES.EMPLOYEE_ID IS NULL
     UNION
     --this part means entire salaries and common part of salaries & employees so NULL values of employees are missing information
     SELECT SALARIES.EMPLOYEE_ID 
     FROM SALARIES LEFT JOIN EMPLOYEES
     ON EMPLOYEES.EMPLOYEE_ID=SALARIES.EMPLOYEE_ID
     WHERE EMPLOYEES.EMPLOYEE_ID IS NULL
     ORDER BY EMPLOYEE_ID;

`595. Big Countries`

     SELECT NAME,POPULATION,AREA
     FROM WORLD
     WHERE AREA>=3000000 OR POPULATION>=25000000
     
`1407. Top Travellers`
    
     --if there is any user who didn't travel any distance then mark them as 0 otherwise find sum of distance of all other users who travelled some distance
     SELECT USERS.NAME, SUM(IFNULL(RIDES.DISTANCE,0)) AS TRAVELLED_DISTANCE
     FROM USERS LEFT JOIN RIDES
     ON USERS.ID=RIDES.USER_ID
     GROUP BY RIDES.USER_ID
     ORDER BY TRAVELLED_DISTANCE DESC, NAME ASC
     
`620. Not Boring Movies`
     
     SELECT ID,MOVIE,DESCRIPTION,RATING 
     FROM CINEMA
     WHERE ID%2!=0 
     AND DESCRIPTION != "BORING"
     ORDER BY RATING DESC
     
`1050. Actors and Directors Who Cooperated At Least Three Times`
     
     SELECT ACTOR_ID,DIRECTOR_ID
     FROM ACTORDIRECTOR
     GROUP BY ACTOR_ID,DIRECTOR_ID
     HAVING COUNT(*)>=3

`584. Find Customer Referee`
   
     SELECT NAME FROM CUSTOMER
     WHERE REFEREE_ID IS NULL 
     OR REFEREE_ID!=2
