
#### Nginx 配置404错误页面的方法

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

		fastcgi_pass  127.0.0.1:9000;
		fastcgi_index index.php;
		fastcgi_param SCRIPT_FILENAME  $document_root$fastcgi_script_name;
		include       fastcgi_params;
	}
	error_page 404 403 500 502 503 504  /404.html;
    error_page 404 = /home/wwwroot/Laputa_admin_demo/404.html;

}
```
