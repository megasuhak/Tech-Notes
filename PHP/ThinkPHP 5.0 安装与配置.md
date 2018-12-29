
#### ThinkPHP 5.0 安装与配置

##### ThinkPHP5的环境要求如下：
* PHP >= 5.4.0
* PDO PHP Extension
* MBstring PHP Extension
* CURL PHP Extension

##### 官网下载安装

下载地址：http://www.thinkphp.cn/donate/download/id/1279.html
http://www.thinkphp.cn/down/framework.html

##### Composer 方式安装
`composer create-project topthink/think=5.0.x tp5`

如果你之前已经安装过，那么切换到你的应用根目录下面，然后执行下面的命令进行更新：
`composer update topthink/framework`



##### Git安装
ThinkPHP5.1主要分为应用和核心两个仓库，主要包括：

应用项目：https://github.com/top-think/think
核心框架：https://github.com/top-think/framework
之所以设计为应用和核心仓库的分离，是为了支持Composer单独更新核心框架。

安装也需要分两步操作，首先克隆下载应用项目仓库
`git clone https://github.com/top-think/think tp5`
然后切换到tp5目录下面，再克隆核心框架仓库（注意目录名称不要改变）：
`cd tp5`
`git clone https://github.com/top-think/framework thinkphp`
