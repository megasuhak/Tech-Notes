
#### Go 下载与安装

(以下网址可能需要科学上网)

##### 下载
* 官网：*https://golang.org*
* 下载：*https://golang.org/dl/*
* 下载文件：**go1.9.2.linux-amd64.tar.gz**

##### 官方文档
* 文档：*https://golang.org/doc/*

##### 操作系统
* CentOS Linux release 7.2

##### 安装
1. 将下载的源码包解压至 /usr/local 目录
`tar -C /usr/local -xzf go1.4.linux-amd64.tar.gz`

2. 将 /usr/local/go/bin 目录添加至PATH环境变量
`export PATH=$PATH:/usr/local/go/bin`

##### 检查版本
`go version`

##### hello world
1. 创建 **hello.go** 文件
```
package main

import "fmt"

func main() {
   fmt.Println("Hello, World!")
}
```
2. 运行 **hello.go** 文件
```
go run hello.go
```
