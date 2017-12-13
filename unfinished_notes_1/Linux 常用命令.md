
#### Linux 常用命令

##### 1


ll

cd

passwd
passwd [username]

vi

clear

exit


ip addr show
ip addr
ip address
ifconfig

查看Linux系统发行版本
lsb_release -a
cat /etc/issue

查看Linux内核版本
uname -a
cat /proc/version

history


查看已有的iptables规则，以序号显示
iptables -L -n --line-numbers


删除对应的DROP规则
iptables -D INPUT 5

清除已有iptables规则
iptables -F
iptables -X
iptables -Z

允许访问80端口
iptables -A INPUT -p tcp --dport 80 -j ACCEPT

允许访问443端口
iptables -A INPUT -p tcp --dport 443 -j ACCEPT

允许FTP服务的21和22端口
iptables -A INPUT -p tcp --dport 21 -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j ACCEPT

允许访问3306端口
iptables -A INPUT -p tcp --dport 3306 -j ACCEPT

允许访问5432端口
iptables -A INPUT -p tcp --dport 5432 -j ACCEPT


====================================================

service
start, stop, restart, try-restart, reload, force-reload, status

====================================================

systemctl
start NAME                 
stop NAME                
reload NAME             
restart NAME
try-restart NAME
reload-or-restart NAME
reload-or-try-restart NAME
isolate NAME
kill NAME
