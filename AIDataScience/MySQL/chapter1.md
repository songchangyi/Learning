# 关系数据库概述

## 数据模型
数据库按照数据结构来组织、存储和管理数据，实际上，数据库一共有三种模型：
- 层次模型
- 网状模型
- 关系模型

随着时间的推移和市场竞争，最终，基于关系模型的关系数据库获得了绝对市场份额。

## 数据类型
对于一个关系表，除了定义每一列的名称外，还需要定义每一列的数据类型。
关系数据库支持的标准数据类型包括数值、字符串、时间等：

| 名称	| 类型	| 说明 |
| --- | --- | --- |
| INT	| 整型	| 4字节整数类型，范围约+/-21亿 |
| BIGINT	| 长整型	| 8字节整数类型，范围约+/-922亿亿 |
| REAL	| 浮点型	| 4字节浮点数，范围约+/-1038 |
| DOUBLE	| 浮点型	| 8字节浮点数，范围约+/-10308 |
| DECIMAL(M,N)	| 高精度小数	| 由用户指定精度的小数，例如，DECIMAL(20,10)表示一共20位，其中小数10位，通常用于财务计算 |
| CHAR(N)	| 定长字符串	| 存储指定长度的字符串，例如，CHAR(100)总是存储100个字符的字符串 |
| VARCHAR(N)	| 变长字符串	| 存储可变长度的字符串，例如，VARCHAR(100)可以存储0~100个字符的字符串 |
| BOOLEAN	| 布尔类型	| 存储True或者False |
| DATE	| 日期类型	| 存储日期，例如，2018-06-22 |
| TIME	| 时间类型	| 存储时间，例如，12:20:59 |
| DATETIME	| 日期和时间类型	| 存储日期+时间，例如，2018-06-22 12:20:59 |

选择数据类型的时候，要根据业务规则选择合适的类型。
通常来说，BIGINT能满足整数存储的需求，VARCHAR(N)能满足字符串存储的需求，这两种类型是使用最广泛的。

## 主流关系数据库
目前，主流的关系数据库主要分为以下几类：
- 商用数据库，例如：Oracle，SQL Server，DB2等；
- 开源数据库，例如：MySQL，PostgreSQL等；
- 桌面数据库，以微软Access为代表，适合桌面应用程序使用；
- 嵌入式数据库，以Sqlite为代表，适合手机应用和桌面程序。

## SQL
总的来说，SQL语言定义了这么几种操作数据库的能力：

DDL：Data Definition Language

DDL允许用户定义数据，也就是创建表、删除表、修改表结构这些操作。通常，DDL由数据库管理员执行。

DML：Data Manipulation Language

DML为用户提供添加、删除、更新数据的能力，这些是应用程序对数据库的日常操作。

DQL：Data Query Language

DQL允许用户查询数据，这也是通常最频繁的数据库日常操作。

# 安装MySQL

MySQL是目前应用最广泛的开源关系数据库。MySQL最早是由瑞典的MySQL AB公司开发，该公司在2008年被SUN公司收购，紧接着，SUN公司在2009年被Oracle公司收购，所以MySQL最终就变成了Oracle旗下的产品。

和其他关系数据库有所不同的是，MySQL本身实际上只是一个SQL接口，它的内部还包含了多种数据引擎。
使用MySQL时，不同的表还可以使用不同的数据库引擎。如果你不知道应该采用哪种引擎，记住总是选择InnoDB就好了。
因为MySQL一开始就是开源的，所以基于MySQL的开源版本，又衍生出了各种版本：

- MariaDB

由MySQL的创始人创建的一个开源分支版本，使用XtraDB引擎。

- Aurora

由Amazon改进的一个MySQL版本，专门提供给在AWS托管MySQL用户，号称5倍的性能提升。

- PolarDB

由Alibaba改进的一个MySQL版本，专门提供给在阿里云托管的MySQL用户，号称6倍的性能提升。

而MySQL官方版本又分了好几个版本：

- Community Edition：社区开源版本，免费；
- Standard Edition：标准版；
- Enterprise Edition：企业版；
- Cluster Carrier Grade Edition：集群版。

以上版本的功能依次递增，价格也依次递增。不过，功能增加的主要是监控、集群等管理功能，对于基本的SQL功能是完全一样的。

## 安装MySQL
- windows : https://dev.mysql.com/downloads/mysql/
- linux : apt-get install mysql-server

在命令提示符下输入mysql -u root -p，然后输入口令，如果一切正确，就会连接到MySQL服务器，同时提示符变为mysql>。

输入exit退出MySQL命令行。注意，MySQL服务器仍在后台运行。
