# Duplicate Emails

## Description
Write a SQL query to find all duplicate emails in a table named Person.
```
+----+---------+
| Id | Email   |
+----+---------+
| 1  | a@b.com |
| 2  | c@d.com |
| 3  | a@b.com |
+----+---------+
```
For example, your query should return the following for the above table:
```
+---------+
| Email   |
+---------+
| a@b.com |
+---------+
```

## Optimal solution
- Code
```
select Email
from Person
group by Email
having count(Email) > 1;
```
-Performance
  - Runtime: 173 ms, faster than 98.94% of MySQL online submissions for Duplicate Emails.
  - Memory Usage: 0B, less than 100.00% of MySQL online submissions for Duplicate Emails.
