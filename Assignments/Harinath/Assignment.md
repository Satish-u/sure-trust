ASSIGNMENT

Employee Table:
	select*from emp;
Department Table:
	select*from dept;

1.Total number of Employees.

  	select count(*)from emp;

2.Total number of departments.

	select count(*)from dept;

3.All the Employees.

	select ename from emp;

4.All the Departments.

	select dname from dept; 

5.Total Salary paid for all Employees.

	select sum(sal)from emp;

6.Total Commission paid to all employees.

	select sum(comm)from emp;

7.Which job titles of the Employees get commission paid.

	select job,comm from emp where comm is not null;

8.System Date.

	select sysdate from dual;

9.Average Salary paid to all Employees.

	select avg(sal)from emp;

10.How many Employees are there in each department?

	select dname,count(ename) from dept full join emp on dept.deptno=emp.deptno group by dname;

11.Total Salary of the Employees in each Department?

	select dname,sum(sal) from dept full join emp on dept.deptno=emp.deptno group by dname;

12.How many Employees are there under each job title?

	select job,count(*)  from emp group by job;

13.Average Salary paid for each job titles.

	select job,avg(sal) from emp group by job;

14.Hire day,month and yearfor each Employee.

 	Select ename,to_char(hiredate,'Day'),to_char(hiredate,'MM'),to_char(hiredate,'YYYY') from emp;

15.Sort the Employee Department wise.

	select dname,ename from emp inner join dept on emp.deptno=dept.deptno order by dname asc;

16.Sort the Employees based on their job titles.

	select job,ename from emp order by job asc;

17.Sort the Employees based on descending order of theirSalaries.

	select ename,sal from emp order by sal desc;

18.Sort the Employees ascending order of their department and             descending order of their salary.

	select ename, dname, sal from emp full join dept on emp.deptno=dept.deptno order by dname asc,sal desc;

19.How many Employees have their name with 6 characters.

	select count(ename) from emp where length(ename)=6;

20.Maximum and minimum salary paid.

	select max(sal),min(sal)from emp;

21.Maximum,Minimum,average and sum of salary paid under each department.

	select dname,max(sal),min(sal),avg(sal),sum(sal) from emp full join dept on emp.deptno=dept.deptno group by dname;

22.Sort the employee based on their hire date.

	select ename,hiredate from emp order by hiredate asc;

23.Employee who joined latest.

	select ename,hiredate from emp order by hiredate desc fetch first row only;

24.Who is the oldest employee in the organization based on their hire date.

	select ename,hiredate from emp order by hiredate asc fetch first row only;

25.Sort the employee based on their hire year(descending) and department(ascending).

	select ename,hiredate,dname from emp full join dept on emp.deptno=dept.deptno order by hiredate desc,dname asc;

26.Employees who get salaries greater than or equal to the average salary of employee.

	select ename,sal from emp where sal>=(select avg(sal) from emp);

27. Employees who get salary less than or equal to the average salary of employee.

	select ename,sal from emp where sal<=(select avg(sal) from emp);

28.Employees get salaries between 2000 and 4000.

	select ename,sal from emp where sal between 2000 and 4000;

29.Which employees get the highest and lowest salary?

	select ename,sal from emp where sal=(select max(sal) from emp) union select ename,sal from emp where sal=(select min(sal) from 	emp);

30.We need to celebrate the joining month of the employees.We plan to buy a gift of each of them.How many gifts do I need to buy for next month?

	select count(to_char(hiredate,'MON'))
	from emp
	where to_char(hiredate,'MON')='MAY';
