## Diary of atom and CGI

### 下载并安装atom编辑器

atom官网atom.io下载对应系统安装包

Linux系统下在shell命令行中输入

```
$ sudo wget -c <下载地址>
```
然后开始安装

```
$ sudo dpkt -i atom-amd64.deb
```
### 开启cgi，并配置相关文件

开启cgi

```
sudo ln -s /etc/apache2/mods-available/cgi.load /etc/apache2/mods-enabled/cgi.load
```
重启服务器

```
service apache2 restart
```

在cgi-stu/stu目录下,执行此复制语句到/var/www/html下

```
cp -r public/ index.html /var/www/html/
```

在根目录下执行下列语句,创建编译后的cgi文件存放目录，并赋予其读写的权限

```
sudo mkdir /usr/lib/cgi-bin/sx
sudo chmod 777 /usr/lib/cgi-bin/sx
```
修改cgi-stu/stu目录下makefile文件，并在其中添加语句

install: 
    cp *.cgi /usr/lib/cgi-bin/sx/
    
在已安装APache的条件下，执行更新语句

```
sudo apt-get update
```

然后可输入

```
sudo apt-get install libmy
```

再按tab查看文件，文件存在则执行
```
sudo apt-get install libmysqlclient-dev
```

安装libmysqlclient

安装成功后在stu文件夹下使用make命令，编译.c文件,成功生成cgi文件后执行make install,目的是将生成的cgi文件存放到/usr/lib/cgi-bin/sx/目录下
