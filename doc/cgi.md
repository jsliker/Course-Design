## cgi接口的简单使用

在仓库目录下执行make命令，对.c文件进行编译，然后再执行make install命令将编译成功后的.cgi

文件复制到执行目录下

然后再通过网页检查.cgi文件的执行情况

因为最初创建数据库时没有将数据库，表，属性的默认编码设为utf8，所以需要对配置文件进行修改

在以下路径
/etc/mysql/mysql.conf.d

通过管理员权限对mysqld.cnf文件进行修改

在[mysqld]

添加

character-set-server=utf8

/etc/mysql/conf.d

通过管理员权限对conf.d文件进行修改

在[mysql]

no-auto-rehash

default-character-set=utf8
