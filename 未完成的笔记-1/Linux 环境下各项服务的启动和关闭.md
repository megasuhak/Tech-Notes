

/usr/local/nginx/sbin/nginx -s start
/usr/local/nginx/sbin/nginx -s stop
/usr/local/nginx/sbin/nginx -s reload

killall php-fpm 
/usr/local/php/sbin/php-fpm

/usr/local/mysql/bin/mysqladmin -uroot -p shutdown
/usr/local/mysql/bin/mysqld_safe &


/etc/init.d/php-fpm reload

/etc/init.d/mysql reload

/etc/init.d/nginx reload


service mysqld start
service mysqld stop

service php-fpm start
service php-fpm stop

service nginx start
service nginx stop

