
#### docker --help

Usage:	docker COMMAND

A self-sufficient runtime for containers

Options:
      --config string      Location of client config files (default "/root/.docker")
  -D, --debug              Enable debug mode
      --help               Print usage
  -H, --host list          Daemon socket(s) to connect to
  -l, --log-level string   Set the logging level ("debug"|"info"|"warn"|"error"|"fatal") (default "info")
      --tls                Use TLS; implied by --tlsverify
      --tlscacert string   Trust certs signed only by this CA (default "/root/.docker/ca.pem")
      --tlscert string     Path to TLS certificate file (default "/root/.docker/cert.pem")
      --tlskey string      Path to TLS key file (default "/root/.docker/key.pem")
      --tlsverify          Use TLS and verify the remote
  -v, --version            Print version information and quit

Management Commands:
  config      Manage Docker configs
  container   Manage containers
  image       Manage images
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  volume      Manage volumes

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes

==========================================

  docker run ：创建一个新的容器并运行一个命令
  语法
  [html] view plain copy
  docker run [OPTIONS] IMAGE [COMMAND] [ARG...]

  OPTIONS说明：
  -a stdin: 指定标准输入输出内容类型，可选 STDIN/STDOUT/STDERR 三项；
  -d: 后台运行容器，并返回容器ID；
  -i: 以交互模式运行容器，通常与 -t 同时使用；
  -t: 为容器重新分配一个伪输入终端，通常与 -i 同时使用；
  --name="nginx-lb": 为容器指定一个名称；
  --dns 8.8.8.8: 指定容器使用的DNS服务器，默认和宿主一致；
  --dns-search example.com: 指定容器DNS搜索域名，默认和宿主一致；
  -h "mars": 指定容器的hostname；
  -e username="ritchie": 设置环境变量；
  --env-file=[]: 从指定文件读入环境变量；
  --cpuset="0-2" or --cpuset="0,1,2": 绑定容器到指定CPU运行；
  -m :设置容器使用内存最大值；
  --net="bridge": 指定容器的网络连接类型，支持 bridge/host/none/container: 四种类型；
  --link=[]: 添加链接到另一个容器；
  --expose=[]: 开放一个端口或一组端口；

==========================================

使用php-fpm镜像

运行容器

w3cschool@w3cschool:~/php-fpm$ docker run -p 9000:9000 --name  myphp-fpm -v ~/nginx/www:/www -v $PWD/conf:/usr/local/etc/php -v $PWD/logs:/phplogs   -d php:5.6-fpm
00c5aa4c2f93ec3486936f45b5f2b450187a9d09acb18f5ac9aa7a5f405dbedf
w3cschool@w3cschool:~/php-fpm$
命令说明:
-p 9000:9000 :将容器的9000端口映射到主机的9000端口
--name myphp-fpm :将容器命名为myphp-fpm
-v ~/nginx/www:/www :将主机中项目的目录www挂载到容器的/www
-v $PWD/conf:/usr/local/etc/php ：将主机中当前目录下的conf目录挂载到容器的/usr/local/etc/php
-v $PWD/logs:/phplogs ：将主机中当前目录下的logs目录挂载到容器的/phplogs

===========================================

使用nginx镜像

运行容器

w3cschool@w3cschool:~/nginx$ docker run -p 80:80 --name mynginx -v $PWD/www:/www -v $PWD/conf/nginx.conf:/etc/nginx/nginx.conf -v $PWD/logs:/wwwlogs  -d nginx
45c89fab0bf9ad643bc7ab571f3ccd65379b844498f54a7c8a4e7ca1dc3a2c1e
w3cschool@w3cschool:~/nginx$
命令说明：
-p 80:80：将容器的80端口映射到主机的80端口
--name mynginx：将容器命名为mynginx
-v $PWD/www:/www：将主机中当前目录下的www挂载到容器的/www
-v $PWD/conf/nginx.conf:/etc/nginx/nginx.conf：将主机中当前目录下的nginx.conf挂载到容器的/etc/nginx/nginx.conf
-v $PWD/logs:/wwwlogs：将主机中当前目录下的logs挂载到容器的/wwwlogs

===========================================

使用mysql镜像

