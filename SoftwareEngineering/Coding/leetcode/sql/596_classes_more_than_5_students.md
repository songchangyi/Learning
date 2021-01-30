# Classes More Than 5 Students

## Description
There is a table courses with columns: student and class

Please list out all classes which have more than or equal to 5 students.

For example, the table:
```
+---------+------------+
| student | class      |
+---------+------------+
| A       | Math       |
| B       | English    |
| C       | Math       |
| D       | Biology    |
| E       | Math       |
| F       | Computer   |
| G       | Math       |
| H       | Math       |
| I       | Math       |
+---------+------------+
```
Should output:
```
+---------+
| class   |
+---------+
| Math    |
+---------+
```
 
***Note:***
The students should not be counted duplicate in each course.

## My solution
- Code
```
SELECT DISTINCT class FROM
    (SELECT COUNT(DISTINCT student) AS cnt, class FROM courses
    GROUP BY class) AS stats
WHERE cnt >= 5
;
```
- Performance
  - Runtime: 381 ms, faster than 40.73% of MySQL online submissions for Classes More Than 5 Students.
  - Memory Usage: 0B, less than 100.00% of MySQL online submissions for Classes More Than 5 Students.

## Optimal solution
- Code
```
SELECT
    class
FROM
    courses
GROUP BY class
HAVING COUNT(DISTINCT student) >= 5
;
```
- Performance
  - Runtime: 282 ms, faster than 52.61% of MySQL online submissions for Classes More Than 5 Students.
  - Memory Usage: 0B, less than 100.00% of MySQL online submissions for Classes More Than 5 Students.
