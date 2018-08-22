
#### GitLab 下载与安装

(以下网址可能需要科学上网)

##### 下载
* [官网](http://www.sublimetext.com/)
* [Sublime Text 3 Download](http://www.sublimetext.com/3)
* 下载文件：*Sublime Text Build 3143 x64 Setup.exe*

##### 官方文档
* [链接1](http://www.sublimetext.com/docs/3/)
* [链接2](http://docs.sublimetext.info/en/latest/index.html)

##### 安装
* 双击安装文件：Sublime Text Build 3143 x64 Setup.exe
* 默认安装路径：D:\Program Files\Sublime Text 3




GitLab 之 Linux十分钟快装

//配置系统防火墙,把HTTP和SSH端口开放.
sudo yum install curl openssh-server postfix cronie
sudo service postfix start
sudo chkconfig postfix on
sudo lokkit -s http -s ssh

//下载rpm安装包
sudo curl -O https://downloads-packages.s3.amazonaws.com/centos-6.6/gitlab-ce-7.10.0~omnibus.2-1.x86_64.rpm
sudo rpm -ivh gitlab-ce-7.10.0~omnibus.2-1.x86_64.rpm

//修改 自带的nginx配置，以及邮件提醒配置
vim /var/opt/gitlab/nginx/conf/gitlab-http.conf
vim /etc/gitlab/gitlab.rb

//保存配置
sudo gitlab-ctl reconfigure
//启动运行，以及查看状态
sudo gitlab-ctl start //stop
sudo gitlab-ctl status



```
xuyixing

//配置系统防火墙,把HTTP和SSH端口开放.
sudo yum install -y curl policycoreutils-python openssh-server postfix openssh-clients cronie
sudo service postfix start
sudo chkconfig postfix on
sudo lokkit -s http -s ssh

//下载rpm安装包
sudo curl -O https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/yum/el7/gitlab-ce-10.1.0-ce.0.el7.x86_64.rpm

//编译安装 glibc_2.1.4
tar -zxvf glibc-2.14.tar.gz
cd glibc-2.14
mkdir build
cd build
../configure --prefix=/usr/local/glibc-2.14
make && make install

//安装 rpm 安装包
sudo rpm -ivh gitlab-ce-10.1.0-ce.0.el7.x86_64.rpm --force --nodeps

--force:强制安装
--nodeps:忽略依赖关系


//修改自带的nginx配置，以及邮件提醒配置
vim /var/opt/gitlab/nginx/conf/gitlab-http.conf
vim /etc/gitlab/gitlab.rb

//保存配置
sudo gitlab-ctl reconfigure

//启动运行，以及查看状态
sudo gitlab-ctl start //stop
sudo gitlab-ctl status

```
