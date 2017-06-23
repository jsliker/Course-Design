# Diary of mysql

## 将远程仓库clone到本地

1.当我们知道git仓库的地址了(在github上有很多的开源仓库.), 就可以使用下面的命令将源码拉取到本地.

```
$ git clone url
```

2.若我们已经拉取源码到本地了, 但是服务器上的git已经更新了, 当我们需要将服务器的源码与本地源进行同步进时, 需要使用下面的命令.

```
$ git pull
```

## 在unbuntu Linux系统下安装MYSQL
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

## ATOM包的安装下载

    wget -c url
    sudo dpkg -i atom-amd64.deb
    
## Atom editor 开环境使用的插件

```
atom .:进入atom的界面，搜索需要的插件进行install,安装插件之后界面更加友好方便使用
activate-power-mode：动感插件 atl + ctrl + o :打开插件
vim-mode：vim模式
ex-mode：实现:w功能
monokai：高亮显示    //theme查找
atom-ternjs：JavaScript 自动补全
autoprefixer：给 CSS 添加适当的前缀
color-picker：选颜色
emmet：写 HTML 的神器
atom-beautify：美化代码，空格啊什么什么的
autoclose-html：HTML自动补全闭标签
file-icons: 增加许多图标,在侧边蓝文件名前面的icon,,很赞
autocomplete-modules: 自动补全插件, 有HTML, CSS, python 等
highlight-selected: 高亮当前所选的文字, 双击后全文这个词或变量都会变高亮.
Open In Browser: 右键打开浏览器.
atom-clock: 在bar显示 时间
autocomplete-js-import: 模块导入智能提示
autocomplete-modules: 模块智能提示【node_modules】
```

## 数据库操作

查看数据库可已使用``` $ show databases ``` 查看已存在数据库

同理若要查看库中表可通过
```
$ use <数据库名>
$ show tables
```
创建数据库stu
```sql
create database stu;
```
