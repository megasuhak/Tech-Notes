
#### Linux etc目录详解



```
https://blog.csdn.net/shixin_0125/article/details/78738866
https://blog.csdn.net/shixin_0125/article/details/78663329
```

```
Linux /etc目录详解
博客分类： ux
linuxbashetcpasswdgroup
Linux /etc目录详解

/etc目录
　　包含很多文件.许多网络配置文件也在/etc 中.

/etc/rc   or/etc/rc.d   or/etc/rc*.d   
　　启动、或改变运行级时运行的scripts或scripts的目录.

/etc/passwd   
　　用户数据库，其中的域给出了用户名、真实姓名、家目录、加密的口令和用户的其他信息.

/etc/fdprm   
　　软盘参数表.说明不同的软盘格式.用setfdprm 设置.

/etc/fstab   
　　启动时mount -a命令(在/etc/rc 或等效的启动文件中)自动mount的文件系统列表.Linux下，也包括用swapon -a启用的swap区的信息.

/etc/group   
　　类似/etc/passwd ，但说明的不是用户而是组.

/etc/inittab   
　　init 的配置文件.

/etc/issue   
　　getty在登录提示符前的输出信息.通常包括系统的一段短说明或欢迎信息.内容由系统管理员确定.

/etc/magic   
　　file 的配置文件.包含不同文件格式的说明，file 基于它猜测文件类型.

/etc/motd   
　　Message Of TheDay，成功登录后自动输出.内容由系统管理员确定.经常用于通告信息，如计划关机时间的警告.

/etc/mtab   
　　当前安装的文件系统列表.由scripts初始化，并由mount 命令自动更新.需要一个当前安装的文件系统的列表时使用，例如df命令.

/etc/shadow   
　　在安装了影子口令软件的系统上的影子口令文件.影子口令文件将/etc/passwd 文件中的加密口令移动到/etc/shadow中，而后者只对root可读.这使破译口令更困难.

/etc/login.defs   
　　login 命令的配置文件.

/etc/printcap   
　　类似/etc/termcap ，但针对打印机.语法不同.

/etc/profile , /etc/csh.login ,/etc/csh.cshrc   
　　登录或启动时Bourne或Cshells执行的文件.这允许系统管理员为所有用户建立全局缺省环境.

/etc/securetty   
　　确认安全终端，即哪个终端允许root登录.一般只列出虚拟控制台，这样就不可能(至少很困难)通过modem或网络闯入系统并得到超级用户特权.

/etc/shells   
　　列出可信任的shell.chsh 命令允许用户在本文件指定范围内改变登录shell.提供一台机器FTP服务的服务进程ftpd检查用户shell是否列在 /etc/shells 文件中，如果不是将不允许该用户登录.

/etc/termcap
　　终端性能数据库.说明不同的终端用什么"转义序列"控制.写程序时不直接输出转义序列(这样只能工作于特定品牌的终端)，而是从/etc/termcap中查找要做的工作的正确序列.这样，多数的程序可以在多数终端上运行.

附：Linux系统 /etc/目录 文件介绍

1. aliases 包含了linux邮件服务所有的分发列表
2. crontab 设置cron环境变量和运行自动任务的时间
3. csh.cshrc csh (c shell) 用户设置系统范围的缺省值
4. csh.login
5. csh.logout
6. daily
7. defaultdomain
8. exports
9. fbtab
10.fstab 标识常见存储设备和它们在linux系统下挂载的位置
11.ftpusers
12.group 确定系统中定义组名和组
13.host.conf 设置TCP/IP网络上搜索域名查看文件的位置
14.hosts 包含了从你的这计算机上可以到达的ip地址和主机名
15.inetd.conf
16.localtime
17.login.conf
18.make.conf
19.monthly
20.motd
21.netstart----新版已改名为/etc/rc.network
22.passwd 为系统上所有合法用户存储帐户信息
23.printcap 包含了为你计算机配置打印机定义
24.profile 为所有用户设置系统范围的环境变量和启动的顺序。当用户登录时读取该文件
25.rc
26.rc.conf----代替原来的/etc/sysconfig 标识dns域名服务器主机的位置，使用TCP/IP协议的时候需要通过DNS服务将因特网上的主机名装换为 ip地址
27.rc.conf.local----代替原来的/etc/rc.local
28.rc.i386
29.rc.local----新版改名为/etc/rc.conf.local
30.rc.network----代替原来的/etc/netstart
31.resolv.conf
32.services 定义了TCP/IP服务和他们的端口分配
33.shells 列出了系统可用的shell 命令行编辑器（bash。sh和csh等）还有它们的位置
34.sysconfig----新版已改名为/etc/rc.conf
35.syslog.conf
36.termcap
37.ttys
38.weekly
39./etc/hosts.allow /etc/hosts.deny
hosts.allow---列出允许使用本地计算机上某些TCP/IP服务的主机
hosts,deny---列出不允许使用本地计算机某些TCP/IP服务的主机 （默认情况下是不存在的）
40./etc/networks /etc/netmasks
41.etc/issue 从本地终端或以控制台文件模式登录到fedora或rhel系统时，显示该文件包含的行
42. /etc/named.boot如果你运行自己家的dns服务器，该文件包含了dns的设置

1. aliases
这个档案主要是告诉 sendmail 要将信转寄给哪些使用者, 或是交由哪个程式处理.
如. root: user1,name2,user3
usenet: "|/usr/local/bin/mail-post.pl"

如上范例, sendmail 会将原先寄给的 root 的信分送给 user1 和 name2 和 user3, 而把寄给 usenet 的信交由 mail-post.pl 处理.

在你修改完之後, 要记得执行 "newaliases" 来更新 /etc/aliases.db
关於 aliases 之详细说明, 请 man aliases 查询.

2. crontab
这是给 root 用的 crontab file, 你也可以杀掉这个档案以 "crontab -e" 来替代.
格式如下...

#分 小时 天 月 礼拜几 用谁的身份 命令
*/5 * * * * root /usr/libexec/atrun

minute: 分钟/小时, 范围自 0 至 59
hour: 小时/天, 范围自 0 至 23
mday: 天/月, 范围自 0 至 31
month: 月/年, 范围自 0 至 12
wday: 天/周, 范围自 0 至 7 (0, 7 表示星期天)
who: 表是以谁的身份执行这个 command
(这只对 /etc/crontab 有用, crontab -e 无此栏位)
command: 命令或是 shell script

*/N: 表示每 N 一算, 像小时而言, */3 指的是 0,3,6,9,12

请 man 5 crontab 去看详细说明.

3. csh.cshrc

# 系统内定给 csh shell 用的 .cshrc 档

## 确定 HOME 目录
setenv HOME $HOME
set home=$HOME
cd $HOME

## 档案权限设定
umask 022

## 就是 Aliases 嘛
alias pftp '/usr/local/bin/pftp'
alias free 'pstat -s|grep -v not'
alias talk ytalk
alias ruptime '/usr/bin/ruptime|grep -v down'
alias ftp ncftp
alias rwho '/usr/bin/rwho -a|grep -v LOGIN'
alias more less
alias zmore zless
alias m less
alias pss 'ps auxw|sort -k 2|grep $USER'
alias psm 'ps auxw|sort -k 1,2|more'
alias psl psm
alias psv 'ps auxw|grep -v $USER|sort -k 2|more'
alias d '/usr/local/bin/colorls -G -alFgk /!* | more'
alias dir '/usr/local/bin/colorls -G -alFgk /!*'
alias rd rmdir
alias md mkdir
alias cls clear
alias cd.. 'cd ..'
alias del '/bin/rm -i'
alias xdel '/bin/rm -rf'
alias mv 'mv -i'
alias dir/w '/bin/ls -aFgk'
alias dw '/bin/ls -aFgk'
#alias x '(startx &)>&/dev/console;sleep 300;lo'
#alias lpr 'lpr -m'
alias cp 'cp -i'
alias rm 'rm -i'
alias lo 'clear;exit'
alias bye 'clear;exit'
#alias vi cvi
alias unlo 'unset autologout;unsetenv autologout'
alias q joe
alias .. 'cd ..'
alias ... 'cd ../..'
#alias ku 'ku -W'
alias tin rtin
#alias s 'exec screen'

## 环境设定
set path = (/sbin /usr/sbin /bin /usr/bin /usr/local/sbin /usr/local/bin)
set path = ($path /etc /usr/etc /usr/local/etc)
set path = ($path /usr/X11R6/bin /usr/games)
set path = ($path ~ ~/bin .)
set mail = (10 /var/mail/$USER)
set recexact
set autolist
set matchbeep = ambiguous
set autoexpand
set autocorrect
set ignoreeof
set noclobber
set notify
set correct = all
if ( ! $?WINDOW ) then
# set prompt = "%B%m [%/] [%?] -%n- "
set prompt = "%B%m [%/] -%n- "
else
set prompt = "%B%m [%/] -%n- [W$WINDOW] "
endif
set prompt2 = "(%t %m)%~ #%% "
set prompt3 = "%SDo you mean [%R] (y/n/e) ? "
set history = 500
set savehist = 500
set time=100
#set watch=(1 any any)
set symlinks = ignore
set listlinks
set listjobs
set rmstar
set showdots
#set tperiod = 30
# set autologout = (60 2)
#setenv MANPATH /usr/man:/usr/local/man:/usr/man
/preformat:/usr/X11/man:/usr/openwin/man
setenv EDITOR /usr/local/bin/joe
setenv VISUAL /usr/local/bin/joe
setenv EXINIT 'set ai'
setenv LESS "-EsPm-LESS-"
setenv LESSCHARDEF "8bcccbcc18b95.."
setenv PAGER "less -Em"
#setenv PAGER more
setenv LC_CTYPE lt_LN.ISO_8859-1
setenv LANG C
setenv BLOCKSIZE 1k
setenv MACHINE_ARCH i386
setenv MACHINE i386
setenv ORGANIZATION "交大资工 ADONIS"

## X 相关设定
setenv XWINHOME '/usr/X11R6'
setenv X11HOME '/usr/X11R6'
setenv OPENWINHOME '/usr/X11R6'
setenv XKEYSYMDB /usr/X11R6/lib/X11/XKeysymDB
setenv XNLSPATH /usr/X11R6/lib/X11/nls
#setenv LD_LIBRARY_PATH /usr/lib:/usr/X11R6/lib:/usr/local/lib
stty erase '^?'

if ( $?TERM ) then
if ($TERM == "xterm" || $TERM == "xterms") then
stty erase '^H'
endif
endif

## 杂七杂八设定
#set term = vt100
#set TERM = vt100
#setenv term vt100
#setenv TERM vt100
#stty extb
stty 38400
stty crt
stty -tabs
stty -istrip
stty pass8
unlo
#bindkey "[HOME]" beginning-of-line
#bindkey "[ESC]" keyboard-quit
limit coredumpsize 0

# 给 FSP Client 用
setenv FSP_PORT 21
setenv FSP_HOST nctuccca.edu.tw
setenv FSP_DIR /
setenv FSP_TRACE
setenv FSP_DELAY 3000

# Aii.. 就是 fsp aliases :)
alias fcat '(set noglob; exec fcatcmd /!*)'
alias fcd 'setenv FSP_DIR `(set noglob; exec fcdcmd /!*)`;fpwd'
alias fdu /(set noglob/; exec fducmd /!)
alias fget '(set noglob; exec fgetcmd /!*)'
alias fgrab '(set noglob; exec fgrabcmd /!*)'
alias fls '(set noglob; exec flscmd -F /!*)'
alias fll '(set noglob; exec flscmd -l /!*)'
alias fdir '(set noglob; exec flscmd -l /!*)'
alias fmore /(set noglob/; exec fcatcmd /!/* /| more/)
alias fpro '(set noglob; exec fprocmd /!*)'
alias fpwd 'echo "$FSP_HOST ($FSP_PORT): $FSP_DIR"'
alias frm '(set noglob; exec frmcmd /!*)'
alias frmdir '(set noglob; exec frmdircmd /!*)'
alias fhost 'setenv FSP_HOST /!*;setenv FSP_DIR /'

4. csh.login

# 系统内定的 .login 档.

#stty extb
stty 38400
#stty crt
#stty -tabs
stty -istrip
stty pass8

# Mesg y if not console
mesg y
if ( `tty | cut -c 6-` == console ) then
mesg n
endif

msgs -fp

5. csh.logout

# 系统内定的 .logout
clear
.

6. daily

cron 会 依照 /etc/crontab 去做每日例行的工作. 注意一下有些 commands 对你的硬盘造成很大的负荷, 像是最後一行 的 "sh /etc/security", 他会从你的根目录开始查询. 你可以加些每天你想要执行的commands, 像 是 "quotacheck -a", "bin/rm/-f /tmp*junk*.

7. defaultdomain

这个档案记载你的 domainname, 你有跑 yp (nis) 时才有用. 当然闲闲填一填也没差啦.

8. exports

这个档案定义哪些目录可经由 NFS 给别人使用.
例如 /cdrom -ro host1,host2
/home -maproot=root host3

Notice: 若你没加 "-ro" 表示可以写入, 所以你应当小心点.

做完修正後, "kill -1 $mountd_pid", 然後用 "showmount -e" 去看看 NFS 是否做的正确. 如果有错, 用 "tail /var/log/messages" 来看错误讯息.

你应该要将 /etc/rc.conf 中的 nfs_client_enable, nfs_server_enable 设为 YES.

详细说明请 man 5 exports.

9. fbtab

/dev/ttyv0 0600 /dev/console
/dev/ttyv1 0600 /dev/console
/dev/ttyv2 0600 /dev/console
/dev/ttyv3 0600 /dev/console
#/dev/ttyv0 0600 /dev/pcaudio:/dev/pcaudioctl

10. fstab

这个档案定义当你开机时, 你想 mount 哪些 partition.
例如.

/dev/sd0a / ufs rw 1 1
/dev/sd0e /dos msdos ro,-gmsdos,-m750 1 1
/dev/sd0g /usr/local ufs rw,userquota 1 1
/dev/sd0h /home ufs rw,userquota,groupquota 1 1
/dev/sd0b none swap sw 0 0
proc /proc procfs rw 0 0
kern /kern kernfs rw 0 0

详情请 man fstab.

如果你的 /usr 没有跟 / 放在一起，要特别注意，/usr 不可以放在使用 LKM 载入的 filesystem 後面。例如，你的 MSDOSFS 是利用 LKM 载入的(也就是说，你没有把 MSDOSFS 编译在 kernel 中)，你的 /dos
一定要放在 /usr 後面，不然开机会失败，例如：

modload:exec(/usr/bin/ld):NO such file or directiory
msdos:vfsload(msdos):Operation not permitted
Filessystem mount failed,startup aborted
Enter pathname of shell or RETURN for sh

11. ftpusers

这个档注明的 users 将无法 ftp 这台机器. 只要写 username 即可. 算是禁止 ftp 进来的黑名单吧.

12.group

这个档案主要记载著 group 名称, group id 以及隶属於该 group 的使用者.

要记得在 FreeBSD 中, 只有属於 wheel group 的使用者才能 su 成 root.

在升级时特别注意 /usr/src/etc/group 中是否有新增系统 group， 如 network 这个 group 就是最近新增的 group.

其他详细请用 man group.

13. host.conf

这个档案决定 DNS-name-lookup 的先後顺序. 你最好先 "hosts", 其次 "bind", 最後用 "nis".

hosts: 自 /etc/hosts 查询.
bind: 自 nameserver (参考 /etc/resolv.conf 设定) 查询.
nis: 自 nis server 查询.

14. hosts

这个档案记载了你所需要的 ip 和 hostname, 最少要包括 localhost 和你自己的 hostname, 通常是提供优先於 nameserver 的查询, 或是没有 nameserver 时的查询.

格式如下：
IP-addr full-hostname alias
如. 123.456.789.123 heaven.net.com heaven

请 man hosts 去看详细说明.

15.inetd.conf
Internet 超级服务器, 相关程序: /usr/sbin/inetd
这个档案定义由 inetd 所提供的服务, 应该要和 /etc/services 保持一致性.
当你修改这个档案的时候, 记得要 kill -1 $inetd_pid 去知会 inetd 要重新更新资料.
你可以安装 tcp-wrapper (tcpd) 以增加安全性.

16.localtime

这个档记载你所在的时区资料, 你可以从 /usr/share/zoneinfo 中选一个适合的来用.

就台湾而言, 你应该用 /usr/share/zoneinfo/Asia/Taipei, 正常来说, 在 install 时会自动将此档案 copy 到 /etc/localtime.

17.login.conf

此档案可控制系统资源与帐号各方面的限制，亦可设定内定之环境变数。

"man login.conf" for detail.

18.make.conf

当你用 make 时, 这个定义档将被参考.

如果不是以 BSD 格式撰写的 Makefiles, 你应该安装 gmake (GNU)

19.monthly

每月例行的 jobs.

20.motd

Message Of Today, 顾名思义, 就是当你 login 时所出现的画面.

假如你要有自己的 motd, 你必须把 /etc/rc.local 前面几行在开机时会更改 motd 的命令拿掉, 否则你每次开机 motd 会被乱改.

21.netstart----新版已改名为/etc/rc.network

目前此档已由 /etc/rc.network 取代 目前此档只作为 root 在 single user mode 要手动启动网路服务
时使用。 这个档案不要做更动, 应该去修改 /etc/rc.conf

22.passwd

/etc/passwd /etc/master.passwd /etc/spwd.db /etc/pwd.db 都是 由 vipw 所产生的. 关於怎样去建一个帐号, 请参考 HOW-TO-adduser.

你可以 man passwd, vipw, chpass, chfn 查询详细说明.

23.printcap

这 个档案定义印表机的设定, 在修改後, 试著用 lpr 去列印一些东西, 假如你觉得很慢, 试著用 lptcontrol -p 去改变 /dev /lpt0 到 poll 模式, 当然, 你可以将 lptcontrol -p 加到 /etc/rc.local 里以使每次开机都有效.

man lptcontrol 查询详细说明.

24.profile

这是 /bin/sh 的 default 设定.

25.rc

当 系统开机时, kernel 会先去载入 /sbin/init, 然後 /sbin/init 会去执行 /etc/rc, 所以 /etc/rc 相 对於 DOS 而言就好像 AUTOEXEC.BAT. 这个档案不要去更改, 假如你不希望每次开机时 /tmp 会被清乾净, 那你可以将 跟 /tmp 相关的几行给砍掉. (个人偏好)

26.rc.conf----代替原来的/etc/sysconfig

这主要用来做系统开机时的环境设定. /etc/rc, /etc/rc.i386, /etc/rc.conf.local, /etc/rc.network, /etc/[bla bla] 都会参考这个档案. 所以这个档案可以说非常重要.

大多都有注解, 以下列举一些你该注意的地方...
1) hostname : 你的完整 hostname (FQDN: 像是 freebsd.csie.nctu.edu.tw)
2) network_interfaces : 网路卡的 device name, 像是 "ed0 lnc0".
3) ifconfig_xxx : 定义网路卡及其 ip address.
像是 ifconfig_ed0="inet 140.113.145.1 netmask 0xffffff00"
ifconfig_ed1="inet 140.113.190.1 netmask 0xffffff00"
方法如下...
ifconfig_$device-name="inet $IP netmask $netmask",
netmask 0xffffff00 就是 255.255.255.0 表 Class C 网路.
4) defaultrouter: 内定的 router IP.(比如: 140.113.122.254)
5) routdflags : 通常 NO. 但是假如你想要跑 routed, 则用 "-s" 或 "-q".
详细说明请 man routed.
6) rwhod : YES 执行 rwho daemon. rwho 跟 ruptime 须此 daemon.
7) sendmail_flags : 执行 sendmail daemon, 通常设为 "-db -q30m"
8) nfs_* : 执行 nfs client 或 server
9) check_quotas : enable 档案系统 quotas
10) accountint : enable command accounting, "lastcomm" 须要.
11) firewall_enable : enable firewall 的功能
firewall_type : 指定 firewall 的形态

你应该设定完後再重新开机以测试是否每个改变都合乎你的要求.

27.rc.conf.local----代替原来的/etc/rc.local

在这个档案加入你个人的设定, 你可以将开机时想要执行的动作放在这里. 像 gopherd, lptcontrol, swap-on-file 等.

28.rc.i386

这个档案不要更动.

29.rc.local----新版改名为/etc/rc.conf.local

新版已由/etc/rc.conf.local所取代。

30.rc.network----代替原来的/etc/netstart

有关网路方面各项设定请由 /etc/rc.conf 设定，原则上此档不需更动

31.resolv.conf

这定义 DNS 查询 nameserver 的先後顺序.

1. domain : 将你的 domainname 放这儿.
2. nameserver : 将你的 nameservers 放这儿, 最前面的会被当成主要的nameserver.
3. search : 将 domainnames 放这儿, 当你没有输入完整的 hostname 时, 他会将 domainnames 附加上去. 例如: search csie.NCTU.edu.tw NCTU.edu.tw edu.tw tw

详情请 man resolver.

32.services

定义 service 名字以及 port. 不需要更动。

33.shells

所有的 shell 都应该放在这个档案里, 像是 /bin/sh, /bin/tcsh, /home/bbs/bin/bbsrf 等等.

假如说有某个使用者的 shell 没有列在这个档案中, 有些程式如 ftpd 会拒绝该使用者 ftp, 如 adduser 将会拒绝执行.

man shells 查询详细说明.

34.sysconfig----新版已改名为/etc/rc.conf

参考 rc.conf。

35.syslog.conf

这个档案指出系统的 log 应该储存在哪儿.

36.termcap

这个应该 link 到 /usr/share/misc/termcap.

37.ttys

定义 tty 的形式及某些 tty 允不允许 root login. 假如某些 ttys 後面加有 "secure", 表示 root 可以 login. 你应当多加些, 如 /dev/tty[pqrs][0-9a-v]

详情请 man ttys。

38.weekly

每周例行的工作。

39./etc/hosts.allow /etc/hosts.deny (Linux下,或使用了tcpd, 参考inetd.conf)

/etc/hosts.allow 设置允许使用inetd服务的机器，如: All:202.118即允许所有来自
202.118.x.x的请求
/etc/hosts.deny 设置不允许使用inetd的机器

这两个文件的设定顺序请参考在线文档：
man tcpd
man hosts.allow
man hosts.deny

Internet 网络服务访问控制文件,

对于安全性要求较高的服务器建议采用xinetd替代inetd,
xinetd debian自带,其他的可以用源代码进行编译安装

40./etc/networks /etc/netmasks

列出路由所需要的网络地址,相关命令/usr/sbin/route，当然也可以不使用这两个
文件，在维护路由表时可直接使用IP地址及网络屏蔽位。

Example:
/etc/networks
dlrin 202.199.128.0
/etc/netmasks
202.199.128.0 255.255.240.0
加入静态路由表项:

+---------------+ DDN
| Cisco 2511 +<-------------->DLMU 202.118.64.0/255.255.255.0
| +<-------------->DLNA 210.47.192.0/255.255.240.0
+-------+-------+
| 202.118.66.254
| 202.118.66.16
+-------+-------+ +-------------+ +-----------+
| Switch/HUB +-------+网络中心 +-----+ LAN Router+
+-------+-------+ +-------------+ +------+----+
| |
|
| 202.118.68.0/255.255.252.0
| +--------------+
+--------------+ 202.118.66.81+ (测试机器)
| +--------------+
|
|
| 202.118.66.1(Default Router)
+-------+-------+
| 路由器 +
+-------+-------+
|202.112.30.65/255.255.255.252
| DDN
 | PPP
|
|202.112.30.66/255.255.255.252
Cernet/Internet

(1) 202.118.66.81(Helius) <-> 202.118.66.18 (peony)
202.118.066.081
255.255.255.0 And
-------------------
202.118.066.0 网络地址 在同一个ip网络段

IP Address <-> MAC(Media Access Address)
202.118.66.18 08:00:20:96:01:6A
 202.118.66.81 00:80:C8:4C:6A:D0
 202.118.66.1 00:60:5C:F3:FF:75

 202.118.66.81 -> 202.118.66.18
以太网的数据包:

08:00:20:96:01:6A + 00:80:C8:4C:6A:D0 + ip数据

(2) 202.118.66.81 -> 202.112.0.36
不在同一个ip段, 通过间接传送(通过路由器).
[hbwork@linden hbwork]$ netstat -rn
Kernel IP routing table
Destination Gateway Genmask Flags MSS Window irtt Iface
202.118.66.0 0.0.0.0 255.255.255.0 U 1500 0 0 eth0
127.0.0.0 0.0.0.0 255.0.0.0 U 3584 0 0 lo
0.0.0.0 202.118.66.1 0.0.0.0 UG 1500 0 0 eth0
 ^^^^^^^
Default Router

(3) 加入静态路由
相关命令：/usr/sbin/route或 /sbin/route
linux下需要加入自己网络的路由表项
/sbin/route add -net 202.118.66.0 netmask 255.255.255.0 eth0
/sbin/route add -net 202.199.128.0 netmask 255.255.240.0 gw 202.118.66.254
Or:
/sbin/route add -net dlrin gw 202.118.66.254
Or:
/sbin/route add -net dlrin gw dlrin-gw
/sbin/route add default gw 202.118.66.1

41.etc/issue 系统进站提示信息(主控台用)
 /etc/issue.net telnet时显示信息( strings in.telnetd |egrep issue)
/etc/motd 用户进入系统后的提示信息

42. /etc/named.boot
DNS(BIND 4.9.x) 启动文件
示例文件:(Caching Only Server)
directory /etc/namedb

primary 0.0.127.in-addr.arpa named.local
cache . root.cache

其中root.cache 文件可通过dig得到:

dig @ns.internic.net . ns > /etc/namedb/root.cache

named.local文件内容如下:

@ IN SOA localhost. root.localhost. (
1999020301
10800
3600
86400
86400 )

IN NS localhost.

1 IN PTR localhost.
/etc/named.conf
DNS(BIND 8.1.x) 启动文件
(在Redhat 5.2下可用/usr/doc/bind-8.1.2/named-bootconf.pl将bind 4.9.x
的named.boot文件转换为bind8的named.conf文件格式, 执行过程如下:
/usr/doc/bind-8.1.2/named-bootconf.pl /etc/named.boot > /etc/named.conf)
```
