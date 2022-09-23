# systemctl命令

## 常用命令
以sshd服务为例，列出常用systemctl命令：
启动sshd服务：systemctl start ssh.service
停止sshd服务：systemctl stop ssh.service
查看sshd服务状态：systemctl status ssh.service
重启sshd服务：systemctl restart ssh.service
设置开机自启动：systemctl enable ssh.service
禁止开机自启动：systemctl disable ssh.service
查看所有已经启动的服务：systemctl list-units --type=service
重新加载配置文件：systemctl daemon-reload

## 自定义service
systemctl启动服务编写
Centos7的服务systemctl脚本存放在：/usr/lib/systemd/目录下，有系统（system）和用户（user）之分，一般需要开机不登录就能运行的程序，就存放在/usr/lib/systemd/system/目录下

每一个服务以.service结尾，一般会分为3部分：[Unit]、[Service]和[Install]，以sshd为实例如下：

[Unit]
Description=OpenSSH server daemon
Documentation=man:sshd(8) man:sshd_config(5)
After=network.target sshd-keygen.service
Wants=sshd-keygen.service

[Service]
Type=notify
EnvironmentFile=/etc/sysconfig/sshd
ExecStart=/usr/sbin/sshd -D $OPTIONS
ExecReload=/bin/kill -HUP $MAINPID
KillMode=process
Restart=on-failure
RestartSec=42s

[Install]
WantedBy=multi-user.target
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
[Unit]部分主要是对这个服务的说明，内容包括Description和After，Description 用于描述服务，After用于描述服务类别;

[Service]部分是服务的关键，是服务的一些具体运行参数的设置;

[Install]部分是服务安装的相关设置，可设置为多用户的;

### 配置文件详解
Unit
After 表示服务需要在***服务启动之后执行 无依赖
Before 表示服务需要在***服务启动之前执行 无依赖
Wants 弱依赖关系
Requires 强依赖关系 ***停止之后本服务也必须停止
Service
ExecStart 启动进程时执行的命令
ExecReload 重启服务时执行的命令
ExecStop 停止服务时执行的命令
ExecStartPre 启动服务之前执行的命令
ExecStartPost 启动服务之后执行的命令
ExecStopPost 停止服务之后执行的命令
所有的启动设置之前，都可以加上一个 连词号（-），表示"抑制错误", 即发生错误的时候，不影响其他命令的执行。比如，EnvironmentFile=-/etc/sysconfig/sshd（注意等号后面的那个连词号），就表示即使/etc/sysconfig/sshd文件不存在，也不会抛出错误。

type参数说明

simple(默认值) ExecStart字段启动的进程为主进程
forking ExecStart字段将以fork()方式启动，此时父进程将会退出，子进程将成为主进程
oneshot 类似于simple，但只执行一次，Systemd 会等它执行完，才启动其他服务
dbus 类似于simple，但会等待 D-Bus 信号后启动
notify 类似于simple，启动结束后会发出通知信号，然后 Systemd 再启动其他服务
idle 类似于simple，但是要等到其他任务都执行完，才会启动该服务。一种使用场合是为让该服务的输出，不与其他服务的输出相混合
KillMode参数说明

control-group（默认值） 当前控制组里面的所有子进程，都会被杀掉
process 只杀主进程
mixed 主进程将收到 SIGTERM 信号，子进程收到 SIGKILL 信号
none 没有进程会被杀掉，只是执行服务的 stop 命令。
Restart参数说明

no（默认值） 退出后不会重启
on-success 只有正常退出时（退出状态码为0），才会重启
on-failure 非正常退出时（退出状态码非0），包括被信号终止和超时，才会重启
on-abnormal 只有被信号终止和超时，才会重启
on-abort 只有在收到没有捕捉到的信号终止时，才会重启
on-watchdog 超时退出，才会重启
always 不管是什么退出原因，总是重启
修改配置文件以后，需要重新加载配置文件，然后重新启动相关服务。

重新加载配置文件

systemctl daemon-reload

原文链接：https://blog.csdn.net/tl4832194/article/details/109781230