## 基于Vmware虚拟机的VMwareTools导入

* 1、点击右下角的小光盘，点击settings
* 2、进入新页面选择VMwareTools的光驱
* 3、找到VMwareTools的镜像文件
* 4、选择linux.iso的路径，进行导入
* 5、进入目录cd /media/linux
* 6、进入目录cd VMware\Tools/
* 7、查看当前目录 ls ,找到tar.gz压缩文件，进行复制：cp VMwareTools-9.2.0-799703.tar.gz ~/
* 8、pwd查看当前用户目录，如果不是在/home/linux下，进入目录cd /home/linux，用ls查看是否复制成功
* 9、tar xvf进行解压
* 10、cd VMware-tools-distrib/
* 11、进行安装：sudo ./vmware-install.pl
