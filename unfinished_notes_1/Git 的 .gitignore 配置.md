
#### Git 的 .gitignore 配置

##### 安装所需环境
1. gcc 安装
`yum install -y gcc-c++`

2. PCRE pcre-devel 安装
`yum install -y pcre pcre-devel`

3. zlib 安装
`yum install -y zlib zlib-devel`

4. OpenSSL 安装
`yum install -y openssl openssl-devel`

##### Nginx 下载并安装
1. 使用wget命令下载（推荐）
```
wget -c https://nginx.org/download/nginx-1.10.3.tar.gz
```

2. 解压
```
tar -zxvf nginx-1.10.3.tar.gz
cd nginx-1.10.3
```

3. 配置
```
./configure
```

4. 编译安装
```
make && make install
```



