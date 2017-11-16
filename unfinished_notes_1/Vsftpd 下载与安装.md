
#### Vsftpd 下载与安装

https://centos.pkgs.org/7/centos-x86_64/vsftpd-3.0.2-22.el7.x86_64.rpm.html


yum install -y vsftpd
安装版本：vsftpd.x86_64 0:3.0.2-22.el7


2、启动服务
使用vsftpd软件，主要包括如下几个命令：
启动ftp命令#service vsftpd start
停止ftp命令#service vsftpd stop
重启ftp命令#service vsftpd restart



3、vsftpd的配置
ftp的配置文件主要有三个，位于/etc/vsftpd/目录下，分别是：
ftpusers    该文件用来指定那些用户不能访问ftp服务器。
user_list   该文件用来指示的默认账户在默认情况下也不能访问ftp
vsftpd.conf   vsftpd的主配置文件
