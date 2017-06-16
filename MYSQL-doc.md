# Course-Design Diary

### 在unbuntu Linux系统下安装MYSQL
1.在home目录下进行如下操作

```
$ vim .vimrc
```

将光标移至第三行，按i进入编辑模式，删除/注释第18行内容。目的是可以在vim编辑模式下使用鼠标右键的粘贴功能。

2.sudo vim /etc/apt/sources.list 进入此文件并将其中代码覆盖成

```
deb http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse
deb http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
##测试版源
deb http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse
# 源码
deb-src http://mirrors.aliyun.com/ubuntu/ xenial main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-security main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-updates main restricted universe multiverse
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-backports main restricted universe multiverse
##测试版源
deb-src http://mirrors.aliyun.com/ubuntu/ xenial-proposed main restricted universe multiverse
# Canonical 合作伙伴和附加
deb http://archive.canonical.com/ubuntu/ xenial partner
deb http://extras.ubuntu.com/ubuntu/ xenial main
```

3.更新源 安装Apache

在安装 Apache时MYSQL也会被同时安装

```
1.$ sudo apt-get update
2.$ sudo apt-get install tasksel
3.$ sudo tasksel
```
在执行第三步时将光标移至LAMP Server按空格选中，回车进行安装，期间会弹出对话框，第一次进行用户名输入，默认为root，第二次弹出设置密码，默认为123456

第三次弹出确认密码框，再次输入123456

安装成功

本地进行连接MYSQL

```
mysql -u root -p
```

回车后显示输入密码

当左侧为mysql>时，可输入show databases来查看数据库中数据

输入exit命令可退出

### 数据库操作

查看数据库可已使用``` $ show databases ``` 查看已存在数据库

同理若要查看库中表可通过
```
$ use <数据库名>
$ show tables
```

创建表格：course

主键：cno（课程号）

属性：cname（课程名），credit（学分），dname（院名）

--------------------------------------------分割线--------------------------------------------------

创建表格：student

主键：sno（学号）

属性：sname（学生姓名），sex（性别），age（年龄）

--------------------------------------------分割线--------------------------------------------------

创建表格：score

主键：cno，sno

属性：score（成绩）

外码：cno，sno
