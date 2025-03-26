---
title: putty连接VirtualBox里的ubuntu，关键步骤：网络设置->端口转发
date: 2019-03-01 15:00:31
---

最关键的设置是“网络”里的端口转发，如下面3图步骤所示：
![“网络地址转换(NAT)”](/media/2019022701.jpg)
![“高级”](/media/2019022702.jpg)
![“端口转发规则”](/media/2019022703.jpg)

- 子系统IP就是VirtualBox里的ubuntu的IP地址，这里我添加了2个常用端口；
- 80一般是网页端口，比如nginx，设置之后就可以在本机访问VirtualBox里的虚拟机网页，如上图端口设置 http://127.0.0.1:1580 就可以访问VirtualBox里的80端口了；
- 22端口就是ssh的端口，putty访问的就是这个端口。

![“putty连接”](/media/2019022704.jpg)