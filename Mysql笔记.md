# 											MYSQL

[TOC]



##### 1、数据库的基本操作：

​		登陆MySQL：`mysql -u root -p`

###### 		1.1）创建数据库：

数据库是存储数据库对象的容器，在Mysql数据库中分为系统数据库和用户数据库两大类

查看数据库：`show databases;`

Cmd创建数据库：`create databases databases_name;`

###### 		1.2)查看和选择数据库

查看数据库：`show databases;`

选择数据库：`use database_name;`

###### 		1.3)删除数据库

删除数据：`drop  database database_name;`

##### 2、存储引擎，数据类型和字符集

###### 		2.1）存储引擎：

查看支持的数据引擎：`show engines;`

说明：1）Engine：表示存储引擎的名称

​			 2）Support：表示Mysql是否支持此 存储引擎

​			 3）Comment：关于此存储引擎的评论

​		      4）Transactions:是否支持事务

查看默认的存储引擎：`show variables link 'default_storage_engine';`

设置默认的存储引擎：`default_storage_engine=存储引擎名；`

###### 		2.2）数据类型：

常用数据的数据类型：

id int(11)  -------->编号

name varchar(30)  -------->姓名

age tinyint(4)  -------->年龄

score float(4,1)  -------->分数

sex enum('选择一','选择二') -------->二选一

hobby set(''选择一,''选择二,''选择三,'选择四') -------->多选

Photo varchar(255) -------->相片

spend decimal(5,1) -------->费用

address json -------->地址

intro text -------->简介

add_time datetime  -------->添加时间

数值类型：

日期类型：

查看系统帮助：`help contents;`

查看数据添加报错：`show warnings;`

###### 		2.3）字符集：

查看Mysql所有可用的字符集：`show character set;`

查看GBK字符集对应的排序规则：`show collation like '字符集名称'`

查看当前服务器使用的字符集：`show variables like 'character_set_server'；`

设置默认字符集和排序规则：

默认字符集：`character-set-server=utf8;`

排序规则：`collation-server=utf8_general_ci;`

建表的时候设置：`create database database_name default cahrset set_name;`

eg:`create database database_name default cahrset utf8;`

##### 3、数据库的基本操作：

###### 			3.1）创建数据表：

```
create table table_name(
col_name1 daty_type[Constraints],
col_name2 daty_type[Constraints],
col_name3 daty_type[Constraints]
.....
col_name4 daty_type[Constraints]
);
```

###### 			3.2）查看当前数据表：`show tables;`

###### 			3.3）设置约束：

1.建表的时候给某个字段设置主键约束：`col_name data_type primary key;`

2.定义在所有字段后设置主键约束：`primary key(col_name);`

3.设置自增约束：`col_name data_type auto_increment;`

注意：只有主键爱你才能添加自增约束，而且只能添加一个，默认值为1，字段类型必须是整数类型；

4.设置非空约束：`col_name data_type not null;`

5.设置唯一约束：`col_name data_type unique;`

​	定义在所有字段后设置唯一约束：`unique key(col_name)`

6.设置无符号约束：`col_name  data_type unsigned;`

7.设置外键约束：

```
constraint  key_name foreign key (child_col_name) references        parent_table_name(parent_col_name);

```

9.



