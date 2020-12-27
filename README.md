# 萌咖大佬的一键DD脚本
Debian/Ubuntu/CentOS 网络安装/网络重装/纯净安装 一键脚本


### 背景:
适用于由GRUB引导的CentOS,Ubuntu,Debian系统.

使用官方发行版去掉模板预装的软件.

同时也可以解决内核版本与软件不兼容的问题。

只要有root权限,还您一个纯净的系统。

注意:

全自动安装默认root密码:```  MoeClub.org  ```指定密码参数后面加 ```-p 密码```

使用默认密码安装完成后请立即更改密码.

能够全自动重装Debian/Ubuntu/CentOS等系统.

同时提供dd安装镜像功能,例如: 全自动无救援dd安装windows系统.

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
# --ip-addr :IP Address/IP地址
# --ip-gate :Gateway   /网关
# --ip-mask :Netmask   /子网掩码
# 以下示例中,将X.X.X.X替换为自己的网络参数.
```

# 快速使用示例:

### centos 6:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -c 6.9 -v 64 -a --mirror 'http://mirror.centos.org/centos'
```
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
### ubuntu 20.04:
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JLyvq') -u 20.04 -v 64 -a
```
### VPS或者独立服务器有多个网卡.
##### 例:安装debian9，网卡名称enp0s5和enp0s6,enp0s6可用.
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -d 9 -v 64 -a -i enp0s6
```
### VPS安装debian9并且自定义源.
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -d 9 -v 64 -a --mirror 'http://archive.ubuntu.com/ubuntu'
```
### VPS安装debian9无法识别IP地址并且自定义源.
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') -d 9 -v 64 -a --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x  --mirror 'http://archive.ubuntu.com/ubuntu'
```
### VPS DD方式安装windwos 7.
```
bash <(wget --no-check-certificate -qO- 'https://git.io/JeiRm') --ip-addr x.x.x.x --ip-gate x.x.x.x --ip-mask x.x.x.x -dd 'https://moeclub.org/get-win7embx86-auto'
```


## 一些可用镜像地址:
```
# 推荐使用带有 /GoogleDrive/<File_ID> 链接, 速度更快.
# 当然也可以使用自己GoogleDrive中储存的镜像,使用方式:
  https://image.moeclub.org/GoogleDrive/<File_ID>
 
# win7emb_x86.tar.gz:
  https://image.moeclub.org/GoogleDrive/1srhylymTjYS-Ky8uLw4R6LCWfAo1F3s7 
  https://image.moeclub.org/win7emb_x86.tar.gz
 
# win8.1emb_x64.tar.gz:
  https://image.moeclub.org/GoogleDrive/1cqVl2wSGx92UTdhOxU9pW3wJgmvZMT_J
  https://image.moeclub.org/win8.1emb_x64.tar.gz
```
## 一些提示:

特别注意:

萌咖提供的dd安装镜像

远程登陆账号为: ```Administrator```

远程登陆密码为: ```Vicer```

仅修改了主机名,可放心使用.(建议自己制作.)

在dd安装系统镜像时:

在你的机器上全新安装,如果你有VNC,可以看到全部过程.

在dd安装镜像的过程中,不会走进度条(进度条一直显示为0%).完成后将会自动重启.

分区界面标题一般显示为: “Starting up the partitioner“

使用谷歌网盘中储存的镜像: [无限制大小] 获取谷歌网盘文件临时直接下载链接

在全自动安装CentOS时:

如果看到 “Starting graphical installation” 或者类似表达,则表示正在安装.

正常情况下只需要耐心等待安装完成即可.

如果需要查看进度,使用VNC Viewer(或者其他VNC连接工具)

连接提示中的IP地址:端口进行连接.(端口一般为```1```或者```5901```)

