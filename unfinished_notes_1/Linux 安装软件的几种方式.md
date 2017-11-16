
#### Linux 安装软件的几种方式

##### tar.gz 安装包解压编译安装

##### yum 安装方式

1. 配置 yum 源
```
vim /etc/yum.repos.d/gitlab-ce.repo

[gitlab-ce]  
name=gitlab-ce  
baseurl=http://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/yum/el7  
repo_gpgcheck=0  
gpgcheck=0  
enabled=1  
gpgkey=https://packages.gitlab.com/gpg.key
```

2. 更新本地 yum 缓存
`sudo yum makecache`

3. yum 安装软件
`sudo yum install -y XXX`

##### rpm 包安装方式




##### deb 包安装方式


##### apt-get 安装方式
