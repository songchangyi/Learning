# Employees Earning More Than Their Managers

## Description
The Employee table holds all employees including their managers. Every employee has an Id, and there is also a column for the manager Id.
```
+----+-------+--------+-----------+
| Id | Name  | Salary | ManagerId |
+----+-------+--------+-----------+
| 1  | Joe   | 70000  | 3         |
| 2  | Henry | 80000  | 4         |
| 3  | Sam   | 60000  | NULL      |
| 4  | Max   | 90000  | NULL      |
+----+-------+--------+-----------+
```
Given the Employee table, write a SQL query that finds out employees who earn more than their managers. For the above table, Joe is the only employee who earns more than his manager.
```
+----------+
| Employee |
+----------+
| Joe      |
+----------+
```

## Optimal solution
- Code
```
select 
    a.Name as 'Employee'
from 
    Employee as a, 
    Employee as b 
where 
    a.ManagerId = b.Id
    and a.Salary > b.Salary
;
```
- Performance
  - Runtime: 376 ms, faster than 76.41% of MySQL online submissions for Employees Earning More Than Their Managers.
  - Memory Usage: 0B, less than 100.00% of MySQL online submissions for Employees Earning More Than Their Managers.
