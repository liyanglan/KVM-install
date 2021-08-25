### 1.新增对 Oracle AMD，Oracle ARM全面支持. 可支持从 Ubuntu, Oracle Linux 等系统网络重装.
### 2.更新 dd 镜像的基础系统版本.
### 3.移除对外部 wget 的依赖.
### 4.新增 -port 参数, 可更改默认SSH端口.
### 5.更新 内置的网络参数计算 逻辑.
### 6.更新 grub 配置文件定位逻辑, 可支持任意引导grub的系统.


### 以下系统已通过测试(其他自测):
Debian: 9, 10, 11;
Ubuntu: 18.04, 20.04;
CentOS: 6.10;
### 以下平台已通过测试(其他自测):
Oracle、Do、Azure

### 示例:
bash <(wget --no-check-certificate -qO- 'https://raw.githubusercontent.com/MoeClub/Note/master/InstallNET.sh') -d 10 -v 64 -p "自定义root密码" -port "自定义ssh端口"

### 开机改密：
#!/bin/bash
echo root:Vicer |sudo chpasswd root
sudo sed -i 's/^#\?PermitRootLogin.*/PermitRootLogin yes/g' /etc/ssh/sshd_config;
sudo sed -i 's/^#\?PasswordAuthentication.*/PasswordAuthentication yes/g' /etc/ssh/sshd_config;
sudo reboot
