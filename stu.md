## 学生信息管理系统

## 数据库设计方案

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

## CGI程序设计接口
