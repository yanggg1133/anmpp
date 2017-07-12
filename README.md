# anmpp
android nginx mysql pgsql php-fpm

	
ANMPP是ANDROID NGINX MYSQL PHP-FPM POSTGRESQL的简写；
ANMPP可以工作在基于X86&ARM的所有ANDROID设备上面（特殊设备除外）；
ANMPP的主要对象是安卓设备，对于其他X86&ARM LINUX设备可能需要做对应的修改；
ANMPP是一个需要ROOT权限的PHP集成环境，提供MYSQL，POSTGRESQL数据库支持；
ANMPP的postgresql数据库服务器超级帐号是root，默认密码root，推荐使用我提供的phppgadmin；
ANMPP的mysql数据库服务器超级帐号是root，没有密码，密码是空的，推荐使用我提供的phpmyadmin；

环境的搭建需要哪些条件：
1、保证你的设备剩余磁盘200MB以上（安卓设备/data分区）
2、保证你的设备系统空闲5MB以上（安卓设备的/system分区）
3、保证你的设备的内核是LINUX，并且内核版本在2.6以上（还需要一些内核模块支持）

BFTPD的FTP账号密码设置格式：
username password ftpgroup homeroot
ANMPP的默认FTP账号设置如下：
root root root /
BFTPD的FTP账号密码配置文件：
/data/data/android.bftpd/etc/passwd.conf

ANMPP v11 安装说明：
需要root权限
安装anmpp.apk
使用anmpp.apk中的安装功能安装anmpp
安装的时候会提示使用的anmpp.zip路径（根据cpu构架把对应的anmpp.zip放到该路径
安装完成后进入软件，然后开启组件，开启组件后在左侧的选项中选择启动，然后对应组件会启动
如果你需要使用终端命令行安装，请使用anmpp.zip中自带的安装shell脚本，anmpp文件为控制文件

ANMPP V11 内网穿透：
内网穿透功能使用ngrok方案
anmpp gui中可以设置内网穿透
anmpp gui中可以查看内网穿透日志
借助内网穿透功能你可以让你的内网服务器被公网访问

ANMPP V12.1 更新日志：
1.更新ngrokc（内网穿透）
2.更新nginx到1.11.0
3.更新php-fpm到5.6.22
4.更新postgresql到9.6beta1
5.更新openssl依赖到1.0.2h
6.解决anmpp12 php curl模块无法解析dns问题

ANMPP V12 更新日志：
1.重大更新为安装和使用时不再操作/system分区，也就是说支持更多的设备
2.支持设置个选项来使设备保持在清醒状态，即使关闭屏幕，ANMPP也不会被系统休眠
3.内建ANMPP12控制文件，因为gnulibc的调整，ANMPP内建的安装和卸载shell都做了调整的
4.内网穿透功能，内网穿透的日志过长不会返回数据的问题已经修复，另外就是内网穿透选项更好的支持需要token才能使用的ngrok服务器

ANMPP V11 更新日志：
1.gnulibc更新（x86&arm）
2.nginx更新到1.10.0（x86&arm）
3.php-fpm更新到5.6.21（x86&arm）
4.加入内网穿透服务支持（x86&arm）
5.anmpp gui加入版本查看及检查更新
Tags： ANMPP   安卓集成环境   安卓环境   安卓开发环境搭建   


-=============================




用安卓设备搭建PHP局域网服务器-ANMPP

    |
    浏览：2222
    |
    更新：2014-05-01 10:52
    |
    标签：安卓 局域网 

所需文件:

请注意，本教程需要用到root权限！

共两个文件:

anmpp.apk PHP集成环境管理软件;下载后直接安装即可。
电脑软件
名称：PHP集成环境管理软件
 
大小：0.7MB|版本：8.0|类别：工具|语言：中文|价格：免费
应用平台：Android 

anmpp.zip PHP集成环境包;下载后放在内存卡根目录即可。
电脑软件
名称：PHP集成环境包
 
大小：23MB|版本：8.1|类别：工具|语言：中文|价格：免费
应用平台：Android 
安装方法：

①安装anmpp.apk管理软件，且移动anmpp.zip环境包放在内存卡根目录，既首目录；

软件主界面：

②打开软件，并点击“高级核心功能”

软件需要root权限，请授予它权限

③更新高级核心列表：

选第二或第三个节点：

更新成功：

④安装环境：

点击“anmpp-install”进行安装：

安装成功：

⑤启动环境：

点击软件主界面的“启动 ”启动环境

⑥查看环境运行状态：

⑥安装成功：

在浏览器打开localhost或127.0.0.1出现以下内容既表示安装并运行成功！

用处：

可以搭建一个小型网站，如论坛，聊天室，同学录，表白网页之类的小程序，跟你同处于同一局域网的人就可以通过IP访问你所搭建的网站。

对于程序猿来说，可以用来调试程序，很方便实用。

一定条件下，还可以让环境让外网访问，但前提是你有路由器的控制权和运营商未限制。
说明：

环境默认网页路径为/data/data/android.wwwroot/ 路径可在nginx.conf文件里修改。

默认MySQL用户名:root；密码为空。

默认postgresql用户名:postgresql；密码为空。

默认FTP用户名:root；密码:root。
