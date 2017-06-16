# Diary of mysql

### 建3个表

### 学生信息表设计（student）

中文名称| 表名| 字段属性| 默认值| 备注
:-----:|:----:|:------:|:----:|:-----:
学号|sno|varchar|not null|主键
学生姓名|sname|varchar|null|暂无
性别|sex|varchar|null|暂无
年龄|age|int|null|暂无

### 课程信息表设计（course）
中文名称| 表名| 字段属性| 默认值| 备注
:-----:|:----:|:------:|:----:|:-----:
课程号|cno|varchar|not null|主键
课程名|cname|varchar|null|暂无
学分|credit|int|null|暂无
院系|dname|varchar|null|暂无

### 成绩信息表设计（score）
中文名称| 表名| 字段属性| 默认值| 备注
:-----:|:----:|:------:|:----:|:-----:
学号|sno|varchar|not null|主键，外码
课程号|cno|varchar|not null|主键，外码
成绩|score|int|null|暂无

## sql语句设计
学生信息表sql语句
```sql
use stu;

create table student(
sno varchar(20) not null,
sname varchar(20) null,
sex varchar(8) null,
age int(4) null,
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
primary key(cno)
);
```

成绩表sql语句
```sql
use stu;

create table score(
cno varchar(20) not null,
sno varchar(20) null,
score int(20) null,
foreign key(cno) references course(cno),
foreign key(sno) references student(sno),
primary key(cno,sno)
);
```