运行容器

w3cschool@w3cschool:~/mysql$ docker run -p 3306:3306 --name mymysql -v $PWD/conf/my.cnf:/etc/mysql/my.cnf -v $PWD/logs:/logs -v $PWD/data:/mysql_data -e MYSQL_ROOT_PASSWORD=123456 -d mysql:5.6
21cb89213c93d805c5bacf1028a0da7b5c5852761ba81327e6b99bb3ea89930e
w3cschool@w3cschool:~/mysql$
命令说明：
-p 3306:3306：将容器的3306端口映射到主机的3306端口
-v $PWD/conf/my.cnf:/etc/mysql/my.cnf：将主机当前目录下的conf/my.cnf挂载到容器的/etc/mysql/my.cnf
-v $PWD/logs:/logs：将主机当前目录下的logs目录挂载到容器的/logs
-v $PWD/data:/mysql_data：将主机当前目录下的data目录挂载到容器的/mysql_data
-e MYSQL_ROOT_PASSWORD=123456：初始化root用户的密码

===========================================

docker run ：创建一个新的容器并运行一个命令

docker kill :杀掉一个运行中的容器。
docker rm ：删除一个或多少容器

docker start :启动一个或多少已经被停止的容器
docker stop :停止一个运行中的容器
docker restart :重启容器

docker ps : 列出容器
docker top :查看容器中运行的进程信息，支持 ps 命令参数。


===========================================
run gitlab-ce

sudo docker run --detach \
    --hostname gitlab.wailianvisa.com \
    --publish 8081:80 \
    --restart unless-stopped \
    --volume /srv/gitlab/config:/etc/gitlab \
    --volume /srv/gitlab/logs:/var/log/gitlab \
    --volume /srv/gitlab/data:/var/opt/gitlab \
    gitlab/gitlab-ce:latest

sudo docker run --detach \
        --hostname gitlab.wailianvisa.com \
        --publish 8081:80 \
        --restart unless-stopped \
        --volume /etc/gitlab/config:/etc/gitlab \
        --volume /etc/gitlab/logs:/var/log/gitlab \
        --volume /etc/gitlab/data:/var/opt/gitlab \
        gitlab/gitlab-ce:latest

```
docker run -d \
    --name gitlab-ce-zh \
    --hostname gitlab.leapoon.com \
    -p 80:80 \
    --restart unless-stopped \
    -v gitlab-config:/etc/gitlab \
    -v gitlab-data:/var/opt/gitlab \
    -v gitlab-logs:/var/log/gitlab \
    gitlab/gitlab-ce


docker run -d \
    --name gitlab-ce-zh \
    --hostname gitlab.wailianvisa.com \
    -p 8081:80 \
    --restart unless-stopped \
    -v gitlab-config:/etc/gitlab \
    -v gitlab-data:/var/opt/gitlab \
    -v gitlab-logs:/var/log/gitlab \
    twang2218/gitlab-ce-zh:10.0
```

===========================================
run nginx

docker run -d \
  -p 127.0.0.1:80:80 \
  --restart unless-stopped \
  -v /home/wwwroot:/www \
  -v /home/wwwconfig/nginx.conf:/etc/nginx/nginx.conf:ro \
  -v /home/wwwlogs:/wwwlogs \
  nginx


  --name nginx-1.13.6 \
  --restart unless-stopped \
===========================================
run php


===========================================
run mysql


===========================================
run panubo/vsftpd

docker run -d \
  -e FTP_USER='xuyixing' \
  -e FTP_PASSWORD='123456' \
  --restart unless-stopped \
  panubo/vsftpd

docker run -d \
-p 21:21 \
-p 4559:4559 -p 4560:4560 -p 4561:4561 -p 4562:4562 -p 4563:4563 -p 4564:4564 \
-e FTP_USER='xuyixing' \
-e FTP_PASSWORD='123456' \
panubo/vsftpd

===========================================
docker run -d \
  -p 80:80 -p 433:433 -p 9000:9000 \
  richarvey/nginx-php-fpm

===========================================

  ```
  service docker start
  service docker stop
  service docker restart


  docker search nginx-php-mysql
  docker search go
  ```

===========================================
