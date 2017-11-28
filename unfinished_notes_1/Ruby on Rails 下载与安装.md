
#### Ruby on Rails 下载与安装

(以下网址可能需要科学上网)

##### 下载

https://www.ruby-lang.org/
https://www.ruby-lang.org/en
https://www.ruby-lang.org/zh_cn/

https://www.ruby-lang.org/en/downloads/

https://cache.ruby-lang.org/pub/ruby/2.4/ruby-2.4.2.tar.gz

https://rubygems.org/


tar -zxvf ruby-2.4.2.tar.gz
cd ruby-2.2.3
现在，配置并编译源代码，如下所示：
./configure
make && make install

ruby -v

`yum install ruby`


下载 RubyGems

https://rubygems.org/rubygems/rubygems-2.7.2.tgz


tar -zxvf ruby-2.4.2.tgz
cd rubygems-2.7.2
ruby setup.rb


安装 Rails

gem install rails

rails -v

##### 下载

##### 官方文档

##### 操作系统

##### 安装


##### Hello World
hello.rb
puts "hello world from Ruby"
ruby hello.rb




##### Nginx 下载并安装
1. 使用wget命令下载（推荐）
```
wget -c https://nginx.org/download/nginx-1.12.0.tar.gz
```

2. 解压
```
tar -zxvf nginx-1.12.0.tar.gz
cd nginx-1.12.0
```

3. 配置
```
./configure
```

4. 编译安装
```
make && make install
```
