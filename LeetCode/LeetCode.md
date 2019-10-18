# 175 组合两个表*

编写一个 SQL 查询，满足条件：无论 person 是否有地址信息，都需要基于上述两表提供 person 的以下信息：

```
FirstName, LastName, City, State
```

SQL架构

```
Create table Person (PersonId int, FirstName varchar(255), LastName varchar(255));

Create table Address (AddressId int, PersonId int, City varchar(255), State varchar(255));

Truncate table Person;
insert into Person (PersonId, LastName, FirstName) values ('1', 'Wang', 'Allen');

Truncate table Address;
insert into Address (AddressId, PersonId, City, State) values ('1', '2', 'New York City', 'New York');
```

解答

```
select t1.FirstName,t1.LastName,t2.City,t2.State
from person t1 left join address t2
on t1.PersonId = t2.PersonId
```



# 176 第二高的薪水*

编写一个 SQL 查询，获取 `Employee` 表中第二高的薪水（Salary） 。

+----+--------+
| Id | Salary |
+----+--------+
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |
+----+--------+ 

例如上述 `Employee` 表，SQL查询应该返回 `200` 作为第二高的薪水。如果不存在第二高的薪水，那么查询应返回 `null`

+---------------------+
| SecondHighestSalary |
+---------------------+
| 200                 |
+---------------------+



SQL架构

```
Create table If Not Exists Employee (Id int, Salary int);
Truncate table Employee;
insert into Employee (Id, Salary) values ('1', '100');
insert into Employee (Id, Salary) values ('2', '200');
insert into Employee (Id, Salary) values ('3', '300');
```

解答

```
select ifnull(
	(select distinct salary 
		from employee order by salary desc limit 1,1),null
) as SecondHighestSalary

```

