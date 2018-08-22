
#### LNMP状态管理命令
作者：licess 发布时间：2013年06月3日 分类：常见问题

##### LNMP状态管理命令：

LNMP 1.2+状态管理: lnmp {start|stop|reload|restart|kill|status}
LNMP 1.2+各个程序状态管理: lnmp {nginx|mysql|mariadb|php-fpm|pureftpd} {start|stop|reload|restart|kill|status}
LNMP 1.1状态管理： /root/lnmp {start|stop|reload|restart|kill|status}
Nginx状态管理：/etc/init.d/nginx {start|stop|reload|restart}
MySQL状态管理：/etc/init.d/mysql {start|stop|restart|reload|force-reload|status}
Memcached状态管理：/etc/init.d/memcached {start|stop|restart}
PHP-FPM状态管理：/etc/init.d/php-fpm {start|stop|quit|restart|reload|logrotate}
PureFTPd状态管理： /etc/init.d/pureftpd {start|stop|restart|kill|status}
ProFTPd状态管理： /etc/init.d/proftpd {start|stop|restart|reload}
Redis状态管理： /etc/init.d/redis {start|stop|restart|kill}

多PHP版本状态管理：/etc/init.d/php-fpm5.5 {start|stop|quit|restart|reload|logrotate} 前面5.5为对应的PHP版本，其他版本自行替换。

如重启LNMP，1.2+输入命令：lnmp restart 即可；单独重启mysql：/etc/init.d/mysql restart 也可以 lnmp mysql restart ，两个是一样的。

##### LNMPA状态管理命令：

LNMPA 1.2+状态管理: lnmp {start|stop|reload|restart|kill|status}
LNMPA 1.2+各个程序状态管理: lnmp {httpd|mysql|mariadb|pureftpd} {start|stop|reload|restart|kill|status}
LNMPA1.1状态管理： /root/lnmpa {start|stop|reload|restart|kill|status}
Nginx状态管理：/etc/init.d/nginx {start|stop|reload|restart}
MySQL状态管理：/etc/init.d/mysql {start|stop|restart|reload|force-reload|status}
Memcached状态管理：/etc/init.d/memcached {start|stop|restart}
PureFTPd状态管理： /etc/init.d/pureftpd {start|stop|restart|kill|status}
ProFTPd状态管理： /etc/init.d/proftpd {start|stop|restart|reload}
Apache状态管理：/etc/init.d/httpd {start|stop|restart|graceful|graceful-stop|configtest|status}

##### LAMP状态管理命令：

LAMP 1.2+状态管理: lnmp {start|stop|reload|restart|kill|status}
LAMP 1.2+各个程序状态管理: lnmp {httpd|mysql|mariadb|pureftpd} {start|stop|reload|restart|kill|status}
