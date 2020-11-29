# KVM-install
Debian/Ubuntu/CentOS 网络安装/网络重装/纯净安装 一键脚本


### 背景:
适用于由GRUB引导的CentOS,Ubuntu,Debian系统.

使用官方发行版去掉模板预装的软件.

同时也可以解决内核版本与软件不兼容的问题。

只要有root权限,还您一个纯净的系统。

注意:

全自动安装默认root密码:```  MoeClub.org  ```指定密码参数后面加 ```-p 密码```

安装完成后请立即更改密码.

能够全自动重装Debian/Ubuntu/CentOS等系统.

同时提供dd安装镜像功能,例如: 全自动无救援dd安装windows系统

全自动安装CentOS时默认提供VNC功能,可使用VNC Viewer查看进度,
VNC端口为1或者5901,可自行尝试连接.(成功后VNC功能会消失.)
目前CentOS系统只支持任意版本重装为 CentOS 6.x 及以下版本.

特别注意:OpenVZ构架不适用.

确保安装了所需软件:
#### Debian/Ubuntu:
```
apt-get install -y xz-utils openssl gawk file
```
#### RedHat/CentOS:
```
yum install -y xz openssl gawk file
```
如果出现了错误,请运行:
#### Debian/Ubuntu:
```
apt-get update
```
#### RedHat/CentOS:
```
yum update
```
# 快速使用示例:

### debian 7:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -d 7 -v 64 -a
```
### debian 8:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -d 8 -v 64 -a
```
### debian 9:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -d 9 -v 64 -a
```
### debian 10:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -d 10 -v 64 -a
```
### ubuntu 14.04:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -u 14.04 -v 64 -a
```
### ubuntu 16.04:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -u 16.04 -v 64 -a
```
### ubuntu 18.04:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -u 18.04 -v 64 -a
```
### VPS或者服务器多个网卡的情况
比如debian9系统，网卡名称enp0s5和enp0s6,但是enp0s6可用,enp0s5不可用
### ubuntu 18.04:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -d 9 -v 64 -a -i enp0s6
```
Usage:
        bash InstallNET.sh      -d/--debian [dist-name]
                                -u/--ubuntu [dist-name]
                                -c/--centos [dist-version]
                                -v/--ver [32/i386|64/amd64]
                                --ip-addr/--ip-gate/--ip-mask
                                -apt/-yum/--mirror
                                -dd/--image
                                -a/-m
 
# dist-name: 发行版本代号
# dist-version: 发行版本号
# -apt/-yum/--mirror : 使用定义镜像
# -a/-m : 询问是否能进入VNC自行操作. -a 为不提示(一般用于全自动安装), -m 为提示.
