
#### 如何屏蔽PHP错误

##### 方法一：@ 屏蔽法
* @ 在php中一个抑制错误的符号，即便是你开启了报错功能，只要在错误语句之前加上 @ 符号，便可屏蔽了错误信息。
* PHP Manual 参考：[错误控制运算符](http://www.php.net/manual/zh/language.operators.errorcontrol.php)
* 代码示例：
```
@mysql_connect() OR die('connect mysql failed');
```

##### 方法二：error_reporting 屏蔽法
* 在php文件开始之前，我们可以加上这样一句话error_reporting(0)；这个函数的意思是设置 PHP 的报错级别并返回当前级别，0则代表禁用错误报告。
* PHP Manual 参考：[error_reporting](http://php.net/manual/zh/function.error-reporting.php)
* 代码示例：
```
<?php
// 关闭所有PHP错误报告
error_reporting(0);
?>
```

##### 方法三：display_errors 屏蔽法
* 这种方法应该是最彻底的一种解决办法，因为前两种方法只能作用于单行或者单个文件，这个则是作用于所有的 php 文件。打开 php.ini 文件，搜索 display_errors = on，默认的应该是 on，即开启报错功能，改为 off 即可。
* PHP Manual 参考：[运行时配置](http://php.net/manual/zh/errorfunc.configuration.php)
* 示例：
```
php.ini

display_errors = off;
```
