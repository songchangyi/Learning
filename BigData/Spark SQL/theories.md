# PySpark SQL理论部分

## 引言

### 为什么需要Spark SQL
Apache Hive的缺点：
- Hive使用MR导致在中小型数据集（200GB以下）上性能不足
- 不具备恢复能力
- Hive不能删除加密数据库

Spark SQL优点：
- 更快的执行：10倍于Hive
- 无障碍迁移
- 实时查询

如何实现：Spark SQL使用Hive的元存储服务来查询Hive中存储和管理的数据

### 什么是Spark SQL
Spark的一个结构化数据处理模块
- 提供DataFrame抽象
- 可以读写多种结构化的数据格式
- 允许使用SQL查询数据
