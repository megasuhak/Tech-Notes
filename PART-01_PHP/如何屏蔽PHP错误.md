
#### 如何屏蔽PHP错误

##### 方法一：@ 屏蔽法
* @在php中一个抑制错误的符号，即便是你开启了报错功能，只要在错误语句之前加上@符号，便可屏蔽了错误信息。
* ![@ 屏蔽法](https://img-blog.csdn.net/20180703113111647?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3JheW5vcnh5eA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

##### 方法二：error_reporting 屏蔽法
* 在php文件开始之前，我们可以加上这样一句话error_reporting(0);这个函数的意思是设置 PHP 的报错级别并返回当前级别，0则代表禁用错误报告。
![error_reporting 屏蔽法_1](https://img-blog.csdn.net/20180703113157911?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3JheW5vcnh5eA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
![error_reporting 屏蔽法_2](https://img-blog.csdn.net/20180703113219801?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3JheW5vcnh5eA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

##### 方法三：display_errors 屏蔽法
* 这种方法应该是最彻底的一种解决办法，因为前两种方法只能作用于单行或者单个文件，这个则是作用于所有的 php 文件。打开 php.ini 文件，搜索 display_errors = on，默认的应该是 on，即开启报错功能，改为 off 即可。
![display_errors 屏蔽法_1](https://img-blog.csdn.net/20180703113913440?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3JheW5vcnh5eA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
![display_errors 屏蔽法_2](https://img-blog.csdn.net/20180703114014715?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3JheW5vcnh5eA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
