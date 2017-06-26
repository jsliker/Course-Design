# 基于关系型数据库的学生信息管理系统

## 系统概述

学生信息管理系统，可用于学校等机构的学生信息管理，查询，更新与维护，使用方便，易用性强，HTML界面清晰明了。该软件用 C 和 HTML 语言编写，用MySQL数据库作为后台的数据库进行信息的存储，用 SQL 语句完成学生学籍信息的添加， 查询，修改，删除的操作以及成绩的录入，修改，删除等。前端使用 HTML5 页面与用户进行交互, ODBC 使用 CGI 与后台 SQL 数据库的连接。MySQL 数据库高效安全，两者结合可相互利用各自的优势。  
  
  系统主要功能：对学生的信息进行管理，如：插入学生信息、删除学生信息 、修改学生信息、查询学生信息。
  
  ## 使用工具
 - [x] ubutun   
 - [x] mysql  
 - [x] c语言  
 - [x] atom 
  
### 学生信息表设计（student）

中文名称| 表名| 字段属性| 默认值| 备注
:-----:|:----:|:------:|:----:|:-----:
学号|sno|varchar|not null|主键
学生姓名|sname|varchar|null|暂无
性别|sex|varchar|null|暂无
年龄|age|int|null|暂无
状态|sta|int|1|判断是否真删除

### 课程信息表设计（course）
中文名称| 表名| 字段属性| 默认值| 备注
:-----:|:----:|:------:|:----:|:-----:
课程号|cno|varchar|not null|主键
课程名|cname|varchar|null|暂无
学分|credit|int|null|暂无
院系|dname|varchar|null|暂无
状态|sta|int|1|判断是否真删除

### 成绩信息表设计（score）
中文名称| 表名| 字段属性| 默认值| 备注
:-----:|:----:|:------:|:----:|:-----:
学号|sno|varchar|not null|主键，外码
课程号|cno|varchar|not null|主键，外码
成绩|score|int|null|暂无
状态|sta|int|1|判断是否真删除

## sql语句设计
学生信息表sql语句
```sql
use stu;

create table student(
sno varchar(20) not null,
sname varchar(20) null,
sex varchar(8) null,
age int(4) null,
sta int(2) not null,
primary key(sno)
);
```

课程信息表sql语句
```sql
use stu;

create table course(
cno varchar(20) not null,
cname varchar(20) null,
credit int(20) null,
dname varchar(20) null,
sta int(2) not null,
primary key(cno)
);
```

成绩表sql语句
```sql
use stu;

create table score(
cno varchar(20) character set utf8 not null,
sno varchar(20) character set utf8 not null,
score int(20) null,
foreign key(cno) references course(cno)
on delete cascade
on update cascade,
foreign key(sno) references student(sno)
on delete cascade
on update cascade,
primary key(cno,sno)
);
```




