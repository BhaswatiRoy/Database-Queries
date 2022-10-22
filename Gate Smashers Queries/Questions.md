### 1. Write an SQL query to display maximum/highest salary from 'employee' table

select max(salary) from employee;

### 2. Write an SQL query to display the name of employee who has maximum/highest salary from 'employee' table

select name from employee where salary = (select max(salary) from employee);

### 3.  Write an SQL query to display the 2nd maximum salary from 'employee' table

select max(salary) from employee where salary <> (select max(salary) from employee);

### 4. Write an SQL query to display the name of employee who has 2nd maximum salary from 'employee' table

select name from employee where salary = (select max(salary) from employee where salary <> (select max(salary) from employee))

### 5. Write an SQL query to display all the department names along with number/count of employees working in that

select department, count( * ) from employee group by department;
