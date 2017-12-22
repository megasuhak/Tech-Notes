
#### Nginx 基本配置

##### nginx.conf

##### Nginx 操作命令


# pm.leapoon.com
server {
	listen 80;
	server_name pm.leapoon.com;
    root  /data/zentaopms/www/;
    index index.php index.html index.htm;

	 location ~ \.php$ {
		#root /var/www; #指定php的根目录
		fastcgi_pass 127.0.0.1:9000;#php-fpm的默认端口是9000
		fastcgi_index index.php;
		fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
		include fastcgi_params;
	}
}




# marketing.wailianvisa.com
server {
	listen 80;

    server_name marketing.wailianvisa.com;

  # access_log              /data/video/www/logs/access.log;
  # error_log               /data/video/www/logs/error.log;
    index                   index.html index.htm index.php;
    root                    /data/marketing/marketing.wailianvisa.com;

    location / {
        if (!-e $request_filename) {  
           rewrite ^/(.*)$ /index.php/$1 last;  
           break;  
        }  
    }  
    location ~ \.php/?.*$ {  
        fastcgi_pass   unix:/var/run/php5-fpm.sock;
        fastcgi_index  index.php;         

        set $fastcgi_script_name2 $fastcgi_script_name;  
        if ($fastcgi_script_name ~ "^(.+\.php)(/.+)$") {  
            set $fastcgi_script_name2 $1;  
            set $path_info $2;  
        }  
        fastcgi_param   PATH_INFO $path_info;  
        fastcgi_param   SCRIPT_FILENAME   $document_root$fastcgi_script_name2;  
        fastcgi_param   SCRIPT_NAME   $fastcgi_script_name2;
		include         fastcgi_params;
    }  
}

# marketing.mofi.com.cn
server {
	listen 80;

    server_name marketing.mofi.com.cn;

    index                   index.html index.htm index.php;
    root                    /data/marketing/marketing.wailianvisa.com;

    location / {
        if (!-e $request_filename) {  
           rewrite ^/(.*)$ /index.php/$1 last;  
           break;  
        }  
    }  
    location ~ \.php/?.*$ {  
        fastcgi_pass   unix:/var/run/php5-fpm.sock;
        fastcgi_index  index.php;         

        set $fastcgi_script_name2 $fastcgi_script_name;  
        if ($fastcgi_script_name ~ "^(.+\.php)(/.+)$") {  
            set $fastcgi_script_name2 $1;  
            set $path_info $2;  
        }  
        fastcgi_param   PATH_INFO $path_info;  
        fastcgi_param   SCRIPT_FILENAME   $document_root$fastcgi_script_name2;  
        fastcgi_param   SCRIPT_NAME   $fastcgi_script_name2;
		include         fastcgi_params;
    }  
}



#    location ~.*\.php?$ {
#        fastcgi_pass  127.0.0.1:9000;
#        fastcgi_index index.php;
#        fastcgi_param SCRIPT_FILENAME  $document_root$fastcgi_script_name;
#        include       fastcgi_params;
#    }
