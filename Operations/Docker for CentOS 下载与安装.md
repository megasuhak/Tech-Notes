
#### Docker for CentOS 下载与安装

(以下网址可能需要科学上网)

##### 官网及官方文档
* 官网：*https://www.docker.com/*
* 官方文档：*https://docs.docker.com/*
* Get Docker CE for CentOS Doc：*https://docs.docker.com/engine/installation/linux/docker-ce/centos/*

##### 操作系统
* CentOS Linux release 7.2

##### yum 安装
1. 配置 yum 源
```
yum install -y yum-utils device-mapper-persistent-data lvm2
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo  
```

2. yum 安装
`yum install -y docker-ce`

3. docker 启动
`systemctl start docker`

4. 运行 docker hello world
```
docker pull hello-world
docker run hello-world
```

##### rpm 包安装
1. 下载
