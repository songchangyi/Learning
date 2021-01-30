# Second Highest Salary

## Description
Write a SQL query to get the second highest salary from the Employee table.
```
+----+--------+
| Id | Salary |
+----+--------+
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |
+----+--------+
```
For example, given the above Employee table, the query should return 200 as the second highest salary. 

If there is no second highest salary, then the query should return null.
```
+---------------------+
| SecondHighestSalary |
+---------------------+
| 200                 |
+---------------------+
```

## My solution
- Code
```
select
    (select distinct 
            Salary 
        from 
            Employee
        order by Salary desc
        limit 1 offset 1) as SecondHighestSalary 
;
```
- Performance
  - Runtime: 290 ms, faster than 49.32% of MySQL online submissions for Second Highest Salary.
  - Memory Usage: 0B, less than 100.00% of MySQL online submissions for Second Highest Salary.
  
## Optimal solution
- Code
```
SELECT
    IFNULL(
      (SELECT DISTINCT Salary
       FROM Employee
       ORDER BY Salary DESC
        LIMIT 1 OFFSET 1),
    NULL) AS SecondHighestSalary
;
```
- Performance
  - Runtime: 144 ms, faster than 89.39% of MySQL online submissions for Second Highest Salary.
  - Memory Usage: 0B, less than 100.00% of MySQL online submissions for Second Highest Salary.
