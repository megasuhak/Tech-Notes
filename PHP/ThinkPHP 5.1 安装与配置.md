
#### ThinkPHP 5.1 安装与配置

##### Composer 方式安装
`composer create-project topthink/think tp5`


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


##### 配置

##### /public/index.php 入口文件配置
```
// 定义应用目录
define('APP_PATH', __DIR__ . '/../application/');

// 定义配置文件目录和应用目录同级
define('CONF_PATH', __DIR__.'/../config/');
```

// 应用调试模式
'app_debug'              => true,
// 应用Trace
'app_trace'              => true,
