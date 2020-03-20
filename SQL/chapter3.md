# 查询数据

## 准备数据
```
mysql -u root -p < init-test-data.sql
```

## 基本查询
```
SELECT * FROM students;
```
虽然SELECT可以用作计算，但它并不是SQL的强项。
但是，不带FROM子句的SELECT语句有一个有用的用途，就是用来判断当前到数据库的连接是否有效。
许多检测工具会执行一条SELECT 1;来测试数据库连接。

## 条件查询
```
SELECT * FROM students 
WHERE score >= 80 AND gender = 'M'
;
```
```
SELECT * FROM students 
WHERE score >= 80 OR gender = 'M'
;
```
```
SELECT * FROM students 
WHERE NOT class_id = 2;
```

## 投影查询
```
SELECT id, score points, name FROM students WHERE gender = 'M';
```

## 排序
```
SELECT id, name, gender, score
FROM students
WHERE class_id = 1
ORDER BY score DESC;
```

## 分页查询
```
SELECT id, name, gender, score
FROM students
ORDER BY score DESC
LIMIT 3 OFFSET 9;
```
### 注意
- OFFSET是可选的，如果只写LIMIT 15，那么相当于LIMIT 15 OFFSET 0。
- 在MySQL中，LIMIT 15 OFFSET 30还可以简写成LIMIT 30, 15。
- 使用LIMIT <M> OFFSET <N>分页时，随着N越来越大，查询效率也会越来越低。

## 聚合查询
```
SELECT COUNT(*) boys FROM students WHERE gender = 'M';
```
除了COUNT()函数外，SQL还提供了如下聚合函数：
- SUM	计算某一列的合计值，该列必须为数值类型
- AVG	计算某一列的平均值，该列必须为数值类型
- MAX	计算某一列的最大值
- MIN	计算某一列的最小值

注意，MAX()和MIN()函数并不限于数值类型。如果是字符类型，MAX()和MIN()会返回排序最后和排序最前的字符。

```
SELECT class_id, gender, COUNT(*) num FROM students GROUP BY class_id, gender;
```

## 多表查询
```
SELECT
    s.id sid,
    s.name,
    s.gender,
    s.score,
    c.id cid,
    c.name cname
FROM students s, classes c
WHERE s.gender = 'M' AND c.id = 1;
```

## 连接查询
```
SELECT s.id, s.name, s.class_id, c.name class_name, s.gender, s.score
FROM students s
INNER JOIN classes c
ON s.class_id = c.id;
```

- INNER JOIN只返回同时存在于两张表的行数据。
- RIGHT OUTER JOIN返回右表都存在的行。如果某一行仅在右表存在，那么结果集就会以NULL填充剩下的字段。
- LEFT OUTER JOIN则返回左表都存在的行。
- FULL OUTER JOIN，它会把两张表的所有记录全部选择出来，并且，自动把对方不存在的列填充为NULL。
