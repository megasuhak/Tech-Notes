
#### LNMP一键安装包 下载与安装

##### LNMP一键安装包的下载
* 使用wget命令下载（推荐）
`wget -c http://soft.vpser.net/lnmp/lnmp1.4-full.tar.gz`

* 手动下载
官网地址：*http://lnmp.org*
下载地址：*http://soft.vpser.net/lnmp/lnmp1.4-full.tar.gz*
下载文件：**lnmp1.4-full.tar.gz (467MB )**
把文件上传到服务器的 `/opt/` 或 `/home/` 目录下

##### LNMP一键安装包的安装
1. STEP-1 解压并安装
```
tar -zxvf lnmp1.4-full.tar.gz
cd lnmp1.2-full
./install.sh lnmp
```

2. STEP-2 选择 MySQL 版本
![](https://lnmp.org/images/1.4/lnmp1.4-install-1.png)

3. STEP-3 输入 MySQL root 用户密码
![](https://lnmp.org/images/1.4/lnmp1.4-install-2.png)

4. STEP-4 选择是否启用 MySQL InnoDB，一般建议开启
![](https://lnmp.org/images/1.4/lnmp1.4-install-3.png)

5. STEP-5 选择 PHP 版本
![](https://lnmp.org/images/1.4/lnmp1.4-install-4.png)

6. STEP-6 选择是否安装内存优化：可以选择不安装、Jemalloc或TCmalloc，输入对应序号回车。
![](https://lnmp.org/images/1.4/lnmp1.4-install-5.png)

7. STEP-7 安装完成。
如果显示 Nginx：OK，MySQL：OK，PHP：OK，并且Nginx、MySQL、PHP都是running，80和3306端口都存在
并提示安装使用的时间及 Install lnmp V1.4 completed! enjoy it. 说明已经安装成功。
![](https://lnmp.org/images/1.4/lnmp1.4-install-success.png)

##### LNMP一键安装包下载安装一键执行
`wget -c http://soft.vpser.net/lnmp/lnmp1.4.tar.gz && tar zxf lnmp1.4.tar.gz && cd lnmp1.4 && ./install.sh lnmp`
