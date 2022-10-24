## Employee Table - Id, Name, Department, Salary

### 1. Write an SQL query to display maximum/highest salary 

select max(salary) from employee;

### 2. Write an SQL query to display the name of employee who has maximum/highest salary from 'employee' table

select name from employee where salary = (select max(salary) from employee);

### 3.  Write an SQL query to display the 2nd maximum salary from 'employee' table

select max(salary) from employee where salary <> (select max(salary) from employee);

### 4. Write an SQL query to display the name of employee who has 2nd maximum salary from 'employee' table

select name from employee where salary = (select max(salary) from employee where salary <> (select max(salary) from employee))

### 5. Write an SQL query to display all the department names along with number/count of employees working in that

select department, count( * ) from employee group by department;

### 6. Write a query to display all employee names of the departments where number of employees are less than 2

select name from employee where department in (select department from employee group by department having count( * ) < 2);

### 7. Write a query to display highest salary department wise and name of employees who is taking that salary

select name from employee where salary in (select max(salary) from employee group by department);


## Employee Table - EId(primary key), EName, Address  &&  Project Table - EId(primary key), PId (foreign key), PName, Location

### 8. Write a query to find details of employee whose address is either Delhi/Chandigarh/Pune

select * from employee where address in ('Delhi', 'Chandigarh', 'Pune');

### 9. Write a query to find details of employee whose address is not amongst Delhi/Chandigarh/Pune

select * from employee where address not in ('Delhi', 'Chandigarh', 'Pune');

### 10. Write a query to find the name of employees who are working on a project

select ename from employee where eid in (select distinct(eid) from project)

### 11. Write a query to find the name of employees who are not working on a project

select ename from employee where eid not in (select distinct(eid) from project)

### 12. Write a query to find the details of employees who are working on atleast 1 project

select * from employee where eid exists (select eid from project where project.eid =  employee.eid)

### 13. Write a query to find the details of employees who are working on any projects

select * from employee where eid not exists (select eid from project where project.eid =  employee.eid)

### 14. Write a query to find sum of all distinct salaries 

select distinct(sum(salary)) from employee;

### 15. Write a query to find the name and salary value of nth highest salary

select name,salary from employee e1 where n-1 = (select count(distinct(salary)) from employee e2 where e2.salary > e1.salary)

