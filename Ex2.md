# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into manager values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into manager values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into manager values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
```
## Creating table query:
```
create table manager(enumber number(6),ename char(15),salary number(5),commission number(4),annualsalary number(7),Hiredate date,designation char(10),deptno number(2),reporting char(10));
insert into managers values(7369,'Dharsan',2500,500,30000,'30-June-81','clerk',10,'John');
insert into managers values(7839,'Subu',3000,400,36000,'1-Jul-82','manager',null,'James');
insert into managers values(7934,'Aadhi',3500,300,42000,'1-May-82','manager',30,NULL);
insert into managers values(7788,'Vikash',4000,0,48000,'12-Aug-82','clerk',50,'Bond');
select * from managers;
```
## Output:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/f25488ef-f5b6-49f3-9913-3cf09e5f13aa)

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
```
update managers set salary=(salary*0.10)+salary;
```

### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/67b2b53c-e6c8-46ff-b155-8ce41154dbdc)

### Q2) Delete the records from manager table where the salary less than 2750.


### QUERY:
```
delete managers where salary<2750;
```

### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/d4528337-5174-468a-a201-34b2390b166a)

### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)


### QUERY:
```
SELECT 
ename AS "Name",
salary*12 AS "Annual salary"
FROM
managers;
```

### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/da58d0b0-df81-4b89-94d0-6f96e21672ff)

### Q5)	List the names of Clerks from emp table.


### QUERY:
```
select ename from managers where designation='clerk';
```
### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/e266756a-c42e-47d3-a4b1-ab1e32389484)


### Q6)	List the names of employee who are not Managers.


### QUERY:
```
select ename from managers where designation!='manager';
```

### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/4862c97e-2d0f-40ed-85a4-030d27549670)


### Q7)	List the names of employees not eligible for commission.


### QUERY:
```
select ename from managers where commission=0;
```
### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/5697e2ce-ea89-439f-aca8-f46234835bf4)


### Q8)	List employees whose name either start or end with ‘s’.


### QUERY:
```
select ename from managers where ename LIKE 'S%' OR ename LIKE '%S';
```
### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/e5fce914-e740-43b0-9025-f935173939c8)


### Q9) Sort emp table in ascending order by hire-date and list ename, job, deptno and hire-date.


### QUERY:
```
select ename,designation,deptno,hiredate from managers order by hiredate ASC;
```

### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/aeca3bda-d5e6-4194-8781-6324ae042172)


### Q10) List the Details of Employees who have joined before 30 Sept 81.


### QUERY:
```
select * from managers where hiredate<'30 SEP 81';
```
### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/f3eff889-77a6-4d98-91d4-df93ab846c9c)


### Q11)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.


### QUERY:
```
select ename,deptno,salary from managers ORDER BY deptno ASC,salary desc;
```

### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/d01fbbaa-ad01-4dfb-b2a4-dd845f91e925)


### Q12) List the names of employees not belonging to dept no 30,40 & 10


### QUERY:
```
select ename from managers where deptno NOT IN (30,40,10);
```
### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/8429121f-a12a-4c2e-bd20-3861dfe20da6)

### Q13) Find number of rows in the table EMP

### QUERY:
```
select count(*) as rownumber from managers;
```
### OUTPUT:

![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/aa80ba0d-674d-495e-8aa3-23f525ea176d)

### Q14) Find maximum, minimum and average salary in EMP table.

### QUERY:
```
select MAX(salary) as maximumsal,MIN(salary) as minimumsal,AVG(salary) as averagesal from managers;
```

### OUTPUT:

![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/c34c581f-929e-42e2-80ef-dd48784bafb6)

### Q15) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
```
select designation,count(*) as number_employee from managers GROUP BY designation ORDER BY number_employee DESC;
```

### OUTPUT:
![image](https://github.com/Jeevapriya14/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/121003043/a4661ee1-8e09-4f4c-9a20-589b02596335)
