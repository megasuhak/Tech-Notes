
#### Nginx 配置 SSI 的方法

##### SSI 简介
SSI：Server Side Include，是一种基于服务端的网页制作技术，在页面内容发送到客户端之前，使用SSI指令将文本、图片或代码信息包含到网页中。对于在多个文件中重复出现内容，使用SSI是一种简便的方法，将内容存入一个包含文件中即可，不必将其输入所有文件。通过一个非常简单的语句即可调用包含文件，此语句指示 Web 服务器将内容插入适当网页。而且，使用包含文件时，对内容的所有更改只需在一个地方就能完成。

##### 修改 Nginx 配置文件
* ssi: 默认值off，启用ssi时将其设为on
* ssi_silent_errors: 默认值off，开启后在处理SSI文件出错时不输出错误提示"[an error occurred while processing the directive]"。
* ssi_types: 默认是text/html，所以如果需支持html，则不需要设置这句，如果需要支持shtml则需要设置：ssi_types text/shtml

##### Nginx.conf 实例
```
server {
	listen 80;
	server_name admin-demo.laputateam.com;
	root /home/wwwroot/Laputa_admin_demo;
	index index.html index.htm index.php;

	location ~.*\.php?$ {
		ssi on;
		ssi_silent_errors on;
		ssi_types text/shtml;

		fastcgi_pass  127.0.0.1:9000;
		fastcgi_index index.php;
		fastcgi_param SCRIPT_FILENAME  $document_root$fastcgi_script_name;
		include       fastcgi_params;
	}
}
```

#####  HTML 页面包含其他页面实例
```
<!DOCTYPE html>
<html>
<!--#include file="moudle_header.html"-->
<body>
	<!--#include file="moudle_navbar.html"-->
	<!--#include file="moudle_sidebar.html"-->
	<div class="main">
	  <!-- 内容主体区域 -->
	</div>
<!--#include file="moudle_footer.html"-->
</body>
</html>
```
