---
title: 从VirtualBox里的虚拟ubuntu server里访问Windows里的文件
date: 2019-08-05 15:00:00
---

VirtualBox版本为6.0.10

# 1.设置共享文件夹
>设置 -> 共享文件夹

这里选择了 C:\Users\myname\Downloads 这个文件夹为共享文件夹
![“设置 -> 共享文件夹”](/media/20190805-2.png)

# 2.安装增强功能
这个文件就在VirtualBox的安装目录下（C:\Program Files\Oracle\VirtualBox\VBoxGuestAdditions.iso），不用再下载了，在“设备->安装增强功能”时会自动调用。
![“VBoxGuestAdditions.iso文件位置”](/media/20190805-1.png)

设备 -> 安装增强功能
![“设备 -> 安装增强功能”](/media/20190805-3.png)

然后再手动执行以下命令：

* 1.加载VBoxGuestAdditions.iso文件

首先进入/media目录，如果里面没有cdrom则建一个
```bash
cd /media
sudo mkdir /media/cdrom
sudo mount /dev/cdrom /media/cdrom
[sudo] password for taosapp:
mount: /media/cdrom: WARNING: device write-protected, mounted read-only.
```

* 2.进入cdrom目录，运行VBoxLinuxAdditions.run

```bash
cd cdrom
ls

AUTORUN.INF  runasroot.sh                       VBoxSolarisAdditions.pkg
autorun.sh   TRANS.TBL                          VBoxWindowsAdditions-amd64.exe
cert         VBoxDarwinAdditions.pkg            VBoxWindowsAdditions.exe
NT3x         VBoxDarwinAdditionsUninstall.tool  VBoxWindowsAdditions-x86.exe
OS2          VBoxLinuxAdditions.run
```
运行
```bash
sudo ./VBoxLinuxAdditions.run
```


完成后media目录下会多一个sf_Downloads
media目录下执行
```bash
sudo mount -t vboxsf sf_Downloads
```
进入到 sf_Downloads 就可以看到共享的文件了

# 3.权限
如果进入 sf_Downloads 文件夹时提示没有权限，运行以下命令把***当前用户***加入到 vboxsf 组
```bash
sudo adduser your-login-name vboxsf
```
添加完成后在此重启Ubuntu即可（必须重启）
```bash
sudo reboot
```

然后就可以在VirtualBox里的ubuntu server里访问Windows里的共享文件夹了