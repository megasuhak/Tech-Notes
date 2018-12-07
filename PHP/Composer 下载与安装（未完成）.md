
#### Composer 下载与安装




Composer - Dependency Manager for PHP
PHP依赖管理器

https://getcomposer.org/

https://www.phpcomposer.com/

https://docs.phpcomposer.com/

https://pkg.phpcomposer.com/


##### 安装 Composer
curl -sS https://getcomposer.org/installer | php
mv composer.phar /usr/local/bin/composer


##### 使用国内镜像
composer config -g repo.packagist composer https://packagist.phpcomposer.com

composer config -g repo.packagist composer https://packagist.laravel-china.org
