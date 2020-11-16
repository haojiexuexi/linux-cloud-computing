[TOC]



# 云计算系统管理

# ADMIN

## 01:云计算介绍、TCP/IP协议及配置



<img src="http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY01/COURSE/LINUXNSD_V01ADMINDAY01_003.png" alt="img"  />

### 服务器架构

#### 什么是服务器

- 能够为其他计算机提供服务的更高级的电脑

  ——机架式

  ——塔式

  ——机柜式

#### 典型服务模式

- C/S，Client/Server 架构

  ——由服务器提供资源或某种功能

  ——客户机使用资源或功能

### TCP/IP协议

#### TCP/IP协议简介

- TCP/IP是最广泛支持的通信协议集合

  ——包括大量Internet应用中的标准协议

  ——支持跨网络架构、跨操作系统平台的通信

- 主机与主机之间通信的三个要素

  ——IP地址（IP address）

  ——子网掩码（subnet mask）

  ——IP路由（IP router）



#### IP地址的概述

- 作用：用来标识一个节点的网络地址

- 地址组成（点分十进制）：

  —**一共32个二进制位**

  

  —表示为4个十进制数，以 .  隔开

- IP地址的分类

  用于一般计算机网络

  ——A类：1~127   网+主+主+主

  ——B类：128 ~ 191   网+网+主+主

  ——C类：192 ~ 223   网+网+网+主

  组播及科研专用（了解内容）

  –D类：224 ~ 239 组播

  –E类：240 ~ 254 科研

- 默认子网掩码

  ——A类地址，255.0.0.0

  ——B类地址，255.255.0.0

  ——C类地址，255.255.255.0

### 基本环境配置

#### TCP/IP参数设置

- 方式1，自动获取IP地址

  ——Windows Server 2008 默认方式

  ——临时地址 169.254.0.0/16

- 方式2，手动配置IP地址

  ——增加管理员负担

  ——容易出错

  ——适合企业内部服务器使用



#### 配置IP地址

- 操作步骤：

  ——右击桌面网络—> 属性—> 更改适配器设置

  ——双击“本地连接” —> 属性

  ——双击“Internet协议版本4（TCP/IPv4)”

  ——配置完成后，单机“确定”完成

#### 查看IP有效配置

- 操作步骤：

  开始 —>控制面板 —>网络和共享中心 —>更改适配器设置

  双击“本地连接” —>详细信息

#### 用命令查看IP有效配置

- 操作步骤：

  ——运行命令：ipconfig

  ——ipconfig/all

#### 使用ping命令测试网络连通性

- 回环测试（ping 127.0.0.1）

  ——验证TCP/IP协议驱动是否正常

- 本网连通性测试

  ——ping同一网段内其他计算机的IP地址

  ——ping默认网关的IP地址

- 远程连通性测试

  ——ping位于其他网络内的远程主机

  ——如果此步成功，则回环测试、本网连通性测试均可忽略，否则可依次执行检查、

- 回环测试结果

  ——确保TCP/IP 协议驱动已安装

  ——可正常收发TCP/IP协议的数据包

### 网关概念与DNS服务器的概念

网关：解决不同网络通信，一个网络到另一个网络的关口地址，涉及到网络设备路由器  

一个网络的出口地址

一个网络的入口地址

 

配置IP地址方式：

1、手工配置 

2、DHCP自动获取（前提是网络中有dhcp服务器）

DNS服务器（导航员）：域名解析系统，提供域名解析的机器。

域名解析：能够将域名解析为IP地址

www.baidu.com----》DNS服务器-----》 IP地址 ----》 百度的服务器

------



## 02:Linux系统简介、安装Linux系统、Linux基本操作



![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY02/COURSE/LINUXNSD_V01ADMINDAY02_003.png)



### 什么是Linux？



#### Linux系统的简介

- Linux****是一种操作系统！！面向服务端设计

操作系统：可以让计算机硬件正常工作，一堆软件

- **Unix/Linux发展史**

UNIX诞生，1970-1-1

-  **Linux之父，Linus Torwalds**

–  1991年10月，发布0.02版（第一个公开版）内核

–  1994年03月，发布1.0版内核

–  标准读音：“哩呐科斯”

–  内核：调配计算机硬件

   用户--->内核---->计算机硬件

   版本号：主版本.次版本.修订号

-  **发行版的名称/版本由发行方决定**

–  Red Hat Enterprise Linux（RHEL） 5/6/7/8

–  Suse Linux Enterprise 12

–  Debian Linux 7.8

–  Ubuntu Linux 14.10/15.04

![image-20200903094642159](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Cimage%5Cimage-20200903094642159.png)

-  **CentOS，社区企业操作系统**

–  Community Enterprise Operating System

–  http://www.centos.org/



![image-20200903094724289](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Cimage%5Cimage-20200903094724289.png)



### 利用虚拟化软件，进行安装Linux操作系统



虚拟化软件（VMware）:虚拟计算机的硬件

- 新建虚拟机

![image-20200903095005588](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095005588.png)



![image-20200903095017463](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095017463.png)



![image-20200903095032263](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095032263.png)

![image-20200903095043125](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095043125.png)

![image-20200903095236246](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095236246.png)

![image-20200903095253663](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095253663.png)

![image-20200903095303632](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095303632.png)

![image-20200903095310183](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095310183.png)

![image-20200903095319018](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095319018.png)

![image-20200903095326650](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095326650.png)

![image-20200903095335200](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095335200.png)

![image-20200903095342013](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095342013.png)

![image-20200903095349001](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095349001.png)

![image-20200903095354026](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095354026.png)

### 为虚拟机安装Linux操作系统

#### 将光盘镜像文件放入虚拟的光驱设备

![image-20200903095510096](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095510096.png)

![image-20200903095515600](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095515600.png)

![image-20200903095524306](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095524306.png)

虚拟机开机：前提虚拟化功能支持（CPU虚拟化功能打开）

•运行虚拟机需要真机开启虚拟化功能：重启真机系统进入BIOS进行设置

•开启虚拟化功能参考： https://blog.csdn.net/Blueberry521/article/details/104240762

Ctrl+Alt=鼠标回到真机

![image-20200903095604140](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095604140.png)

![image-20200903095613129](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095613129.png)

![image-20200903095619721](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095619721.png)

![image-20200903095626742](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095626742.png)

![image-20200903095632787](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095632787.png)

![image-20200903095641361](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095641361.png)

![image-20200903095649273](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095649273.png)

![image-20200903095657882](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095657882.png)

**双击完成**

![image-20200903095712075](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095712075.png)

![image-20200903095802513](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095802513.png)

**双击完成**

![image-20200903095811562](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095811562.png)

![image-20200903095817451](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095817451.png)

![image-20200903095825317](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095825317.png)

![image-20200903095830788](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095830788.png)

![image-20200903095838137](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095838137.png)

![image-20200903095844643](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095844643.png)

![image-20200903095850053](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095850053.png)

![image-20200903095855828](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095855828.png)

![image-20200903095900679](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095900679.png)

![image-20200903095907624](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095907624.png)

![image-20200903095913752](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095913752.png)

![image-20200903095921112](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095921112.png)

![image-20200903095927023](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095927023.png)

![image-20200903095931952](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903095931952.png)

#### 修改系统的时间

![image-20200903100018159](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100018159.png)

![image-20200903100022988](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100022988.png)

![image-20200903100030722](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100030722.png)

#### 关闭系统的节能功能

![image-20200903100044971](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100044971.png)





### **Linux**系统的目录结构

> 根目录(利用/表示)：Linux系统的起点（所有的数据都在此目录下）
>
> /dev：设备(键盘、鼠标、硬盘、光驱…..)相关的数据

> /dev/abc/1.txt：一个完整的路径，只有开头的/才表示为根目录，其他的/表示为分隔符

![image-20200903100209324](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100209324.png)

![image-20200903100215457](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100215457.png)

###  **Linux**系统的硬盘(磁盘)表示

![image-20200903100249412](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100249412.png)

### Linux哲学的理念: 一切皆文件

![image-20200903100313382](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100313382.png)

> /dev/sda:表示SCSI接口的硬盘第一块 
>
> /dev/sdb:表示SCSI接口的硬盘第二块

> /dev/sdc:表示SCSI接口的硬盘第二块
>
> ……….

### Linux基本操作

#### 获得命令行

> 方式一：虚拟控制台切换（ Ctrl + Alt + Fn 组合键）
>
> –  tty1：图形桌面
>
> –  tty2~tty6：字符控制台
>
> 方式二：在图形桌面

![image-20200903100450644](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100450644.png)

![image-20200903100457847](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100457847.png)

![image-20200903100503513](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903100503513.png)

###  **Linux**命令行操作

#### 命令行提示符

```
[root@localhost ~]#
```

> [当前登录的用户@主机名 当前所在的位置] #
>
> 如果以#结尾：表示当前登录的身份为超级管理员root
>
> 如果以$结尾：表示当前登录的身份为普通用户
>
>   放大: Ctrl  shift +
>
>    变小: Ctrl -
>

#### pwd — Print Working Directory

> 用途：查看当前工作目录（显示当前所在的位置）



#### cd — Change Directory

> 用途：切换工作目录
>
> 格式：cd [目标文件夹位置]



#### ls — List

> 格式：ls  [目录或文件名]…



> ```
> [root@localhost ~]# pwd      #显示当前所在的位置
> [root@localhost ~]# cd    /    #切换到根目录
> [root@localhost /]# pwd
> [root@localhost /]# ls            #显示当前目录的内容
> [root@localhost /]# cd   /home
> [root@localhost home]# pwd
> [root@localhost home]# ls
> 
> [root@localhost home]# cd   /opt
> [root@localhost opt]# pwd
> [root@localhost opt]# ls
> 
> [root@localhost opt]# cd  /root
> [root@localhost ~]# pwd
> [root@localhost ~]# ls
> 
>  蓝色：目录
>  黑色：文件
> ```

#### ls — List：显示指定目录内容

```
[root@localhost ~]# ls  /opt

[root@localhost ~]# ls  /home

[root@localhost ~]# ls  /

[root@localhost ~]# ls  /tmp

[root@localhost ~]# ls  /dev

[root@localhost ~]# ls  /etc

[root@localhost ~]# ls  /boot
```

#### cd — Change Directory：切换目录

> 绝对路径：以根目录开头的路径
>
> 相对路径：以当前所在目录，为参照的路径

```
]# cd   /etc/pki/             #绝对路径
]# pwd 
]# ls 
]# cd   /etc/pki/CA       #绝对路径，与当前所在位置无关
]# pwd
]# ls

]# cd   /etc/pki/         #绝对路径
]# pwd
]# ls
]# cd  CA        #相对路径，与当前所在位置有关
]# pwd

```

#### .. ：上一级目录

```
[root@localhost CA]# cd   /etc/pki/CA
[root@localhost CA]# pwd
/etc/pki/CA
[root@localhost CA]# cd   ..           #返回上一级目录
[root@localhost pki]# pwd
/etc/pki
[root@localhost pki]# cd  ..              #返回上一级目录
[root@localhost etc]# pwd
/etc
[root@localhost etc]# cd   ..            #返回上一级目录
[root@localhost /]#

```

#### 查看文本文件内容命令:cat 适合查看内容较少的文件

```

[root@localhost /]# cat   /root/anaconda-ks.cfg
[root@localhost /]# cat   /etc/redhat-release   #显示系统版本
CentOS Linux release 7.5.1804 (Core)

[root@localhost /]# cat   /etc/passwd
[root@localhost /]# cat   /etc/fstab
[root@localhost /]# cat   /etc/hosts
[root@localhost /]# cat   /etc/shells 

```

#### 查看文本文件内容命令:less 适合查看内容较多的文件

```
[root@localhost /]# less   /etc/passwd
 按上下键进行滚动，按q进行退出

```

#### 查看文本文件部分内容命令head、tail 命令   

> –  格式：head -n 数字 文件名   #头几行
>
> ​            tail -n 数字 文件名   #尾几行

```
[root@localhost /]# head -1   /etc/passwd

[root@localhost /]# head  -2  
/etc/passwd
[root@localhost /]# head  -3   /etc/passwd
[root@localhost /]# head  -13   /etc/passwd

[root@localhost /]# tail   -1   /etc/passwd
[root@localhost /]# tail   -2   /etc/passwd

```

#### 过滤包含指定字符串的行  

```
[root@localhost /]# grep  root  /etc/passwd
[root@localhost /]# grep  a    /etc/passwd
[root@localhost /]# grep  bash  /etc/passwd
[root@localhost /]# grep  dog   /etc/passwd

```

#### 修改文本文件内容：vim（文本编辑器）

>  三个模式：命令模式、插入模式(输入模式)、末行模式
>
> ```
> ]# vim  /opt/nsd.txt  #当文件不存在，会新建文件
> ```
>
> 命------i键 或者 o键------>插入模式(按Esc回到命令模式)
>
> 令
>
> 模
>
> 式------输入 ： ----------->末行模式(按Esc回到命令模式)
>
>  末行模式  :wq   #保存并退出
>
>  末行模式  :q！   #强制不保存并退出
>
> ]# cat  /opt/nsd.txt
>
> 

#### 新建目录：mkdir

```
[root@localhost /]# mkdir    /opt/nsd01
[root@localhost /]# ls    /opt/
[root@localhost /]# mkdir   /root/nsd02    /opt/nsd03
[root@localhost /]# ls    /root/
[root@localhost /]# ls    /opt/

```

#### 新建文件：touch

```
[root@localhost /]# touch    /opt/a.txt
[root@localhost /]# ls   /opt/

[root@localhost /]# touch     /opt/b.txt
[root@localhost /]# ls    /opt/

```

#### 查看以及设置主机名的命令：hostname

```
[root@localhost /]# hostname
localhost.localdomain
[root@localhost /]# hostname   hahaxixi    #设置主机名
[root@localhost /]# hostname                    #查看主机名
开启一个新的命令行
[root@hahaxixi ~]# hostname  nb.tedu.cn
[root@hahaxixi ~]# hostname
开启一个新的命令行
[root@nb ~]# hostname

```

#### 查看网卡IP地址命令：ifconfig

```
[root@nb ~]# ifconfig
```

lo: 回环测试接口，专门用于测试，本机访问自己

​    127.0.0.1：特殊IP地址，永远代表本机

 

​    virbr0：虚拟网卡

```
[root@nb ~]# ping 127.0.0.1
```

**按 Ctrl+c结束正在运行的指令**



#### 查看cpu信息

```
[root@nb ~]# lscpu
…….
型号名称：        Intel(R) Core(TM) i7-7700 CPU @ 3.60GHz
…….

```

####  查看内存信息

```
[root@nb ~]# cat  /proc/meminfo

MemTotal:    1865284 kB   #内存一共大小

…….
```

#### 关机poweroff

#### 重启reboot



### VMware拍摄快照

![image-20200903102453013](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903102453013.png)

![image-20200903102458290](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903102458290.png)

#### **还原快照：**

![image-20200903102517405](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903102517405.png)

![image-20200903102523997](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903102523997.png)

### 课后练习：

案例：ls命令练习

1. 查看根目录下内容

```
[root@localhost ~]# ls  /
```

2. 显示/etc目录内容 

3. 显示/boot目录内容的

4. 显示/root的内容

5. 显示/bin/bash程序

[root@localhost ~]# ls /bin/bash

6. 显示/opt目录内容

 

案例：查看文件内容练习

 1.查看/etc/passwd文件内容

 2.查看/etc/default/useradd文件内容

 3.查看内存信息

 4.查看/etc/hosts文件内容

 5.显示文件/etc/passwd文件内容的头3行内容

 6.显示文件/etc/passwd文件内容的尾4行内容

 7.显示文件/etc/passwd文件内容的头12行内容

 8.利用less分屏阅读/etc/passwd文件内容

 9.利用grep命令显示/etc/passwd文件内容中，包含root的行

 

案例：cd命令练习

 1.切换到根目录，利用pwd命令查看当前位置

 2.切换到/root，利用pwd命令查看当前位置

 3.切换到/boot，利用pwd命令查看当前位置

 4.切换到/opt，利用pwd命令查看当前位置

 5.切换到/tmp，利用pwd命令查看当前位置

 6.切换到/var，利用pwd命令查看当前位置

 7.切换到/home，利用pwd命令查看当前位置

 8.切换到/etc，利用pwd命令查看当前位置

 9.切换到/proc，利用pwd命令查看当前位置

 10.切换到/etc/pki，利用pwd命令查看当前位置,再利用cd ..进行返回上一层目录

 

案例：主机名与查看网卡命令练习

 1.显示当前系统主机名

 2.修改当前系统的主机名为svr.tedu.cn

 3.查看当前系统网卡IP地址信息

 

案例：创建命令练习

 1.请在/root创建三个目录分别为student、file、nsd18

 2.请在/opt创建三个文本文件分别为1.txt、a.txt、nsd.txt

 

案例：vim练习

 1.利用vim编辑/opt/Linux.txt，写入内容“I Love Studying Linux” 并用cat查看文件内容验证结果

 2.利用vim编辑/etc/myhost文件，写入内容“I Love Dc” ，并用cat查看文件内容验证结果

 3.利用vim编辑/etc/mystu.txt文件，写入内容“好好学习，天天向上” ，并用cat查看文件内容验证结果



------



## 03:命令行基础、目录及文件管理、文本内容操作

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY03/COURSE/LINUXNSD_V01ADMINDAY03_003.png)

### 如何编写命令

#### 什么是命令?

- **Linux命令**

> –  用来实现某一类功能的指令或程序 
>
> Linux中执行大多数命令，都要找到命令所对应的程序
>
> –  命令的执行依赖于解释器（默认的解释器程序:/bin/bash）
>
> 用户------>解释器------>内核------>硬件
>
> 
>
> 绿色：可以执行的程序
>
> 青色：快捷方式
>
> ```
> [root@localhost ~]# cat /etc/shells
> ```

- **Linux命令的分类**

> —内部命令：属于解释器的一部分
>
> —外部命令：解释器之外的其他程序

#### 命令行的一般格式

> –  命令字  [选项]…  [参数1]  [参数2]…

```
]# cat     /etc/shells
]# cat   --help              #查看命令的帮助信息
]# cat  -n   /etc/shells       #显示行号
]# cat  -n   /etc/passwd
]# cat  -n   /etc/hosts
]# cat  -n   /etc/redhat-release

]# ls   -l   /etc/shells   #利用长格式显示（显示详细属性）
]# ls  -l   /etc/redhat-release
]# ls  -l   /etc/passwd
]# ls  -l   /root          #显示目录所有内容的详细属性

1EB=1024PB
1PB=1024TB
1TB=1024GB
1GB=1024MB

```

#### 快速编辑技巧

- **Tab自动补全**

> –  可补齐命令字、选项、参数、文件路径、软件名、服务名

```
[root@localhost ~]# if(tab) (tab)
[root@localhost ~]# ifco(tab)
[root@localhost ~]# cat  /etc/redhat-release 
[root@localhost ~]# cat  /et(tab)/red(tab)

[root@localhost ~]# ls  /etc/sysconfig/network-scripts/
[root@localhost ~]# ls  /et(tab)/sysco(tab)/netw(tab)- (tab)

```

- **快捷键**

  > –  Ctrl + l：清空整个屏幕
  >
  > –  Ctrl + c：废弃当前编辑的命令行（结束正在运行命令）
  >
  > –  Esc + .或 Alt + .：粘贴上一个命令的参数
  >
  > ```
  > ]# ls  /etc/redhat-release 
  > 
  > ]# ls -l  Alt + .
  > 
  > ]# cat   Alt + .
  > 
  > ]# cat  -n  Alt + .
  > ```
  >
  > –  Ctrl + u：清空至行首
  >
  > –  Ctrl + w：往回删除一个单词（以空格界定）



### mount挂载操作：让目录成为设备的访问点

- #### 什么是挂载？

> **—将光盘/U盘/分区/网络存储等设备装到某个Linux目录**
>
> **—各种命令工具通过访问Linux目录来操作这些设备**

#### **Linux系统命令行显示光盘内容**

> **Windows：显示光盘内容**

>   光盘----->光驱设备----->DVD驱动器(访问点)
>
> **Linux: 显示光盘内容**
>
>   光盘----->光驱设备----->目录(访问点)

> 1.将光盘镜像文件放入虚拟光驱设备

> ![image-20200903104612467](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903104612467.png)![image-20200903104628589](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200903104628589.png)
>
> 

2.查看光驱设备(一切皆文件)     

```
[root@localhost ~]# ls  /dev/sr0   #实际名字

/dev/sr0

[root@localhost ~]# ls  /dev/cdrom   #快捷方式

/dev/cdrom

[root@localhost ~]# ls  -l  /dev/cdrom
```

 

3.利用mount命令进行挂载光驱设备

```
[root@localhost ~]# mkdir  /dvd

–  格式：mount  设备路径   挂载点目录

 

[root@localhost ~]# mount   /dev/cdrom   /dvd

mount: /dev/sr0 写保护，将以只读方式挂载

 

[root@localhost ~]# ls  /dvd/

[root@localhost ~]# ls  /dvd/Packages
```

4.卸载 

```
[root@localhost ~]# umount  /dvd

[root@localhost ~]# ls  /dvd/

[root@localhost ~]# mkdir  /nsd2007

[root@localhost ~]# mount   /dev/cdrom  /nsd2007

mount: /dev/sr0 写保护，将以只读方式挂载

[root@localhost ~]# ls  /nsd2007
```

**注意事项：**

**1.卸载时，当前位置不能是挂载点目录**

```
[root@localhost ~]# cd  /nsd2007**

**[root@localhost nsd2007]# ls**

**[root@localhost nsd2007]# umount  /nsd2007**

**umount: /nsd2007：目标忙。**
```

​    **(有些情况下通过 lsof(8) 或 fuser(1) 可以**

​     **找到有关使用该设备的进程的有用信息)**

**2.挂载时，自行创建目录**

**3.挂载允许将一个设备，挂载到不同的挂载点**

**4.不允许一个挂载点，挂载不同设备**



### 查看及切换目录

#### **cd** **— Change Directory**

> –  用途：切换工作目录
>
> –  格式：cd  [目标文件夹位置]
>
> **.**  当前目录
>
> **..**  父目录（上一层）
>
> **~** 用户家目录（存放用户个性化信息的目录）
>
> **~user**  用户user的家目录
>
> /root:管理员的家目录
>
> /home:存放所有普通用户的家目录

```
[root@localhost etc]# cd  ~root        #去往root用户的家目录
[root@localhost ~]# pwd

[root@localhost /]# useradd  harry     #创建harry用户
[root@localhost /]# cd  ~harry      #去往harry用户的家目录
[root@localhost harry]# pwd

[root@localhost harry]# useradd tom    #创建tom用户
[root@localhost harry]# cd ~tom   #去往tom用户的家目录
[root@localhost tom]# pwd
```

#### **ls** **— List常用命令选项**

> –  -l：以长格式显示,显示详细信息
>
> –  -A：显示所有内容包含隐藏数据
>
> –  -d：显示目录本身（而不是内容）的属性
>
> –  -h：提供易读的容量单位（K、M等）
>
> –  -R：递归显示内容(显示目录下所有内容，包括子目录)

```
]# ls   -l    /etc/passwd        #显示详细属性
]# ls   -lh    /boot/initramfs-3.10.0-862.el7.x86_64.img
]# ls  -lh   /etc/passwd      #显示详细属性，加上容量单位 

]# ls  -ld    /etc/                #显示目录本身的详细属性
]# ls  -ld    /home             #显示目录本身的详细属性
]# ls  -ld    /root                #显示目录本身的详细属性

]# ls   -A    /root               #显示目录所有内容，包括隐藏数据
]# ls   -A    /home/harry

]# ls   -R      /boot/            #递归显示目录内容
]# ls   -R    /                    #递归显示目录内容

```

### **通配符:针对不确定的文档名称，以特殊字符表示**

> –  *：任意多个任意字符
>
> –  ?：单个字符

```
[root@localhost /]# ls  /boot/vm*
[root@localhost /]# ls  /root/a*
[root@localhost /]# ls  /dev/tty*
[root@localhost /]# ls  /etc/*tab
[root@localhost /]# ls  /etc/*.conf
[root@localhost /]# ls  /etc/r*.conf
[root@localhost /]# ls  /etc/??tab
[root@localhost /]# ls  /dev/tty?
[root@localhost /]# ls  /dev/tty??
```

> –  [a-z]：多个字符或连续范围中的一个，若无则忽略
>
> –  {a,min,xy}：多组不同的字符串，全匹配

```
[root@localhost /]# ls   /dev/tty[3-6]
[root@localhost /]# ls   /dev/tty[1-9]
[root@localhost /]# ls   /dev/tty[0-9]

[root@localhost /]# ls   /dev/tty{1,3,7,9,11,28}
[root@localhost /]# ls   /dev/tty{1,2,3,4}
```

### **别名的定义:简化复杂的命令**

•   查看已设置的别名

–  alias [别名名称]

•   定义新的别名

–  alias 别名名称= '实际执行的命令行'

•   取消已设置的别名

–  unalias [别名名称] 

```
[root@localhost /]# hostname
[root@localhost /]# alias     hn='hostname'    #定义别名
[root@localhost /]# hn

[root@localhost /]# alias    myls='ls   -ld'   #定义别名
[root@localhost /]# myls   /root
[root@localhost /]# alias                #查看系统中所有有效别名
[root@localhost /]# unalias  myls   #删除别名

```

###  **新建文档**

> mkdir — Make Directory
>
> 格式：mkdir [-p] [/路径/]目录名…
>
> -p：创建多级目录，创建父目录

```
[root@localhost /]# mkdir   -p   /opt/aa/bb/cc/dd
[root@localhost /]# ls -R /opt/aa

[root@localhost /]# mkdir  -p   /vod/movie/cartoon
[root@localhost /]# ls -R /vod

```

###  ***rm*删除数据Remove**

> 格式：rm   [选项]...   文件或目录…
>
> 常用命令选项：
>
> -r、-f：递归删除（含目录）、强制删除

```
[root@localhost /]# rm  -rf   /opt/aa
[root@localhost /]# ls  /opt

```

### mv — Move移动，源数据会消失

> ```
> –	格式：mv     原文件…     目标路径
> ```

```
[root@localhost /]# rm  -rf   /opt/*
[root@localhost /]# mkdir    /opt/nsd01
[root@localhost /]# touch   /opt/1.txt
[root@localhost /]# ls   /opt/
1.txt  nsd01
[root@localhost /]# mv    /opt/1.txt   / opt/nsd01
[root@localhost /]# ls    /opt/
nsd01
[root@localhost /]# ls   /opt/nsd01/
1.txt
[root@localhost /]#
```

#### •重命名:路径不变的移动

```
[root@localhost /]# ls   /opt/
nsd01
[root@localhost /]# mv   /opt/nsd01/    /opt/abc01
[root@localhost /]# ls    /opt/
abc01
[root@localhost /]# mv   /opt/abc01/     /opt/student
[root@localhost /]# ls    /opt/
student
```

#### •    在移动的时候，可以重新命名目标路径下数据的名称

```
]# ls /opt/

]# mv    /opt/student/    /mnt/stu01     #移动过去并且改名
]# ls /mnt/

]# mkdir   /opt/test
]# ls  /opt/

]# mv     /opt/test/    /mnt/stu01   #移动到/mnt/stu01目录下
]# ls   /mnt/
]# ls   /mnt/stu01/

```

#### •    mv支持多个参数，永远会把最后一个参数作为目标，其他全部作为源数据

```
]# touch    /mnt/1.txt
]# touch    /mnt/2.txt
]# mkdir    /mnt/nsd10
]# ls   /mnt/
]# mv    /mnt/1.txt    /mnt/2.txt    /mnt/nsd10/     /opt/
]# ls   /opt/

```

### **cp** **— Copy复制，源数据不会消失**

> **–  格式：cp [选项]... 原文件… 目标路径**
>
> **常用命令选项**
>
> **–  -r：递归，复制目录时必须有此选项**

```
[root@localhost /]# rm  -rf    /opt/*
[root@localhost /]# cp    /etc/redhat-release    /opt/
[root@localhost /]# ls   /opt/

[root@localhost /]# cp  -r     /home   /opt/     #复制目录
[root@localhost /]# ls   /opt/

```

#### •    复制出现重名覆盖

> ]# cp  -r  /home/   /opt/
>
> ]# \cp  -r  /home/   /opt/  #在本次操作临时取消别名

#### •    在复制的时候，可以重新命名目标路径下数据的名称

> [root@localhost /]# cp  /etc/redhat-release   /opt/haha
>
> [root@localhost /]# ls  /opt/
>
> [root@localhost /]# cp -r  /boot/   /opt/myboot
>
> [root@localhost /]# ls /opt/

#### •    cp支持多个参数，永远会把最后一个参数作为目标，其他全部作为源数据

```
]# cp   /etc/passwd     /etc/hosts   /etc/fstab    /opt/
]# ls /opt/

```

#### •    在复制的时候，可以与点进行连用

```
[root@localhost /]# cd   /opt/
[root@localhost opt]# pwd
[root@localhost opt]# cp /etc/shells    .     #复制到当前路径下
[root@localhost opt]# ls  

[root@localhost opt]# cd  /etc/sysconfig/network-scripts/
[root@localhost network-scripts]# pwd
[root@localhost network-scripts]# cp  /etc/fstab     .
[root@localhost network-scripts]# ls

```

### **在文本文件内容中，输出包含指定字符串的行**

> **–  grep   '关键字'   文本文件...**

#### 常用命令选项

> **–  -v，取反匹配**
>
> **–  -i，忽略大小写**

```
]# grep  root    /etc/passwd
]# grep   -v    root    /etc/passwd    #输出不包含root的行

]# grep   -i   man    /etc/man_db.conf   #忽略大小写

```

> –  ^word      以字符串word开头
>
> –  word$      以字符串word结尾

```
[root@localhost /]# grep   ^root    /etc/passwd 

[root@localhost /]# grep   bash$   /etc/passwd

```

------



## 04：归档及压缩、重定向与管道操作、find精确查找、vim高级使用

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_003.png)

### 归档及压缩

#### 归档和压缩

- #### 归档的含义

  **——将许多零散的文件整理为一个文件**

  **——文件总的大小基本不变**

- #### 压缩的含义

  **——按某种算法减小文件所占用空间的大小**

  **——恢复时对应的逆向算法解压**

  > **常见的压缩格式及命令工具：**
  >
  > **.gz --> gzip、gunzip**
  >
  > **.bz2 --> bzip2、bunzip2**
  >
  > **.xz --> xz、unxz**



#### tar工具的常用选项

- **tar**  **集成备份工具**

  -  **—c :创建归档**

  - **—x :释放归档**

  - **—f: 指定归档文件名称**

  - **—z 、—j、—J :调用 .gz、.bz2、.xz 格式的工具进行处理**

  - **—t: 显示归档中的文件清单**

  - **—C : 指定释放路径**

    

### 备份与恢复操作

#### 制作tar备份包

- **使用 tar -c ... 命令**

  > **-tar -zcf  备份文件.tar.gz 被备份的文档......**
  >
  > **-tar  -jcf   备份文件.tar.bz2被备份的文档......**
  >
  > **-tar  -Jcf   备份文件.tar.xz备份的文档......**

  ```
  [root@svr7~]# tar -jcf /root/home.tar.bz2  /home
  [root@svr7~]# ls -lh /root/home.tar.bz2
  -rw-r--r--, 1 root root 1.9k Nov 11 16:41 /root/home.tar.bz2
  ```

  

#### 查看tar备份包内容

- **使用 tar -t  ... 命令**

  **-tar  - tf     备份文件,tar.gz**

  ```
  [root@svr7~]# tar -tf /root/home.tar.bz2
  home/
  home/student/
  home/student/.bash_logout
  home/student/.bash_profile
  ....
  ```

  

#### 从tar备份包恢复文档

- **使用 tar -x ... 命令**

  **-tar  -xf  备份文件.tar.gz  [-C  目标文件夹]**

  ```
  [root@svr7~]# rm -rf /home
  [root@svr7~]# tar -xf  /root/home.tar.bz2  -C /
  [root@svr7~]# ls -ld /home/
  drwxr-xr-x.5 root root 45 Nov 11 16:09 /home
  
  
  [root@svr7~]# tar -xf /root/home.tar.bz2 -C /tmp/
  tar: Removing leading '/' from member names
  
  [root@svr7~]# ls -ld /tmp/home/
  drwxr-xr-x.5 root root 45 Nov 11.16:09 /tmp/home/
  ```

  ![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_012.png)



### **重定向**

#### 重定向输出

- **将屏幕显示信息保存到文件**

  **——覆盖重定向：cmd > file**

  **——追加重定向：cmd >> file**

  ```
  [root@svr7~]# hostname > /opt/hn.txt
  [root@svr7~]# cat /opt/hn.txt
  server0.example.com
  [root@svr7~]# hostname >> /opt/hn.txt
  [root@svr7~]# cat /opt/hn.txt
  server0.example.com
  server0.example.com
  ```

### 管道操作

#### 管道传递

- **使用 | 管道 操作**

  **——将前一条命令的标准输出交给后一条命令处理**

  **——cmd1 | cmd2    [  | cmd3] ......**

  ```
  [root@svr7~]# ls --help | less
  ..
  [root@svr7~]# ifconfig | head -2
  ..
  [root@svr7~]# head -12 /etc/passwd | tail -5
  
  ```

###  **grep过滤包含指定字符串的行**

> **-v:取反过滤**
>
>  **^字符串:以字符串开头**
>
> **字符串$:以字符串开头结尾**
>
> **^$:匹配空行**

```
]# cat    /etc/default/useradd
]# grep    ^$   /etc/default/useradd    
]# grep  -v  ^$   /etc/default/useradd     #不要空行
 在Linux系统中，大多数配置文件以#开头的行，为注释行

]# grep  -v  ^#   /etc/default/useradd
显示有效配置(去除空行与注释行)
]# grep  -v  ^#   /etc/default/useradd    |    grep   -v  ^$
]# grep  -v  ^#  /etc/default/useradd   |    grep   -v   ^$  >  /opt/nsd03.txt
]# cat   /opt/nsd03.txt

]# grep  -v  ^#   /etc/login.defs
显示有效配置(去除空行与注释行)
]# grep  -v  ^#   /etc/login.defs    |    grep   -v  ^$
]# grep  -v  ^#  /etc/login.defs   |    grep   -v   ^$  >  /opt/nsd04.txt
]# cat   /opt/nsd04.txt

```



![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_018.png)



### find基本使用

#### 常用条件

- **根据预设的条件递归查找对应的文件**

  **——find [目录]  [条件1]**

  **——常用条件表示：**

  -  **-type 类型（f、d、l)**
  - **-name "文档名称“**
  - **-size + | - 文件大小 （K 、M、G）**
  - **-user   用户名**
  - **-mtime 修改时间**

  

### find高级使用



#### 处理查找的内容

- **操作方法：**

  - **find  [范围]   [条件]  -exec  处理命令  {}  \;**\ 

  -  **根据条件查找并处理结果**

    ```
    [root@svr7~]# find /boot -size +10M
    /boot/initramfs-2.6.32-431.e16.x86_64.img
    
    
    [root@svr7~]#  find /boot -size +10M -exec ls -lh {} \;
    -rw-------. 1 root root 17M 10月 21 15：10 /boot/initramfs-2.6.32-431.e16.x86_64.img
    ```

    

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_024.png)



### 命令模式操作

#### 光标跳转

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_026.png)



#### 复制/粘贴/删除

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_027.png)

#### 查找/撤销/保存

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_028.png)

### 末行模式操作

#### 保存、退出、文件操作

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_030.png)



#### 字符串替换

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_031.png)



#### 开关参数的控制

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY04/COURSE/LINUXNSD_V01ADMINDAY04_032.png)

###  **常见问题：交换文件产生   名称为:\*.swp**

> ```
> E325: 注意
> 
> 发现交换文件 "/opt/.c.txt.swp"
> 
> ​      所有者: root  日期: Fri Sep 4 17:22:51 2020
> 
> ​      文件名: /opt/c.txt
> 
> ​      修改过: 是
> 
> ​      用户名: root   主机名: localhost.localdomain
> 
> ​      进程 ID: 17881
> 
> 正在打开文件 "/opt/c.txt"
> 
>  **……..**
> 
> [root@localhost ~]# rm  -rf   /opt/.c.txt.swp  #手动删除交换文件
> 
> [root@localhost ~]# vim  /opt/c.txt
> ```

## 05：RPM软件包管理、Yum软件包仓库、命令补充

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY05/COURSE/LINUXNSD_V01ADMINDAY05_003.png)

### RPM包管理机制

#### 常见的软件封包类型

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY05/COURSE/LINUXNSD_V01ADMINDAY05_005.png)

#### RPM的含义

•    RPM Package Manager

由红帽公司提出，RedHat、SUSE等系列采用

建立集中数据库，记录软件包安装/卸载等变化信息，分析软件包依赖关系 

• RPM包文件名特征

–  软件名-版本信息.操作系统.硬件架构.rpm

 firefox-52.7.0-1.el7.centos.x86_64.rpm

#### 常见安装位置

- RPM包的一般安装位置（分散）

| **文件类别**         | **默认安装位置**                  |
| -------------------- | --------------------------------- |
| 普通执行程序         | /usr/bin/ 、/bin/                 |
| 服务器程序、管理工具 | /usr/sbin/ 、/sbin/               |
| 配置文件             | /etc/ 、/etc/软件名/              |
| 日志文件             | /var/log/、/var/log/软件名/       |
| 程序文档、man手册页  | /usr/share/doc/ 、/usr/share/man/ |

### 查询软件信息

#### 查询已安装的软件

- **查询已安装的RPM软件包的信息**

  **-格式： rpm -q[子选项] [软件名称]**

- **常用的子选项**
  - **-a : 列出已安装的所有软件包**
  - **-i : 查看指定软件的详细信息**
  - **-l : 查看指定软件的文件安装清单**

- ### 确认软件包的安装情况

  ```
  ]# rpm  -qa    #当前系统中所有已安装的软件包
  
  ]# rpm  -q   firefox    #查看firefox是否安装
  firefox-52.7.0-1.el7.centos.x86_64
  ]# rpm  -q   httpd    
  未安装软件包 httpd
  ]# rpm  -q   bash
  bash-4.2.46-30.el7.x86_64
  ```

- **了解软件包在详细安装信息**

```
]# rpm  -qi   firefox       #查询软件信息
]# rpm  -ql   firefox       #查询软件安装了哪些内容(安装清单)
]# rpm  -ql    firefox   |   less
```

- **查询某个目录/文件是哪个RPM包带来的**

  **–  格式：rpm -qf [文件路径]…**

  **–  即使目标文件被删除，也可以查询**

  ```
  [root@localhost ~]# which  vim   #查询命令对应的程序文件
  /usr/bin/vim
  [root@localhost ~]# rpm -qf  /usr/bin/vim
  vim-enhanced-7.4.160-4.el7.x86_64
  [root@localhost ~]# rpm -q vim-enhanced
  vim-enhanced-7.4.160-4.el7.x86_64
  ```

- **查询未安装软件包**

  **格式：rpm -q [子选项]  [RPM 包文件**

  **常用的子选项**

  > **-pi: 查看指定软件的详细信息**
  >
  > **-pl: 查看指定软件的文件安装清单**

```
]# rpm  -q   vsftpd     #查询vsftpd软件是否安装
未安装软件包 vsftpd 
]# ls /mnt/Packages/vsftpd-3.0.2-22.el7.x86_64.rpm

查询软件包的安装清单：
]# rpm -qpl  /mnt/Packages/vsftpd-3.0.2-22.el7.x86_64.rpm
查询软件包信息
]# rpm -qpi /mnt/Packages/vsftpd-3.0.2-22.el7.x86_64.rpm

```

#### 导入红帽签名信息（了解）

```
]# rpm  --import    /mnt/RPM-GPG-KEY-CentOS-7
查询软件包信息
]# rpm -qpi  /mnt/Packages/vsftpd-3.0.2-22.el7.x86_64.rpm
```

### 安装/卸载软件包

#### **安装**

- **安装RPM软件**

  **-格式：rpm -i RPM包文件**

- **辅助选项**

  **–   -v：显示细节信息**

  **–   -h：以#号显示安装进度**

  **–   --force：强制安装、覆盖安装**

  **–   --test：测试安装，不做真实安装动作**

```
]# rpm  -q   vsftpd        #查询当前的系统是否安装了该软件
未安装软件包 vsftpd 

]# rpm  -ivh  /mnt/Packages/vsftpd-3.0.2-22.el7.x86_64.rpm 
]# rpm  -q  vsftpd    #查询当前的系统是否安装了该软件
vsftpd-3.0.2-22.el7.x86_64

]# rpm -e vsftpd            #卸载软件
]# rpm -q vsftpd            #查询当前的系统是否安装了该软件
未安装软件包 vsftpd
```

#### **--force：强制安装、覆盖安装**

```
]# which   hostname
/usr/bin/hostname
]# rm   -rf   /usr/bin/hostname     
]# hostname
bash: hostname: 未找到命令...

]# rpm -qf   /usr/bin/hostname     #查看由哪个软件包产生
hostname-3.13-3.el7.x86_64

]# rpm  -ivh   --force   /mnt/Packages/hostname-3.13-3.el7.x86_64.rpm

```

#### **解决依赖关系**

> –  先安装/卸载要求的包
>
> 如果RPM包齐全但比较多，可以用通配符 *
>
> •   忽略依赖关系（不推荐）
>
> –  可能会导致软件运行异常
>
> –  辅助选项 --nodeps
>
> 常见依赖关系的报错：
>
> [root@localhost ~]# rpm -ivh /mnt/Packages/bind-chroot-9.9.4-61.el7.x86_64.rpm 
>
> 错误：依赖检测失败：bind = 32:9.9.4-61.el7 被 bind-chroot-32:9.9.4-61.el7.x86_64 需要

#### **卸载**

- **卸载RPM软件**

  **-格式 ： rpm -e 软件名.. ..**

  ```
  ]# rpm -e vsftpd
  ]# rpm -q vsftpd
  未安装软件包 vsftpd
  ```

  

### 构建Yum软件包仓库

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ADMIN/DAY05/COURSE/LINUXNSD_V01ADMINDAY05_024.png)

**作用：自动解决依赖关系安装软件**

**服务：自动解决依赖关系安装软件**

 

**服务端(本机): 1.众多的软件  2.仓库数据文件（repodata）**

​           **3.FTP协议  或  http 协议**    

**本地Yum仓库：服务端需要有光盘内容即可**

****

**客户端(本机)：指定服务端位置**

**–  仓库配置：/etc/yum.repos.d/*.repo**

**–  错误的文件会影响正确的文件**

 

#### **客户端文件配置内容：**

**–  [源名称] ：自定义名称，具有唯一性**

**–  name：本软件源的描述字串**

**–  baseurl：指定YUM服务端的URL地址**

**–  enabled：是否启用此频道**

**–  gpgcheck：是否验证待安装的RPM包**

**–  gpgkey：用于RPM软件包验证的密钥文件**

```
完整示例：
]# vim   /etc/yum.repos.d/mydvd.repo 
[nsd2008]
name=hahaxixi
baseurl=file:///mnt
enabled=1
gpgcheck=1        
gpgkey=file:///mnt/RPM-GPG-KEY-CentOS-7

]# ls    /etc/yum.repos.d/
]# mkdir     /etc/yum.repos.d/bak
]# mv   /etc/yum.repos.d/*.repo      /etc/yum.repos.d/bak
]# ls   /etc/yum.repos.d/
bak

]# vim     /etc/yum.repos.d/mydvd.repo
[nsd2008]                #仓库的名称
name=hahaxixi         #仓库描述信息
baseurl=file:///mnt   #指定服务端位置file://表示本地为服务端
enabled=1           #本文件启用
gpgcheck=0        #不检测红帽签名

]# yum  repolist      #列出仓库信息

```

####  **总结：本地Yum仓库构建方法**

**1.服务端：显示光盘的内容，挂载光驱设备**

**2.客户端：书写客户端配置文件，指定服务端位置**

**3.执行流程: yum命令--->/etc/yum.repos.d/*.repo--->baseurl=file:///mnt**

------



### Yum的使用

#### **安装软件**

```
[root@localhost ~]# yum -y install httpd
[root@localhost ~]# rpm -q httpd

[root@localhost ~]# yum -y install bind-chroot
[root@localhost ~]# rpm -q  bind-chroot

[root@localhost ~]# yum -y install sssd
[root@localhost ~]# rpm -q  sssd

[root@localhost ~]# yum -y install gcc
[root@localhost ~]# rpm -q  gcc

[root@localhost ~]# yum -y install  xorg-x11-apps
[root@localhost ~]# rpm -q  xorg-x11-apps

[root@localhost ~]# rpm  -ql   xorg-x11-apps   |   less
[root@localhost ~]# xeyes
```

#### **卸载软件**

```
[root@localhost ~]# yum   remove   gcc
[root@localhost ~]# yum   remove   httpd
```

#### **查询**

```
[root@localhost ~]# yum list  ftp    #查询仓库是否有ftp软件
可安装的软件包  #表示当前系统没有安装该软件
ftp.x86_64        0.17-67.el7         nsd2008
[root@localhost ~]# yum  list  httpd

[root@localhost ~]# yum  search  ftp   #包含ftp就匹配

]# yum   provides   /usr/bin/xeyes  
]# yum  provides  /etc/passwd  #仓库中那个软件包产生该文件
```

#### **清空缓存**

```
[root@localhost ~]# yum  clean   all
[root@localhost ~]# yum   repolist
```

### **命令补充**

#### **获取命令帮助**

> **方式一：命令  --help**
>
> ```
> [root@localhost ~]# cat  --help
> ```
>
> **方式二：man  命令**  
>
> ```
> [root@localhost ~]# man  cat    #按q退出
> [root@localhost ~]# man   passwd    #显示passwd命令帮助
> [root@localhost ~]# man  5  passwd
> ```

#### **历史命令**

##### **管理/调用曾经执行过的命令**

> –  history：查看历史命令列表
>
> –  history -c：清空历史命令
>
> –  !n：执行命令历史中的第n条命令
>
> –  !str：执行最近一次以str开头的历史命令

```
[root@svr7 ~]# vim  /etc/profile
HISTSIZE=1000      #默认记录1000条

[root@localhost ~]# history          #显示历史命令列表
[root@localhost ~]# history   -c    #清空历史命令
[root@localhost ~]# history                 
[root@localhost ~]# cat   /etc/redhat-release 
[root@localhost ~]# ls   /root
[root@localhost ~]# history

[root@localhost ~]# !cat  #指定最近一条以cat开头的历史命令
[root@localhost ~]# !ls  #指定最近一条以ls开头的历史命令
```

#### **du**, **统计文件的占用空间**

> **–  du [选项]... [目录或文件]...**
>
> **–  -s：只统计每个参数所占用的总空间大小**
>
> **–  -h：提供易读容量单位（K、M等）**

```
[root@localhost ~]# du  -sh   /root
[root@localhost ~]# du  -sh   /etc
[root@localhost ~]# du  -sh   /
```

#### **date，查看/调整系统日期时间**

> **–  date +%F、date +%R**
>
> **–  date +"%Y-%m-%d %H:%M:%S"**
>
> **–  date -s "yyyy-mm-dd HH:MM:SS"** 

```
]# date
]# date  -s    "2008-9-6   11:11:11"     #修改系统时间
]# date

]# date   -s    "2020-9-5   15:37:11"   
]# date

[root@localhost ~]# date   +%Y     #显示年
[root@localhost ~]# date   +%m   #显示月
[root@localhost ~]# date   +%d   #显示日期

[root@localhost ~]# date   +%H   #显示时
[root@localhost ~]# date   +%M   #显示分
[root@localhost ~]# date   +%S    #显示秒

[root@localhost ~]# date   +%F   #显示年-月-日
[root@localhost ~]# date   +%R   #显示时:分

```

#### **制作连接(链接)文件（制作快捷方式）**

> **格式：ln -s  /路径/源数据   /路径/快捷方式的名称   #软连接**

```
]# ln  -s    /etc/sysconfig/network-scripts/   /ns
]# ls   /
]# ls   -l   /ns    #查看快捷方式的信息

]# touch   /ns/haha.txt
]# touch   /ns/maohehaozi.txt
]# touch   /ns/shukehebeita.txt
]# ls   /etc/sysconfig/network-scripts/
```

> 软连接优势：可以针对目录与文件制作快捷方式，支持跨分区
>
> 软连接缺点：源数据消失，快捷方式失效

> **格式：ln   /路径/源数据   /路径/快捷方式的名称   #硬链接**
>
> 硬链接优势：源数据消失，快捷方式仍然有效
>
> 硬链接缺点：只能针对文件制作快捷方式，不支持支持跨分区

```
[root@localhost ~]# rm  -rf   /opt/*
[root@localhost ~]# echo  123   >   /opt/A.txt
[root@localhost ~]# ln  -s   /opt/A.txt    /opt/B.txt   #软连接
[root@localhost ~]# ls /opt/

[root@localhost ~]# ln    /opt/A.txt    /opt/C.txt   #硬链接
[root@localhost ~]# ls    /opt/
[root@localhost ~]# cat    /opt/B.txt 
[root@localhost ~]# cat    /opt/C.txt 

[root@localhost ~]# rm  -rf   /opt/A.txt 
[root@localhost ~]# ls   /opt/
[root@localhost ~]# cat  /opt/B.txt      #软连接失效
cat: /opt/B.txt: 没有那个文件或目录
[root@localhost ~]# cat   /opt/C.txt     #硬链接仍然有效
```

#### **zip归档工具，跨平台**

•   **归档+压缩操作: zip [-r]  备份文件.zip   被归档的文档...** 

[-r]: 被归档的数据有目录，必须加上此选项

```
]# zip   -r     /opt/abc.zip        /etc/passwd     /home
]# ls   /opt/
```

•   **释放归档+解压操作: unzip  备份文件.zip  [-d  目标文件夹]** 

```
]# mkdir   /nsd20
]# unzip       /opt/abc.zip       -d    /nsd20
]# ls   /nsd20
]# ls   /nsd20/etc/
]# ls   /nsd20/home/
```

------

## 06:用户管理、组账号管理、计划任务

### 用户简介

> **用户账户**：1.可以登陆操作系统 2.资源访问控制(不同的人，有不同的权限)
>
> 组账户:方便管理众多的用户
>
> **唯一标识**：UID   GID
>
> **管理员root的UID永远为0，普通用户UID从1000开始**
>
> **Linux一个用户必须至少属于一个组**
>
> **组账户分类**：基本组、附加组(从属组)
>
>   基本组：由系统创建，与用户同名
>
>   附加组(从属组)：由管理员创建，由管理员管理组成员

```
[root@localhost ~]# useradd  tom
```

> **•   本地账户的数据文件**
>
> ​	**–  /etc/passwd、/etc/shadow**
>
> ​	**–  /etc/group、/etc/gshadow**

#### **/etc/passwd**，保存用户帐号的基本信息

> –  每个用户记录一行，以：分割为7个字段
>
> ```
> [root@localhost ~]# head -1 /etc/passwd
> root:x:0:0:root:/root:/bin/bash
> ```
>
> **用户名:密码占位符:UID:基本的GID:用户描述信息:家目录:解释器**

### 用户账号创建

**•    useradd命令**

**格式：useradd [选项]... 用户名**

**•    常用命令选项**

**-u：指定 UID 标记号**

**-d：指定宿主目录（家目录），缺省为 /home/用户名**

**-G：指定所属的附加组**

**-s：指定用户的登录解释器**



#### **-u：指定 UID 标记号**

```
[root@localhost ~]# useradd    nsd01
[root@localhost ~]# grep   nsd    /etc/passwd

[root@localhost ~]# ls   /home/
[root@localhost ~]# useradd   nsd02
[root@localhost ~]# grep   nsd   /etc/passwd

[root@localhost ~]# useradd  -u   1400   nsd03
[root@localhost ~]# grep   nsd    /etc/passwd
[root@localhost ~]# useradd    nsd04
[root@localhost ~]# id  nsd01   #显示用户基本信息
```

#### **-d：指定宿主目录（家目录），缺省为 /home/用户名**

```
[root@localhost ~]# ls /home
[root@localhost ~]# useradd   -d   /opt/stu    nsd05 
[root@localhost ~]# ls   /opt/
[root@localhost ~]# grep    nsd05   /etc/passwd

[root@localhost ~]# useradd   -d    /opt/aa     nsd06
[root@localhost ~]# id   nsd06
[root@localhost ~]# grep    nsd06    /etc/passwd
[root@localhost ~]# ls    /opt/
```

#### **-G：指定所属的附加组**

```
[root@localhost ~]# groupadd tarena       #创建组
[root@localhost ~]# useradd -G  tarena  nsd07
[root@localhost ~]# id nsd07
```

#### **-s：指定用户的登录解释器**

```
/sbin/nologin：禁止用户登录系统
[root@localhost ~]# useradd -s /sbin/nologin   nsd08
[root@localhost ~]# grep nsd08 /etc/passwd
[root@localhost ~]# useradd -s /sbin/nologin   nsd09
[root@localhost ~]# grep nsd09 /etc/passwd
```

### **用户账号属性修改**

> **•   usermod命令**
>
> **–  格式：usermod [选项]... 用户名**
>
> •   **常用命令选项**
>
> **–  -l：更改用户帐号的登录名称**
>
> **–  -u：用户id**
>
> **–**  **-s：登录解释器**
>
>  
>
> **–  -d：家目录路径**
>
> **–  -G：附加组   //重置附加组**

#### **修改用户的名字**

```
[root@localhost ~]# useradd  nsd10
[root@localhost ~]# id nsd10
[root@localhost ~]# grep nsd10   /etc/passwd

[root@localhost ~]# usermod -l abc10  nsd10
[root@localhost ~]# id nsd10
id: nsd10: no such user
[root@localhost ~]# id abc10
[root@localhost ~]# grep abc10 /etc/passwd
```

#### **修改用户的UID与登录解释器** 

```
]# id   abc10
]# grep   abc10    /etc/passwd
]# usermod    -u   1500    -s    /sbin/nologin    abc10
]# grep   abc10    /etc/passwd
```

#### **修改用户家目录，但是不会新建用户家目录**

```
[root@localhost ~]# useradd nsd11
[root@localhost ~]# grep nsd11 /etc/passwd
[root@localhost ~]# ls /home/
[root@localhost ~]# usermod  -d  /opt/xixidi  nsd11
[root@localhost ~]# grep nsd11 /etc/passwd
```

#### **修改用户，重置附加组**

```
[root@localhost ~]# useradd nsd12
[root@localhost ~]# id nsd12
[root@localhost ~]# usermod  -G  tarena  nsd12
[root@localhost ~]# id nsd12
uid=1502(nsd12) gid=1502(nsd12) 组=1502(nsd12),1404(tarena)

[root@localhost ~]# groupadd   tmooc     #创建tmooc组
[root@localhost ~]# usermod   -G   tmooc   nsd12
[root@localhost ~]# id  nsd12
uid=1502(nsd12) gid=1502(nsd12) 组=1502(nsd12),1503(tmooc)

```



### **设置用户的密码**

####  **方式一：交互式的设置**

```
[root@localhost ~]# passwd   nsd01  #设置nsd01密码
更改用户 nsd01 的密码 。
新的 密码：                  #输入新的密码
无效的密码： 密码少于 8 个字符
重新输入新的 密码：     #重新输入密码
passwd：所有的身份验证令牌已经成功更新。
[root@localhost ~]# su  -  nsd01     #临时切换用户身份
[nsd01@localhost ~]$ passwd 
更改用户 nsd01 的密码 。
为 nsd01 更改 STRESS 密码。
（当前）UNIX 密码：         #输入旧密码
新的 密码：                        #输入新的密码
重新输入新的 密码：           #重新输入密码
passwd：所有的身份验证令牌已经成功更新。
[nsd01@localhost ~]$ exit    #回到root

```

 **方式二：非交互式的设置**

```
]# echo   123456    |   passwd   --stdin   nsd01
]# echo   abc    |    passwd   --stdin     nsd01
]# echo   redhat    |    passwd   --stdin    nsd01

```

####   **/etc/shadow**，**保存密码字串/有效期等信息**

> 每个用户记录一行，以：分割为9个字段

```

[root@localhost ~]# grep  nsd01  /etc/shadow
nsd01:$6$5UmdkQ0Y$VwyszJIIM0KWMlzyZsf6ZETANNcZBpujmyN38sEzSIn5A/7q431C5kNDQt4aivOFVIyOb6erMLx42DEiDa4Vo.:18512:0:99999:7:::
用户名:密码加密字符串:上一次修改密码的时间

```

> 上一次修改密码的时间:从1970-1-1到达上一次修改密码时间，经历的天数
>
> 字段1：用户帐号的名称
>
> 字段2：加密后的密码字符串
>
> 字段3：上次修改密码的时间
>
> 字段4：密码的最短有效天数，默认0
>
> 字段5：密码的最长有效天数，默认99999
>
> 字段6：密码过期前的警告天数，默认7
>
> 字段7：密码过期后多少天禁用此用户账号
>
> 字段8：帐号失效时间，默认值为空
>
> 字段9：保留字段（未使用）



### 用户家目录的配置文件

#### •   用户家目录下配置文件来源

> **–  新建用户时，根据 /etc/skel 模板目录复制**

```
[root@localhost ~]# touch  /etc/skel/haha.txt

[root@localhost ~]# mkdir  /etc/skel/xixi

[root@localhost ~]# ls  -A  /etc/skel/
[root@localhost ~]# useradd   nsd15
[root@localhost ~]# ls   -A   /home/nsd15

```

####  •   **主要的初始配置文件**

> **–  ~/.bash_profile：每次登录时执行，定义初始化变量**
>
> **–  ~/.bashrc：每次开启新的终端时执行，定义永久的别名**

```
[root@localhost ~]# useradd  nsd16

[root@localhost ~]# vim  /home/nsd16/.bashrc

alias  hn='hostname'

[root@localhost ~]# vim  /root/.bashrc

alias  haha='echo  hahaxixi'
```

> **开启新的终端进行验证**

```
[root@localhost ~]# haha

[root@localhost ~]# su - nsd16

[nsd16@localhost ~]$ hn

[nsd16@localhost ~]$ exit
```

####  **全局配置文件：/etc/bashrc、/etc/profile(定义初始变量)**

```
[root@localhost ~]# vim  /etc/bashrc  #定义所有用户都生效

alias  xixi='echo   hehelele'
```

> **开启新的终端进行验证**

```
[root@localhost ~]# xixi

hehelele

[root@localhost ~]# su  -  nsd16

[nsd16@localhost ~]$ xixi

hehelele

[nsd16@localhost ~]$ exit
```

### **用户家目录的删与查**

> **•   userdel命令**
>
> **–  格式：userdel [-r] 用户名**
>
> **–  添加 -r 选项，宿主目录(家目录)/用户邮件也一并删除**

```
[root@localhost ~]# userdel    nsd16    
[root@localhost ~]# id  nsd16
id: nsd16: no such user
[root@localhost ~]# ls   /home/

[root@localhost ~]# userdel  -r   nsd15
[root@localhost ~]# id  nsd15
id: nsd15: no such user
[root@localhost ~]# ls  /home
```

### 组账号管理

#### **/etc/group，保存组帐号的基本信息**

> –  **每个组记录一行，以：分割为4个字段**

```
[root@localhost ~]# groupadd  stugrp    #创建stugrp组
[root@localhost ~]# grep  stugrp    /etc/group
stugrp:x:1506:
```

**组名:组的密码占位符:组的GID:本组成员列表**

```
[root@localhost ~]# useradd   harry
[root@localhost ~]# useradd   natasha
[root@localhost ~]# useradd   kenji
[root@localhost ~]# useradd   kaka
```

####  **gpasswd命令管理组成员**

> **–  格式：gpasswd [选项]... 组名**
>
> **•   常用命令选项**
>
> **–  -a：添加组成员，每次只能加一个**
>
> **–  -d： 删除组成员，每次只能删一个**
>
> **–  -M：定义组成员用户列表，可设置多个**
>
> **–  -A：定义组管理员列表**

```
]# grep stugrp /etc/group         #查看stugrp组基本信息
]# gpasswd -a natasha stugrp    #加入组成员
]# grep stugrp /etc/group

]# gpasswd -a  harry   stugrp      #加入组成员
]# grep stugrp /etc/group

]# gpasswd -M  kaka,kenji   stugrp     #定义组成员列表
]# grep stugrp   /etc/group

]# gpasswd  -d  kenji  stugrp      #删除组成员
]# grep  stugrp   /etc/group
 
]# gpasswd   -M  ''   stugrp      #定义组成员列表为空
]# grep  stugrp   /etc/group

```

#### **/etc/gshadow，保存组帐号的管理信息**

> **–  每个组记录一行，以：分割为4个字段**

```
]# grep  stugrp   /etc/gshadow
stugrp:!::

组名:组的密码加密字符串:组的管理员列表:组的成员列表
```

#### **-A：定义组管理员列表**

```
# grep   stugrp   /etc/gshadow   #查看组的管理信息
]# su - natasha
]$ gpasswd  -a   harry   stugrp
gpasswd：没有权限。
]$ exit
]# gpasswd  -A  natasha   stugrp   #定义组管理员为natasha
]# grep  stugrp    /etc/gshadow
]# su  -   natasha 
]$ gpasswd  -a   harry   stugrp
]$ exit

]# gpasswd   -A ''   stugrp          #删除组管理员
]# grep stugrp /etc/gshadow
stugrp:!::
]# gpasswd  -A    natasha,harry  stugrp   #定义多个组管理员
]# grep   stugrp   /etc/gshadow


```

#### **groupdel命令**

> **–  格式：groupdel  组名**
>
> **–  删除的目标组不能是用户的基本组**

```
[root@localhost ~]# groupdel  stugrp
[root@localhost ~]# grep  stugrp   /etc/group

```

### 计划任务

> **•   用途:按照设置的时间间隔为用户反复执行某一项固定的系统任务**
>
> **•   软件包：cronie、crontabs**
>
> **•   系统服务：crond**
>
> **•   日志文件：/var/log/cron**
>
>  
>
> **•   使用 crontab 命令**
>
> **–  编辑计划任务：crontab -e [-u 用户名]**
>
> **–  查看计划任务：crontab -l [-u 用户名]**
>
> **–  清除计划任务：crontab -r [-u 用户名]**
>
>  
>
> **•   周期性计划任务书写格式**
>
> 分  时   日  月  周    任务命令行（绝对路径）
>
> \*    *    *   *   *      每分钟执行一次
>
> 30  23   *   *   *      每天晚上11点30分执行一次
>
> 30  23   *   *   5     每周的周五晚上11点30分执行一次
>
> 30  23   *   *   1-5   周一至周五晚上11点30分执行一次
>
> 30  23   *   *   1,5    周一和周五晚上11点30分执行一次
>
> 30  23   1   *   1     每月一号或者每周的周一，晚上11点30分执行一次
>
>  
>
> */5   *    *   *   *       每隔5分钟执行一次
>
> 1   */2    *   *   *       每隔两个小时执行一次
>
>  
>
> *：匹配范围内任意时间
>
> ,：分隔多个不连续的时间点
>
> -：指定连续时间范围
>
> /n：指定时间频率，每n ...

**每分钟记录当前系统的时间，写入到/opt/time.txt**

```
[root@localhost ~]# date
[root@localhost ~]# date   >>   /opt/time.txt
[root@localhost ~]# cat   /opt/time.txt
 
[root@localhost ~]# crontab  -e  -u  root
*    *    *    *    *    date   >>  /opt/time.txt

[root@localhost ~]# cat   /opt/time.txt

```



------

# Admin-周考

1、(单选题)UNIX诞生日是什么时候()
A.1973年 
B.1969年年底 
C.1970年1月1号 
D.1980年 
【正确答案】C
【答案解析】无

2、(单选题)以下（）命令可以列出/etc/文件夹本身的属性 
A.ls  -lA    /etc/  
B.ls  -ld   /etc/ 
C.ls  -A  /etc/ 
D.ls  -lh    /etc/ 
【正确答案】B
【答案解析】

3、(单选题)关于mount挂载，下列描述正确的是（     ）
A.挂载后只能重启卸载 
B.挂载点必须是一个文件 
C.挂载点必须是一个目录 
D.一个设备不可以有多个挂载点 
【正确答案】C
【答案解析】

4、(单选题)（）目录存放设备文件
A./root 
B./etc 
C./dev 
D./opt 
【正确答案】C
【答案解析】

5、(单选题)/etc/passwd文件以冒号分割了7个字段，第7个字段为（）
A.用户名 
B.用户登录解释器 
C.用户家目录 
D.用户UID 
【正确答案】B
【答案解析】

6、(单选题)关于find，下列描述正确的是（   ）
A.-mtime按照文件的修改时间查找 
B.-type l代表查找文件类型是文件 
C.-name选项不可以用通配符 
D.find会查找文本文件内容 
【正确答案】A
【答案解析】

7、(单选题)（）文件存放组的基本信息
A./etc/gpasswd 
B./etc/group 
C./etc/gshadow 
D./etc/passwd 
【正确答案】B
【答案解析】无

8、(单选题)（）命令可以创建用户
A.groupadd 
B.usermod 
C.passwd 
D.useradd 
【正确答案】D
【答案解析】无

9、(单选题)Linux中默认的解释器程序为（）
A./bin/nologin 
B./bin/bash 
C./bin/csh 
D./bin/login 
【正确答案】B
【答案解析】无

10、(单选题)如何查看当前已设置的所有别名（）
A.ls 
B.lsalias 
C.alias 
D.unalias 
【正确答案】C
【答案解析】无

11、(单选题)Linux中编写周期性计划任务，时间的格式（）
A.分 时  日  周   月 
B.分 时  月  日   周 
C.时  分  日  月  周 
D.分 时  日  月  周 
【正确答案】D
【答案解析】无

12、(单选题)命令行提示符（）符号代表当前登录身份为管理员
A.] 
B.# 
C.* 
D.$ 
【正确答案】B
【答案解析】无

13、(单选题)useradd命令指定附加组选项为（）
A.-G 
B.-g 
C.-u 
D.-s 
【正确答案】A
【答案解析】无

14、用户存放密码信息配置文件为（）
A./etc/fstab 
B./etc/crontab 
C./etc/shadow 
D./etc/passwd 
【正确答案】C
【答案解析】

15、(单选题)使用 tar 工具制作/root/backup.tar.bz2 的归档文件，其中包含 /usr/local 目录中的内容，该命令为（）
A.tar  -jxf  /root/backup.tar.bz2   /usr/local 
B.tar  -zcf  /root/backup.tar.bz3   /usr/local 
C.tar  -Jcf  /root/backup.tar.bz4 
D.tar  -jcf  /root/backup.tar.bz2   /usr/local 
【正确答案】D
【答案解析】无

16、(单选题)关于Yum客户端配置文件描述正确的是（）
A.以上说法均不正确 
B.只要保证有一个配置文件正确即可 
C.文件结尾必须是.rope 
D.存放路径为/etc/yum.repo.d 
【正确答案】A
【答案解析】无

17、(单选题)（）命令可以显示/etc/passwd文件中以root开头的行
A.grep root$ /etc/passwd 
B.grep  -i root /etc/passwd 
C.grep root /etc/passwd 
D.grep ^root /etc/passwd 
【正确答案】D
【答案解析】无

18、(单选题)请显示/etc/login.defs文件有效信息，该命令是()
A.grep -v ^#   |   grep  -v  ^$  /etc/login.defs 
B.grep -v  ^# /etc/login.defs  |   grep  -v   ^$ 
C.grep  ^# /etc/login.defs  |   grep  -v  ^$ 
D.grep -v ^# /etc/login.defs  |   grep    ^$ 
【正确答案】B
【答案解析】无

19、(单选题)查看CPU信息命令是（）
A.ifconfig 
B.hostname 
C.uname  -r 
D.lscpu 
【正确答案】D
【答案解析】无

20、(单选题)利用find查找/boot目录下大于300k并且必须是文件，拷贝到/opt
该如何操作（）
A.find  /boot  -size  +300k  -type  f  -exec  cp  -r  {}   /opt  \; 
B.find  /boot  -size  +300k  -type  f  -exec  cp  -r  {}   /opt  \ 
C.find  /boot  -size  +300k  -type  d -exec  cp  -r  {}   /opt  \; 
D.find  /boot  -size  +300k  -type  f  -exec  cp  -r  {}   /opt  \: 
【正确答案】A
【答案解析】无

21、(单选题)如何添加用户harry到组tarena中()
A.groupadd  -a  tarena   harry   
B.gpasswd  -a  harry  tarena 
C.groupadd  -a  harry  tarena 
D.gpasswd  -a  tarena  harry 
【正确答案】B
【答案解析】无

22、(多选题)快捷键（）可以粘贴上一个命令的参数
A.Esc + . 
B.Ctrl +  l 
C.Alt + . 
D.Ctrl + c 
【正确答案】A,C
【答案解析】无

23、(多选题)如何验证一个用户是否存在（）
A.查询/etc/default/useradd内容 
B.查询/etc/passwd内容 
C.查看/home内容 
D.id命令 
【正确答案】B,D
【答案解析】无

24、(多选题)在执行mount  /dev/cdrom  /rhel7/dvd命令，执行不成功，原因有哪些（）
A.挂载点不存在 
B.设备不存在 
C.光盘未放入光驱设备 
D.参数书写颠倒 
【正确答案】A,B,C
【答案解析】无

25、(多选题)去往管理员家目录，操作方式有哪些（）
A.cd root 
B.cd  /home 
C.cd  ~root 
D.cd  /root 
【正确答案】C,D
【答案解析】无





# ENGINEER

## 01：基本权限和归属、附加权限、ACL策略管理

### 权限和归属关系

- #### 基本权限

  > **–  读取：允许查看内容-read 利用r表示**
  >
  > **–  写入：允许修改内容-write 利用w表示**
  >
  > **–  可执行：允许运行和切换-excute 利用x表示**

- #### 对于文本文件

  >  **读取权限(r)：cat、head、tail、less、grep**
  >
  >   **写入权限(w)：vim（保存退出）、>、>>**
  >
  > **可执行权限(x)：Shell脚本、Python脚本**

- #### 归属关系

  > **–  所有者：拥有此文件/目录的用户-user 利用u表示**
  >
  > **–  所属组：拥有此文件/目录的组-group 利用g表示**
  >
  > **–  其他用户：除所有者、所属组以外的用户-other 利用o表示**

- #### 执行 ls -l或ls  -ld命令查看文件/目录权限

  > **以-开头：表示文本文件**
  >
  >  **以d开头：表示目录**
  >
  >  **以l开头:快捷方式或者链接文件**

```
[root@A ~]# ls  -l   /etc/shadow
[root@A ~]# ls  -l   /etc/passwd
[root@A ~]# ls  -ld   /etc/
[root@A ~]# ls  -ld   /root
[root@A ~]# ls  -ld   /home/zhangsan
[root@A ~]# ls  -ld   /tmp     #默认具备附加权限的目录

```



### 修改权限

#### **chmod命令**

> **–**  **格式：chmod [ugoa] [+-=] [rwx]   文件...**

- 常用命令选项

> **–  -R：递归修改权限**

```
[root@A /]# mkdir /nsd01
[root@A /]# ls -ld /nsd01

[root@A /]# chmod u-w /nsd01        #修改所有者权限
[root@A /]# ls -ld /nsd01

[root@A /]# chmod   u+w   /nsd01       #修改所有者权限
[root@A /]# ls -ld  /nsd01
[root@A /]# chmod   g=rwx   /nsd01    #修改所属组权限
[root@A /]# ls -ld  /nsd01

[root@A /]# chmod u=rwx,g=rx,o=---   /nsd01
[root@A /]# ls -ld /nsd01

[root@A /]# chmod  a=rwx    /nsd01     #赋予所有人rwx权限
[root@A /]# ls -ld /nsd01

[root@A /]# mkdir  -p    /opt/aaa/bbb/ccc
[root@A /]# ls -R   /opt/aaa

[root@A /]# chmod  -R   o=---   /opt/aaa    #递归设置权限
[root@A /]# ls  -ld   /opt/aaa
[root@A /]# ls  -ld   /opt/aaa/bbb/
[root@A /]# ls  -ld   /opt/aaa/bbb/ccc/

```



#### **Linux 判断用户具备的权限**

> **1.首先判断，用户对于该数据，处于的身份(角色)**
>
> **2.查看数据，相应身份的权限位置，权限内容**

•    **用户对于目录具备权限**

   **读取权限(r)：可以查看目录内容**

   **写入权限(w)：可以新建、删除、改名,目录的内容，对目录本身没有修改权限**

   **可执行权限(x)：可以进入切换到该目录下(一位用户能否切换到一个目录只和x执行权限有**关) 



#### **案例1：设置基本权限**

##### 1）以root身份新建/nsddir1/目录，在此目录下新建readme.txt文件

```
[root@localhost ~]# mkdir /nsddir1

[root@localhost ~]# echo 123456 > /nsddir1/readme.txt

[root@localhost ~]# cat /nsddir1/readme.txt
```

##### 2）使用户zhangsan能够修改readme.txt文件内容

```

[root@localhost ~]# chmod  o+w  /nsddir1/readme.txt
```

##### 3）使用户zhangsan不可以修改readme.txt文件内容

```
[root@localhost ~]# chmod  o-w  /nsddir1/readme.txt
```

##### 4）使用户zhangsan能够在此目录下创建/删除子目录

```
[root@localhost ~]# chmod  o+w  /nsddir1/

[root@localhost ~]# ls  -ld  /nsddir1/
```

##### 5）调整此目录的权限，使任何用户都不能进入，然后测试用户zhangsan是否还能修改readme.txt（测试结果不能，对父目录没有权限）

```
[root@localhost ~]# chmod  a-x  /nsddir1/
```

##### 6）为此目录及其下所有文档设置权限 rwxr-x---

```
[root@localhost ~]# chmod -R u=rwx,g=rx,o=--- /nsddir1/
```



#### **权限位的8进制数表示**

> **r、w、x分别对应4、2、1，后3组分别求和**

| **分组** |   User权限    |  Group权限  |  Other权限  |
| :------: | :-----------: | :---------: | :---------: |
| **字符** | **r   w   x** | **r  -  x** | **r  -  x** |
| **数字** |  **4  2  1**  | **4  0  1** | **4  0  1** |
| **求和** |     **7**     |    **5**    |    **5**    |

```
[root@A /]# mkdir /nsd03
[root@A /]# ls -ld  /nsd03
[root@A /]# chmod  700  /nsd03
[root@A /]# ls  -ld   /nsd03

[root@A /]# chmod  007  /nsd03
[root@A /]# ls  -ld   /nsd03

[root@A /]# chmod  750  /nsd03
[root@A /]# ls  -ld   /nsd03

```

#### 新建文件/目录的默认权限

> **–  一般文件默认均不给 x 执行权限**
>
> **–  其他取决于 `umask` 设置**
>
> **–  目录默认的权限为755，文件的默认权限为644**

```
[root@A /]# umask 
0022
[root@A /]# umask 077      #修改umask值
[root@A /]# umask 
0077
[root@A /]# mkdir /nsd05
[root@A /]# ls -ld /nsd05
drwx------. 2 root root 6 9月   8 14:17 /nsd05
[root@A /]# umask 022

```



### **修改归属关系**

- **chown命令**

> **–  chown 属主 文件...**
>
> **–  chown 属主:属组 文件...**
>
> **–  chown :属组 文件...**

- **常用命令选项**

> **–  -R：递归修改归属关系**

```
[root@A /]# mkdir   /nsd07
[root@A /]# ls -ld   /nsd07
[root@A /]# groupadd    tmooc    #创建tmooc组

[root@A /]# chown    zhangsan:tmooc      /nsd07
[root@A /]# ls -ld /nsd07

[root@A /]# chown   lisi     /nsd07     #单独修改所有者
[root@A /]# ls   -ld   /nsd07 
[root@A /]# chown   :root   /nsd07     #单独修改所属组
[root@A /]# ls -ld    /nsd07

```

#### Linux 判断用户具备的权限     匹配即停止原则

> **1.用户对于该数据处于的身份(角色)   所有者 > 所属组 >其他人**
>
> **2.查看数据，相应身份的权限位置，权限内容**

#### **案例2：归属关系练习**  

##### 1）利用root的身份新建/tarena目录，并进一步完成下列操作

```
[root@localhost ~]# mkdir /tarena
```

##### 2）将/tarena属主设为gelin01，属组设为tmooc组 

```
[root@localhost ~]# useradd  gelin01

[root@localhost ~]# groupadd  tmooc

[root@localhost ~]# chown  gelin01:tmooc   /tarena
```

##### 3）使用户gelin01对此目录具有rwx权限，除去所有者与所属组之外的用户对此目录无任何权限

```
[root@localhost ~]# chmod o=--- /tarena
```

##### 4）使用户gelin02能进入、查看此目录

```
[root@localhost ~]# useradd gelin02

[root@localhost ~]# gpasswd -a gelin02 tmooc 
```

##### 5）将gelin01加入tmooc组，将tarena目录的权限设为450，测试gelin01用户能否进入此目录

```
[root@localhost ~]# gpasswd -a gelin01 tmooc 

[root@localhost ~]# chmod 450 /tarena
```



#### 案例3：   实现lisi用户可以读取/etc/shadow文件内容，您有几种办法？

1. 利用其他人

```
[root@A /]# chmod o+r  /etc/shadow 
```

2. 利用所属组

```
[root@A /]# chown  :lisi  /etc/shadow 

[root@A /]# chmod  g+r  /etc/shadow
```

3. 利用所有者

```
[root@A /]# chown lisi  /etc/shadow

[root@A /]# chmod  u+r  /etc/shadow
```

4. 利用ACL策略

```
[root@A /]# setfacl -m u:lisi:r  /etc/shadow 
```



### 附加权限（特殊权限）

#### **粘滞位，Sticky Bit 权限**

> –  占用其他人（Other）的 x 位
>
> –  显示为 t 或 T，取决于其他人是否有 x 权限
>
> –  适用于目录，用来限制用户滥用写入权
>
> –  在设置了粘滞位的文件夹下，即使用户有写入权限，也不能删除或改名其他用户文档

```
[root@A /]# mkdir   /home/public
[root@A /]# chmod   777   /home/public
[root@A /]# ls -ld   /home/public

[root@A /]# chmod  o+t   /home/public
[root@A /]# ls  -ld   /home/public

```

#### **SGID 权限**

> –  占用属组（Group）的 x 位
>
> –  显示为 s 或 S，取决于属组是否有 x 权限
>
> –  对目录有效
>
> –  在一个具有SGID权限的目录下，<u>***新建***</u>  的文档会<u>***自动继承***</u>此目录的属组身份

```
[root@A /]# mkdir /nsd10
[root@A /]# ls -ld /nsd10

[root@A /]# chown   :tmooc    /nsd10
[root@A /]# ls   -ld   /nsd10

[root@A /]# mkdir  /nsd10/abc01
[root@A /]# ls -ld  /nsd10/abc01

[root@A /]# chmod  g+s    /nsd10       #赋予SetGID权限
[root@A /]# ls    -ld    /nsd10
[root@A /]# mkdir   /nsd10/abc02
[root@A /]# ls   -ld    /nsd10/abc02

[root@A /]# touch    /nsd10/1.txt
[root@A /]# ls   -l   /nsd10/1.txt

```

> groupadd  caiwu
>
> chown  :caiwu /bjtt
>
> chmod  g+s  /bjtt
>
> /bjtt： o= ---
>
>  /bjtt/yg-2020-9-8.txt
>
>  /bjtt/yg-2020-9-9.txt
>
>  /bjtt/yg-2020-9-10.txt

### ACL策略管理（ACL权限）

#### **acl 访问策略**

> –  **<u>*能够对个别用户、个别组设置独立的权限*</u>**
>
> –  大多数挂载的EXT3/4、XFS文件系统默认已支持

**•   setfacl命令**

> –  格式：setfacl [选项] u:用户名:权限 文件...
>
> ​            setfacl [选项] g:组名:权限 文件...

•   **常用命令选项**

> –  -m：定义一条ACL策略
>
> –  -x：清除指定的ACL策略
>
> –  -b：清除所有已设置的ACL策略
>
> –  -R：递归设置ACL策略

```
[root@A /]# mkdir /nsd11
[root@A /]# chmod 770 /nsd11
[root@A /]# ls -ld /nsd11

[root@A /]# su - lisi
[lisi@A ~]$ cd /nsd11
-bash: cd: /nsd11: 权限不够
[lisi@A ~]$ exit

[root@A /]# setfacl   -m   u:lisi:rx     /nsd11   #设置ACL策略
[root@A /]# getfacl   /nsd11                        #查看ACL策略
[root@A /]# su  -  lisi
[lisi@A ~]$ cd     /nsd11
[lisi@A nsd11]$  pwd
[lisi@A nsd11]$   exit
[root@A /]#

```

#### **将某个用户拉黑（制作黑名单）**

```
[root@A /]# ls -ld  /home/public/
drwxrwxrwt. 2 root root 41 9月   8 15:53 /home/public/
[root@A /]# setfacl  -m   u:lisi:---   /home/public

```



#### **setfacl 命令练习**

```
[root@A /]# mkdir /nsd12
[root@A /]# setfacl -m  u:dc:rwx    /nsd12
[root@A /]# setfacl -m  u:zhangsan:rx   /nsd12
[root@A /]# setfacl -m  u:lisi:rwx   /nsd12
[root@A /]# setfacl -m  u:tom:rwx   /nsd12

[root@A /]# getfacl  /nsd12           #查看ACL策略
[root@A /]# setfacl -x  u:zhangsan  /nsd12  #删除指定ACL
[root@A /]# getfacl  /nsd12
[root@A /]# setfacl -b  /nsd12         #清除所有ACL策略
[root@A /]# getfacl  /nsd12

```



#### **-R : 递归设置 ACL 策略**

```
[root@A /]# ls  -R   /opt/aaa
/opt/aaa:
bbb
/opt/aaa/bbb:
ccc
/opt/aaa/bbb/ccc:
[root@A /]# setfacl  -Rm   u:lisi:rx   /opt/aaa
[root@A /]# getfacl   /opt/aaa
[root@A /]# getfacl   /opt/aaa/bbb
[root@A /]# getfacl   /opt/aaa/bbb/ccc

```



### **课后习题**

#### 案例1：chmod权限设置

  1）以root用户新建/nsddir/目录，在该目录下新建文件readme.txt

```
[root@Localhost ~]# mkdir /nsddir/
[root@Localhost ~]# touch /nsddir/readme.txt
```

  2）使用户zhangsan能够在/nsddir/目录下创建/删除子目录

```
[root@Localhost ~]# useradd zhangsan 
[root@Localhost ~]# chmod o+w /nsddir/
[root@localhost ~]# su -zhangsan
[zhangsan@localhost ~]$ mkdir /nsddir/zhangsan
[zhangsan@localhost ~]$ ls /nsddir
[zhangsan@localhost ~]$ exit
```

  3）使用户zhangsan能够修改/nsddir/readme.txt文件的容

```
[root@Localhost ~]# chmod o+w /nsddir/readme.txt
[zhangsan@localhost ~]$ echo xixi >> /nsddir/readme.txt
[zhangsan@localhost ~]$ cat /nsddir/readme.txt
[zhangsan@localhost ~]$ exit
```

#### 案例2：chown归属设置

  1）新建/tarena1目录

​     a）将属主设为gelin01，属组设为tarena组

```
[root@Localhost ~]# mkdir /tarena1
[root@Localhost ~]# useradd gelin01
[root@Localhost ~]# groupadd tarena
[root@Localhost ~]# chown gelin01:tarena /tarena1 
```

​     b）使用户gelin01对此目录具有rwx权限，其他人对此目录无任何权限

```
[root@Localhost ~]# ls -ld /tarena1
[root@Localhost ~]# chmod o=--- /tarena1
[root@Localhost ~]# ls -ld /tarena1
```

  2）使用户gelin02能进入、查看/tarena1文件夹（提示：将gelin02加入所属组）

```
[root@Localhost ~]# useradd gelin02
[root@Localhost ~]# gpasswd -a gelin02 tarena
[root@Localhost ~]# id gelin02
[root@Localhost ~]# su-gelin02
[gelin02@Localhost ~]# cd /tarena1
[gelin02@Localhost ~]# ls
[gelin02@Localhost ~]# exit
```

  3）新建/tarena2目录

​     a）将属组设为tarena

```
[root@Localhost ~]# mkdir /tarena2
[root@Localhost ~]# chown :tarena /tarena2
```

​     b）使tarena组的任何用户都能在此目录下创建、删除文件

```
[root@Localhost ~]# chmod g+w /tarena2
[root@Localhost ~]# useradd ceshi
[root@Localhost ~]# gpasswd -a ceshi tarena
[root@Localhost ~]# id ceshi
[root@Localhost ~]# su -ceshi
[ceshi@Localhost ~]# mkdir /tarena2/ceshi
[ceshi@Localhost ~]# ls /tarena2
[ceshi@Localhost ~]# exit
```

  4）新建/tarena/public目录

​     a）使任何用户对此目录都有rwx权限

```
[root@Localhost ~]# mkdir -p /tarena/public
[root@Localhost ~]# chmod 777 /tarena/public
```

​     b）拒绝zhangsan进入此目录，对此目录无任何权限（提示ACL黑名单）

```
[root@Localhost ~]# ls -ld /tarena/public
[root@Localhost ~]# setfacl -m u:zhangsan:--- /tarena/public
[root@Localhost ~]# useradd zhangsan
[root@Localhost ~]# su -zhangsan 
[zhangsan@Localhost ~]# ls /tarena/public
[zhangsan@Localhost ~]# cd /tarena/public
[zhangsan@Localhost ~]# exit
```

 

#### 案例3:权限设置

   1、创建文件夹/data/test,设置目录的访问权限，使所有者和所属组具备读写执行的权限；其他人无任何权限。

```
[root@Localhost ~]# mkdir -p /data/test
[root@Localhost ~]# chmod u=rwx,g=rwx,o=--- /data/test 或者  chmod 770 /data/test
[root@Localhost ~]# ls -ld /data/test
```

   2、递归修改文件夹/data/test的归属使所有者为zhangsan，所属组为tarena。

```
[root@Localhost ~]# chown -R zhangsan:tarena /data/test
[root@Localhost ~]# ls -ld /data/test
```

   3、请实现在test目录下，新建的所有子文件或目录的所属组都会是tarena。

```
[root@Localhost ~]# chmod g+s /data/test
[root@Localhost ~]# mkdir /data/test/abc
[root@Localhost ~]# ls -ld /data/test/abc
```

   4、为lisi创建ACL访问权限，使得lisi可以查看/etc/shadow文件

```
[root@Localhost ~]# useradd lisi
[root@Localhost ~]# setfacl -m u:liai:r /etc/shadow
[root@Localhost ~]# getfacl /etc/shadow
[root@Localhost ~]# su-lisi
[lisi@Localhost ~]# cat /etc
```

 

#### 案例4:虚拟机 上操作

   将文件 /etc/fstab 拷贝为 /var/tmp/fstab，并调整文件 /var/tmp/fstab权限 

   满足以下要求：

   – 此文件的拥有者是 root 

   – 此文件对任何人都不可执行

   – 用户 natasha 能够对此文件执行读和写操作 

   – 用户 harry 对此文件既不能读，也不能写 

```
[root@Localhost ~]# mkdir -p /var/tmp/fstab
[root@Localhost ~]# cp  /etc/fstab /var/tmp/fstab
[root@Localhost ~]# ls -l /var/tmp/fstab
[root@Localhost ~]# chmod a-x /var/tmp/fstab

[root@Localhost ~]# setfacl -m u:natasha:rw /var/tmp/fstab
[root@Localhost ~]# getfacl /var/tmp/fstab
[root@Localhost ~]# su -natasha
[natasha@Localhost ~]# cat /var/tmp/fstab
[natasha@Localhost ~]# echo ceshi >> /var/tmp/fstab
[natasha@Localhost ~]# cat /var/tmp/fstab
[natasha@Localhost ~]# exit
[root@Localhost ~]# setfacl -m u:harry:--- /var/tmp/fstab
[root@Localhost ~]# getfacl /var/tmp/fstab
[root@Localhost ~]# su-harry
[harry@Localhost ~]# cat /var/tmp/fstab
[harry@Localhost ~]# echo ceshi >> /var/tmp/fstab
[harry@Localhost ~]# exit
```



#### 案例5:虚拟机上操作

   创建一个共用目录 /home/admins，要求如下： 

​    – 此目录的所属组是 adminuser 

​    – adminuser 组的成员对此目录有读写和执行的权限，并且其他用户没有任何权限

​    – 在此目录中创建的文件，其所属组会自动设置为 属于 adminuser 组

```
[root@Localhost ~]# mkdir /home/admins
[root@Localhost ~]# groupadd adminuser
[root@Localhost ~]# chown :adminuser /home/admins
[root@Localhost ~]# ls -ld /home/admins
[root@Localhost ~]# chmod g:rwx,o:--- /home/admins
[root@Localhost ~]# chown g+s  /home/admins
[root@Localhost ~]# ls -ld /home/admins

[root@Localhost ~]# mkdir /home/admins/ceshi
[root@Localhost ~]# ls -ld/home/admins/ceshi
```



## 02：磁盘空间管理、交换空间

### 硬盘分区管理

#### 硬盘结构及概念

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/ENGINEER/DAY02/COURSE/LINUXNSD_V01ENGINEERDAY02_005.png)

#### 一块硬盘的“艺术”之旅

- ​                         **识别硬盘      =>      分区规划         =>          格式化        =>      挂载使用**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml8\wps1.jpg)

- MBR/ msdos 分区模式
  - 1~4 个主分区，或者0~3 个主分区 + 1个 扩展分区（n个逻辑分区）
  - 最大支持容量为 2.2 TB 的磁盘
  - 扩展分区不能格式化

#### 使用 fdisk 分区工具

- 查看分区表 

  `fdisk -l /dev/sda`

  

- 修改硬盘的分区表

  `fdisk 硬盘设备`

  ```
  [root@localhost ~]# fdisk   /dev/sdb  
  n 创建新的分区----->分区类型 回车----->分区编号 回车---->起始扇区 回车----->在last结束时 +2G
  
  p 查看分区表
  
  n 创建新的分区----->分区类型 回车----->分区编号 回车---->起始扇区 回车----->在last结束时 +1G
  
  w 保存并退出
  
  [root@localhost ~]# lsblk
  [root@localhost ~]# ls   /dev/sdb[1-2]
  ```

常用交互指令：

> m  列出指令帮助
>
> p  查看现有的分区表
>
> n  新建分区
>
> d  删除分区
>
> q  放弃更改并退出
>
> w  保存更改并退出



### 格式化分区

#### 常用的格式化工具

- mkfs  工具集

  > —mkfs.ext3  分区设备路径
  >
  > —mkfs. ext4  分区设备路径
  >
  > —mkfs.xfs  分区设备路径
  >
  > —mkfs.vfat   分区设备路径

 格式化：赋予空间文件系统类型过程

文件系统：空间存储数据的规则

Windows常见文件系统：NTFS、FAT、FAT32

Linux常见文件系统: ext4(RHEL6)、XFS(RHEL7)

```
[root@localhost ~]# mkfs.ext4   /dev/sdb1  
[root@localhost ~]# blkid  /dev/sdb1     #查看文件系统类型

[root@localhost ~]# mkfs.xfs  /dev/sdb2
[root@localhost ~]# blkid  /dev/sdb2     #查看文件系统类型
```

#### 挂载使用

```
[root@localhost ~]# mkdir   /mypart1
[root@localhost ~]# mount   /dev/sdb1    /mypart1
[root@localhost ~]# df  -h   #查看当前系统正在挂载设备

[root@localhost ~]# mkdir   /mypart2
[root@localhost ~]# mount   /dev/sdb2    /mypart2
[root@localhost ~]# df  -h    #查看当前系统正在挂载设备
```

### 开机自动挂载 /etc/fstab

格式：设备路径  挂载点    类型   参数   备份标记   检测顺序

```
[root@localhost ~]# blkid /dev/sdb1    #查看文件系统类型
[root@localhost ~]# blkid /dev/sdb2   #查看文件系统类型

[root@localhost ~]# vim  /etc/fstab      
/dev/sdb1   /mypart1   ext4   defaults   0  0
/dev/sdb2   /mypart2   xfs   defaults   0  0

[root@localhost ~]# umount   /mypart1
[root@localhost ~]# umount   /mypart2
[root@localhost ~]# df -h  | grep sdb
[root@localhost ~]# mount  -a
检测/etc/fstab开机自动挂载配置文件,格式是否正确
检测/etc/fstab中,书写完成,但当前没有挂载的设备,进行挂载 
[root@localhost ~]# df -h   |   grep   sdb
```



/etc/fstab书写错误：

1.输入root的密码（输入的内容不显示）

![image-20200909184621617](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200909184621617.png)

2.继续编辑/etc/fstab内容进行修复

![image-20200909184632938](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200909184632938.png)



### 综合分区

```
[root@localhost ~]# fdisk   /dev/sdb
p 查看分区表
n 创建主分区----->回车----->回车---->回车----->在last结束时 +2G
p 查看分区表
n 创建扩展分区 ----->回车---->起始回车----->结束回车 将所有空间给扩展分区
p 查看分区表
n 创建逻辑分区----->起始回车------>结束+2G
n 创建逻辑分区----->起始回车------>结束+2G
n 创建逻辑分区----->起始回车------>结束+2G
p 查看分区表
w 保存并退出
[root@localhost ~]# partprobe   #刷新分区表
Warning: 无法以读写方式打开 /dev/sr0 (只读文件系统)。/dev/sr0 已按照只读方式打开。
[root@localhost ~]# lsblk
```

总结：

1.识别硬盘   lsblk

2.分区规划   fdisk   分区模式MBR

3.刷新分区表  partprobe

4.格式化  mkfs.ext4  mkfs.xfs  blkid 

5.挂载使用  mount   /etc/fstab   mount  -a   df  -h



###  添加全新的硬盘，为GPT分区模式准备

1.关闭虚拟机

```
[root@localhost ~]# poweroff
```

2.添加一块50G硬盘

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml8\wps2.jpg) 

3.查看系统识别的硬盘

```
[root@localhost ~]# lsblk
```

### GPT分区模式，分区进阶

-  GPT，GUID Partition Table

> – 全局唯一标识分区表
>
> – 突破固定大小64字节的分区表限制
>
> – 最多可支持128个主分区，最大支持18EB容量
>
> – 1 EB = 1024 PB = 1024 x 1024 TB

-  parted常用分区指令（专门划分GPT分区模式）

```
[root@localhost ~]# parted  /dev/sdc   

(parted) mktable  gpt       #指定分区模式为GPT 

(parted) mkpart            #划分新的分区

分区名称？ []? Haha          #分区的名字，随意起名

文件系统类型？  [ext2]? ext4    #文件系统类型，随意写

起始点？ 0                  #起始点

结束点？ 4G                  #结束点

忽略/Ignore/放弃/Cancel? Ignore   #忽略分区表占用的空间

(parted) print 

(parted) unit  GB               #采用GB作为单位

(parted) print

(parted) mkpart 

分区名称？  []? haha     

文件系统类型？  [ext2]? ext4 

起始点？ 4G

结束点？ 100%                 #全部空间

(parted) print                

(parted) quit 
```

### 交换空间（虚拟内存）

**利用硬盘的空间，充当真正内存**

**作用：当物理内存不够时候，暂时将物理内存中的数据，放到交换空间中，缓解真实物理内存的不足**

 **CPU----->内存------>硬盘**

- 方式一：利用未使用的分区空间制作交换空间

```
]# ls  /dev/sdc1
]# mkswap  /dev/sdc1  #格式化交换文件系统
]# blkid  /dev/sdc1     #查看文件系统

]# swapon  /dev/sdc1   #启用交换分区
]# swapon     #查看组成交换空间的成员信息
]# free -m     #查看交换空间总共的大小
 
]# swapoff  /dev/sdc1   #停用交换分区
]# swapon     #查看组成交换空间的成员信息
]# free -m     #查看交换空间总共的大小
 
]# vim  /etc/fstab  #开机自动启用交换分区
/dev/sdc1   swap   swap   defaults  0   0
]# swapon
]# swapon  -a   #专门用于检测交换分区
]# swapon
```

- 方式二：利用一个文件，进行制作交换空间

1.生成一个2G的文件

– dd  if=源设备  of=目标设备  bs=块大小  count=次数

```
]# ls  /dev/zero   #永远产生数据
]# dd  if=/dev/zero  of=/opt/swap.txt  bs=1M  count=2048
]# du -sh  /opt/swap.txt   #查看占用磁盘空间大小
```

2.利用文件占用空间，充当交换空间

```
]# mkswap  /opt/swap.txt   #格式化交换文件系统
]# swapon  /opt/swap.txt    #启用交换文件
swapon: /opt/swap.txt：不安全的权限 0644，建议使用 0600。
]# swapon       #查看交接空间组成的成员信息
```



### 课后习题：

#### 案例1：复制、粘贴、移动

 以root用户新建/example/目录，在此目录下新建nsd.txt文件，并进一步完成下列操作

```
[root@localhost ~]# mkdir /example/
```

 1）将“I love Study”写入到文件nsd.txt 

```
[root@localhost ~]# echo I love Study > /example/nsd.txt
[root@localhost ~]# cat /example/nsd.txt
```

 2）将nsd.txt重命名为mylove.txt

```
[root@localhost ~]# mv /example/nsd.txt /example/mylove.txt
```

 3）将/etc/passwd、/boot、/etc/group同时拷贝到/example/目录下

```
[root@localhost ~]# cp -r /etc/passwd /boot /etc/group  /example
[root@localhost ~]# ls /example
```

 4）将ifconfig命令的前两行内容，追加写入mylove.txt

```
[root@localhost ~]# ifconfig | head -2 >> /example/mylove.txt
```

 5）将主机名永久配置文件(/etc/hostname)，拷贝到/example/目录下

```
[root@localhost ~]# cp /etc/hostnaem /example/
[root@localhost ~]# ls /example
```

 6）将DNS永久配置文件（/etc/resolv.conf），拷贝到/example/目录下

```
[root@localhost ~]# cp /etc/resolv.conf  /example
[root@localhost ~]# ls /example
```

 7）将开机自动挂载配置文件(/etc/fstab)，拷贝到/example/目录下

```
[root@localhost ~]# cp /etc/fstab /example/
[root@localhost ~]# ls /example
```

 

#### 案例2:虚拟机上操作,（MBR分区模式）规划分区

 添加一块60G的硬盘并规划分区：

  划分2个10G的主分区；1个12G的主分区;1个20G的逻辑分区。

```
[root@localhost ~]# lsblk
[root@localhost ~]# fdisk /dev/sdb
n 创建新的分区----->分区类型 回车----->分区编号 回车---->起始扇区 回车----->在last结束时 +10G
p 查看分区表 
n 创建新的分区----->分区类型 回车----->分区编号 回车---->起始扇区 回车----->在last结束时 +10G
p 查看分区表
n 创建新的分区----->分区类型 回车----->分区编号 回车---->起始扇区 回车----->在last结束时 +12G
p 查看分区表
n 创建新的分区----->分区类型 回车----->分区编号 回车---->起始扇区 回车----->在last结束时 回车 将所有空间给扩展分区
p 查看分区表
n 创建逻辑分区----->分区类型 回车----->分区编号 回车---->起始扇区 回车----->在last结束时 +20G
p 查看分区表
w 保存并退出
[root@localhost ~]# partprobe
[root@localhost ~]# lsblk 
[root@localhost ~]# ls /dev/sdd[1-5]
```

#### 案例3:虚拟机上操作,分区使用

1、案例2中新添加60G硬盘的第一个逻辑分区

– 格式化成xfs文件系统，实现该分区开机自动挂载，挂载点为/mnt/xfs

```
[root@localhost ~]# mkfs.xfs /dev/sdd5
[root@localhost ~]# mkdir /mnt/xfs
[root@localhost ~]# vim /etc/fstab
/dev/sdd5 /mnt/xfs xfs defaults 0 0
:wq
[root@localhost ~]# mount -a

```

2、案例2中新添加60G硬盘的第一个主分区

– 完成开机自动挂载，挂载点/mnt/mypart,文件系统为ext4

```
[root@localhost ~]# mkdir /mnt/mypart
[root@localhost ~]# mkfs.ext4 /dev/sdb1
[root@localhost ~]# vim /etc/fstab
/dev/sdd1 /mnt/mypart ext4 defaults 0 0
:wq
[root@localhost ~]# mount -a
[root@localhost ~]# df -h 
```

 

#### 案例4:虚拟机上操作,采用GPT分区模式，利用parted规划分区

 添加一块20G的硬盘并规划分区：

  划分2个2G的主分区；1个5G的主分区;

```
[root@localhost ~]# lsblk
[root@localhost ~]# parted  /dev/sde  

(parted) mktable  gpt       #指定分区模式为GPT 

(parted) print

(parted) mkpart            #划分新的分区

分区名称？ []? xixi          #分区的名字，随意起名

文件系统类型？  [ext2]? xfs    #文件系统类型，随意写

起始点？ 0                  #起始点

结束点？ 2G                  #结束点
警告: The resulting partition is not properly aligned for best performance.
忽略/Ignore/放弃/Cancel? Ignore   #忽略分区表占用的空间

(parted) print 

(parted) mkpart 

分区名称？  []? haha     

文件系统类型？  [ext2]? xfs 

起始点？ 2G

结束点？ 4G              
(parted) print
(parted) mkpart 

分区名称？  []? haha     

文件系统类型？  [ext2]? xfs

起始点？ 4G

结束点？ 9G   

(parted) print                

(parted) quit 
[root@localhost ~]# lsblk
[root@localhost ~]# ls /dev/sde[1-3]
```

 

#### 案例5:虚拟机上操作,交换分区使用

1、案例4中新添加20G硬盘的第一个主分区

– 格式化成交换文件系统，实现该分区开机自动启用

```
[root@localhost ~]# swapon -s
[root@localhost ~]# mkswap  /dev/sde3
[root@localhost ~]# blkid /dev/sde3
[root@localhost ~]# vim  /etc/fstab
/dev/sde3  swap  swap  defaults  0   0
[root@localhost ~]# swapon  -a 

```

2、案例4中新添加20G硬盘的第二个主分区

– 格式化成交换文件系统，实现该分区开机自动启用

```
[root@localhost ~]# swapon
[root@localhost ~]# mkswap  /dev/sdc2
[root@localhost ~]# vim  /etc/fstab
/dev/sdc2  swap  swap  defaults  0   0
:wq
[root@localhost ~]# swapon -a
[root@localhost ~]# swapon -s
```

 

#### 案例6:虚拟机上操作,文件扩展Swap空间

 

1. 使用dd命令创建一个大小为2048MB的交换文件，放在/opt/swap.db

```
[root@localhost ~]# dd if=/dev/zero of=/opt/swap.db bs=1M count=2048
[root@localhost ~]# ls -lh /opt/swap.db
```

2. 将swap.db文件格式化成swap文件系统

```
[root@localhost ~]# mkswap -f /opt/swap.db
[root@localhost ~]# blkid /opt/swap.db
```

3. 启用swap.db文件，查看swap空间组成

```
[root@localhost ~]# swapon /opt/swap.db
[root@localhost ~]# swapon -s
```

4. 停用swap.db文件，查看swap空间组成

```
[root@localhost ~]# swapoff /opt/swap.db
[root@localhost ~]# swapon -s
```

------

## 03：逻辑卷管理、VDO、RAID磁盘阵列、进程管理

### 一、 构建Yum仓库，环境准备

#### 1.光盘文件放入光驱设备

![image-20200912150945474](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912150945474.png)

![image-20200912150956324](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912150956324.png)

#### 2.挂载光驱设备

```
[root@localhost ~]# mkdir  /nsd50

[root@localhost ~]# mount  /dev/cdrom  / nsd50 [root@localhost ~]# ls  /nsd50
```

#### 3.书写客户端配置文件

```
[root@localhost ~]# rm -rf  /etc/yum.repos.d/*

[root@localhost ~]# vim  /etc/yum.repos.d/nsd.repo

[centos]

name=2008

baseurl=file:///nsd50

enabled=1

gpgcheck=0

[root@localhost ~]# yum  -y  install  httpd

[root@localhost ~]# rpm -q httpd
```

### 二、 添加新的硬盘进行分区

> 添加一块60G的硬盘并规划分区(采用MBR分区模式)
>
> 划分2个10G的主分区,1个12G的主分区,1个20G的逻辑分区。

#### 1.关闭虚拟机添加新的硬盘

```
[root@localhost ~]# poweroff
```

#### 2.进行分区的规划

```
[root@localhost ~]# fdisk  /dev/sdb

p 查看分区表

n 创建主分区----->回车----->回车---->回车----->在last结束时 +10G

n 创建主分区----->回车----->回车---->回车----->在last结束时 +10G

n 创建主分区----->回车----->回车---->回车----->在last结束时 +12G

p 查看分区表

n 创建扩展分区 ----->回车---->起始回车----->结束回车 将所有空间给扩展分区

p 查看分区表

n 创建逻辑分区----->起始回车------>结束+20G

p 查看分区表

w 保存并退出

[root@localhost ~]# lsblk
```

### 三、 逻辑卷简介(虚拟磁盘技术)

作用：1.可以整合分散的空间  2.空间可以扩大

制作过程：将众多的物理卷(PV)，组建成卷组(VG)，再从卷组中划分出逻辑卷(LV)

LVM管理工具集

| ***\*功能\**** | ***\*物理卷管理\**** | ***\*卷组管理\**** | ***\*逻辑卷管理\**** |
| -------------- | -------------------- | ------------------ | -------------------- |
| Scan 扫描      | pvscan               | vgscan             | lvscan               |
| Create 创建    | pvcreate             | vgcreate           | lvcreate             |
| Display 显示   | pvdisplay            | vgdisplay          | lvdisplay            |
| Remove 删除    | pvremove             | vgremove           | lvremove             |
| Extend 扩展    | /                    | vgextend           | lvextend             |

### 四、 逻辑卷的制作 

#### **制作卷组**  

**格式：vgcreate**  **卷组名**   **设备路径……**   

Successfully:成功

```
]# ls  /dev/sdb[1-2]

]# vgcreate  systemvg   /dev/sdb1   /dev/sdb2

 Physical volume "/dev/sdb1" successfully created.

 Physical volume "/dev/sdb2" successfully created.

 Volume group "systemvg" successfully created

]# vgs    #显示系统所有的卷组信息

]# pvs    #显示系统所有的物理卷信息
```

 **制作逻辑卷**

格式: lvcreate -L 逻辑卷大小   -n 逻辑卷名字   基于卷组

```
[root@localhost ~]# lvcreate  -L  16G   -n   vo    systemvg 

Logical volume "vo" created.
 
[root@localhost ~]# lvs   #查看逻辑卷的信息
[root@localhost ~]# vgs  #查看卷组的信息
```

**逻辑卷的使用**

```
]# ls  -l  /dev/systemvg/vo

]# mkfs.xfs  /dev/systemvg/vo   #格式文件系统类型

]# blkid  /dev/systemvg/vo    #查看文件系统类型

]# vim  /etc/fstab

/dev/systemvg/vo   /mylv   xfs   defaults   0  0

[root@localhost ~]# mount  -a

mount: 挂载点 /mylv 不存在

[root@localhost ~]# mkdir   /mylv   #创建挂载点目录

[root@localhost ~]# mount  -a    #测试fstab是否书写正确

[root@localhost ~]# df  -h  #查看正在挂载的设备信息

[root@localhost ~]# lsblk
```



### 五、 逻辑卷的扩展

####  **卷组有足够的剩余空间**

##### **1.扩展空间大小**

```
[root@localhost ~]# vgs

[root@localhost ~]# lvs

[root@localhost ~]# lvextend  -L  18G  /dev/systemvg/vo

[root@localhost ~]# lvs


[root@localhost ~]# df  -h  |  tail  -1

/dev/mapper/systemvg-vo  16G  33M  16G   1% /mylv

[root@localhost ~]# lvs

 vo  systemvg  -wi-ao----  18.00g
```

##### **2.扩展文件系统**

resize2fs:刷新ext4文件系统        

xfs_growfs: 刷新xfs文件系统

```
[root@localhost ~]# xfs_growfs  /dev/systemvg/vo

[root@localhost ~]# df  -h  |   tail -1

/dev/mapper/systemvg-vo  18G  33M  16G   1% /mylv
```

 

####  **卷组没有足够的剩余空间**

##### **1.扩展卷组空间**

```
[root@localhost ~]# vgs

[root@localhost ~]# vgextend  systemvg  /dev/sdb3

[root@localhost ~]# vgs
```

##### **2.扩展逻辑卷空间大小**

```
[root@localhost ~]# lvs

[root@localhost ~]# lvextend  -L  25G  /dev/systemvg/vo

[root@localhost ~]# lvs

[root@localhost ~]# df  -h  |  tail  -1

[root@localhost ~]# lvs
```

##### **3.扩展文件系统**    

```
[root@localhost ~]# xfs_growfs  /dev/systemvg/vo

[root@localhost ~]# df  -h  |   tail  -1

/dev/mapper/systemvg-vo  25G  33M  16G   1% /mylv
```



### 六、 逻辑卷的补充

####  **逻辑卷也可以缩减(了解)**

 

#####  **卷组划分空间单位**  **PE**

默认情况下PE大小为4M

```
]# vgdisplay  systemvg   #查看卷组详细信息

  PE Size        4.00 MiB

]# vgchange  -s   1M   systemvg    #修改PE的大小

]# lvcreate -L  250M  -n  test   systemvg

]# lvcreate -l 50  -n  redhat  systemvg  #利用PE个数

]# lvs
```

 

####  **删除逻辑卷**

##### **1.删除正在使用的逻辑卷**

```
[root@localhost ~]# lvremove  /dev/systemvg/vo

 Logical volume systemvg/vo contains a filesystem in use.

[root@localhost ~]# umount  /mylv   #卸载逻辑卷

[root@localhost ~]# lvremove  /dev/systemvg/vo

Do you really want to remove active logical volume systemvg/vo? [y/n]:***\*y\****

 Logical volume "vo" successfully removed

[root@localhost ~]# vim  /etc/fstab  #删除开机自动挂载配置
```

 

##### **2.删除卷组：基于此卷组创建的所有逻辑卷全部删除**

```
[root@localhost ~]# lvremove  /dev/systemvg/test

[root@localhost ~]# lvremove  /dev/systemvg/redhat

[root@localhost ~]# vgs

 VG    #PV #LV #SN Attr   VSize  VFree  

 centos    1   2  0 wz--n-  <19.00g    0 

 systemvg  3   0  0 wz--n-  <31.99g <31.99g

[root@localhost ~]# vgremove  systemvg

[root@localhost ~]# vgs

```





### 七、 进程管理

>   程序：静态没有运行的代码  占用硬盘空间
>
>   进程：正在运行的代码  占用CPU与内存的资源
>
> 进程唯一标识:PID
>
>   父进程与子进程    树型结构

 

systemd：所有进程的父进程，***\*上帝进程\****

 

#### **查看进程pstree — Processes Tree**

> – 格式：pstree  [选项]  [PID或用户名]
>
> • 常用命令选项
>
> – -a：显示完整的命令行
>
> – -p：列出对应PID编号 

```
[root@localhost ~]# pstree      #查看正在运行的进程信息

[root@localhost ~]# useradd  lisi

[root@localhost ~]# pstree  lisi

未发现进程。

[root@localhost ~]# pstree  lisi

bash───vim

[root@localhost ~]# pstree -p  lisi  #显示进程的PID

bash(6838)───vim(6874) 

[root@localhost ~]# pstree -a  lisi  #显示完成的命令

bash

 └─vim a.txt
```

 

####  **查看进程**

• ps  aux 操作（显示的信息非常详细）   

– 列出正在运行的所有进程

用户 进程ID  %CPU  %内存 虚拟内存 固定内存 终端 状态 起始时间 CPU时间 程序指令 

 

计算正在运行的进程的个数？

```
[root@localhost ~]# wc  -l  /etc/passwd

43 /etc/passwd

[root@localhost ~]# ps   aux   |   wc  -l

[root@localhost ~]# ps  -elf   |   wc  -l

[root@localhost ~]# find /etc  -name “*.conf”

[root@localhost ~]# find /etc  -name “*.conf”  |  wc  -l
```

 

• ps  -elf 操作（可以显示进程的父进程PID）

– 列出正在运行的所有进程

 

#### **进程动态排名top 交互式工具**

– 格式：top  [-d  刷新秒数]  [-U  用户名]

```
[root@localhost ~]# top

  输入P(大写)，按照CPU进行排序

  输入M(大写)，按照内存进行排序

  输入q退出
```

 

#### **检索进程pgrep — Process Grep**

– 用途：pgrep  [选项]...  查询条件

• 常用命令选项

– -l：输出进程名，而不仅仅是 PID

– -U：检索指定用户的进程

– -x：精确匹配完整的进程名

```
[root@localhost ~]# pgrep  -l  a

[root@localhost ~]# pgrep  -l  c
```

#### **进程的前后台调度**

> • Ctrl + z 组合键
>
> – 挂起当前进程（暂停当前的进程并转入后台）
>
> • jobs 命令
>
> – 查看后台任务列表
>
> • fg 命令
>
> – 将后台任务恢复到前台运行
>
> • bg 命令
>
> – 激活后台被挂起的任务

```
[root@localhost /]# ls  /nsd50

[root@localhost /]# mount   /dev/cdrom   /nsd50

[root@localhost /]# yum -y  install  xorg-x11-apps

[root@localhost /]# xeyes  &   #进程正在运行的状态放入后台

[root@localhost /]# firefox &

 
[root@localhost ~]# yum -y  install  xorg-x11-apps

[root@localhost ~]# xeyes

^Z                   #按ctrl +z  暂停放入后台

[1]+  已停止        xeyes

[root@localhost ~]# jobs     #查看后台进程的信息

[1]+  已停止        xeyes

[root@localhost ~]# bg 1    #将后台编号为1 的进程恢复运行

[1]+ xeyes &

[root@localhost ~]# jobs

[1]+  运行中        xeyes &


[root@localhost ~]# fg 1   #将后台编号为1的进程恢复到前台

xeyes

^C     #按ctrl +c 结束进程

[root@localhost ~]#            
```

 

####  **杀死进程**

• 干掉进程的不同方法

– Ctrl+c 组合键，中断当前命令程序

– kill  [-9]  PID... 、kill  [-9]  %后台任务编号

– killall  [-9]  进程名...

– pkill  [-9] 查找条件，包含就可以

```
[root@localhost ~]# xeyes &

[root@localhost ~]# xeyes &

[root@localhost ~]# xeyes &

[root@localhost ~]# jobs  -l    #显示后台进程信息，显示PID

[1]  8618 运行中        xeyes &

[2]-  8625 运行中        xeyes &

[3]+  8632 运行中        xeyes &

[root@localhost ~]# kill  8618    #按照PID杀死

[1]  已终止        xeyes

[root@localhost ~]# jobs  -l

[root@localhost ~]# killall   xeyes   #杀死所有xeyes进程
```

 

杀死一个用户开启的所有进程（强制踢出一个用户）

```
[root@localhost ~]# killall  -9  -u  lisi
```

 

### 八、 RAID磁盘阵列

#### • 廉价冗余磁盘阵列

– Redundant Arrays of Inexpensive Disks 

– 通过硬件/软件技术，将多个较小/低速的磁盘整合成一个大磁盘

– 阵列的价值：提升I/O效率、硬件级别的数据冗余

– 不同RAID级别的功能、特性各不相同

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps1.jpg) 

 

#### • RAID 0，条带模式

– 同一个文档分散存放在不同磁盘

– 并行写入以提高效率，没有容错功能

– 至少需要两块磁盘

 

#### • RAID 1，镜像模式

– 一个文档复制成多份，分别写入不同磁盘

– 多份拷贝提高可靠性，效率无提升，有容错功能

– 至少需要两块磁盘

 

#### • RAID5，高性价比模式

– 相当于RAID0和RAID1的折中方案

– 需要至少一块磁盘的容量来存放校验数据

– 至少需要三块磁盘

 

#### • RAID6，高性价比/可靠模式

– 相当于扩展的RAID5阵列，提供2份独立校验方案

– 需要至少两块磁盘的容量来存放校验数据

– 至少需要四块磁盘

 

#### • RAID 0+1/RAID 1+0

– 整合RAID 0、RAID 1的优势

– 并行存取提高效率、镜像写入提高可靠性

– 至少需要四块磁盘

| ***\*对比项\**** | ***\*RAID 0\**** | ***\*RAID 1\**** | ***\*RAID 10\**** | ***\*RAID 5\**** | ***\*RAID 6\**** |
| ---------------- | ---------------- | ---------------- | ----------------- | ---------------- | ---------------- |
| 磁盘数           | ≧ 2              | ≧ 2              | ≧ 4               | ≧ 3              | ≧ 4              |
| 存储利用率       | 100%             | ≦ 50%            | ≦ 50%             | n-1/n            | n-2/n            |
| 校验盘           | 无               | 无               | 无                | 1                | 2                |
| 容错性           | 无               | 有               | 有                | 有               | 有               |
| IO性能           | 高               | 低               | 中                | 较高             | 较高             |



### 九、 VDO 了解内容

•Virtual Data Optimizer（虚拟数据优化器）

–一个内核模块，目的是通过重删减少磁盘的空间占用，以及减少复制带宽

–VDO是基于块设备层之上的，也就是在原设备基础上映射出mapper虚拟设备，然后直接使用即可

 

•重复数据除

–输入的数据会判断是不是冗余数据

–判断为重复数据的部分不会被写入，然后对源数据进行更新，直接指向原始已经存储的数据块即可

•压缩

–对每个单独的数据块进行处理

```
]# yum -y install vdo kmod-kvdo  #所需软件包
```

 

•制作VDO卷

•vdo基本操作：参考man vdo 全文查找/example

```
–vdo create --name=VDO卷名称 --device=设备路径 --vdoLogicalSize=逻辑大小

–vdo list

–vdo status -n VDO卷名称

–vdo remove -n VDO卷名称

–vdostats [--human-readable] [/dev/mapper/VDO卷名称]

```

•VDO卷的格式化加速（跳过去重分析）：

–mkfs.xfs –K  /dev/mapper/VDO卷名称

–mkfs.ext4 -E nodiscard /dev/mapper/VDO卷名称

 

前提制作VDO需要2G以上的内存

```
[root@nb ~]# vdo create --name=vdo0 --device=/dev/sdc --vdoLogicalSize=200G

[root@nb ~]# mkfs.xfs -K /dev/mapper/vdo0 

[root@nb ~]# mkdir /nsd01

[root@nb ~]# mount /dev/mapper/vdo0 /nsd01

[root@nb ~]# df -h

[root@nb ~]# vdostats --hum /dev/mapper/vdo0 #查看vdo设备详细信息

 
[root@svr7 ~]# vim /etc/fstab 

/dev/mapper/vdo0  /nsd01 xfs defaults,_netdev 0 0 
```



### 课后习题：

#### 案例1：复制、粘贴、移动

 以root用户新建/exam/目录，在此目录下新建king.txt文件，并进一步完成下列操作

 1）将“I Love hehe”写入到文件king.txt 

```
[root@localhost ~]# mkdir /exam
[root@localhost ~]# echo "I Love hehe" > /exam/king.txt
[root@localhost ~]# cat /exam/king.txt
```

 2）将king.txt重命名为my.txt

```
[root@localhost ~]# move /exam/king.txt  /exam/my.txt
```

 3）将/etc/passwd、/boot、/etc/group同时拷贝到/exam/目录下

```
[root@localhost ~]# cp -r /etc/passwd /boot /etc/group /exam
```

 4）将ifconfig命令的前两行内容，追加写入king.txt

```
[root@localhost ~]# ifconfig | head -2
[root@localhost ~]# ifconfig | head -2 >> /exam/king.txt
```

 5）将主机名永久配置文件(/etc/hostname)，拷贝到/exam/目录下

```
[root@localhost ~]# cp /etc/hostname /exam/
[root@localhost ~]# ls /exam
```

 6）将存放组基本信息的配置文件（/etc/group），拷贝到/exam/目录下

```
[root@localhost ~]# cp /etc/group /exam
[root@localhost ~]# ls /exam
```

 7）将开机自动挂载配置文件，拷贝到/exam/目录下

```
[root@localhost ~]# cp /etc/fstab/ /exam
[root@localhost ~]# ls /exam
```



#### 案例2:虚拟机上操作,采用GPT分区模式，利用parted规划分区

 添加一块30G的硬盘并规划分区：

  划分2个2G的主分区；1个5G的主分区;

```
[root@localhost ~]# parted /dev/sdb
(parted) mktable  gpt             #指定分区模式为GPT 
(parted) print
(parted) mkpart                       #划分新的分区
分区名称？  []? xixi                 #分区的名字，随意起名
文件系统类型？  [ext2]? xfs     #文件系统类型，随意写
起始点？ 0                                   #起始点
结束点？ 2G                                   #结束点
警告: The resulting partition is not properly aligned for best performance.
忽略/Ignore/放弃/Cancel? Ignore    #选择忽略，给出存放分区表信息的空间
(parted) print 
(parted) unit  GB                             #采用GB作为单位
(parted) print
(parted) mkpart 
分区名称？  []? xixi      
文件系统类型？  [ext2]? xfs
起始点？ 2G
结束点？ 4G
(parted) print
(parted) mkpart 
分区名称？  []? hehe         
文件系统类型？  [ext2]? xfs
起始点？ 4G
结束点？ 9G
(parted) print                              
(parted) quit 

[root@localhost ~]# lsblk
```



#### 案例3:虚拟机上操作,交换分区使用

1、案例2中新添加30G硬盘的第一个主分区

– 格式化成交换文件系统，实现该分区开机自动启用

```
[root@localhost ~]# mkswap /dev/sdb1
[root@localhost ~]# blkid /dev/sdb1
[root@localhost ~]# swapon
[root@localhost ~]# swapon /dev/sdb1
[root@localhost ~]# swapon
[root@localhost ~]# free -m
```

2、案例2中新添加30G硬盘的第二个主分区

– 格式化成交换文件系统，实现该分区开机自动启用

```
[root@localhost ~]# mkswap /dev/sdb2
[root@localhost ~]# blkid /dev/sdb2
[root@localhost ~]# swapon
[root@localhost ~]# swapon /dev/sdb2
[root@localhost ~]# swapon
[root@localhost ~]# free -m
```



#### 案例4:虚拟机上操作,文件扩展Swap空间

1. 使用dd命令创建一个大小为2048MB的交换文件，放在/opt/swap.db

```
[root@localhost ~]# dd if=/dev/zero of=/opt/swap.db bs=1M count=2048
[root@localhost ~]# ls -lh /opt/swap.db
```

2. 将swap.db文件格式化成swap文件系统

```
 [root@localhost ~]# mkswap -f /opt/swap.db
 [root@localhost ~]# blkid /opt/swap.db
```

3. 启用swap.db文件，查看swap空间组成

```
 [root@localhost ~]# swapon
 [root@localhost ~]# swapon /opt/swap.db
 [root@localhost ~]# swapon    #查看组成交换空间的成员信息
 [root@localhost ~]# free-m  #查看交换空间总共的大小
```

4. 停用swap.db文件，查看swap空间组成

```
 [root@localhost ~]# swapoff /opt/swap/db
 [root@localhost ~]# swapon
 [root@localhost ~]# free-m  #查看交换空间总共的大小
```



#### 案例5:虚拟机操作，构建 LVM 存储

– 新建一个名为 systemvg 的卷组 

```
[root@localhost ~]# parted /dev/sdb
(parted) mkpart 
分区名称？  []? xixi                                                   
文件系统类型？  [ext2]? xfs                                             
起始点？ 8G                                                             
结束点？ 100%
(parted) print
(parted) quit

[root@localhost ~]# vgcreate systemvg /dev/sdb4
[root@localhost ~]# vgs
```

– 在此卷组中创建一个名为 vo 的逻辑卷，大小为8G 

```
[root@localhost ~]# lvcreate -L 8G -n vo systemvg
[root@localhost ~]# lvs
```

– 将逻辑卷 vo 格式化为 xfs 文件系统 

```
[root@localhost ~]# mkfs.xfs /dev/systemvg/vo
[root@localhost ~]# blkid /dev/systemvg/vo  #查看文件系统类型
```

– 将逻辑卷 vo 挂载到 /vo 目录，并在此目录下建立一个测试文件 votest.txt，内容为“I AM KING.” 

```
[root@localhost ~]# mkdir /vo
[root@localhost ~]# echo "I AM KING" > /vo/votest.txt
[root@localhost ~]# mount /dev/systemvg/vo /vo
```

– 实现逻辑卷vo开机自动挂载到/vo

```
[root@localhost ~]# vim /etc/fstab
 /dev/systemvg/vo /vo xfs defaults 0 0
[root@localhost ~]# umount /vo
[root@localhost ~]# mount -a
[root@localhost ~]# df -h   #查看正在挂载的设备信息
```



#### 案例6:虚拟机操作，构建 LVM 存储(修改PE大小)

– 新的逻辑卷命名为 database，其大小为50个PE的大小，属于 datastore 卷组 

– 在 datastore 卷组中其PE的大小为1M

```
[root@localhost ~]# vgchange -s 1M datestore /dev/sdb3
[root@localhost ~]# vgs
[root@localhost ~]# vgdisplay datastore
[root@localhost ~]# 
[root@localhost ~]# lvcreate -l 50 -n database  datastore
[root@localhost ~]# lvs

```

– 使用 EXT4 文件系统对逻辑卷 database 格式化，此逻辑卷应该在开机时自动挂载到 /mnt/database 目录

```
[root@localhost ~]# mkfs.ext4 /dev/datastore/database
[root@localhost ~]# blkid /dev/datastore/database
[root@localhost ~]# mkdir /mnt/database
[root@localhost ~]# vim /etc/fstab
/dev/datastore/database /mnt/database ext4 defaults 0 0
[root@localhost ~]# mount -a
[root@localhost ~]# df -h
```



#### 案例7:虚拟机 server0操作，扩展逻辑卷

– 将/dev/systemvg/vo逻辑卷的大小扩展到20G

```
[root@localhost ~]# vgs
[root@localhost ~]# lvextend -L 20G /dev/systemvg/vo
[root@localhost ~]# vgs
[root@localhost ~]# lvs
[root@localhost ~]# df -h | tail -1
[root@localhost ~]# xfs_growfs /dev/systemvg/vo
[root@localhost ~]# df -h | tail -1
```



#### 案例8:进程管理

 1.查看当前系统中整个进程树信息

```
[root@localhost ~]# pstree -ap
```

 2.利用pstree查看lisi开启的进程

```
[root@localhost ~]# useradd lisi
[root@localhost ~]# pstree -ap lisi
```

 3.显示当前系统正在运行的所有进程信息

```
[root@localhost ~]# ps aux
```

 4.检索当前系统中进程，进程名包含cron的PID是多少？

```
[root@localhost ~]# pgrep cron
```

 5.开启5个xeyes放入后台运行

```
[root@localhost ~]# ls /nsd50
[root@localhost ~]# mount /dev/cdrom /nsd50
[root@localhost ~]# yum -y install xorg-x11-apps
[root@localhost ~]# xeyes &
[root@localhost ~]# xeyes &
[root@localhost ~]# xeyes &
[root@localhost ~]# xeyes &
[root@localhost ~]# xeyes &
```

 6.杀死所有xeyes进程

```
[root@localhost ~]# killall -9 xeyes
```

------



## 04：配置Linux网络、源码编译安装。自定义yum仓库、日志管理

下载今日所需软件：MobaXterm_Professinal_20.3_Preview4.zip

 

\####################################################

### 一、 构建Yum仓库，环境准备

#### 1.光盘文件放入光驱设备

![image-20200912174828852](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912174828852.png)

![image-20200912174833712](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912174833712.png)



#### 2.挂载光驱设备

```
[root@localhost ~]# mkdir  /mydvd

[root@localhost ~]# mount  /dev/cdrom  /mydvd 
[root@localhost ~]# ls  /mydvd
```

#### 3.书写客户端配置文件

```
[root@localhost ~]# rm  -rf  /etc/yum.repos.d/*

[root@localhost ~]# vim  /etc/yum.repos.d/mydvd.repo

[centos]

name=2008

baseurl=file:///mydvd

enabled=1

gpgcheck=0

[root@localhost ~]# yum  -y  install  xorg-x11-apps

[root@localhost ~]# rpm -q xorg-x11-apps
```

 

#### 4．完成开机自动挂载

```
]# blkid  /dev/cdrom  #查看 光驱设备文件系统类型

]# vim  /etc/fstab

/dev/cdrom  /mydvd   iso9660   defaults  0  0

]# umount  /mydvd

]# mount  -a

]# ls  /mydvd


]# reboot     #重启测试

]# yum -y install httpd  #测试安装软件包

```



### 二、 配置网络参数之主机名  

####  **配置永久的主机名**

```shell
[root@localhost ~]# echo svr7.tedu.cn  >  /etc/hostname

[root@localhost ~]# cat  /etc/hostname

svr7.tedu.cn

[root@localhost ~]# hostname svr7.tedu.cn  #修改当前

[root@localhost ~]# hostname

svr7.tedu.cn
```

开启一个新的终端查看提示符的变化

### 三、 配置网络参数之IP地址与子网掩码、网关地址

#### **修改网卡命令规则(eth0、eth1、eth2……)**

```shell
]# ifconfig  |   head   -2

ens33: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500

    ether 00:0c:29:8a:72:4f  txqueuelen 1000  (Ethernet)


]# vim  /etc/default/grub  #grub内核引导程序

……..

GRUB_CMDLINE_LINUX="…….. quiet  net.ifnames=0  biosdevname=0"

……..

 

]# grub2-mkconfig  -o  /boot/grub2/grub.cfg  #让网卡命名规则生效

 

]# reboot

]# ifconfig  |  head  -2

eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500

   inet 192.168.81.132  netmask 255.255.255.0  broadcast 192.168.81.255
```

 

####  **nmcli命令的网卡命名，删除错误网卡命名**

```shell
[root@svr7 ~]# nmcli  connection  show       #查看

[root@svr7 ~]# nmcli  connection  delete  ens33

[root@svr7 ~]# nmcli  connection  show


[root@svr7 ~]# nmcli  connection  show

[root@svr7 ~]# nmcli  connection  delete  有线连接\ 1 

[root@svr7 ~]# nmcli  connection  show
```

 

#### **nmcli命令的网卡命名，添加网卡命名**   

```shell
[root@svr7 ~]# nmcli connection add type ethernet    ifname eth0  con-name eth0


[root@svr7 ~]# nmcli connection 添加  类型  以太网设备

网卡设备名为eth0   nmcli命令的命名为eth0

[root@svr7 ~]# nmcli  connection show
```



#### **修改IP地址、子网掩码、网关地址**

```shell
[root@svr7 ~]# nmcli connection modify  eth0   

ipv4.method   manual              

ipv4.addresses  192.168.4.7/24         

ipv4.gateway  192.168.4.254         

connection.autoconnect   yes

[root@svr7 ~]# nmcli connection  修改 网卡名  

ipv4.方法  手工配置             

ipv4.地址  192.168.4.7/24         

ipv4.网关  192.168.4.254         

每次开机自动启用


[root@svr7 ~]# nmcli connection up eth0   #激活

[root@svr7 ~]# ifconfig  |  head  -2
```



网卡配置文件：/etc/sysconfig/network-scripts/ifcfg-eth0

```shell
[root@svr7 ~]# route  -n     #查看网关地址信息

Kernel IP routing table

Destination   Gateway     Genmask     Flags Metric Ref   Use Iface

0.0.0.0     ***\*192.168.4.254\****  0.0.0.0     UG   100   0     0 eth0

192.168.4.0   0.0.0.0     255.255.255.0  U   100   0     0 eth0

192.168.122.0  0.0.0.0     255.255.255.0  U   0    0     0 virbr0
```



### 四、 配置网络参数之DNS服务器地址

DNS服务器：负责域名解析的机器，将域名解析为IP地址

```
[root@svr7 ~]# echo nameserver  8.8.8.8  > /etc/resolv.conf

[root@svr7 ~]# cat  /etc/resolv.conf

nameserver  8.8.8.8
```



### 五、 模板机器的修改

将UUID进行修改，修改为/dev/sda1

```
[root@svr7 ~]# vim  /etc/fstab

……. 

/dev/sda1  /boot          xfs   defaults     0 0

…….
```



### 六、 真机与虚拟机的通信

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps2.jpg) 



#### 1.查看真机虚拟网卡

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps3.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps4.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps5.jpg) 

#### 2.真机配置VMnet1的网卡IP地址为192.168.4.1

**双击**VMnet1网络适配器

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps6.jpg) 

 ![image-20200912175756716](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912175756716.png)

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps7.jpg) 

![image-20200912175819697](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912175819697.png)

#### 3.配置虚拟机网络类型

右击----》选择设置

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps8.jpg) 

![image-20200912175853735](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912175853735.png)

#### 4.测试通信                  

Windows键+r快捷键

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps9.jpg) 

![image-20200912175912628](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912175912628.png)

常见问题：

1.虚拟网卡vmnet1没有

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps10.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps11.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps12.jpg) 

 

如果还是无法出现vmnet1，参考下列网站方法

https://jingyan.baidu.com/article/066074d6f19bd0c3c31cb048.html



 

### 七、 虚拟机拍摄快照



|      |                                                              |
| ---- | ------------------------------------------------------------ |
|      | ![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps13.jpg) |

[root@svr7 ~]# poweroff

|      |                                                              |
| ---- | ------------------------------------------------------------ |
|      | ![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps14.jpg) |

 

### 八、 克隆虚拟机A（克隆必须关闭模板机器）

 ![image-20200912183432853](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183432853.png)



![image-20200912183437438](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183437438.png)

![image-20200912183441382](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183441382.png)

![image-20200912183507250](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183507250.png)

![image-20200912183517834](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183517834.png)

![image-20200912183607558](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183607558.png)

 

### 九、 虚拟机B配置

虚拟机B：

```
[root@svr7 ~]# hostname   pc207.tedu.cn

[root@svr7 ~]# echo  pc207.tedu.cn  >  /etc/hostname

[root@svr7 ~]# hostname

pc207.tedu.cn
```

 

新开一个终端进行测试

```
[root@pc207 ~]# nmcli  connection  modify  eth0 ipv4.method  manual  ipv4.addresses  192.168.4.207/24 connection.autoconnect  yes

[root@pc207 ~]# nmcli connection up eth0 

[root@pc207 ~]# ifconfig  |  head  -2

[root@pc207 ~]# ping 192.168.4.7

```

### 十、 虚拟机B拍摄快照

```
[root@pc207 ~]# poweroff
```

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps15.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml9748\wps16.jpg) 

### 十一、 利用真机windows进行远程管理

![image-20200912183757606](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183757606.png)

![image-20200912183802973](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183802973.png)

![image-20200912183811084](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183811084.png)

Ctrl+滚轮=可以放大或变小字体

### 十二、 源码编译安装

RPM包：rpm  -ivh    yum  install

源码包---开发工具--->可以执行的程序------>运行安装

• 主要优点

– 获得软件的最新版，及时修复bug

– 软件功能可按需选择/定制，有更多软件可供选择

– 源码包适用各种平台

– ……

#### **将真机的tools.tar.gz传递数据到虚拟机A**

![image-20200912183935392](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200912183935392.png)



```
[root@svr7 ~]# ls    /root

tools.tar.gz   下载  公共   音乐
[root@svr7 ~]#
```

 

#### 源码编译安装步骤：

##### 步骤一:安装开发工具

```
]# yum  -y  install  make

]# yum  -y  install  gcc

]# rpm  -q  gcc

]# rpm  -q  make
```

##### 步骤二:进行tar解包               

```
]# tar  -xf  /root/tools.tar.gz  -C  /usr/local/

]# ls  /usr/local/

]# ls  /usr/local/tools/

]# tar -xf  /usr/local/tools/inotify-tools-3.13.tar.gz  -C /usr/local/

]# ls  /usr/local/
```

 

##### 步骤三：运行configure脚本进行配置

作用1：检测系统是否安装gcc 

作用2：可以指定安装位置及功能

```
]# cd  /usr/local/inotify-tools-3.13/

]# ./configure  --prefix=/opt/myrpm   #指定安装位置
```

 

常见错误：没有安装gcc

```
checking for gcc... no

checking for cc... no

checking for cl.exe... no

configure: error: no acceptable C compiler found in $PATH

See `config.log' for more details.
```

 

##### 步骤四：make进行编译，产生可以执行的程序

```
]# cd   /usr/local/inotify-tools-3.13/

]# make
```



##### 步骤五：make  install进行安装

```
]# cd   /usr/local/inotify-tools-3.13/

]# make   install

]# ls /opt/

]# ls /opt/myrpm/

]# ls /opt/myrpm/bin/
```



 

### 十三、 远程管理(Linux与Linux)

####  **软件包的安装**

```shell
[root@svr7 /]# rpm  -qa   |  grep  openssh

openssh-7.4p1-16.el7.x86_64

openssh-server-7.4p1-16.el7.x86_64

openssh-clients-7.4p1-16.el7.x86_64
```

 

#### **远程登录工具 ssh**

虚拟机A：

```shell
[root@svr7 /]#  >  /etc/resolv.conf

[root@svr7 /]#  ssh   root@192.168.4.207

………necting (yes/no)? yes

root@192.168.4.207's password:    #输入密码

[root@pc207 ~]# touch  /root/hahaxixi.txt

[root@pc207 ~]# exit

登出

Connection to 192.168.4.207 closed.

[root@svr7 /]# cat /root/.ssh/known_hosts  #记录曾经远程管理的机器
```

 

####  **实现ssh远程管理无密码验证**

虚拟机A：

1.生成公钥(锁)与私钥(钥匙)进行验证

```
[root@svr7 ~]# ssh-keygen    #一路回车

…….save the key (/root/.ssh/id_rsa):   #保存位置

……..assphrase):   #设置密码为空

…….. again:   #设置密码为空

[root@svr7 ~]# ls /root/.ssh/

id_rsa(私钥)   id_rsa.pub(公钥)   known_hosts
```

2.将公钥(锁)传递给虚拟机B 

```
[root@svr7 ~]# ssh-copy-id  root@192.168.4.207  

[root@svr7 ~]# ssh  root@192.168.4.207  #测试无密码

[root@pc207 ~]# exit

登出

Connection to 192.168.4.207 closed.

[root@svr7 ~]#

虚拟机B     

[root@pc207 ~]# ls   /root/.ssh/

authorized_keys(别的机器传递过来的公钥)   known_hosts

[root@pc207 ~]#
```

 

#### **安全复制工具 scp=ssh+cp**

– scp  [-r]  用户名@服务器:路径    本地路径

– scp  [-r]  本地路径   用户名@服务器:路径

虚拟机A：

```
]# scp  /etc/passwd    root@192.168.4.207:/root

]# scp  -r  /home    root@192.168.4.207:/root/

]# scp  root@192.168.4.207:/etc/passwd    /mnt/
```

虚拟机B：

```
]# ls  /root
```



### 课后习题：

#### 案例1:虚拟机B上操作：实现静态网络参数配置

– 主机名:test.example.com

– IP地址:172.25.0.11

– 子网掩码:255.255.0.0

– 默认网关:172.25.0.254

– DNS服务器:172.25.254.254

```
[root@B ~]# hostname    test.example.com
[root@B ~]# echo    test.example.com   >   /etc/hostname 
[root@B ~]# cat   /etc/hostname

[root@B ~]# nmcli connection show 
[root@B ~]# nmcli   connection   modify    'ens33'    ipv4.method    manual     ipv4.addresses 172.25.0.11/18 ipv4.gateway   172.25.0.254    connection.autoconnect    yes

[root@B ~]# nmcli   connection   up   'ens33'    

[root@B ~]# route   -n        #查看网关地址
[root@B ~]# ifconfig   |   head -2     #查看网卡地址

[root@B ~]# echo  nameserver   172.25.254.254    >   /etc/resolv.conf     
[root@B ~]# cat   /etc/resolv.conf
```



#### 案例2:虚拟机B上操作：实现静态网络参数配置

– 主机名:B.tedu.cn

– IP地址:192.168.1.1

– 子网掩码:255.255.255.0

– 默认网关:192.168.1.254

– DNS服务器:8.8.8.8

```
[root@B ~]# echo B.tedu.cn > /etc/hostname
[root@B ~]# hostname B.tedu.u
[root@B ~]# cat /etc/hostname
[root@B ~]# nmcli connection show
[root@B ~]# nmcli connection modify 'ens33' ipv4.method manual
ipv4.address 192.168.1.1/24 ipv4.gateway 192.168.1.254 connection.autoconnect yes
[root@B ~]# nmcli connection up 'ens33'
[root@B ~]# route -n  #查看网关地址
[root@B ~]# ifcongig | head -2   #查看网卡地址
[root@B ~]# echo nameserver 8.8.8.8 > /etc/resolv.conf
[root@B ~]# cat /etc/resolv.conf
```



#### 案例3:虚拟机B上操作：实现静态网络参数配置

– 主机名:pc207.tedu.cn

– IP地址:192.168.4.207

– 子网掩码:255.255.255.0

– 默认网关:192.168.4.254

– DNS服务器:1.1.1.1

```
[root@B ~]# hostname pc207.tedu.cn
[root@B ~]# echo pc207.tedu.cn > /etc/hostname
[root@B ~]# cat /etc/hostname
[root@B ~]# nmcli connection modify 'ens33' ipv4.method manual ipv4.address 192.168.4.207/24 ipv4.gateway 192.168.4.254 connection.autoconnect yes

[root@B ~]# nmcli connection up 'ens33'

[root@B ~]# route -n  #查看网关地址
[root@B ~]# echo nameserver 1.1.1.1 > /etc/resolv.conf
[root@B ~]# cat /etc/resolv.conf
```



#### 案例4:虚拟机A上操作：实现静态网络参数配置

– 主机名:svr7.tedu.cn

– IP地址:192.168.4.7

– 子网掩码:255.255.255.0

– 默认网关:192.168.4.254

– DNS服务器:1.1.1.1

```
[root@A ~]# hostname svr7.tedu.cn
[root@B ~]# echo svr7.tedu.cn > /etc/hostname
[root@B ~]# cat /etc/hostname
[root@B ~]# nmcli connection modfiy 'ens33' ipv4.method manual ipv4.address 192.168.4.7/24 ipv4.gateway 192.168.4.254 connection.autoconnect yes
[root@B ~]# rount -n  #查看网关地址
[root@B ~]# ifconfig | head-2 #查看网卡地址
[root@B ~]# echo nameserver 1.1.1.1 > /etc/resolv.conf
[root@B ~]# cat /etc/resolv.conf
```

 

#### 案例5：虚拟机B

 1.源码编译安装 inotify-tools 软件工具

 2.安装位置为/usr/local/tools

```
[root@B ~]# yum -y install gcc make
[root@B ~]# tar -xf /root/tools.tar.gz -C /
[root@B ~]# tar -xf /tools/inotify-tools-3.13.tar.gz -C /
[root@B ~]# ls /
[root@B ~]# ls /inotify-tools-3.13/
[root@B ~]# cd /inotify-tools-3.13/
[root@B inotify-tools-3.13]# ./configure --prefix=/usr/local/tools #指定安装位置
[root@B inotify-tools-3.13]# make 
[root@B inotify-tools-3.13]# make install 
[root@B inotify-tools-3.13]# ls /usr/local/tools
```

 

#### 案例6：虚拟机B：传递数据

 1.将本机/usr/local/tools/other目录传递到虚拟机A，放在虚拟机A的/usr/目录下

```
[root@B ~]# scp -r /usr/local/tools/other root@192.168.4.7:/usr/
```

 2.将本机/etc/gshadow文件传递到虚拟机A，放在虚拟机A的/root目录下

```
[root@B ~]# scp /etc/gshadow root@192.168.4.7:/root/
```

 3.将本机/etc/skel目录传递到虚拟机A，放在虚拟机A的/tmp目录下

```
[root@B ~]# scp -r /etc/skel root@192.168.4.7:/tmp

[root@A ~]# ls /usr/
[root@A ~]# ls /root
[root@A ~]# ls /tmp
```



#### 案例7：虚拟机B：远程无密码验证

 1.实现虚拟机B远程管理虚拟机A，无需密码验证

```
1.生成公钥  私钥
[root@pc207 ~]# ssh-keygen   #一路回车
[root@pc207 ~]# ls /root/.ssh/

2.传递公钥 到虚拟机A
[root@pc207 ~]# ssh-copy-id root@192.168.4.7

3.虚拟机A：查看
[root@svr7 ~]# ls /root/.ssh/

4.虚拟机B：测试无密码
[root@pc207 ~]# ssh root@192.168.4.7
```



## 05：SELinux、系统故障修复、防火墙策略管理、服务管理



### **一、** **添加一张新的网卡设备**

####  **关闭虚拟机**

[root@svr7 ~]# poweroff

####  **添加网卡设备**

![image-20200914183311583](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200914183311583.png)

![image-20200914183317032](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200914183317032.png)

![image-20200914183321571](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200914183321571.png)

![image-20200914183327794](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200914183327794.png)

```
[root@svr7 ~]# ifconfig  | less

eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500

​    inet 192.168.4.7  netmask 255.255.255.0  broadcast 192.168.4.255

 

eth1: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500

​    inet 192.168.81.130  netmask 255.255.255.0  broadcast 192.168.81.255
```

 

####  **为eth1配置IP地址**

```
[root@svr7 ~]# nmcli connection show

[root@svr7 ~]# nmcli connection delete  有线连接\ 1 

成功删除连接 '有线连接 1'（1c99da34-de09-3f0d-9f7c-40c842036e40）。

[root@svr7 ~]# nmcli connection add type ethernet     con-name eth1  ifname eth1

连接“eth1”(4ab21424-4281-427d-b5fd-87fd0644b00a) 已成功添加。

[root@svr7 ~]# nmcli  connection  show

 
[root@svr7 ~]# nmcli connection modify eth1 

ipv4.method manual ipv4.addresses 192.168.1.1/24 connection.autoconnect  yes

[root@svr7 ~]# nmcli connection up eth1

连接已成功激活（D-Bus 活动路径：/org/freedesktop/NetworkManager/ActiveConnection/6）

[root@svr7 ~]# ifconfig  eth1  |  head -2

eth1: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500

​    inet 192.168.1.1 netmask 255.255.255.0 broadcast 192.168.1.255
```

### 二、**网络工具**

#### **利用ip命令，查看IP地址**

```
[root@svr7 ~]# ip  address  show

[root@svr7 ~]# ip  a  s    #支持命令的缩写
```

####  **利用ip命令，临时设置IP地址**

```
[root@svr7 ~]# ip address add  192.168.8.1/24  dev eth0   [root@svr7 ~]# ip   a   s   |  less

2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc pfifo_fast state UP group default qlen 1000

  link/ether 00:0c:29:a1:a5:d3 brd ff:ff:ff:ff:ff:ff

  inet 192.168.4.7/24 brd 192.168.4.255 scope global noprefixroute eth0

​    valid_lft forever preferred_lft forever

  inet 192.168.8.1/24 scope global eth0

​    valid_lft forever preferred_lft forever
```

 

#### **ping测试网络通信**

 **-c:指定ping包的个数**

```
[root@svr7 ~]# ping  -c  2  192.168.4.7

[root@svr7 ~]# ping  -c  4  192.168.4.7
```

### 三、 源码编译安装

RPM包：rpm -ivh   yum  install

源码包----开发工具---->可以执行的程序----->运行安装

 

#### • 主要优点

– 获得软件的最新版，及时修复bug

– 软件功能可按需选择/定制，有更多软件可供选择

– 源码包适用各种平台

– ……

 

#### • 传递源码包到虚拟机B

![image-20200914183953794](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200914183953794.png)

```
[root@pc207 /]# ls  /root/      

anaconda-ks.cfg    公共  文档

fstab         模板  下载

initial-setup-ks.cfg  视频  音乐

tools.tar.gz     图片  桌面
```

##### 步骤1：安装开发工具

```
/]# yum  -y  install  gcc

/]# yum  -y  install  make
```

##### 步骤2：tar解包，释放源代码至指定目录

```
]# tar -xf /root/tools.tar.gz  -C  /usr/local/

]# ls /usr/local/

]# ls /usr/local/tools/

]# tar -xf /usr/local/tools/inotify-tools-3.13.tar.gz  -C  /usr/local/

]# ls /usr/local/

]# cd /usr/local/inotify-tools-3.13/

]# ls
```

 

##### 步骤3：./configure 配置，指定安装目录/功能模块等选项

作用1：检测系统是否安装gcc  作用2：指定安装位置

```
]# ./configure     --prefix=/opt/myrpm     #当前运行脚本指定安装位置
```

##### 步骤4：make 编译，生成可执行的二进制程序文件

```
]# make
```

##### 步骤5：make install 安装，将编译好的文件复制到安装目录

```
]# make  install

]# ls  /opt/

]# ls  /opt/myrpm/

]# ls  /opt/myrpm/bin/    #查看安装好的程序
```

### 四、 自定义Yum仓库

将自己准备的众多软件包，制作成一个软件仓库

Yum仓库：1.众多的软件包  2.仓库数据文件

虚拟机A：

#### 1. .将真机tools.tar.gz传递虚拟机A

![image-20200914195730467](C:\Users\BJTT\AppData\Roaming\Typora\typora-user-images\image-20200914195730467.png)

#### 2.进行tar解包

```
]# tar  -tf  /root/tools.tar.gz    #查看包里内容

]# tar  -xf  /root/tools.tar.gz  -C   /

]# ls  /

]# ls  /tools
```



#### 3.生成仓库数据文件

```
[root@svr7 ~]# createrepo    /tools/other/
[root@svr7 ~]# ls   /tools/other/
```

#### 4.书写客户端配置文件

```
[root@svr7 ~]# vim   /etc/yum.repos.d/mydvd.repo
[centos]
name=2008
baseurl=file:///mydvd
enabled=1
gpgcheck=0
[myrpm]
name=2008
baseurl=file:///tools/other          
enabled=1
gpgcheck=0
[root@svr7 ~]# yum -y install sl
[root@svr7 ~]# yum -y install cmatrix
[root@pc207 /]# cmatrix

```

### 五、 日志简介

#### • 系统和程序的“日记本”

记录系统、程序运行中发生的各种事件

通过查看日志，了解及排除故障

信息安全控制的“依据”

#### • 由系统服务rsyslog统一记录/管理

– 日志消息采用文本格式

– 主要记录事件发生的时间、主机、进程、内容

#### • 常见的日志文件

| ***\*日志文件\**** | ***\*主要用途\****               |
| ------------------ | -------------------------------- |
| /var/log/messages  | 记录内核消息、各种服务的公共消息 |
| /var/log/dmesg     | 记录系统启动过程的各种消息       |
| /var/log/cron      | 记录与cron计划任务相关的消息     |
| /var/log/maillog   | 记录邮件收发相关的消息           |
| /var/log/secure    | 记录与访问限制相关的安全消息     |

 

#### • 日志分析

##### • 通用分析工具

– tail、tailf、less、grep等文本浏览/检索命令

– awk、sed等格式化过滤工具

tailf：实时跟踪日志消息

##### • users、who、w 命令

– 查看已登录的用户信息，详细度不同

##### • last、lastb 命令

– 查看最近登录成功/失败的用户信息

```
[root@pc207 /]# users

[root@pc207 /]# who

[root@pc207 /]# w

pts（图形命令行终端）

[root@pc207 /]#last -2  #最近登录成功的2条记录

[root@pc207 /]#lastb -2  #最近登录失败的2条记录
```

 

##### • Linux内核定义的事件紧急程度

– 分为 0~7 共8种优先级别

– 其数值越小，表示对应事件越紧急/重要

0  EMERG（紧急）     会导致主机系统不可用的情况

1  ALERT（警告）      必须马上采取措施解决的问题

2  CRIT（严重）	      比较严重的情况

3  ERR（错误）	      运行出现错误

4  WARNING（提醒）   可能会影响系统功能的事件

5  NOTICE（注意）     不会影响系统但值得注意

6  INFO（信息）	      一般信息

7  DEBUG（调试）      程序或系统调试信息等

 

##### • 提取由 systemd-journal 服务搜集的日志

– 主要包括内核/系统日志、服务日志

###### • 常见用法

– journalctl  |  grep  关键词

– journalctl  -u  服务名  [-p  优先级]

– journalctl  -n  消息条数



### 六、 SELinux安全机制

#### • Security-Enhanced Linux

– 美国NSA国家安全局主导开发，一套增强Linux系统安全的强制访问控制体系

– 集成到Linux内核（2.6及以上）中运行

– RHEL7基于SELinux体系针对用户、进程、目录和文件提供了预设的保护策略，以及管理工具

 

#### • SELinux的运行模式

– enforcing（强制）、permissive（宽松）

– disabled（彻底禁用）

– 任何模式变成disabled，都需要重启系统

#### • 切换运行模式

– 临时切换：setenforce  1|0

– 固定配置：/etc/selinux/config 文件

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml468\wps1.jpg) 

 

虚拟机A：

```
[root@svr7 /]# getenforce   #查看当前系统SELinux模式

Enforcing

[root@svr7 /]# setenforce  0  #临时设置当前SELinux模式

[root@svr7 /]# getenforce

Permissive

[root@svr7 /]# vim /etc/selinux/config

SELINUX=permissive
```

虚拟机B：同上

 

### 七、 系统故障修复

#### **etc\fstab\书写错误：**

##### 1.输入root的密码（输入的内容不显示）

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml468\wps2.jpg) 

##### 2.继续编辑/etc/fstab内容进行修复

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml468\wps3.jpg) 

 

####  **遗忘root的密码（破解系统root的密码）**

前提：必须是服务器的管理者，涉及重启服务器

破解密码思路

##### 1)**重启系统**,进入 恢复模式

```
[root@A ~]# reboot 
```

开启虚拟机A，在此界面按e键

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml468\wps4.jpg) 

找到linux16该行，在该行的最后，空格输入 rd.break  console=tty0

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml468\wps5.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml468\wps6.jpg) 

按 **ctrl + x** 启动，会看到switch_root#

 

##### 2)以可写方式重新挂载 /,并切换到此环境    

```
switch_root# mount -o remount,rw  /sysroot #让根目录下所有数据，可以读也可以写入
sh-4.4# chroot /sysroot  #切换环境，切换到硬盘操作系统的环境
```

 

##### 3)重新设置root的密码 

```
sh-4.4# echo 1  |  passwd  --stdin root
```

##### 4)如果SELinux是强制模式，才需要重设SELinux策略（其他模式不需要做此操作）

```
sh-4.4# vim  /etc/selinux/config #查看SELinux开机的运行模式

sh-4.4# touch /.autorelabel  #SELinux是强制模式，让SELinux失忆
```

##### 5)强制重启系统完成修复

```
sh-4.4# reboot -f 
```

### 八、 构建基本的Web服务

 Web服务：提供网页内容的服务

 Web服务器：提供网页内容的服务机器

 实现web服务软件：httpd  nginx  tomcat

 http协议:超文本传输协议

 

虚拟机A：

#### 1.安装httpd软件

```
[root@svr7 ~]# yum  -y  install  httpd
```

#### 2.写一个网页文件

```
[root@svr7 ~]# vim   /var/www/html/index.html

hahaxixihehelele哈哈嘻嘻         
```

#### 3.运行httpd程序

```
[root@svr7 ~]# > /etc/resolv.conf   #清空文件内容，加快启用

[root@svr7 ~]# /usr/sbin/httpd    #绝对路径方式运行程序

[root@svr7 ~]# pgrep -l httpd     #查看httpd进程

[root@svr7 ~]# killall httpd       #停下httpd进程

[root@svr7 ~]# pgrep -l httpd

[root@svr7 ~]# /usr/sbin/httpd    #绝对路径方式运行程序

[root@svr7 ~]# firefox http://192.168.4.7  #图形浏览器

[root@svr7 ~]# curl  http://192.168.4.7   #命令行浏览器

hahaxixihehelele哈哈嘻嘻
```

### 九、 防火墙管理

 作用：隔离，严格过滤入站，放行出站

 硬件防火墙：保护一个网络中所有机器

 软件防火墙：保护本机

 

> • 管理工具：firewall-cmd(命令)、firewall-config(图形工具)
>
> • 根据所在的网络场所区分，预设保护规则集
>
> • public：仅允许访问本机的ssh、dhcp、ping服务
>
> • trusted：允许任何访问
>
> • block：拒绝任何来访请求，有明确的回应
>
> • drop：丢弃任何来访的数据包，没有明确的回应

 

#### • 防火墙判定的规则：

#####  1.查看请求中源IP地址，查看自己所有区域，哪个区域有该源IP地址规则，则进入哪个区域

#####  2.进入默认区域（默认情况下为public）

 

#### **修改默认区域**

虚拟机A：

```
[root@svr7 ~]# rpm -q  firewalld  #防火墙软件

firewalld-0.4.4.4-14.el7.noarch
```

虚拟机A        

```
]# firewall-cmd  --get-default-zone   #查看默认区域
```

虚拟机B

```
[root@pc207 /]#  ping  -c  2  192.168.4.7   #成功

[root@pc207 /]#  curl  http://192.168.4.7  #失败
```

 

虚拟机A

```
]# firewall-cmd  --set-default-zone=trusted   #修改默认区域
```

虚拟机B

```
[root@pc207 /]#  ping -c 2 192.168.4.7   #成功

[root@pc207 /]#  curl  http://192.168.4.7  #成功
```



####  **区域中添加允许的协议**

虚拟机A：

```
]# firewall-cmd  --set-default-zone=public  #修改默认区域

]# firewall-cmd  --get-default-zone   #查看默认区域

]# firewall-cmd  --zone=public  --list-all  #查看区域规则

]# firewall-cmd  --zone=public  --add-service=http  #添加协议

]# firewall-cmd  --zone=public  --list-all   #查看区域规则
```

 

虚拟机B

```
[root@pc207 /]#  curl http://192.168.4.7   #访问成功

hahaxixihehelele哈哈嘻嘻

[root@pc207 /]#
```

 

 

####  **永久规则**

**–** **永久（--permanent）**

**–** **默认区域的修改，默认就是永久的**

**虚拟机A：**

```
]# firewall-cmd  --reload     #重新加载防火墙永久的配置

]# firewall-cmd  --zone=public  --list-all   #查看区域规则

]# firewall-cmd  --permanent --zone=public  --add-service=http     #永久规则

 

]# firewall-cmd  --zone=public  --list-all  #查看区域规则 

]# firewall-cmd  --reload   #重新加载防火墙永久的配置 

]# firewall-cmd  --zone=public  --list-all   #查看区域规则 
```

 

####  **单独拒绝192.168.4.207所有访问，允许其他机器**

##### 防火墙判定的规则：

 1.查看请求中源IP地址，查看自己所有区域，哪个区域有该源IP地址规则，则进入哪个区域

 2.进入默认区域（默认情况下为public）

虚拟机A

.添加源IP地址规则

```
]# firewall-cmd --zone=block   --add-source=192.168.4.207

]# firewall-cmd --get-default-zone  #查看默认区域

public
```

虚拟机B

```
]# curl http://192.168.4.7  #访问失败
```



### 课后习题：

#### 案例1：设置SELinux运行模式

为虚拟机A、虚拟机B 配置SELinux 

 1）确保 SELinux 处于宽松模式（permissive） 

 2）在每次重新开机后，此设置必须仍然有效

```
虚拟机A
[root@svr7 ~]# setenforce  0  #当前关闭SELinux
[root@svr7 ~]# getenforce     #查看当前SELinux运行模式
Permissive
[root@svr7 ~]# vim  /etc/selinux/config  
SELINUX=permissive
虚拟机B同上
```



#### 案例2：实现虚拟机A 的Web服务

 1）利用httpd软件搭建Web服务，页面显示内容为 小蝌蚪找妈妈 

```
[root@svr7 ~]# yum -y install httpd
[root@svr7 ~]# vim /var/www/html/index.html
小蝌蚪找妈妈
[root@svr7 ~]# systemctl  restart  httpd
```



#### 案例3：实现虚拟机A 的防火墙配置

 1）修改虚拟机A防火墙配置，明确拒绝所有客户端访问(默认区域修改block)

```
[root@svr7 ~]# firewall-cmd --set-default-zone=block
```

 2）在虚拟机B上,测试能否访问虚拟机A 的Web服务

```
[root@pc207 ~]# curl http://192.168.4.7
```

 3）在虚拟机B上,测试能否 ping通 虚拟机A

```
[root@pc207 ~]# ping -c 2 192.168.4.7
```



#### 案例4：实现虚拟机A 的防火墙配置

 1）修改虚拟机A防火墙配置，将默认区域修改为public

```
[root@svr7 ~]# firewall-cmd --get-default-zone  #查看默认区域
[root@svr7 ~]# firewall-cmd --set-default-zone=public  #修改默认区域
```

 2）在虚拟机B上,测试能否访问虚拟机A 的Web服务

```
[root@pc207 ~]# curl http://192.168.4.7
```

 3）在虚拟机B上,测试能否 ping通 虚拟机A

```
[root@svr7 ~]# ping -c 2 192.168.4.7
```



#### 案例5：实现虚拟机A的防火墙配置

 1）修改虚拟机A防火墙配置，将默认区域修改为public

```
[root@svr7 ~]# firewall-cmd --get-default-zone   #查看默认区域
[root@svr7 ~]# firewall-cmd --set-default-zone=public  #修改默认区域
```

 2）修改虚拟机A永久的防火墙配置，在public区域中添加http协议

```
[root@svr7 ~]# firewall-cmd --permanent --zone=public --add-service=http
[root@svr7 ~]# firewall-cmd --reload  #重新加载防火墙所有永久配置
[root@svr7 ~]# firewall-cmd  --zone=public  --list-all
```

 3）在虚拟机B上,测试能否访问虚拟机A 的Web服务

```
[root@pc207 ~]# curl http://192.168.4.7
```

------

# ENGINEER-周考

1、【单选题】
(单选题)下面关于IP地址的组成正确的是（  ）
A.IP地址由48个二进制数组成 
B.IP地址由40个十进制组成 
C.IP地址由32个十进制数组成 
D.IP地址由32个二进制数组成 
【正确答案】D
【答案解析】

2、【单选题】
(单选题)在Linux系统中，yum仓库的配置文件存放在/etc/yum.repos.d/目录下，一般以（ ）结尾
A..tar.gz 
B..yum 
C..bz2 
D..repo 
【正确答案】D
【答案解析】yum客户端文件必须以.repo结尾

3、【单选题】
(单选题)创建卷组是如何指定PE大小( )
A.vgcreate -s PE大小 卷组名  空闲分区 
B.lvcreate -s PE大小 卷组名  空闲分区 
C.vgextend -s PE大小 卷组名  空闲分区 
D.lvextend  -s PE大小 卷组名  空闲分区 
【正确答案】A
【答案解析】lvcreate为创建逻辑卷，lvextend为扩展逻辑卷，在创建及扩展
逻辑卷时，均不能指定PE大小，vgextend为扩展卷组，扩展卷组时也不
能指定PE大小

4、【单选题】
(单选题)在Linux系统中，若要实现开机自动挂载文件系统，需要修改（ ）
配置文件。
A./etc/startup 
B./etc/mount 
C./etc/auto.master 
D./etc/fstab 
【正确答案】D
【答案解析】/etc/auto.master为autofs触发挂载配置文件

5、【单选题】
(单选题)在Linux系统删除一个组的命令应该是什么( )
A.userdel 
B.groupdel 
C.usermod 
D.groupmod 
【正确答案】B
【答案解析】groupmod修改组属性，userdel删除用户，usermod修改用户属性

6、【单选题】
(单选题)Mariadb监听的端口号是多少(  )
A.3306 
B.3389 
C.3260 
D.21 
【正确答案】A
【答案解析】3389为windows远程管理，3260位ISCSI共享存储，21位
FTP文件传输

7、【单选题】
(单选题)使用cp命令时以下说法正确的是（）
A.cp  -f 不可以拷贝文件 
B.cp  -rf 可以拷贝文件和目录 
C.cp  -f 可以拷贝目录 
D.cp  -r 可以拷贝文件，但不能拷贝目录 
【正确答案】B
【答案解析】cp命令-r选项可以拷贝目录，-f选项代表强制在cp命令运用中
由于有别名的存在所以-f无任何效果

8、【单选题】
(单选题)使用命令（  ）可以查看后台所有的进程，并且输出进程的PID
A.jobs -l 
B.bg 
C.fg 
D.jobs 
【正确答案】A
【答案解析】无

9、【单选题】
(单选题)在Linux系统中，使用lvextend命令为指定的逻辑卷动态扩容以后，
通过df命令查看时该分区显示的大小并未变化，还需要进行（ ）操作
以便系统能够更新ext4文件系统大小。
A.mount 
B.lvscan 
C.resize2fs 
D.partprobe 
【正确答案】C
【答案解析】partprobe为刷新分区表，lvscan为查看逻辑卷信息，mount为mount 挂载

10、【单选题】
(单选题)下面关于列出内核版本命令正确的是（）
A.uname     -r 
B.lscpu  
C.cat    /etc/redhat-release 
D.cat   /proc/meminfo 
【正确答案】A
【答案解析】lscpu查看CPU信息，cat    /etc/redhat-release是查看系统
具体版本，cat   /proc/meminfo是查看内存信息，查看内核版本为
uname  -r

11、【单选题】
(单选题)在Linux系统中，以下（ ）文件用来记录用户账号的用户名、家目录、登
录Shell等信息
A./etc/passwd 
B./etc/bashrc 
C./root/.bashrc 
D./etc/shadow 
【正确答案】A
【答案解析】/etc/passwd存放用户基本信息，/root/.bashrc定义root自定义初始化信息例如别名定义、变量定义等，/etc/shadow保存用户密码 信息，/etc/bashrc为全局配置文件

12、【单选题】
(单选题)快捷键Esc+.代表什么意思( )
A.输出上一个命令的参数 
B.清空至行尾 
C.清空整个屏幕 
D.清空至行首 
【正确答案】A
【答案解析】清空整个屏幕为Ctrl+l，清空至行尾为Ctrl+k，清空至行首为Ctrl+u

13、【单选题】
(单选题)在一台Linux服务器上，使用Apache作为Web服务程序，服务器
名称是www.tarena.com，管理员把所有对外提供的文档放
在/usr/local/source目录下面，希望远程用户在浏览器中使用
http://www.tarena.com地址即能访问这些文档，他需要对
Apache进行（ ）设置。
A.修改Apache配置文件httpd.conf中的Listen的值为8000 
B.修改Apache配置文件httpd.conf中的ServerRoot项值为“/usr/local/source” 
C.修改Apache配置文件httpd.conf中的DocumentRoot项值为“/usr/local/source” 
D.安装Apache服务器在/usr/local/目录下即可 
【正确答案】C
【答案解析】A选项安装目录与网页文件根路径无关，B选项指定httpd服务 配置文件根路径与网页文件根路径无关，D选项指定端口与网页文件根 路径无关

14、【单选题】
(单选题)自定义yum源时可以利用（  ）命令生成仓库数据文件
A.yumrepo 
B.createrepo 
C.yum-repo 
D.addrepo 
【正确答案】B
【答案解析】无

15、【单选题】
(单选题)下列对于IP地址的作用和配置方法，描述正确的是(   )
A.在一个局域网中IP地址可以重复 
B.IP地址可以唯一标识一台主机 
C.IP地址只能手工配置 
D.IP地址只要配置DHCP自动获取，即可成功获取IP地址 
【正确答案】B
【答案解析】在局域网中IP地址不可重复；IP也可以通过DHCP自动获取 ；DHCP自动获取IP，需要局域网中具备DHCP服务器

16、【单选题】
(单选题)Windows查看IP地址的命令为（  ）
A.ifconfig 
B.ipconfig 
C.ipconf 
D.ifconf 
【正确答案】B
【答案解析】

17、【单选题】
(单选题)set GID中附加权限S 与s的有什么差别( )
A.有执行权限为s 没有执行权限为S 
B.没有差别 
C.S比s权限低 
D.S比s权限更高 
【正确答案】A
【答案解析】SGID附加权限，会叠加在所属组的执行权限位置，当所属组有执行权限显示为s，所属组没有执行权限显示为S

18、【单选题】
(单选题)使用tar命令打包文档时如果包的结尾是.tar.xz那么打包时用（ ）选项
A.-Jcf  
B.-Pzcf 
C.-jcf 
D.-zcf 
【正确答案】A
【答案解析】-zcf归档文件为.tar.gz，-jcf归档文件为.tar.bz2，-P代表绝对
路径归档

19、【单选题】
(单选题)postfix默认端口号是（ ）
A.110 
B.53 
C.23 
D.25 
【正确答案】D
【答案解析】23为telnet远程管理，53位DNS域名解析，110位pop3用户 收邮件协议

20、【单选题】
(单选题)在vim编辑器的（  ）模式中可以实现录入、退格等编辑操作
A.退出模式 
B.输入模式 
C.末行模式 
D.命令模式 
【正确答案】B
【答案解析】无

21、【单选题】
(单选题)在/etc目录（含子目录）下查找文件名包含"passwd"的文件，可以执行
（ ）操作
A.ls  /etc | grep 'passwd' 
B.find /etc -name "passwd*" 
C.find /etc -name "*passwd*" 
D.ls -A /etc | grep '*passwd*' 
【正确答案】C
【答案解析】find本身会对查找路径，进行递归查找。grep命令本身默认为模糊匹配，不能用通配符

22、【单选题】
(单选题)在pxe一键装机中客户端由网卡pxe启动完毕后，主机引导权交给（  ）
A.syslinux 
B.pxelinux.0 
C.passwd
D.shadow
【正确答案】B
【答案解析】无

23、【单选题】
(单选题)在常见的Linux日志文件中，以下哪个文件（  ）的作用是记录与系统启动
相关的消息
A./var/log/secure 
B./var/log/maillog 
C./var/log/messages 
D./var/log/dmesg 
【正确答案】D
【答案解析】/var/log/messages记录各种服务公共消息，/var/log/secure记录用户登录安全相关，/var/log/maillog邮件收发相关信息

24、【单选题】
(单选题)想把一个用户加入到组下的命令是什么 （ ）
A.gpasswd -a 组名 用户名 
B.gpasswd -a 用户名 组名 
C.gpasswd -add 用户名 组名 
D.gpasswd -in 用户名 组名 
【正确答案】B
【答案解析】gpasswd -a 用户名 组名，为正确格式。-add与-in无此选项

25、【单选题】
(单选题)安装DNS服务的软件包名是(   )
A.bind bind-chroot 
B.named 
C.name 
D.DNS 
【正确答案】A
【答案解析】named为服务 名

26、【单选题】
(单选题)在Linux系统中，若执行 scp dumb bilbo@www.foobar.com: 命令，
可以实现（  ）功能
A.将远程服务器www.foobar.com 上用户“bilbo”主目录下的一个名为 “dumb”的文件拷贝到本地计算机当前目录下，并且登录远程服务器上的账号名为 “bilbo” 
B.将本地计算机“dumb”目录下所有的文件拷贝到远程服务器 www.fobar.com的根目录下，并且登录远程服务器上的密码为“bilbo” 
C.将本地计算机当前目录下的一个名为“dumb”的文件发送到邮件 bilbo@www.foobar.com 
D.将本地计算机当前目录下的一个名为“dumb”的文档拷贝到远程主机www.foobar.com中用户 “bilbo”的主目录下 
【正确答案】D
【答案解析】无

27、【单选题】
(单选题)配置Postfix邮件服务时，以下（ ）参数表示外发邮件时的发件域地址
A.mydestination 
B.myorigin 
C.mydomain 
D.inet_interfaces 
【正确答案】B
【答案解析】inet_interfaces指定网络接口，mydomain指定本机域名，mydestination指定收件人域名 为本域邮件

28、【单选题】
(单选题)日志文件存放的路径是（  ）
A./etc/log 
B./tmp/log 
C./dev/log 
D./var/log 
【正确答案】D
【答案解析】/var/log为日志文件存放的路径。其他的选项均为错误路径

29、【单选题】
(单选题)关于硬RAID实现的方式，以下说法正确的是（  ）
A.主板—>操作系统—>磁盘—>阵列卡—>数据 
B.主板—>磁盘—>操作系统—>阵列卡—>数据 
C.主板—>磁盘—>阵列卡—>操作系统—>数据 
D.主板—>阵列卡—>磁盘—>操作系统—>数据 
【正确答案】D
【答案解析】服务器是同过阵列卡来识别磁盘，识别硬盘后才可以安装操作 系统或读取操作系统数据

30、【单选题】
(单选题)在安装并配置了DHCP服务之后，以下（  ）操作可以使配置生效
A.systemctl enable dhcpd 
B.systemctl status dhcpd 
C.systemctl stop dhcpd 
D.systemctl restart dhcpd 
【正确答案】D
【答案解析】无

31、【单选题】
(单选题)SSH远程登录服务使用的默认端口是（ ）
A.80 
B.69 
C. 22 
D.23 
【正确答案】C
【答案解析】80为http，23为telnet，69位tftp

32、【单选题】
(单选题)配置bind域名服务时，管理员执行了cp -p /var/named/named.localhost  /var/named/tedu.cn.zone操作，
其中选项-p的作用是（  ）
A.递归拷贝 
B.拷贝目录 
C.保持原文件属性不变 
D.拷贝连接 
【正确答案】C
【答案解析】-p选项是在拷贝是保持源文件属性不变

33、【单选题】
(单选题)在常见的RAID级别中，（  ）的设备冗余度最好，也称为镜像模式
A.RAID1 
B.RAID6 
C.RAID0 
D.RAID5 
【正确答案】A
【答案解析】RAID0为条带模式无冗余，RAID5采用校验算法进行 可靠性的提升，RAID6为RAID5的提升

34、【单选题】
(单选题)在配置DNS服务的时候，正向解析记录的资源类型是（  ）
A.PTR 
B.SOA 
C.A 
D.CNAME 
【正确答案】C
【答案解析】PTR代表方向解析记录，CNAME代表解析记录别名，SOA代表授权记录

35、【单选题】
(单选题)vim有几种工作模式( )
A.2种 
B.7种 
C.3种 
D.5种 
【正确答案】C
【答案解析】vim模式分为命令模式、输入模式、末行模式

36、【单选题】
(单选题)某公司有www.google.com和www.goojie.com两个站点，使用相同
的公网IP地址，若要在一台Linux主机中提供两个站点的Web服务，可
采用的最佳方案为（ ）
A.安装一个httpd软件包，为两个Web站点指定基于IP地址的虚拟主机 
B.安装一个httpd软件包，为两个Web站点配置基于域名的虚拟主机 
C.安装一个httpd软件包，使用httpd1.conf、httpd2.conf两个独立配置文件 
D.安装两个httpd软件包，每个软件包对应一个Web站点 
【正确答案】B
【答案解析】本题考查虚拟Web主机功能，在一台Linux服务器上实现多个 网站，且域名不同。利用基于域名的虚拟Web主机即可实现

37、【单选题】
(单选题)在Linux系统中，执行（ ）命令可以把/dev/sdb6格式化成交换分区
A.mkfs  -t  ext3  /dev/sdb6 
B.mkswap /dev/sdb6 
C.fdisk /dev/sdb6 
D.format /dev/sdb6 
【正确答案】B
【答案解析】无

38、【单选题】
(单选题)使用vim编辑器时，要把一个文档内所有的年份“2007”替换成“2016”，
可以执行（   ）
A.:s/2007/2016/g 
B.:%s/2007/2016/all 
C.:s/2007/2016/all 
D.:%s/2007/2016/g 
【正确答案】D
【答案解析】无

39、【单选题】
(单选题)配置Postfix邮件服务时，通常应修改主配置文件（ ）
A./etc/postfix/master.conf 
B./etc/postfix/mail.conf 
C./etc/postfix/main.cf 
D./etc/postfix/main.conf 
【正确答案】C
【答案解析】无

40、【单选题】
(单选题)使用grep过滤时选项（）可以忽略大小写
A.-v  
B.-i 
C.^ 
D.$  
【正确答案】B
【答案解析】-v为取反查找，^为匹配以字符串开头，$为匹配以字符串结尾

41、【多选题】
把命令cp /ISO/1.txt /mnt无论状态如何，放入后台的命令是( )
A.Ctrl+C 
B.cp /ISO/1.txt  /mnt $ 
C.cp /ISO/1.txt  /mnt& 
D.快捷键Ctrl+z 
【正确答案】C,D
【答案解析】无

42、【多选题】
(多选题)关于Linux系统的常见目录，以下描述正确的是（  ）
A./dev目录用来存放配置文件 
B./root目录是所有用户的家目录 
C./boot目录用来存放启动相关文件 
D./tmp是临时目录 
【正确答案】C,D
【答案解析】无

43、【多选题】
(多选题)常见的数据库软件有（ ）
A.DB2 
B.SQL Server 
C.virtualbox 
D.MySQL 
【正确答案】A,B,D
【答案解析】

44、【多选题】
(多选题)Linux典型的文件系统类型有（     ）
A.NTFS  
B.ext4 
C.swap 
D.xfs 
【正确答案】B,C,D
【答案解析】RHEL6默认的文件系统为ext4，RHEL7默认的文件系统为 xfs，Linux交换文件系统为swap，Windows一般为NTFS文件系统

45、【多选题】
(多选题)在Linux系统中，用户root依次执行下列操作：  
chmod  777  /dir；chmod o+t /dir；touch /dir/root.file ， 
则可知（  ）
A.普通账户可以在/dir目录下创建文件 
B.普通账户可删除/dir目录下的所有文件 
C.普通账户可以删除文件root.file 
D.普通账户可以删除在/dir目录下自己创建的文件 
【正确答案】A,D
【答案解析】权限为777说明其他人具备rwx，所以可以新建文档，但由于 有t权限，该权限限制删除非本人的文档

46、【多选题】
(多选题)关于Linux命令行环境的通配符，以下描述正确的是（ ）
A.* 匹配单个字符 
B.{a,min,xy} 分别匹配不连续的a,min,xy多组字符 
C.？匹配任意多个字符 
D.[a-z] 匹配连续多个字符a-z中的一个 
【正确答案】B,D
【答案解析】*匹配任意多个字符，？匹配单个字符

47、【多选题】
(多选题)安装源码包时需要安装编译工具有（  ）
A.gcc 
B.C++	 
C.g++ 
D.make 
【正确答案】A,D
【答案解析】无

48、【多选题】
(多选题)vim编辑器中调到首行的快捷键是(   )
A.1g 
B.1G 
C.gg 
D.GG 
【正确答案】B,C
【答案解析】GG跳转到末行，1g无作用

49、【多选题】
(多选题)杀死一个进程的方式有(   ) 
A.pkill -9 -u  用户名 
B.Ctrl+z 
C.killall -9 进程名 
D.kill -9 PID	 
【正确答案】C,D
【答案解析】Ctrl+z将进程或程序暂停放入后台，pkill -9 -u  用户名 杀死一个用户开启的 所有的进程

50、【多选题】
(多选题)在vim编辑器的（ ）工作模式中可以实现保存退出的操作
A.修改模式 
B.输入模式 
C.末行模式 
D.命令模式 
【正确答案】C,D
【答案解析】命令模式可以利用ZZ，末行模式为：wq



# SERVICES

## 01：KVM构建及管理、virsh控制工具、镜像管理、虚拟机快建技术

### 一、服务管理

#### •上帝进程：systemd

#### •Linux系统和服务管理器

–是内核引导之后加载的第一个初始化进程（PID=1）

–负责掌控整个Linux的运行/服务资源组合

 

#### •一个更高效的系统&服务管理器

–开机服务并行启动，各系统服务间的精确依赖

–配置目录：/etc/systemd/system/

–服务目录：/lib/systemd/system/

–主要管理工具：systemctl

```
[root@svr7 ~]# systemctl  -t  service  --all  #列出所有的服务
```

 

#### •对于服务的管理

> systemctl  restart  服务名 	 #重起服务
>
> systemctl  start  服务名 		#开启服务 
>
> systemctl  stop  服务名 		#停止服务
>
> systemctl  status  服务名		 #查看服务当前的状态
>
>
> systemctl  enable  服务名 		#设置服务开机自启动
>
> systemctl  disable  服务名 		#设置服务禁止开机自启动
>
> systemctl  is-enabled  服务名	 #查看服务是否开机自启

```
[root@svr7 ~]# killall httpd       #杀死手动启动的httpd

[root@svr7 ~]# yum  -y  install  httpd

[root@svr7 ~]# > /etc/resolv.conf    #加快httpd服务启动

[root@svr7 ~]# systemctl  restart  httpd #重启httpd服务

[root@svr7 ~]# systemctl  status  httpd  #查看服务httpd状态

[root@svr7 ~]# systemctl  enable  httpd #设置httpd开机自启动

Created symlink from /etc/systemd/system/multi-user.target.wants/httpd.service to /usr/lib/systemd/system/httpd.service.

 

[root@svr7 ~]# systemctl is-enabled httpd #查看httpd是否是开机自启动

[root@svr7 ~]# systemctl disable httpd  #关闭httpd开机自启动

Removed symlink /etc/systemd/system/multi-user.target.wants/httpd.service.

[root@svr7 ~]# systemctl is-enabled httpd
```



####  **管理运行级别**

RHEL6:运行级别 300

0：关机    0个服务

1：单用户模式（基本功能的实现，破解Linux密码）   50个服务

2：多用户字符界面（不支持网络）    80个服务

***\*3：多用户字符界面（支持网络）服务器默认的运行级别\****  100个服务

4：未定义    0个服务

***\*5：图形界面    300个服务\****

6：重起      0个服务

> 切换运行级别：init  数字 

 



#### RHEL7：运行模式（运行级别）  

> 字符模式：multi-user.target
>
> 图形模式：graphical.target

 

 当前直接切换到字符模式 

```
[root@svr7 /]# systemctl  isolate  multi-user.target   #相当于原来的init  3
```

 当前直接切换到图形模式

```
[root@svr7 /]# systemctl  isolate  graphical.target   #相当于原来的init  5
```

 

查看每次开机默认进入模式

```
[root@svr7 /]# systemctl  get-default
```

设置永久策略，每次开机自动进入multi-user.target 

```
[root@svr7 /]# systemctl  set-default  multi-user.target 

[root@svr7 /]# reboot 
```

 

###  二、虚拟机A环境准备



#### 1.关机虚拟机A

#### 2.修改内存大小，建议6G

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps1.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps2.jpg) 

 

#### 3.添加一块新的硬盘50G

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps3.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps4.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps5.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps6.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps7.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps8.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps9.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps10.jpg) 

 

#### 4.CPU开启虚拟化功能

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps11.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps12.jpg) 

#### 5.开启虚拟机



### 三 、空间规划

#### 情况一：根设备为逻辑卷

```
[root@svr7 ~]# vgextend centos /dev/sdb  #扩展卷组

 Physical volume "/dev/sdb" successfully created.

 Volume group "centos" successfully extended

[root@svr7 ~]# vgs  #查看卷组信息

 

[root@svr7 ~]# lvextend -L 40G /dev/centos/root  #扩展空间

[root@svr7 ~]# lvs   #查看逻辑卷空间大小

[root@svr7 ~]# xfs_growfs  /dev/centos/root  #刷新文件系统

[root@svr7 ~]# df -h  #查看文件系统的大小
```

 

#### 情况二：根设备为基本分区

```
[root@svr7 ~]# fdisk  /dev/sdb

命令(输入 m 获取帮助)：n

Partition type:

p primary (0 primary, 0 extended, 4 free)

e extended

Select (default p): #回车

Using default response p

分区号 (1-4，默认 1)： #回车

起始 扇区 (2048-83886079，默认为 2048)： #回车

将使用默认值 2048

Last 扇区, +扇区 or +size{K,M,G} (2048-83886079，默认为 83886079)： #回车

将使用默认值 83886079

分区 1 已设置为 Linux 类型，大小设为 50 GiB

命令(输入 m 获取帮助)：w #保存并退出

The partition table has been altered!

Calling ioctl() to re-read partition table.

正在同步磁盘。

[root@svr7 ~]# lsblk 

[root@svr7 ~]# mkfs.xfs  /dev/sdb1 #格式化文件系统

[root@svr7 ~]# mkdir  /iso

[root@svr7 ~]# mount  /dev/sdb1  /iso

[root@svr7 ~]# vim  /etc/fstab 

/dev/sdb1  /iso  xfs  defaults  0 0

[root@svr7 ~]# umount  /iso #卸载设备

[root@svr7 ~]# df  -h

[root@svr7 ~]# mount -a #检测/etc/fstab是否书写正确

[root@svr7 ~]# df -h
```

### 四、 传递系统光盘镜像文件    

```
[root@svr7 ~]# mkdir  /iso       
```

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps13.jpg) 

```
[root@svr7 ~]# du -sh  /iso/

8.8G	 /iso/

[root@svr7 ~]# ls  /iso/

CentOS7-1804.iso

[root@svr7 ~]#
```

 

### 五、Linux平台构建虚拟化

 

#### • KVM虚拟化主要软件包

> – qemu-kvm :为 kvm 提供底层仿真支持
>
> – libvirt-daemon :libvirtd 守护进程，管理虚拟机
>
> – libvirt-client :用户端软件，提供客户端管理命令
>
> – libvirt-daemon-driver-qemu :libvirtd 连接 qemu 的驱动
>
> – virt-manager :图形管理工具

```
[root@svr7 ~]# yum -y install qemu-kvm

[root@svr7 ~]# yum -y install libvirt-daemon

[root@svr7 ~]# yum -y install libvirt-client #***

[root@svr7 ~]# yum -y install libvirt-daemon-driver-qemu

[root@svr7 ~]# yum -y install virt-manager #***

 

[root@svr7 ~]# virt-manager  #开启虚拟机图形管理工具
```

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps14.jpg) 

 

### 六、新建虚拟机

```
[root@svr7 ~]# virt-manager  #开启虚拟机图形管理工具
```

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps15.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps16.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps17.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps18.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps19.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps20.jpg) 

安装系统

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps21.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps22.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps23.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps24.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps25.jpg) 

 

设置root的密码

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10808\wps26.jpg) 

 

### 七、管理虚拟机的命令

虚拟机A：KVM服务器

#### • 查看KVM节点（服务器）信息：virsh  nodeinfo

#### • 列出虚拟机: virsh  list  [--all]

```
[root@svr7 ~]# virsh list 

[root@svr7 ~]# virsh  shutdown  nsd01  #关闭虚拟机nsd01

[root@svr7 ~]# virsh list       #仅列出正在运行的虚拟机

[root@svr7 ~]# virsh list --all   #列出运行与关闭的所有虚拟机

[root@svr7 ~]# virsh  start nsd01   #开启虚拟机nsd01

[root@svr7 ~]# virsh list 
```

#### • 查看指定虚拟机的信息:virsh  dominfo  虚拟机名称

```
[root@svr7 ~]# virsh dominfo nsd01

[root@svr7 ~]# virsh autostart  nsd01   #设置开机自启动

[root@svr7 ~]# virsh dominfo nsd01
```

 

```
[root@svr7 ~]# virsh autostart  nsd01  --disable  #禁止开启自启动

[root@svr7 ~]# virsh dominfo nsd01
```

#### • 强制关闭指定的虚拟机: virsh  destroy  虚拟机名称

```
[root@svr7 ~]# virsh  destroy  nsd01

域 nsd01 被删除

[root@svr7 ~]# virsh  list  --all
```



### 八、KVM虚拟机的组成

> – xml配置文件：定义虚拟机的名称、UUID、CPU、内存、虚拟磁盘、网卡等各种参数设置
>
> /etc/libvirt/qemu：xml配置文件默认存放路径
>
>  
>
> – 磁盘镜像文件：保存虚拟机的操作系统及文档数据，镜像路径取决于xml配置文件中的定义
>
> /var/lib/libvirt/images/:磁盘镜像文件默认存放路径

### 九、命令行手动克隆虚拟机

#### 1.产生新的磁盘镜像文件

```
[root@svr7 ~]# virsh  destroy  nsd01  #强制关闭虚拟机

[root@svr7 ~]# virsh  list  --all

[root@svr7 ~]# cd  /var/lib/libvirt/images/

[root@svr7 images]# cp  nsd01.qcow2  nsd02.qcow2

[root@svr7 images]# ls

nsd01.qcow2   nsd02.qcow2

[root@svr7 images]#
```

#### 2.建立xml配置文件 

```
[root@svr7 /]# cd  /etc/libvirt/qemu/

[root@svr7 qemu]# cp  nsd01.xml  nsd02.xml

[root@svr7 qemu]# ls

autostart  networks  nsd01.xml  nsd02.xml

[root@svr7 qemu]# vim  /etc/libvirt/qemu/nsd02.xml

 虚拟机的名字：<name>nsd02</name>

 虚拟机UUID整行删除：<uuid>1b0f……….535</uuid>

 磁盘镜像文件路径：<source file='/var/lib/libvirt/images/nsd02.qcow2'/>

 网卡的MAC地址整行删除： <mac address='52:5……….:cb'/>
```

#### 3．导入xml配置文件 

```
]# virsh define  /etc/libvirt/qemu/nsd02.xml   #导入

]# virsh list --all    #显示系统所有虚拟机

]# virsh start nsd02  #开启nsd02虚拟机

]# virt-manager     #开启图形虚拟机管理工具

]# virsh destroy nsd02  #强制关闭   
```



### 十、命令行手动克隆虚拟机（再来一遍）

#### 1.产生新的磁盘镜像文件

```
[root@svr7 ~]# virsh  destroy  nsd01  #强制关闭虚拟机

[root@svr7 ~]# cd  /var/lib/libvirt/images/

[root@svr7 images]# cp  nsd01.qcow2  dc01.qcow2

[root@svr7 images]# ls
```

#### 2.建立xml配置文件 

```
[root@svr7 /]# cd  /etc/libvirt/qemu/

[root@svr7 qemu]# cp  nsd01.xml  dc01.xml

[root@svr7 qemu]# vim  /etc/libvirt/qemu/dc01.xml

 虚拟机的名字：<name>dc01</name>

 虚拟机UUID整行删除：<uuid>1b0f……….535</uuid>

 磁盘镜像文件路径:<source file='/v………/es/dc01.qcow2'/>

 网卡的MAC地址整行删除：<mac address='52:5……….:cb'/>
```

#### 3．导入xml配置文件 

```
]# virsh define  /etc/libvirt/qemu/dc01.xml   #导入

]# virsh list --all    #显示系统所有虚拟机

]# virsh start dc01  #开启dc01虚拟机

]# virt-manager     #开启图形虚拟机管理工具

]# virsh destroy dc01  #强制关闭
```



### 十一、命令行手动克隆虚拟机（再再来一遍）

#### 1.产生新的磁盘镜像文件

```
[root@svr7 ~]# virsh  destroy  nsd01  #强制关闭虚拟机

[root@svr7 ~]# cd  /var/lib/libvirt/images/

[root@svr7 images]# cp  nsd01.qcow2  stu01.qcow2

[root@svr7 images]# ls
```

#### 2.virsh edit 三合一命令（建立、修改、导入）

```
[root@svr7 images]# virsh  edit  nsd01    #以nsd01为模板

 虚拟机的名字：<name>stu01</name>

 虚拟机UUID整行删除：<uuid>1b0f……….535</uuid>

 磁盘镜像文件路径:<source file='/v………/es/stu01.qcow2'/>

 网卡的MAC地址整行删除：<mac address='52:5……….:cb'/>

[root@svr7 images]# virsh  list  --all  
```

### 十二、快速建立新的虚拟机

COW：写时复制

> •  Copy On Write，写时复制
>
> – 直接映射原始盘(后端盘)的数据内容
>
> – 原始盘(后端盘)内容不变，并且不能修改原始盘内容，否则所有前端盘无法使用
>
> – 对前端盘的修改不回写到原始盘
>
>  
>
> • qemu-img 通过 -b 选项复用指定后端盘
>
> – qemu-img  create  -f  qcow2  -b  后端盘   前端盘

#### 1.产生新的磁盘镜像文件

```
]# cd  /var/lib/libvirt/images/

]# qemu-img create  -f   qcow2  -b  nsd01.qcow2  tc01.qcow2

]# qemu-img  info  tc01.qcow2   #查看前端盘信息

………

virtual size: 9.0G (9663676416 bytes)   #虚拟大小

disk size: 196K      #占用磁盘空间真正的大小

backing file: nsd01.qcow2     #原始盘

……….
```

 

#### 2.virsh edit 三合一命令（建立、修改、导入）

```
[root@svr7 images]# virsh  edit  nsd01    #以nsd01为模板

 虚拟机的名字：<name>tc01</name>

 虚拟机UUID整行删除：<uuid>1b0f……….535</uuid>

 磁盘镜像文件路径:<source file='/v………/es/tc01.qcow2'/>

 网卡的MAC地址整行删除：<mac address='52:5……….:cb'/>

[root@svr7 images]# virsh  list  --all  

[root@svr7 images]# virsh start  tc01

[root@svr7 images]# virt-manager
```



#### **离线访问虚拟机**

• 使用 guestmount 工具

– 支持离线挂载 raw、qcow2 格式虚拟机磁盘

– 可以在虚拟机关机的情况下，直接修改磁盘中的文档

– 方便对虚拟机定制、修复、脚本维护

​     !!! 需要注意 SELinux 机制的影响

 

• 基本用法

guestmount  -a  虚拟机磁盘路径  -i  /挂载点

```
]# guestmount

bash: guestmount: 未找到命令...

]# yum  provides   */guestmount    #查看仓库中那个包产生

]# yum  -y  install  libguestfs-tools-c

]# virsh  destroy  tc01    #关闭虚拟机tc01

]# guestmount  -a  /var/lib/libvirt/images/tc01.qcow2  -i  /mnt/

]# ls  /mnt

]# umount  /mnt  #卸载
```



### 十三、修改用户家目录

```
[root@svr7 ~]# useradd  tom

[root@svr7 ~]# grep tom  /etc/passwd

[root@svr7 ~]# ls /home/


[root@svr7 ~]# usermod -d  /opt/mytom  tom

[root@svr7 ~]# grep  tom  /etc/passwd

[root@svr7 ~]# ls /opt/mytom

ls: 无法访问/opt/mytom: 没有那个文件或目录

 
[root@svr7 ~]# ls -A /etc/skel/   #用户家目录配置文件来源的模板目录

[root@svr7 ~]# cp  -r  /etc/skel/    /opt/mytom

[root@svr7 ~]# ls  -A   /opt/mytom

[root@svr7 ~]# chown  -R  tom:tom  /opt/mytom  #修改归属关系

[root@svr7 ~]# ls  -ld  /opt/mytom

[root@svr7 ~]# ls  -lA  /opt/mytom
```

------

## 02：Web基础应用、NFS服务基础、触发挂载

### 一、 两台虚拟机进行环境准备

#### 1.SELinux设置宽松模式

```
[root@svr7 ~]# setenforce  0  #设置当前系统SELinux为宽松

[root@svr7 ~]# getenforce     #查看当前系统SELinux模式

Permissive

[root@svr7 ~]# vim  /etc/selinux/config

SELINUX=permissive
```

2.防火墙设置

```
]# firewall-cmd  --set-default-zone=trusted
```



### 二、 Web服务器

• 基于 B/S （Browser/Server）架构的网页服务

– 服务端提供网页

– 浏览器下载并显示网页

• 实现Web服务的软件:httpd（Apache）、Nginx、tomcat

• Hyper Text Markup Language(html)，超文本标记语言

• Hyper Text Transfer  Protocol(http)，超文本传输协议



### 三、 构建Web服务

虚拟机A：

#### 1.安装httpd软件(Apache基金会)

```
[root@svr7 ~]# yum  -y  install  httpd
[root@svr7 ~]# rpm -q  httpd
```

#### 2.书写一个页面文件

```
]# ls  /var/www/html/
]# echo NSD2008 Web > /var/www/html/index.html
```

#### 3.重启httpd服务

```
]# > /etc/resolv.conf     #清空文件内容，加快httpd启动

]# systemctl restart httpd

]# curl  http://192.168.4.7     #测试访问

NSD2008 Web
```

### 四、 Web服务器配置

三步走：装包、配置、启服务

配置文件: /etc/httpd/conf/httpd.conf

排错思路：

```
[root@svr7 ~]# systemctl restart httpd    

Job for httpd.service failed because the control process exited with error code. See "systemctl status httpd.service" and "journalctl -xe" for details.

[root@svr7 ~]# journalctl  -xe
-- Unit httpd.service has begun starting up.
9月 16 10:22:10 svr7.tedu.cn httpd[12652]: ***AH00526: Syntax error on line 3 of /etc/httpd/conf/httpd.conf:***
9月 16 10:22:10 svr7.tedu.cn httpd[12652]: Invalid command 'configuration', perhaps misspelled or defined by a module not
9月 16 10:22:10 svr7.tedu.cn systemd[1]: httpd.service: main process exited, code=exited, status=1/FAILURE
9月 16 10:22:10 svr7.tedu.cn kill[12653]: kill: cannot find process ""
9月 16 10:22:10 svr7.tedu.cn systemd[1]: httpd.service: control process exited, code=exited status=1
9月 16 10:22:10 svr7.tedu.cn systemd[1]: Failed to start The Apache HTTP Server.
-- Subject: Unit httpd.service has failed
```

#### • 提供的默认配置

> – Listen：监听地址:端口（80）**
>
> – ServerName：本站点注册的DNS名称（空缺）**
>
> – DocumentRoot：网页根目录（/var/www/html）**
>
> – DirectoryIndex：起始页/首页文件名（index.html）

 

####  DocumentRoot：网页文件根目录（/var/www/html）

网页文件的根目录：存放网页文件的路径，也是httpd软件寻找网页文件的路径

虚拟机A

```
]# vim   /etc/httpd/conf/httpd.conf

此处省略一万字……
119行   DocumentRoot   "/var/www/myweb"
此处省略一万字……

]# mkdir  /var/www/myweb
]# echo wo shi myweb > /var/www/myweb/index.html
]# systemctl restart httpd  #重启httpd服务
]# curl http://192.168.4.7
wo shi myweb
```



#### 针对网页文件存放路径，具有访问控制

默认情况下子目录默认继承父目录的访问控制

除非针对子目录有单独的访问控制规则

默认情况下只有/var/www/下是允许所有人访问

```
<Directory  />          #针对/进行访问控制
  Require all denied   #拒绝所有客户端访问
</Directory>
```



```
<Directory  "/var/www">  #针对/var/www进行访问控制
  Require all granted   #允许所有客户端访问
</Directory>
```

 

虚拟机A：

```
[root@svr7 ~]# mkdir    /abc
[root@svr7 ~]# echo wo shi abc  >  /abc/index.html

[root@svr7 ~]# vim   /etc/httpd/conf/httpd.conf
此处省略一万字……
119行   DocumentRoot   "/abc"
此处省略一万字……
<Directory   "/abc">          #针对/abc进行访问控制
    Require  all  granted      #允许所有人访问
</Directory>
此处省略一万字……
[root@svr7 ~]# systemctl   restart   httpd
[root@svr7 ~]# curl  192.168.4.7
wo shi abc 
```

 

#### 实际路径与网络路径

实际路径：网页文件存放在服务器上路径

网络路径：在浏览器输入的路径



> 客户端 firefox  192.168.4.7--->http协议进行访问192.168.4.7--->服务端 由httpd软件进行接收--->DocumentRoot /abc--->/abc/index.html

网络路径: firefox  192.168.4.7

实际路径：/abc/

 

网络路径: firefox  192.168.4.7/nsd

实际路径：/abc/nsd

 

网络路径: firefox  http://192.168.4.7/abc/nsd/test

实际路径：/abc/abc/nsd/test



DocumentRoot /abc

网络路径: firefox  http://192.168.4.7/abc/nsd/test

实际路径：/abc/abc/nsd/test

 

虚拟机A：

```
[root@svr7 ~]# mkdir  /abc/nsd

[root@svr7 ~]# echo wo shi nsd > /abc/nsd/index.html

[root@svr7 ~]# curl  192.168.4.7/nsd/
```

 

####  Listen：监听地址:端口（80）

端口：数字编号，标识作用。标识程序与协议

 达外理发店：珠市口大街44号(IP地址)

​     理发师：10（端口）

​     http协议默认端口：80



```
客户端 firefox  192.168.4.7--->http协议进行访问192.168.4.7--->服务端 由httpd软件进行接收--->DocumentRoot /abc--->/abc/index.html
```



虚拟机A

```
[root@svr7 ~]# vim /etc/httpd/conf/httpd.conf
此处省略一万字……
42行  Listen  80
43行  Listen  8000
此处省略一万字……
[root@svr7 ~]# systemctl restart httpd
[root@svr7 ~]# curl  192.168.4.7
wo shi abc
[root@svr7 ~]# curl  192.168.4.7:8000    #指定端口号
wo shi abc
```



### 五、 Web服务器配置-虚拟Web主机

#### • 虚拟Web主机

– 由同一台服务器提供多个不同的Web站点

#### • 区分方式

– 基于域名的虚拟主机       

– 基于端口的虚拟主机

– 基于IP地址的虚拟主机

 

#### • 为每个虚拟站点添加配置

```
<VirtualHost  IP地址:端口>

  ServerName  此站点的DNS名称

  DocumentRoot  此站点的网页根目录

</VirtualHost>
```

#### • 配置文件路径

```
– /etc/httpd/conf/httpd.conf   #主配置文件

– /etc/httpd/conf.d/*.conf    #调用配置文件
```

虚拟机A：

1.建立调用配置文件

```
[root@svr7 ~]# vim   /etc/httpd/conf.d/nsd01.conf

<VirtualHost   *:80>      #启用虚拟Web主机的功能

 ServerName   www.baidu.com    #设置网站名称

 DocumentRoot   /var/www/baidu  #设置网页文件存放路径

</VirtualHost>           #配置结束

<VirtualHost   *:80>

 ServerName   www.qq.com

 DocumentRoot   /var/www/qq

</VirtualHost>

]# mkdir  /var/www/baidu

]# mkdir  /var/www/qq

]# echo woshi baidu > /var/www/baidu/index.html

]# echo woshi QQ > /var/www/qq/index.html

]# systemctl restart httpd
```

 

2.直接为本机提供域名解析/etc/hosts   

```
[root@svr7 ~]# vim   /etc/hosts

此处省略一万字……

192.168.4.7   www.qq.com   www.baidu.com

[root@svr7 ~]# curl  www.qq.com

woshi QQ

[root@svr7 ~]# curl  www.baidu.com

woshi baidu
```

 一旦使用虚拟Web主机功能，那么所有的Web页面都必须用虚拟Web主机功能进行呈现

 

### 六、 构建NFS共享服务

 

#### • Network File System，网络文件系统

– 用途：为客户机提供共享使用的文件夹

– 协议：NFS（TCP/UDP 2049）、RPC（TCP/UDP 111）

#### • 服务端与客户端所需软件包：nfs-utils

#### • 系统服务：nfs-server

 

虚拟机A

1.安装软件包

```
[root@svr7 ~]# rpm  -q  nfs-utils

nfs-utils-1.3.0-0.54.el7.x86_64

[root@svr7 ~]# mkdir  /public   #创建用于共享的目录

[root@svr7 ~]# touch  /public/abc.txt

[root@svr7 ~]# ls  /public/

abc.txt
```

3.修改配置文件                   

```
[root@svr7 ~]# vim  /etc/exports

/public     *(ro)  

共享目录    客户端的地址(权限)
```

 

4.启动服务

```
]# systemctl  restart  rpcbind   #动态端口，依赖的服务

]# systemctl  restart  nfs-server
```

 

虚拟机B

1.安装软件包nfs-utils

```
[root@pc207 ~]# rpm  -q  nfs-utils

nfs-utils-1.3.0-0.54.el7.x86_64
```

2.挂载访问

```
[root@pc207 ~]# mkdir   /mynfs

[root@pc207 ~]# mount  192.168.4.7:/public   /mynfs

[root@pc207 ~]# df  -h   |   tail  -1

[root@pc207 ~]# ls   /mynfs
```

3.开机自动挂载

>  **_netdev：声明网络设备，开机启动时，首先将网络参数配置之后再挂载本设备**

```
[root@pc207 ~]# vim   /etc/fstab

192.168.4.7:/public  /mynfs  ***\*nfs\****  defaults***\*,_netdev\****  0 0

[root@pc207 ~]# umount  /mynfs

[root@pc207 ~]# mount -a

[root@pc207 ~]# df  -h  |  tail -1

192.168.4.7:/public    17G  3.5G  14G  21% /mynfs
```

 

### 七、触发挂载(针对于客户端设置)

 

•由 autofs 服务提供的“按需访问”机制     

–只要访问挂载点，就会触发响应，自动挂载指定设备

–闲置超过时限（默认5分钟）后，会自动卸载

 触发挂载需要两级目录：

​    第一级目录为监控目录，第二级目录为挂载点

 

 •主配置文件 /etc/auto.master

–监控点目录  挂载配置文件的路径

 /misc     /etc/auto.misc

  

•挂载配置文件，比如 /etc/auto.misc

–触发点子目录   -挂载参数   :设备名

 

 虚拟机B：  

```
 [root@pc207 ~]# yum -y install autofs

 [root@pc207 ~]# systemctl restart autofs

 [root@pc207 ~]# ls  /misc

 [root@pc207 ~]# ls  /misc/cd

```

 虚拟机B：监控目录为/nsd20 ,挂载点目录dc 触发挂载的设备为/dev/cdrom

 1.手动创建监控目录

```
 [root@pc207 /]# mkdir  /nsd20
```

 2.修改主配置文件

```
 [root@pc207 /]# vim  /etc/auto.master
```

 ..........此处省略一万字

```
 /nsd20   /opt/xixi.txt     #指定监控目录为/nsd20
```

 3.建立挂载配置文件

```
[root@pc207 /]# cp  /etc/auto.misc   /opt/xixi.txt

[root@pc207 /]# vim  /opt/xixi.txt     #该文件只需要保留一行内容

 dc    -fstype=iso9660    :/dev/cdrom

 挂载点目录    设备的文件系统类型   挂载的设备

[root@pc207 /]# systemctl  restart  autofs
```

4.测试

```
[root@pc207 /]# ls /nsd20

[root@pc207 /]# ls /nsd20/dc

[root@pc207 /]# ls /nsd20
```

二、触发挂载进阶

监控目录为/nsd20 ,挂载点目录tc 触发挂载的设备为192.168.4.7:/public

**虚拟机B：**

1.建立挂载配置文件

```
 [root@pc207 /]# vim  /opt/xixi.txt    

dc   -fstype=iso9660  :/dev/cdrom

tc   -fstype=nfs    192.168.4.7:/public

[root@pc207 /]# systemctl  restart  autofs


[root@pc207 /]# ls /nsd20

[root@pc207 /]# ls /nsd20/dc

[root@pc207 /]# ls /nsd20/tc

[root@pc207 /]# ls /nsd20
```

 

三、链路聚合

 网卡team（网卡组队、链路聚合）

 作用：备份网卡设备，提高可靠性

​              eth0         eth1

​         虚拟网卡：team0  192.168.1.1

1.关闭虚拟机添加两块网卡

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml18292\wps2.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml18292\wps3.jpg) 

 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml18292\wps4.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml18292\wps5.jpg) 

```
[root@A ~]# ifconfig  |  less
```

2.建立虚拟网卡设备，参考 man teamd.conf  进行全文查找 /example

```
[root@A ~]# nmcli  connection   add   type   team  ifname  team0  con-name  team0           

 autoconnect  yes  config   '{"runner": {"name": "activebackup"}}'

[root@A ~]# nmcli   连接      添加   类型   组队  网卡名  team0   配置文件名  team0

  每次开机自启动   工作方式   活跃备份

[root@A ~]# ifconfig
```

3.添加成员

```
[root@A ~]# nmcli connection add type team-slave autoconnect yes ifname eth1 con-name team0-1  master team0

[root@A ~]# nmcli connection add type team-slave autoconnect yes ifname eth2 con-name team0-2  master team0

[root@A ~]# nmcli  连接     添加  类型  组队-成员  每次开机自动启用  网卡名 eth2  配置文件名  team0-2   主设备为  team0
```

4.激活，以配置文件的名进行激活

```
successfully（成功）

[root@A ~]# nmcli connection up team0

[root@A ~]# nmcli connection up team0-1

[root@A ~]# nmcli connection up team0-2
```

5.为team0配置IP地址

```
[root@A ~]# nmcli  connection  modify  team0  ipv4.method  manual  ipv4.addresses 192.168.1.1/24 connection.autoconnect  yes

[root@A ~]# nmcli  connection  up  team0

[root@A ~]# teamdctl team0 state    #专门查看team0状态的命令

[root@A ~]# ifconfig eth1 down

[root@A ~]# teamdctl team0 state 

setup:

 runner: activebackup

ports:

 eth1

  link watches:

   link summary: down

   instance[link_watch_0]:

    name: ethtool

    link: down

   down count: 1

 eth2

  link watches:

   link summary: up

   instance[link_watch_0]:

    name: ethtool

    link: up
    
    down count: 0

runner:

 active port: eth2
```



#### 课后习题：SELinux与防火墙进行关闭

#### 案例1:为虚拟机A 配置以下虚拟Web主机

\- 实现三个网站的部署

\- 实现客户端访问server0.example.com网页内容为 大圣归来

\- 实现客户端访问www0.example.com网页内容为  大圣又归来

\- 实现客户端访问webapp0.example.com网页内容为 大圣累了

虚拟机A：

```
[root@A ~]# firewall-cmd --set-default-zone=trusted
[root@A ~]# setenforce 0
[root@A ~]# yum -y install httpd
[root@A ~]# mkdir /var/www/nsd01
[root@A ~]# mkdir /var/www/nsd02
[root@A ~]# mkdir /var/www/nsd03
[root@A ~]# echo 大圣归来 > /var/www/nsd01/index.html
[root@A ~]# echo 大圣又归来 > /var/www/nsd02/index.html
[root@A ~]# echo 大圣累了 > /var/www/nsd03/index.html
[root@A ~]# vim /etc/httpd/conf.d/vhost.conf
<VirtualHost *:80>
ServerName server0.example.com
DocumentRoot /var/www/nsd01
<\VirtualHost>
<VirtualHost *:80>
ServerName www0.example.com
DocumentRoot /var/www/nsd02
<\VirtualHost>
<VirtualHost *:80>
ServerName webapp0.example.com
DocumentRoot /var/www/nsd03
<\VirtualHost>
[root@A ~]# systemctl restart httpd

```

 虚拟机B：测试

```
[root@B ~]# vim /etc/hosts
192.168.4.7 server0.example.com www0.example.com webapp0.example.com
[root@B ~]# curl server0.example.com
[root@B ~]# curl www0.example.com
[root@B ~]# curl webapp0.example.com
```



#### 案例2:为虚拟机A 使用自定Web根目录

调整 Web 站点 http://www0.example.com 的网页文件目录，要求如下：

1）新建目录 /webroot，作为此站点新的网页文件目录（Web访问控制）

2）确保站点 http://www0.example.com  仍然可访问

虚拟机A

```
[root@A ~]# vim /etc/httpd/conf.d/vhost.conf
...
<VirualHost *:80>
ServerName www0.example.com
DocumentRoot /webroot
</VirualHost>
...
[root@A ~]# mkdir /webroot
[root@A ~]# echo 'this is webroot' > /webroot/index.html
[root@A ~]# vim /etc/httpd/conf.d/myacl.conf
<Directory /webroot>
 Require all granted
</Directory>
[root@A ~]# systemctl restart httpd

虚拟机B:
[root@B ~]# curl www0.example.com
```



#### 案例3：为虚拟机A 部署站点

为站点 webapp0.example.com 进行配置，要求如下：

1）此虚拟主机侦听在端口8909

2）从浏览器访问 http://webapp0.example.com:8909 

虚拟机A:

```
[root@A ~]# vim /etc/httpd/conf.d/vhost.conf
...
Listen 8909
<VirualHost *:8909>
ServerName webapp0.example.com
DocumentRoot /var/www/nsd03
...
[root@A ~]# systemctl restart httpd
```

 虚拟机B

```
[root@B ~]# curl webapp0.example.com:8909
大圣累了
```



#### 案例4：普通NFS共享的实现

1.在虚拟机A上配置NFS服务，只读的方式共享目录 /public

2.在虚拟机B上访问NFS共享目录

 a）将虚拟机A 的 /public 挂到本地 /mnt/nfsmount 

 b）这些文件系统在系统启动时自动挂载

虚拟机A：

```
[root@A ~]# yum -y install nfs-utils
[root@A ~]# mkdir /public
[root@A ~]# touch /public/1.txt
[root@A ~]# ls /public
[root@A ~]# vim /etc/exports
/public *(ro)
[root@A ~]# systemctl restart rpcbind #先重启
[root@A ~]# systemctl restart nfs-server #后重启
[root@A ~]# 
```

 虚拟机B：

```
[root@B ~]# mkdir /mnt/nfsmount
[root@B ~]# vim /etc/fstab
192.168.4.7:/public /mnt/nfsmount nfs defaults,_netdev 0 0
[root@B ~]# mount -a
[root@B ~]# df -h | tail -1
192.168.4.7:/public       17G  3.5G   14G   21% /mnt/nfsmount
```

 



------



## 03：DNS服务基础、特殊解析、DNS子域授权、DNS主从架构

### 一、 两台虚拟机进行环境准备

#### 1.SELinux设置宽松模式

```
[root@svr7 ~]# setenforce  0  #设置当前系统SELinux为宽松

[root@svr7 ~]# getenforce    #查看当前系统SELinux模式

Permissive

[root@svr7 ~]# vim  /etc/selinux/config

SELINUX=permissive
```

 

#### 2.防火墙设置

```
]# firewall-cmd  --set-default-zone=trusted
```



### 二、 NFS服务

虚拟机A：

```
[root@svr7 ~]# mkdir /student

[root@svr7 ~]# echo 123 > /student/a.txt

[root@svr7 ~]# vim /etc/exports

/student   *(ro)

]# systemctl  restart  rpcbind  #依赖服务，优先启动

]# systemctl  restart  nfs-server

```

虚拟机B：

```
[root@pc207 ~]# mkdir  /mnt/nsd

[root@pc207 ~]# mount  192.168.4.7:/student   /mnt/nsd

[root@pc207 ~]# df  -h  |  tail  -1

192.168.4.7:/student    17G  3.4G  14G  20% /mnt/nsd

[root@pc207 ~]#
```



### 三、 NFS服务&autofs服务

案例：构建触发挂载，192.168.4.7:/student触发挂载到/mnt/haha，其中/mnt为监控目录。haha为挂载点

 

虚拟机B：

```
[root@pc207 ~]# yum -y install autofs

[root@pc207 ~]# vim  /etc/auto.master

/mnt   /etc/stu.conf

[root@pc207 ~]# cp  /etc/auto.misc   /etc/stu.conf

[root@pc207 ~]# vim  /etc/stu.conf

haha    -fstype=nfs   192.168.4.7:/student

 
[root@pc207 ~]# systemctl  restart autofs

[root@pc207 ~]# ls /mnt/

[root@pc207 ~]# ls /mnt/haha
```

### 四、 DNS服务

#### 为什么需要DNS系统

> www.baidu.com 与 119.75.217.56，哪个更好记？
>
> 互联网中的114查号台/导航员

#### DNS服务器的功能

> 正向解析：根据注册的域名查找其对应的IP地址
>
> 反向解析：根据IP地址查找对应的注册域名，不常用

####   DNS服务器分类：

> 根域名服务器、一级DNS服务器、二级DNS服务器、三级DNS服务器

> 域名系统: 所有的域名都必须要以点作为结尾，树型结构
>
>   www.qq.com    www.qq.com.

> 根域名 :              .
>
>  一级域名：  .cn     .us   .tw   .hk   .jp    .kr   ……….
>
> 二级域名:   .com.cn   .org.cn  .net.cn ………
>
> 三级域名：  haha.com.cn   xixi.com.cn   .nb.com.cn  …..



#### FQDN（完全合格的主机名）：站点名+注册的域名

• BIND（Berkeley Internet Name Daemon）

– 伯克利 Internet 域名服务 

– 官方站点：https://www.isc.org/

 

daemon

英 [ˈdiːmən] 美 [ˈdiːmən]

(古希腊神话中的)半神半人精灵（守护神）

 

• BIND服务器端程序

– 主要执行程序：/usr/sbin/named

– 系统服务：named

– DNS协议默认端口：TCP/UDP 53

– 运行时的虚拟根环境：/var/named/chroot/

 

• 主配置文件：/etc/named.conf  #设置负责解析的域名 

• 地址库文件：/var/named/   #完全合格的主机名与IP地址对应关系



#### 虚拟机A：构建DNS服务器

1.安装软件包

```
[root@svr7 ~]# yum -y install  bind   bind-chroot

bind（主程序）

bind-chroot（提供牢笼政策）
```

2.修改主配置文件

```
[root@svr7 ~]# cp  /etc/named.conf   /root   #备份数据

[root@svr7 ~]# vim /etc/named.conf

options {

   directory    "/var/named";    #定义地址库文件存放路径

};

zone "tedu.cn" IN {       #定义负责的解析tedu.cn域名

    type master;         #权威主DNS服务器

    file  "tedu.cn.zone";   #地址库文件名称

};
```

3.建立地址库文件

 保证named对地址库文件有读取权限

 所有的域名都要以点作为结尾

 如果没有以点作为结尾，那么默认补全本地库文件负责的域名

```
]# cd  /var/named/

]# cp  -p  named.localhost   tedu.cn.zone   #保持权限不变

]# ls  -l  tedu.cn.zone

]# vim   tedu.cn.zone

……此处省略一万字

tedu.cn.    NS    svr7        #声明DNS服务器为svr7

svr7        A     192.168.4.7  #svr7解析结果为192.168.4.7

www       A     1.1.1.1

ftp         A     2.2.2.2

[root@svr7 named]# systemctl restart named
```

 

虚拟机B：测试DNS服务器

```
]# echo nameserver  192.168.4.7  > /etc/resolv.conf

]# cat /etc/resolv.conf

]# nslookup  www.tedu.cn  

]# nslookup  ftp.tedu.cn  
```



### 五、 多区域的DNS服务器

虚拟机A：

```
[root@svr7 /]# vim  /etc/named.conf

options {

    directory    "/var/named";

};

zone "tedu.cn"  IN  {

    type  master;

    file  "tedu.cn.zone";

};

zone  "lol.com"  IN  {

     type  master;

     file  "lol.com.zone";

};

[root@svr7 /]# cd /var/named/

[root@svr7 named]# cp -p tedu.cn.zone  lol.com.zone

[root@svr7 named]# vim lol.com.zone

……此处省略一万字

lol.com.  NS  svr7

svr7     A   192.168.4.7

www    A   3.3.3.3

[root@svr7 named]# systemctl  restart named
```

虚拟机B

```
[root@pc207 ~]# nslookup  www.lol.com
```



### 六、特殊解析

####  **DNS的轮询(负载均衡)**

```
[root@svr7 /]# vim  /var/named/tedu.cn.zone

……此处省略一万字

tedu.cn.  NS  svr7

svr7      A   192.168.4.7

www     A   192.168.4.20

www     A   192.168.4.21

www     A   192.168.4.22

ftp      A   2.2.2.2

[root@svr7 /]# systemctl  restart named
```



#### **DNS的泛域名解析**

```
[root@svr7 /]# vim  /var/named/tedu.cn.zone

……此处省略一万字

tedu.cn.  NS  svr7

svr7     A   192.168.4.7

www    A   192.168.4.20

ftp      A   2.2.2.2

\*        A   4.4.4.4

tedu.cn.  A   5.5.5.5

[root@svr7 /]# systemctl  restart  named
```

 

虚拟机B测试：

```
[root@pc207 /]#  nslookup  wwwwww.tedu.cn

[root@pc207 /]#  nslookup  tedu.cn
```

 

#### **DNS的解析记录的别名**

```
[root@svr7 /]# vim  /var/named/tedu.cn.zone

……此处省略一万字

tedu.cn.  NS  svr7

svr7     A   192.168.4.7

www    A   192.168.4.20

ftp      A   2.2.2.2

\*        A   4.4.4.4

tedu.cn.  A   5.5.5.5

vip    CNAME   ftp     #vip解析结果与ftp解析结果一致

[root@svr7 /]# systemctl  restart  named
```

虚拟机B：测试

```
[root@pc207 ~]# nslookup vip.tedu.cn
```



### 七、递归查询与迭代查询   

递归查询：客户端发送请求给首选DNS服务器，首选DNS服务器与其他的DNS服务器交互，最终将解析结果带回来过程

迭代查询: 客户端发送请求给首选DNS服务器，首选DNS服务器告知下一个DNS服务器地址

 

#### 虚拟机B：构建DNS服务器负责bj.tedu.cn

```
[root@pc207 ~]# yum -y install bind bind-chroot

options {

    directory    "/var/named";

};

zone "bj.tedu.cn" IN {

    type master;

    file "bj.tedu.cn.zone";

};

]# cd /var/named/

]# cp -p named.localhost   bj.tedu.cn.zone

]# vim bj.tedu.cn.zone

……此处省略一万字

bj.tedu.cn.   NS  pc207

pc207      A   192.168.4.207

www       A   6.6.6.6

]# systemctl restart named
```



#### 虚拟机A:子域授权

```
[root@svr7 /]# vim /var/named/tedu.cn.zone

tedu.cn.    NS   svr7

bj.tedu.cn.  NS   pc207

svr7       A    192.168.4.7

pc207     A    192.168.4.207

www      A    192.168.4.20

ftp        A    2.2.2.2

\*          A    4.4.4.4

tedu.cn.    A    5.5.5.5

vip        CNAME  ftp

[root@svr7 /]# systemctl restart named

虚拟机B：测试

[root@pc207 /]# nslookup  www.bj.tedu.cn    192.168.4.7

Server:     192.168.4.7

Address:     192.168.4.7#53

 

Non-authoritative answer:   #非权威解答

Name:  www.bj.tedu.cn

Address: 6.6.6.6
```



### 虚拟机A:禁止递归查询

```
[root@svr7 /]# vim /etc/named.conf

options {

    directory    "/var/named";

    recursion no;   #禁止递归查询

};

zone "tedu.cn" IN {

    type master;

    file "tedu.cn.zone";

};

zone "lol.com" IN {

    type master;

    file "lol.com.zone";

};

[root@svr7 /]# systemctl restart named


[root@pc207 /]# dig  @192.168.4.7  www.bj.tedu.cn  #专业域名解析的工具

bj.tedu.cn.       86400  IN    NS    pc207.tedu.cn.


;; ADDITIONAL SECTION:

pc207.tedu.cn.      86400  IN    A    192.168.4.207
```



### 八、DNS主从架构

 作用：提高可靠性，从DNS服务器备份主DNS服务器的数据

虚拟机A：主DNS服务器，以lol.com域名

虚拟机B：从DNS服务器，以lol.com域名

 

#### 虚拟机A：主DNS服务器

1. 授权从DNS服务器

```
[root@svr7 /]# man  named.conf     #参考man帮助

[root@svr7 /]# vim  /etc/named.conf

options {

   directory    "/var/named";

   allow-transfer  {  192.168.4.207;  };   #允许谁进行传输数据

};

zone "tedu.cn" IN {

    type master;

    file "tedu.cn.zone";

};

zone "lol.com" IN {

    type master;

    file "lol.com.zone";

};
```



2. 声明从DNS服务器

```
[root@svr7 /]# vim   /var/named/lol.com.zone

lol.com.  NS  svr7

lol.com.  NS  pc207       #声明从DNS服务器

svr7     A   192.168.4.7

pc207   A   192.168.4.207

www    A   3.3.3.3

[root@svr7 /]# systemctl  restart  named
```

 

#### 虚拟机B：从DNS服务器

1.安装软件包

```
[root@pc207 /]# yum -y install bind bind-chroot
```

2.修改主配置文件

```
[root@pc207 /]# cp  /etc/named.conf  /root

[root@pc207 /]# vim  /etc/named.conf

options {

    directory    "/var/named";

};

zone "lol.com" IN {

 type  slave;        #类型为从服务器

 file "/var/named/slaves/lol.com.slave";  #确保named用户有读写执行权限

 masters   {  192.168.4.7;   };  #指定主DNS服务器

 masterfile-format   text;     #地址库文件明文存储

};

[root@pc207 /]# ls  /var/named/slaves/           [root@pc207 /]# systemctl restart named

[root@pc207 /]# ls  /var/named/slaves/

lol.com.slave

[root@pc207 /]# vim  /etc/resolv.conf

nameserver 192.168.4.7

nameserver 192.168.4.207

[root@pc207 /]# nslookup  www.lol.com
```

 

### 九、DNS主从数据同步

虚拟机A：

```
[root@svr7 /]# vim  /var/named/lol.com.zone

…….此处省略一万字

   2020081801    ; serial  #数据的版本号，由10个数字组成

      1D    ; refresh   #每隔1天主从进行数据交互

      1H    ; retry     #失效之后的时间间隔每一个1小时

      1W    ; expire   #真正的失效时间，1周

      3H )   ; minimum  #失效记录的记忆时间3小时

lol.com.  NS  svr7

lol.com.  NS  pc207

svr7     A   192.168.4.7

pc207   A   192.168.4.207

www    A   8.8.8.8

[root@svr7 /]# systemctl  restart  named
```

虚拟机B：

```
[root@pc207 /]# nslookup  www.lol.com  192.168.4.207
```



------



## 04：缓存DNS、Split分离解析、电子邮件通信、Web服务器项目实战

### 一、 环境的准备

 **关闭两台虚拟机的SELinux**

```
[root@svr7 ~]# setenforce  0    #修改当前运行模式

[root@svr7 ~]# getenforce     #查看当前运行模式

Permissive

[root@svr7 ~]# vim  /etc/selinux/config  #永久修改

SELINUX=permissive
```

 **设置两台虚拟机防火墙**

```
[root@svr7 ~]# firewall-cmd  --set-default-zone=trusted
```



### 二、 构建基本的DNS服务器

虚拟机A：负责解析lol.com

```
[root@svr7 ~]# yum -y  install  bind  bind-chroot

[root@svr7 ~]# cp  /etc/named.conf   /root

[root@svr7 ~]# vim  /etc/named.conf

options {

    directory    "/var/named";

};

zone  "lol.com"  IN  {   #声明负责的域名

     type  master;     #声明本机为权威主DNS服务器

     file  "lol.com.zone";   #指明地址库文件名称

};

]# cp  -p  named.localhost   lol.com.zone

]# ls  -l  lol.com.zone

]# vim  lol.com.zone

此处省略一万字………

lol.com.  NS   svr7

svr7     A    192.168.4.7

www     A    1.2.3.4

]# systemctl  restart  named
```

 

虚拟机B：测试

```
]# echo  nameserver  192.168.4.7  >  /etc/resolv.conf

]# cat  /etc/resolv.conf

]# nslookup  www.lol.com  
```

### 三、 DNS子域授权

虚拟机A：负责lol.com域名

虚拟机B：负责bj.lol.com域名

 

虚拟机B：构建DNS服务器

```
[root@pc207 ~]# yum -y install  bind  bind-chroot

[root@pc207 ~]# cp /etc/named.conf /root

[root@pc207 ~]# vim /etc/named.conf

options {

    directory    "/var/named";

};

zone "bj.lol.com" IN {

    type master;

    file "bj.lol.com.zone";

};

[root@pc207 ~]# cd /var/named/

[root@pc207 named]# cp -p named.localhost  bj.lol.com.zone

[root@pc207 named]# vim bj.lol.com.zone

此处省略一万字………

bj.lol.com.   NS    pc207

pc207  A    192.168.4.207

www   A    2.2.2.2

[root@pc207 named]# systemctl restart named
```

 

测试：

```
[root@pc207 /]# nslookup  www.bj.lol.com  192.168.4.207

Server:     192.168.4.207

Address:     192.168.4.207#53

Name:  www.bj.lol.com

Address: 2.2.2.2
```

虚拟机A：能够解析虚拟机B负责的域名（子域授权）

1. 修改地址库文件进行声明

此处省略一万字………

```
[root@svr7 /]# cd /var/named/

[root@svr7 named]# vim lol.com.zone

lol.com.   NS  svr7

bj.lol.com. NS  pc207

svr7      A   192.168.4.7

pc207     A   192.168.4.207

www     A   1.2.3.4

[root@svr7 /]# systemctl  restart  named

[root@pc207 /]# nslookup  www.bj.lol.com   192.168.4.7

Server:     192.168.4.7

Address:     192.168.4.7#53


Non-authoritative answer:   #非权威解答

Name:  www.bj.lol.com

Address: 2.2.2.2
```

 

#### 递归解析：客户端发送请求给首选DNS服务器，首选DNS服务器与其他DNS服务器交互，最终将解析结果带回来过程

 

#### 迭代解析：客户端发送请求给首选DNS服务器，首选DNS服务器告知下一个DNS服务器地址

 

### 四、 缓存DNS

作用：缓存解析结果，加快访问

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml1392\wps1.jpg) 

 

虚拟机A：为真正的DNS服务器

虚拟机B：缓存DNS服务器



虚拟机B：

```
[root@pc207 /]# yum -y  install  bind  bind-chroot

[root@pc207 /]# vim  /etc/named.conf

options  {

    directory    "/var/named";

    forwarders  {  192.168.4.7;  };\****   #转发给192.168.4.7

};

[root@pc207 /]# systemctl restart named

[root@pc207 /]# nslookup www.lol.com  192.168.4.207

Server:     192.168.4.207

Address:     192.168.4.207#53


Non-authoritative answer:

Name:  www.lol.com

Address: 1.2.3.4
```



### 五、 分离解析

 

#### • 当收到客户机的DNS查询请求的时候

– 能够区分客户机的来源地址

– 为不同类别的客户机提供不同的解析结果（IP地址）

– 为客户端提供最近的服务器

 

牛老师(首都机场)--->达外酒店--->地图软件--->机场大街88号

王老师(北京南站)--->达外酒店--->地图软件--->南站大街10号

客户端(源IP地址) --->域名--->DNS服务器--->解析结果

 

 

#### • 分离解析配置

– 客户端必须找到自己的类型

– 由上到下依次匹配，匹配及停止  

– 所有的zone都必须在view

```
view  "haha" {

  match-clients  {  192.168.4.207;  .. ..;   };

  zone  "12306.cn"  IN  {

   …… 地址库1;

  };   };                         

view  "xixi" { 

  match-clients  {   any;    };

  zone  "12306.cn"  IN {

    …… 地址库2;

  };   };
```

 

#### • 环境及需求

– 权威DNS：svr7.tedu.cn  192.168.4.7

– 负责区域：lol.com

– A记录分离解析 —— 以 www.lol.com为例

192.168.4.207或者192.168.7.0/24----->192.168.4.100

 any----->1.2.3.4

 

虚拟机A：

1.修改主配置文件

```
[root@svr7 /]# vim /etc/named.conf

options {

   directory    "/var/named";

};

view    "nsd"   {

 match-clients   {   192.168.4.207;   192.168.7.0/24;   };

 zone  "lol.com"   IN {

    type  master;

    file   "lol.com.zone";

 };

};

view    "other"   {

 match-clients    {   any;   };

 zone "lol.com"   IN {

   type   master;
   file   "lol.com.other";

 };

};
```

2．建立地址库文件

```
]# cd  /var/named/

]# vim   lol.com.zone

此处省略一万字……..

lol.com.   NS  svr7

svr7      A  192.168.4.7

www     A  192.168.4.100

]# cp  -p   lol.com.zone    lol.com.other

]# vim     lol.com.other

此处省略一万字……..

lol.com.   NS  svr7

svr7      A   192.168.4.7

www      A   1.2.3.4

[root@svr7 named]# systemctl  restart  named
```

 

#### • 多域名分离解析环境及需求

– 客户端必须找到自己的类型

– 由上到下依次匹配，匹配及停止  

– 所有的zone都必须在view

– 每一个view中，zone个数要一致

– 每一个view中，zone负责的域名要一致

– 

– 权威DNS：svr7.tedu.cn  192.168.4.7

– 负责区域：lol.com  qq.com

– A记录分离解析 —— 以 www.lol.com  www.qq.com为例

• 192.168.4.207 -- www.lol.com --->192.168.4.100

• any--- www.lol.com -->1.2.3.4

 

• 192.168.4.207--www.qq.com--->192.168.4.200

• any-- www.qq.com --->10.20.30.40

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml1392\wps2.jpg) 

 

虚拟机A：

```
[root@svr7 named]# vim /etc/named.conf

options {

   directory    "/var/named";

};

view "nsd" {

 match-clients  {  192.168.4.207;  192.168.7.0/24;  };

 zone "lol.com" IN {

    type master;

    file "lol.com.zone";

 };

 zone "qq.com" IN {

    type master;

    file "qq.com.zone";

 };

};


view "other" {

 match-clients {  any;  };

 zone "lol.com" IN {

    type master;

    file "lol.com.other";

 };

 zone "qq.com" IN {

    type master;

    file "qq.com.other";

 };

};
```

2.建立地址库文件

```
]# cd  /var/named/

]# cp -p  named.localhost   qq.com.zone

]# vim  qq.com.zone        

此处省略一万字……..

qq.com.  NS    svr7

svr7     A    192.168.4.7

www    A    192.168.4.200

]# cp -p qq.com.zone  qq.com.other

]# vim qq.com.other

此处省略一万字……..

qq.com. NS    svr7

svr7    A    192.168.4.7

www   A    10.20.30.40

[root@svr7 named]# systemctl  restart named
```

 

• 针对来源地址定义acl列表(了解内容)

– 若地址比较少，也可以不建立列表

```
options {

    directory    "/var/named";

};

acl "test"  {  192.168.4.207;   192.168.7.0/24;  };

view "nsd" {

 match-clients {  test;  };

 zone "lol.com" IN {

此处省略一万字……..
```



### 六、 NTP时间服务器

作用：提供标准时间

• Network Time Protocol（网络时间协议）

• 它用来同步网络中各个计算机的时间的协议

• 210.72.145.39 (国家授时中心服务器IP地址)

 

• Stratum（分层设计）

• Stratum层的总数限制在15以内（包括15i）

 

虚拟机A：时间服务器

1.安装软件包chrony

```
[root@svr7 /]# yum  -y  install  chrony
```

2.修改配置文件

```
[root@svr7 /]# vim  /etc/chrony.conf    

server  0.centos.pool.ntp.org  iburst   #与谁同步时间

server  1.centos.pool.ntp.org  iburst   #iburst表示快速同步

server  2.centos.pool.ntp.org  iburst

server  3.centos.pool.ntp.org  iburst


26行  allow  all      #开头的#去掉，修改为允许所有客户端
 

29行  local  stratum  10   #设置本机为第10层的时间服务器
```

3.重启时间服务

```
[root@svr7 /]# systemctl   restart   chronyd
```

虚拟机B：客户端

1.安装软件包chrony

```
[root@pc207 /]# yum  -y  install  chrony

[root@pc207 /]# rpm -q chrony

chrony-3.2-2.el7.x86_64
```

2.修改配置文件

```
[root@pc207 /]# vim  /etc/chrony.conf    

server  192.168.4.7  iburst    #与192.168.4.7同步时间

\#server  1.centos.pool.ntp.org  iburst   #iburst表示快速同步

\#server  2.centos.pool.ntp.org  iburst

\#server  3.centos.pool.ntp.org  iburst
```

3.重启时间服务

```
[root@pc207 /]# systemctl  restart  chronyd
```

4.测试： 

```shell
[root@pc207 /]# date  -s  "2008-10-1"

[root@pc207 /]# date

[root@pc207 /]# systemctl  restart  chronyd 

[root@pc207 /]# date

[root@pc207 /]# date

2020年 09月 18日 星期五 16:16:22 CST

[root@pc207 /]#

[root@pc207 /]#  chronyc  sources  -v   #列出时间服务器信息
```



 

### 七、 邮件服务器

 

#### • 电子邮件服务器的基本功能

– 为用户提供电子邮箱存储空间（用户名@邮件域名）

– 处理用户发出的邮件 —— 传递给收件服务器

– 处理用户收到的邮件 —— 投递到邮箱

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml1392\wps3.jpg) 

虚拟机A：DNS服务器，添加邮件解析功能

1.修改主配置文件

```shell
[root@svr7 /]# vim /etc/named.conf

options {

    directory    "/var/named";

};

Zone  "qq.com"  IN  {

     type  master;

     file  "qq.com.zone";

};
```

2.建立地址库文件

```shell
[root@svr7 /]# cd /var/named/

[root@svr7 named]# vim qq.com.zone

此处省略一万字……..

qq.com.  NS      svr7

qq.com.  MX  10  mail      #数字10为优先级，越小越优先

svr7     A    192.168.4.7

mail     A    192.168.4.7

www    A    192.168.4.200 

]# systemctl  restart  named

]# echo nameserver 192.168.4.7 > /etc/resolv.conf

]# host  -t  MX  qq.com     #测试qq.com区域邮件交换记录

qq.com mail is handled by 10 mail.qq.com.

]# host mail.qq.com        #测试域名完整解析

mail.qq.com has address 192.168.4.7
```

 

虚拟机A：邮件服务器

1.安装软件包

```shell
[root@svr7 /]# rpm -q postfix

postfix-2.10.1-6.el7.x86_64
```

2.修改配置文件

```shell
[root@svr7 /]# vim  /etc/postfix/main.cf

99 myorigin = qq.com  #默认补全，域名后缀

116 inet_interfaces =  all #本机所有IP地址均提供邮件收发功能

164 mydestination = qq.com   #判断本域邮件的依据
```

3.重启邮件服务

```shell
[root@svr7 /]# systemctl restart postfix
```

 

4.测试

• mail 发信操作:mail  -s  '邮件标题'   -r   发件人  收件人 

```shell
[root@svr7 /]# useradd yg

[root@svr7 /]# useradd xln

[root@svr7 /]# mail -s 'test01'  -r yg  xln

ahahaxixiehehelele

.       #一行只有一个点表示提交

EOT

[root@svr7 /]#
```

 

• mail 收信操作:mail  [-u  用户名]

```shell
[root@svr7 /]# mail -u xln

\>N  1 yg@qq.com       Fri Sep 18 17:24  18/510

&  1      #输入邮件编号


&  quit    #退出


[root@svr7 /]# echo 123456  |  mail  -s  'test02'  -r yg  xln

[root@svr7 /]# mail -u xln  
```



### 八、 综合实验

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml1392\wps4.jpg) 

要求：

1.在Web1机器上构建Web服务，实现基于域名的虚拟Web主机，提供www.163.com与www.qq.com两个网站

2.在Web2机器上构建Web服务，实现基于域名的虚拟Web主机，提供www.163.com与www.qq.com两个网站

3.客户端192.168.4.207访问www.163.com与www.qq.com两个网站，由Web1服务器提供

4.客户端192.168.4.208访问www.163.com与www.qq.com两个网站，由Web2服务器提供 

5.在192.168.4.7上实现DNS服务器分离解析，5台机器DNS服务器指向192.168.4.7

构建Web服务器
虚拟机Web1：

```shell
[root@Web1 ~]# yum -y install httpd
[root@Web1 ~]# vim /etc/httpd/conf.d/nsd.conf
<VirtualHost  *:80>
  ServerName www.qq.com
  DocumentRoot   /var/www/qq
</VirtUalHost>
<VirtualHost  *:80>
  ServerName www.163.com
  DocumentRoot   /var/www/163
</VirtUalHost>
[root@Web1 ~]# mkdir /var/www/qq  /var/www/163
[root@Web1 ~]# echo Web1 QQ > /var/www/qq/index.html
[root@Web1 ~]# echo Web1 163 > /var/www/163/index.html
[root@Web1 ~]# systemctl  restart  httpd
```

构建Web服务器
虚拟机Web2：

```shell
[root@Web2 ~]# yum -y install httpd
[root@Web2 ~]# scp root@192.168.4.10:/etc/httpd/conf.d/nsd.conf   /etc/httpd/conf.d/
[root@Web2 ~]# cat  /etc/httpd/conf.d/nsd.conf
[root@Web2 ~]# mkdir /var/www/qq  /var/www/163
[root@Web2 ~]# echo Web2 QQ > /var/www/qq/index.html
[root@Web2 ~]# echo Web2 163 > /var/www/163/index.html
[root@Web2 ~]# systemctl restart httpd
```

构建DNS服务器
虚拟机svr7：

```shell
[root@svr7 ~]# yum -y install bind  bind-chroot
[root@svr7 ~]# cp   /etc/named.conf   /root/
[root@svr7 ~]# vim   /etc/named.conf
options {
        directory       "/var/named";
};
view "haha" {
 match-clients {  192.168.4.207;   };
 zone "qq.com" IN {
        type master;
        file "qq.com.zone";
 };
 zone "163.com" IN {
        type master;
        file "163.com.zone";
 };
};
view "xixi" {
 match-clients {   any;   };
 zone "qq.com" IN {
        type master;
        file "qq.com.other";
 };
 zone "163.com" IN {
        type master;
        file "163.com.other";
 };
};
[root@svr7 ~]# cd  /var/named/
[root@svr7 named]# cp -p named.localhost    qq.com.zone
[root@svr7 named]# vim qq.com.zone
此处省略一万字……..
qq.com.  NS      svr7
svr7        A       192.168.4.7
www       A       192.168.4.10
[root@svr7 named]# cp -p qq.com.zone 163.com.zone
[root@svr7 named]# vim 163.com.zone
此处省略一万字……..
163.com.        NS      svr7
svr7      A       192.168.4.7
www     A       192.168.4.10
[root@svr7 named]# cp -p qq.com.zone qq.com.other
[root@svr7 named]# vim qq.com.other
此处省略一万字……..
qq.com. NS      svr7
svr7    A       192.168.4.7
www     A       192.168.4.20
[root@svr7 named]# cp -p 163.com.zone 163.com.other
[root@svr7 named]# vim 163.com.other
此处省略一万字……..
163.com.        NS      svr7
svr7    A       192.168.4.7
www     A       192.168.4.20
[root@svr7 named]# systemctl restart named
```

指定DNS服务器地址  

```shell
[root@pc207 ~]# echo nameserver 192.168.4.7 > /etc/resolv.conf
[root@pc208 ~]# echo nameserver 192.168.4.7 > /etc/resolv.conf
[root@svr7 named]# echo nameserver 192.168.4.7 > /etc/resolv.conf
[root@Web1 ~]# echo nameserver 192.168.4.7 > /etc/resolv.conf
[root@Web2 ~]# echo nameserver 192.168.4.7 > /etc/resolv.conf
```



------



## 05：批量装机环境、配置PXE引导、Kickstart自动应答、Cobbler装机平台



### 一、 环境的准备

**关闭虚拟机A的SELinux**

```shell
[root@svr7 ~]# setenforce  0    #修改当前运行模式

[root@svr7 ~]# getenforce     #查看当前运行模式

Permissive

[root@svr7 ~]# vim  /etc/selinux/config  #永久修改

SELINUX=permissive
```

**设置虚拟机A防火墙**

```shell
[root@svr7 ~]# firewall-cmd  --set-default-zone=trusted
```



### 二、 构建DHCP服务器

• Dynamic Host Configuration Protocol

– 动态主机配置协议，由 IETF（Internet 网络工程师任务小组）组织制定，用来简化主机地址分配管理

• 主要分配以下入网参数

– IP地址/子网掩码/广播地址

– 默认网关地址、DNS服务器地址

 

• DHCP地址分配的四次会话(以广播形式进行，先到先得)

– DISCOVERY --> OFFER --> REQUEST -->ACK

• 一个网络中只能有一台DHCP服务器

 

1.安装软件包

```shell
[root@svr7 /]# yum  -y  install  dhcp
```

2.修改配置文件

```shell
[root@svr7 /]# vim  /etc/dhcp/dhcpd.conf

末行模式下  :r  /usr/share/doc/dhcp*/dhcpd.conf.example

subnet  192.168.4.0  netmask  255.255.255.0  {  #分配网段

 range  192.168.4.100   192.168.4.200;    #分配IP地址范围

 option  domain-name-servers  192.168.4.7;  #分配DNS

 option  routers  192.168.4.254;  #分配的网关地址

 default-lease-time  600;

 max-lease-time  7200;

}

[root@svr7 /]# systemctl  restart  dhcpd
```



### 三、 网络装机服务器简介

• 规模化：同时装配多台主机

• 自动化：装系统、配置各种服务

• 远程实现：不需要光盘、U盘等物理安装介质

• PXE，Pre-boot eXecution Environment

• 预启动执行环境，在操作系统之前运行

• 可用于远程安装

• 工作模式

• PXE client 集成在网卡的启动芯片中

• 当计算机引导时，从网卡芯片中把PXE client调入内存执行，获取PXE server配置、显示菜单，根据用户选择将远程引导程序下载到本机运行

 

• 网络装机服务器:

– DHCP服务，分配IP地址、定位引导程序

– TFTP服务，提供引导程序下载

– HTTP服务（或***\*FTP\****/NFS），提供yum安装源

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps1.jpg) 



### 四、 配置DHCP服务

```shell
[root@svr7 /]# vim  /etc/dhcp/dhcpd.conf

此处省略一万字……

 default-lease-time 600;

 max-lease-time 7200;

 next-server   192.168.4.7;   #下一个服务器的IP地址

 filename  “pxelinux.0”;   #指明网卡引导文件名称

}

[root@svr7 /]# systemctl  restart  dhcpd
```

pxelinux.0：网卡引导文件（网络装机说明书）

​        二进制文件，安装一个软件可以获得该文件



### 五、 配置tftp服务，传输众多的引导文件

tftp:简单的文件传输协议  默认端口：69

​    tftp默认共享的主目录:/var/lib/tftpboot

#### **安装软件**

```shell
[root@svr7 /]# yum  -y  install  tftp-server

[root@svr7 /]# systemctl  restart  tftp
```

 

####  **部署pxelinux.0文件**

```shell
]# yum  provides  */pxelinux.0  #查询哪个包产生该文件

]# yum -y install syslinux   #安装syslinux软件包

]# rpm -ql syslinux  |  grep  pxelinux.0   #查询软件包安装清单

]# cp  /usr/share/syslinux/pxelinux.0   /var/lib/tftpboot/

]# ls  /var/lib/tftpboot/

pxelinux.0  
```

 

总结思路:

1. DHCP服务: IP地址、next-server、filename pxelinux.0

   2.tftp服务: pxelinux.0

3. pxelinux.0： /var/lib/tftpboot/pxelinux.cfg/default(默认菜单文件)

 

####  **部署菜单文件(将光盘中的菜单文件进行复制)**

```shell
[root@svr7 /]# ls  /mydvd/isolinux/

[root@svr7 /]# mkdir  /var/lib/tftpboot/pxelinux.cfg

[root@svr7 /]# ls /var/lib/tftpboot/

pxelinux.0  pxelinux.cfg

[root@svr7 /]# cp  /mydvd/isolinux/isolinux.cfg   /var/lib/tftpboot/pxelinux.cfg/default

[root@svr7 /]# ls  /var/lib/tftpboot/pxelinux.cfg/
```

 

#### **部署图形模块(vesamenu.c32)与背景图片（splash.png）**

```shell
[root@svr7 /]# cp  /mydvd/isolinux/vesamenu.c32    /mydvd/isolinux/splash.png   /var/lib/tftpboot/

[root@svr7 /]# ls  /var/lib/tftpboot/

pxelinux.0   splash.png

pxelinux.cfg  vesamenu.c32
```

 

#### **部署启动内核(vmlinuz)与驱动程序（initrd.img）**

```shell
[root@svr7 /]# cp  /mydvd/isolinux/vmlinuz  /mydvd/isolinux/initrd.img  /var/lib/tftpboot/

[root@svr7 /]# ls   /var/lib/tftpboot/

initrd.img  pxelinux.cfg  vesamenu.c32

pxelinux.0  splash.png   vmlinuz
```

 

####  **修改菜单文件内容**

```shell
[root@svr7 /]# vim  /var/lib/tftpboot/pxelinux.cfg/default

末行模式:set  nu开启行号功能

1 default  vesamenu.c32    #默认加载运行图形模块

2 timeout 600            #读秒时间60秒，1/10秒

此处省略一万字……..

10 menu background  splash.png       #背景图片

11 menu title  PXE  NSD2008  Server    #菜单界面的标题

此处省略一万字……..

61 label  linux

 62  menu label  ^Install  CentOS 7   #界面显示内容

 63  menu  default     #读秒结束后默认的选项

 64  kernel  vmlinuz      #加载内核

 65  append  initrd=initrd.img   #加载驱动程序

以下全部删除             
```

 

#### 总结思路:

1. DHCP服务: IP地址、next-server、filename pxelinux.0

   2.tftp服务: pxelinux.0

3. pxelinux.0： /var/lib/tftpboot/pxelinux.cfg/default(默认菜单文件)

4. default: 图形模块、背景图片、内核、驱动程序…..



### 六、 初步测试

####  **重启相关的服务**

```shell
[root@svr7 /]# systemctl  restart  dhcpd

[root@svr7 /]# systemctl  restart  tftp
```

####  **关闭VMware软件的DHCP服务**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps2.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps3.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps4.jpg) 

 

####  **新建虚拟机，内存2G，网络类型选项vmnet1**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps5.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps6.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps7.jpg) 

####  **菜单界面的显示**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps8.jpg) 

 

#### 排错思路：                

1. 查看DHCP服务配置文件

```shell
filename  "\pxelinux.0\";
```

2. 查看/var/lib/tftpboot目录内容

```shell
[root@svr7 /]# ls  /var/lib/tftpboot/

initrd.img  pxelinux.cfg  vesamenu.c32

pxelinux.0  splash.png   vmlinuz
```

3.菜单文件的名称

```shell
[root@svr7 /]# ls  /var/lib/tftpboot/pxelinux.cfg

default
```



### 七、 构建FTP服务，提供光盘内容

 FTP:文件传输协议   默认端口:21

 默认共享数据的主目录:/var/ftp

 

#### 1.安装软件包

```shell
[root@svr7 /]# yum -y  install  vsftpd

[root@svr7 /]# systemctl  restart  vsftpd
```



#### 2.建立挂载点

```shell
[root@svr7 /]# mkdir  /var/ftp/centos

[root@svr7 /]# mount  /dev/cdrom   /var/ftp/centos

mount: /dev/sr0 写保护，将以只读方式挂载

[root@svr7 /]# ls  /var/ftp/centos
```



#### 3.测试

```shell
[root@svr7 /]# curl   ftp://192.168.4.7/centos/
```



### 八、 实现无人值守安装，生成应答文件

#### **安装ystem-config-kickstart图形的工具**

```shell
[root@svr7 /]# yum -y install  system-config-kickstart

[root@svr7 /]# system-config-kickstart   #运行


system-config-kickstart程序需要Yum仓库的支持才能显示软件包的选择，必须要求Yum仓库的标识为[development]

[root@svr7 /]# vim  /etc/yum.repos.d/mydvd.repo 

[development]

name=centos7

baseurl=file:///mydvd

enabled=1

gpgcheck=0

[root@svr7 /]# system-config-kickstart 
```

#### 首先查看“软件包选择”是否可用

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps9.jpg) 

 

—运行图形的工具system-config-kickstart 进行选择

**[root@svr7 ~]#  system-config-kickstart**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps10.jpg) 

 

**ftp://192.168.4.7/centos**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps11.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps12.jpg) 

 

#### **重新划分新的分区**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps13.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps14.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps15.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps16.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps17.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps18.jpg) 

 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps19.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps20.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps21.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps22.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps23.jpg) 

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml14328\wps24.jpg) 

 

```shell
[root@svr7 /]# ls  /root/ks.cfg    

/root/ks.cfg

[root@svr7 /]# vim  /root/ks.cfg
```

 

#### 2.利用FTP服务共享应答文件

```shell
[root@svr7 /]# cp  /root/ks.cfg   /var/ftp/

[root@svr7 /]# ls  /var/ftp/

centos  ks.cfg  pub

[root@svr7 /]#
```

#### 3.修改菜单文件，指定应答文件获取方式

```shell
[root@svr7 /]# vim  /var/lib/tftpboot/pxelinux.cfg/default

……..此处省略一万字

label linux

menu label ^Install CentOS 7

menu  default

kernel vmlinuz

append initrd=initrd.img  ks=ftp://192.168.4.7/ks.cfg

```

 

#### 总结思路：

1.dhcp服务---》IP地址、next-server、filename "pxelinux.0"

2.tftp服务---》 "pxelinux.0"

3.pxelinux.0---》读取菜单文件/var/lib/tftpboot/pxelinux.cfg/default

4.default---》vesamenu.c32、读秒时间、vmlinuz、initrd.img、ftp://192.168.4.7/ks.cfg

5.ks.cfg应答文件---》语言、键盘类型、分区、安装方式url --url="ftp://192.168.4.7/centos"

 

在虚拟机B构建网络装机时，关闭虚拟机A的DHCP服务，避免冲突

------



## 06：rsync同步操作、inotify实时同步、数据库服务基础、管理表数据

### 一、 环境的准备

#### **关闭所有虚拟机的SELinux**

```shell
[root@svr7 ~]# setenforce  0    #修改当前运行模式

[root@svr7 ~]# getenforce     #查看当前运行模式

Permissive

[root@svr7 ~]# vim  /etc/selinux/config  #永久修改

SELINUX=permissive
```

#### **设置所有虚拟机防火墙**

```shell
[root@svr7 ~]# firewall-cmd  --set-default-zone=trusted
```

 

### 二、 数据同步

 

#### • 命令用法

– rsync  [选项...]  源目录   目标目录

• 同步与复制的差异

– 复制：完全拷贝源到目标

– 同步：增量拷贝，只传输变化过的数据

 

#### • rsync操作选项

– -n：测试同步过程，不做实际修改

– --delete：删除目标文件夹内多余的文档

– -a：归档模式，相当于-rlptgoD

– -v：显示详细操作信息

– -z：传输过程中启用压缩/解压

 

####  **本地同步**

```shell
[root@svr7 ~]# mkdir /mydir  /todir

[root@svr7 ~]# cp /etc/passwd   /mydir

[root@svr7 ~]# touch  /mydir/1.txt

[root@svr7 ~]# ls /mydir

[root@svr7 ~]# rsync -av  /mydir   /todir   #同步目录本身

[root@svr7 ~]# ls /todir
 

[root@svr7 ~]# rsync -av  /mydir/  /todir   #同步目录内容

[root@svr7 ~]# ls /todir

[root@svr7 ~]# touch  /mydir/2.txt

[root@svr7 ~]# rsync -av  /mydir/  /todir   #同步目录内容

[root@svr7 ~]# ls /todir

[root@svr7 ~]# echo 123 > /mydir/1.txt

[root@svr7 ~]# rsync -av  /mydir/  /todir   #同步目录内容
 

[root@svr7 ~]# rsync  -av  --delete  /mydir/  /todir/

[root@svr7 ~]# ls  /mydir/

[root@svr7 ~]# ls  /todir/


[root@svr7 ~]# touch  /todir/a.txt

[root@svr7 ~]# ls  /todir/

[root@svr7 ~]# rsync  -av  --delete  /mydir/  /todir/

[root@svr7 ~]# ls  /todir/

[root@svr7 ~]# ls  /mydir/
```

 

#### **远程同步**

• 与远程的 SSH目录保持同步

– 下行：rsync  [...]  user@host:远程目录  本地目录

– 上行：rsync  [...]  本地目录  user@host:远程目录

 

虚拟机A的/mydir目录的内容与虚拟机B的/opt进行同步

虚拟机A：

```shell
]# rsync  -av  --delete   /mydir/   root@192.168.4.207:/opt

……..connecting (yes/no)? yes

root@192.168.4.207's password:     #输入密码
```

虚拟机B：

```shell
]# ls /opt/

1.txt  haha  passwd  xixi.txt
```



### 三、 实时数据同步

虚拟机A的/mydir目录的内容与虚拟机B的/opt进行同步

 

####  **实现ssh无密码验证(公钥与私钥)**

虚拟机A

1.生成公钥与私钥

```shell
[root@svr7 ~]# ssh-keygen

[root@svr7 ~]# ls   /root/.ssh/

id_rsa  id_rsa.pub  known_hosts
```

 

2．将公钥传递给虚拟机B

```shell
]# ssh-copy-id   root@192.168.4.207

]# rsync -av --delete  /mydir/   root@192.168.4.207:/opt
```

 

#### **监控目录内容变化工具**

**将真机的tools.tar.gz传递数据到虚拟机A**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10228\wps1.jpg) 

```shell
[root@svr7 ~]# ls    /root

tools.tar.gz            下载

公共                   音乐

[root@svr7 ~]#
```

 

源码编译安装步骤：

步骤一:安装开发工具

```shell
]# yum  -y  install  make

]# yum  -y  install  gcc

]# rpm  -q  gcc

]# rpm  -q  make
```

步骤二:进行tar解包               

```shell
]# tar  -xf  /root/tools.tar.gz  -C  /usr/local/

]# ls  /usr/local/

]# ls  /usr/local/tools/

]# tar -xf  /usr/local/tools/inotify-tools-3.13.tar.gz  -C /usr/local/

]# ls  /usr/local/
```

 

步骤三：运行configure脚本进行配置

作用1：检测系统是否安装gcc 

作用2：可以指定安装位置及功能

```shell
]# cd   /usr/local/inotify-tools-3.13/

]# ./configure   --prefix=/opt/myrpm   #指定安装位置
```

 

常见错误：没有安装gcc

```shell
checking for gcc... no

checking for cc... no

checking for cl.exe... no

configure: error: no acceptable C compiler found in $PATH

See `config.log' for more details.
```

 

步骤四：make进行编译，产生可以执行的程序

```shell
]# cd   /usr/local/inotify-tools-3.13/

]# make
```

 

步骤五：make  install进行安装

```shell
]# cd   /usr/local/inotify-tools-3.13/

]# make   install

]# ls /opt/

]# ls /opt/myrpm/

]# ls /opt/myrpm/bin/        
```

 

• 基本用法

– inotifywait  [选项]  目标文件夹

• 常用命令选项

– -m，持续监控（捕获一个事件后不退出）

– -r，递归监控、包括子目录及文件

– -q，减少屏幕输出信息

– -e，指定监视的 modify、move、create、delete、attrib 等事件类别    

 

#### **书写shell脚本**

脚本：可以运行一个文件，实现某种功能

中文:新建用户zhangsan    shell： useradd  zhangsan

 

重复性：循环解决

死循环：while循环 

   while 条件

   do

​     重复执行的事情

   done

 

```shell
[root@svr7 /]# vim  /etc/rsync.sh

while  /opt/myrpm/bin/inotifywait   -rqq  /mydir/

do

rsync -a  --delete  /mydir/  root@192.168.4.207:/opt

done

[root@svr7 /]# chmod  a+x  /etc/rsync.sh  #赋予执行权限

[root@svr7 /]# /etc/rsync.sh  &  #运行脚本程序

[root@svr7 /]# jobs -l

[1]+ 17707 运行中        /etc/rsync.sh &

[root@svr7 /]# kill  17707    #停止脚本
```



### 四、 数据库服务基础（数据库系统）

数据库：存放数据的仓库

在数据库系统中，有很多的数据库，在每一个库中有很多的表格

 

• 常见的关系型 数据库管理系统

– 微软的 SQL Server

– IBM的 DB2

– 甲骨文的 Oracle、MySQL

– 社区开源版 MariaDB 

– ……

 

####  **部署MariaDB 数据库系统**

```shell
[root@svr7 /]# yum -y install mariadb-server

[root@svr7 /]# systemctl  restart  mariadb
```

 

#### **MariaDB基本使用** 

1. Linux系统的管理指令不能使用

2. 所有的数据库系统指令都必须以 ; 结尾

3. 数据库系统的指令大部分不支持tab补全

 

```mariadb
[root@svr7 /]# mysql      #进入数据库系统

> create  database  nsd01;   #创建nsd01数据库

> show  databases;        #查看所有数据库

> drop  database  nsd01;   #删除数据库nsd01

> show  databases;        #查看所有数据库

> exit;
```

 

```mysql
[root@svr7 /]# mysql      #进入数据库系统

MariaDB [(none)]> use  mysql;     #切换到mysql数据库

MariaDB [mysql]> show  tables;    #查看当前库中所有表格

MariaDB [mysql]> show  databases;   #查看所有数据库

MariaDB [mysql]> use  test;  #切换到test数据库

MariaDB [test]> exit;
```

 

 

####  **为数据库系统管理员设置密码**

– mysqladmin  [-u用户名]  [-p[旧密码]]  password  '新密码'

 

数据库系统管理员:对于数据库系统有最高权限，名字为root，能够登陆数据系统的用户信息有mysql库中user表进行储存

 

Linux系统管理员: 对于Linux系统有最高权限，名字为root，能够登陆Linux系统的用户信息/etc/passwd进行储存

```mysql
[root@svr7 /]# mysqladmin  -u  root    password   '456'

[root@svr7 /]# mysql  -u  root  -p   #交互式进行登录

Enter password:

[root@svr7 /]# mysql  -u  root   -p456   #非交互式进行登录
```

 

已知旧密码修改新密码

```mariadb
]# mysqladmin  -u  root   -p456    password  '123'

]# mysql  -u  root   -p123
```

 

 

####  **恢复数据到数据库中**

1.建立新的数据库

```mariadb
[root@svr7 /]# mysql  -u  root   -p123

MariaDB [(none)]> create  database  nsd2008;

MariaDB [(none)]> show  databases;

MariaDB [(none)]> exit;
```

2.传递备份好的数据文件users.sql到虚拟机A中

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10228\wps2.jpg) 

```shell
[root@svr7 /]# ls  /root

abc02  users.sql       图片  桌面

[root@svr7 /]#
```

3.恢复数据到数据库

```mariadb
]# mysql -u root   -p123   nsd2008  <  /root/users.sql

]# mysql  -u  root  -p123

MariaDB [(none)]> use nsd2008;   #切换到数据库nsd2008

MariaDB [nsd2008]> show tables;   #查看当前库有哪些表格

+-------------------+

| Tables_in_nsd2008 |

+-------------------+

| base        |

| location      |

+-------------------+
```

 

#### **表格操作：**

**–** **增(insert)   删（delete）  改（update）  查(select)**

**–** **表字段、表记录**

| 编号 | 姓名 | 住址 |
| ---- | ---- | ---- |
| 1    | Dc   | 东村 |
| 2    | Tc   | 西村 |

**l** **查(select)** 

格式: select  表字段，表字段，……   from  库名.表名;

```mariadb
[root@svr7 /]# mysql  -u  root   -p123

> use nsd2008;

> select  *  from  base;     #查看base所有表字段内容

> select  *  from  location;   #查看location所有表字段内容

 

MariaDB [nsd2008]> use test;

MariaDB [test]> select  *  from   nsd2008.base;   

 

> use  nsd2008;

> select  id,name   from   base;

> select  *  from   base   where  password='456';

> select  *   from  base   where  id='4';
> select * from base   where  id='4'  and  password='123';

> select * from base   where  id='4'  or  password='123';
```

 

**l** **增(insert)**

格式：insert 表名   values (‘值’,‘值’,‘值’);

```mariadb
MariaDB [nsd2008]> insert  base  values('10','dc','789');

MariaDB [nsd2008]> insert  base  values('11','tcc','369');

MariaDB [nsd2008]> select  *  from base ;
```

 

**l** **改（update）**

格式：

update  表名   set 表字段=‘新值’ where 表字段=’值’；



```mysql
> select  *  from base ;

> update  base  set  password='8888'  where  id='1';

> select * from base ;  


> update  base  set  password='9999'  where  id='2';

> select * from base ;  
```



**l** **删（delete）**

```mysql
> delete  from base  where   id='4' ;

> select  *  from  base ;


> delete  from  base  where   id='3' ;

> select  *  from  base ;
 
```

#### ***•* 数据库授权操作**              

MariaDB [(none)]> 交互指令

– GRANT  权限列表  ON  数据库名.表名  TO  用户名@客户机地址  IDENTIFIED  BY   '密码';

 

```mysql
> grant  select   on   nsd2008.*   to  dcc@localhost  identified  by  '123';

> exit；
```

当dcc从localhost本地登录输入密码123，将会获得nsd2008库中所有表格的查询权限

```shell
[root@svr7 /]# mysql  -u  dcc   -p123   #测试
```



------

# 第一阶段月考

1、【单选题】
(单选题)下面关于IP地址的组成正确的是（  ）
A.IP地址由40个十进制组成 
B.IP地址由48个二进制数组成 
C.IP地址由32个二进制数组成 
D.IP地址由32个十进制数组成 
【正确答案】C
【答案解析】

2、【单选题】
(单选题)使用cp命令时以下说法正确的是（）
A.cp  -f 不可以拷贝文件 
B.cp  -r 可以拷贝文件，但不能拷贝目录 
C.cp  -f 可以拷贝目录 
D.cp  -rf 可以拷贝文件和目录 
【正确答案】D
【答案解析】cp命令-r选项可以拷贝目录，-f选项代表强制在cp命令运用中
由于有别名的存在所以-f无任何效果

3、【单选题】
(单选题)在Linux系统中配置防火墙策略时，通过（ ）命令重新加载防火墙策略
A.firewall-cmd --reload 
B.firewall-cmd --restart 
C.firewall-cmd --start 
D.firewall-cmd --repo 
【正确答案】A
【答案解析】无--restart、--start、--repo 选项

4、【单选题】
(单选题)创建用户时使用选项（）可指定用户id值
A.-d  
B.-u 
C.-s  
D.-G 
【正确答案】B
【答案解析】-d指定家目录，-s指定登录系统的解释器，-G指定附加组

5、【单选题】
(单选题)在常见的RAID级别中，（  ）的设备冗余度最好，也称为镜像模式
A.RAID6 
B.RAID1 
C.RAID0 
D.RAID5 
【正确答案】B
【答案解析】RAID0为条带模式无冗余，RAID5采用校验算法进行 可靠性的提升，RAID6为RAID5的提升

6、【单选题】
MariaDB数据库安装直接启动服务，默认的管理员用户密码是多少( )
A.mysql 
B.无密码 
C.tarna1 
D.123456 
【正确答案】B
【答案解析】在默认安装MySQL，直接启动服务，默认为空密码

7、【单选题】
(单选题)/tmp/存放的是（  ）文件
A.硬盘，键盘，鼠标，等各种设备文件 
B.日志文件 
C.系统运行中使用的临时文件 
D.内存中的映射文件，不占用磁盘 
【正确答案】C
【答案解析】无

8、【单选题】
(单选题)在Linux系统中配置防火墙策略时，通过（）命令设置永久策略
172.30.0.0/24网络进入drop区域
A.firewall-cmd --zone=drop --add-forward=172.30.0.0/24 
B.firewall-cmd --permanent --zone=drop --add-forward=172.30.0.0/24 
C.firewall-cmd --zone=drop --add-source=172.30.0.0/24 
D.firewall-cmd --permanent --zone=drop --add-source=172.30.0.0/24 
【正确答案】D
【答案解析】无

9、【单选题】
(单选题)在Linux系统中，以下（ ）命令可用来查找文件所在路径
A.whoami 
B.where 
C.grep 
D.find 
【正确答案】D
【答案解析】whoami显示当前用户，grep在文本文件内容过滤指定字符串， where无此命令

10、【单选题】
(单选题)配置Postfix邮件服务时，以下（ ）参数表示外发邮件时的发件域地址
A.mydestination 
B.myorigin 
C.mydomain 
D.inet_interfaces 
【正确答案】B
【答案解析】inet_interfaces指定网络接口，mydomain指定本机域名，mydestination指定收件人域名 为本域邮件

11、【单选题】
(单选题)下面关于列出内核版本命令正确的是（）
A.uname     -r 
B.lscpu  
C.cat    /etc/redhat-release 
D.cat   /proc/meminfo 
【正确答案】A
【答案解析】lscpu查看CPU信息，cat    /etc/redhat-release是查看系统
具体版本，cat   /proc/meminfo是查看内存信息，查看内核版本为
uname  -r

12、【单选题】
(单选题)扩展逻辑卷的命令为( )
A.vgcreate 
B.lvextend 
C.lvcreate 
D.vgextend 
【正确答案】B
【答案解析】lvcreate为创建逻辑卷的命令，vgcreate为创建卷组的命令，
vgextend为扩展卷组的命令

13、【单选题】
(单选题)在配置DNS服务的时候，正向解析记录的资源类型是（  ）
A.A 
B.PTR 
C.SOA 
D.CNAME 
【正确答案】A
【答案解析】PTR代表方向解析记录，CNAME代表解析记录别名，SOA代表授权记录

14、【单选题】
(单选题)在Linux上使用kickarstart生成ks文件yum仓库源ID应设置为（  ）
A.rhel7 
B.默认名称 
C.development 
D.ksckarstart 
【正确答案】C
【答案解析】通过图形工具system-config-kickstart生成ks文件时，软件包
可以选择需要将yum仓库源ID设置为[development] 

15、【单选题】
(单选题)创建卷组是如何指定PE大小( )
A.lvcreate -s PE大小 卷组名  空闲分区 
B.vgcreate -s PE大小 卷组名  空闲分区 
C.lvextend  -s PE大小 卷组名  空闲分区 
D.vgextend -s PE大小 卷组名  空闲分区 
【正确答案】B
【答案解析】lvcreate为创建逻辑卷，lvextend为扩展逻辑卷，在创建及扩展
逻辑卷时，均不能指定PE大小，vgextend为扩展卷组，扩展卷组时也不
能指定PE大小

16、【单选题】
(单选题)在Linux系统中从源代码安装软件时，编译成功后执行安装的命令通常是
（  ）
A../configure 
B.make 
C.make install 
D.make all 
【正确答案】C
【答案解析】无

17、【单选题】
(单选题)在Linux系统中，yum仓库的配置文件存放在/etc/yum.repos.d/目录下，一般以（ ）结尾
A..tar.gz 
B..bz2 
C..repo 
D..yum 
【正确答案】C
【答案解析】yum客户端文件必须以.repo结尾

18、【单选题】
(单选题)UNIX诞生日是什么时候(      )
A.1970年1月1号 
B.1969年年底 
C.1973年 
D.1991年10月 
【正确答案】A
【答案解析】UNIX操作系统诞生为1970-1-1

19、【单选题】
(单选题)在常见的Linux日志文件中，以下哪个文件（  ）的作用是记录与系统启动
相关的消息
A./var/log/maillog 
B./var/log/dmesg 
C./var/log/secure 
D./var/log/messages 
【正确答案】B
【答案解析】/var/log/messages记录各种服务公共消息，/var/log/secure记录用户登录安全相关，/var/log/maillog邮件收发相关信息

20、【单选题】
(单选题)以下哪种RAID级别必须使用四块及以上磁盘才能实现（  ）
A.RAID 0 
B.RAID 1 
C.RAID 10 
D.RAID 5 
【正确答案】C
【答案解析】RAID 0至少需要2块磁盘，RAID 1至少需要2块磁盘，RAID 5至少 需要3块磁盘

21、【单选题】
(单选题)在搭建PXE服务器时，用来提供给客户机的网卡引导文件是（  ）
A.vmlinuz 
B.vesamenu.c32 
C.ifcfg-eth0 
D.pxelinux.0 
【正确答案】D
【答案解析】ifcfg-eth0为网卡配置文件与PXE引导无关，vesamenu.c32为图形引导模块， vmlinuz启动加载的内核程序

22、【单选题】
(单选题)在Linux系统中，执行（ ）操作可以将/mail文件夹的属组设置为postfix
A.chmod postfix /mail 
B.chown :postfix /mail 
C.groupmod postfix /mail 
D.chmod :postfix /mail 
【正确答案】B
【答案解析】chmod无法修改归属关系，groupmod修改组账号属性的命令

23、【单选题】
(单选题)配置Postfix邮件服务时，通常应修改主配置文件（ ）
A./etc/postfix/master.conf 
B./etc/postfix/main.conf 
C./etc/postfix/mail.conf 
D./etc/postfix/main.cf 
【正确答案】D
【答案解析】无

24、【单选题】
(单选题)set GID中附加权限S 与s的有什么差别( )
A.S比s权限更高 
B.没有差别 
C.S比s权限低 
D.有执行权限为s 没有执行权限为S 
【正确答案】D
【答案解析】SGID附加权限，会叠加在所属组的执行权限位置，当所属组有执行权限显示为s，所属组没有执行权限显示为S

25、【单选题】
(单选题)在Linux系统中配置httpd服务器时，设置项（ ）用来指定该Web服务
器的站点名
A.ServerName 
B.DocumentRoot 
C.ServerRoot 
D.ServerAdmin 
【正确答案】A
【答案解析】DocumentRoot指定网页文件根目录，ServerAdmin指定管理员的邮箱，ServerRoot指定httpd配置文件根路径

26、【单选题】
(单选题)在Linux系统中，执行（  ）命令可以设置DHCP服务下次开机自启动
A.systemctl stop dhcpd 
B.systemctl enable dhcpd 
C.systemctl status dhcpd 
D.systemctl restart dhcpd 
【正确答案】B
【答案解析】无

27、【单选题】
(单选题)光盘的系统类型为(  )
A.xfs 
B.iso9660 
C.defaults 
D.iso9600 
【正确答案】B
【答案解析】xfs是RHEL7分区与系统常用的文件系统，iso9600无此 文件系统

28、【单选题】
(单选题)在Linux系统中，使用命令rpm -e卸载软件包时，返回错误提示：
“Failed dependencies”，这可能是由于（ ）
A.该软件包已损坏 
B.该软件包与其他软件包之间存在依赖关系 
C.该软件包已存在 
D.该软件包已不存在 
【正确答案】B
【答案解析】报错信息为错误的依赖关系

29、【单选题】
(单选题)Apache的网页文件默认根目录是在（ ）
A./etc/http/httpd/ 
B./etc/httpd	 
C./etc/http/ 
D./var/www/html/ 
【正确答案】D
【答案解析】无

30、【单选题】
(单选题)在Linux系统中，以下（ ）文件用来记录用户账号的用户名、家目录、登
录Shell等信息
A./etc/bashrc 
B./etc/passwd 
C./etc/shadow 
D./root/.bashrc 
【正确答案】B
【答案解析】/etc/passwd存放用户基本信息，/root/.bashrc定义root自定义初始化信息例如别名定义、变量定义等，/etc/shadow保存用户密码 信息，/etc/bashrc为全局配置文件

31、【单选题】
(单选题)在Linux系统中配置防火墙策略时，通过（ ）命令设置默认区域为
trusted
A.firewall-cmd --default --zone=trusted 
B.firewall-cmd --get-default-zone=trusted 
C.firewall-cmd --set-default-zone=trusted 
D.firewall-cmd --permanent  --zone=trusted 
【正确答案】C
【答案解析】无

32、【单选题】
(单选题)在/etc/passwd文件内有一条 student:x:600:1000::/home/student:/bin/bash 记录，其中的
600表示（ ）
A.用户ID号 
B.组ID号 
C.系统账号过期天数 
D.密码失效期限 
【正确答案】A
【答案解析】密码失效期限与系统账号过期天数存放在/etc/shadow中，
组id号位4个字段

33、【单选题】
(单选题)下列对于IP地址的作用和配置方法，描述正确的是(   )
A.IP地址可以唯一标识一台主机 
B.IP地址只能手工配置 
C.在一个局域网中IP地址可以重复 
D.IP地址只要配置DHCP自动获取，即可成功获取IP地址 
【正确答案】A
【答案解析】在局域网中IP地址不可重复；IP也可以通过DHCP自动获取 ；DHCP自动获取IP，需要局域网中具备DHCP服务器

34、【单选题】
(单选题)Windows查看IP地址的命令为（  ）
A.ifconf 
B.ipconf 
C.ipconfig 
D.ifconfig 
【正确答案】C
【答案解析】

35、【单选题】
(单选题)在Linux系统中，管理员发现PID为2048的进程没有响应，可以执行（  ）
命令强行中止该进程
A.kill +9 2048 
B.kill -9 2048 
C.killall +9 2048 
D.pkill  -9 2048 
【正确答案】B
【答案解析】pkill命令参数为进程名，killall命令参数为进程名

36、【单选题】
(单选题)通过执行tail -n 5 /var/log/messages后，得到的其中一行信息如下：  
Oct 29 13:19:48 web5 dhclient: DHCPACK from 192.168.8.254 (xid=0x7c.. ..)，其中web5表示的是（  ）
A.程序名 
B.时间标签 
C.消息内容 
D.主机名 
【正确答案】D
【答案解析】本题考查日志记录的格式，按照时间、地点、人物、发生的事件
进行记录，在计算机中地点会写主机名，所以Web5为主机名

37、【单选题】
(单选题)http默认监听的端口号是（ ）
A.23 
B.80 
C.53 
D.25 
【正确答案】B
【答案解析】23为telnet远程管理，53为dns域名解析，25位SMTP邮件 传输协议

38、【单选题】
(单选题)在Linux系统中，若要查询文件/etc/dovecot.conf 是由哪个RPM软件包
安装的，可以使用（  ）命令
A.rpm –ql /etc/dovecot.conf 
B.rpm –q /etc/dovecot.conf 
C.yum list /etc/dovecot.conf 
D.yum provides /etc/dovecot.conf 
【正确答案】D
【答案解析】无

39、【单选题】
(单选题)semanage  port  -a  -t  http_port_t  -p  tcp  8909 命令的含义
是什么(  )
A.调整SELinux策略，允许Web服务使用8909端口 
B.调整SELinux策略，拒绝Web服务使用8909端口 
C.在semanage中删除http端口 
D.在semanage中添加http端口 
【正确答案】A
【答案解析】本题考查SELinux策略设置，-a选项代表添加并非删除，作用 是允许Web服务使用8909端口

40、【单选题】
(单选题)在Linux系统中，若执行 scp dumb bilbo@www.foobar.com: 命令，
可以实现（  ）功能
A.将本地计算机当前目录下的一个名为“dumb”的文件发送到邮件 bilbo@www.foobar.com 
B.将本地计算机“dumb”目录下所有的文件拷贝到远程服务器 www.fobar.com的根目录下，并且登录远程服务器上的密码为“bilbo” 
C.将远程服务器www.foobar.com 上用户“bilbo”主目录下的一个名为 “dumb”的文件拷贝到本地计算机当前目录下，并且登录远程服务器上的账号名为 “bilbo” 
D.将本地计算机当前目录下的一个名为“dumb”的文档拷贝到远程主机www.foobar.com中用户 “bilbo”的主目录下 
【正确答案】D
【答案解析】无

41、【多选题】
(多选题)安装源码包时需要安装编译工具有（  ）
A.g++ 
B.C++	 
C.gcc 
D.make 
【正确答案】C,D
【答案解析】无

42、【多选题】
(多选题)以下（     ）属于Linux发行版本
A.Red Hat Enterprise Linux 
B.IBM AIX 
C.CentOS 
D.Windows Server 2008 
【正确答案】A,C
【答案解析】

43、【多选题】
(多选题)关于Linux命令行环境的通配符，以下描述正确的是（ ）
A.* 匹配单个字符 
B.{a,min,xy} 分别匹配不连续的a,min,xy多组字符 
C.？匹配任意多个字符 
D.[a-z] 匹配连续多个字符a-z中的一个 
【正确答案】B,D
【答案解析】*匹配任意多个字符，？匹配单个字符

44、【多选题】
(多选题)在Linux系统中，用户root依次执行下列操作：  
chmod  777  /dir；chmod o+t /dir；touch /dir/root.file ， 
则可知（  ）
A.普通账户可以在/dir目录下创建文件 
B.普通账户可以删除在/dir目录下自己创建的文件 
C.普通账户可以删除文件root.file 
D.普通账户可删除/dir目录下的所有文件 
【正确答案】A,B
【答案解析】权限为777说明其他人具备rwx，所以可以新建文档，但由于 有t权限，该权限限制删除非本人的文档

45、【多选题】
(多选题)常见的数据库软件有（ ）
A.DB2 
B.virtualbox 
C.SQL Server 
D.MySQL 
【正确答案】A,C,D
【答案解析】

46、【多选题】
(多选题)Linux典型的文件系统类型有（     ）
A.xfs 
B.swap 
C.ext4 
D.NTFS  
【正确答案】A,B,C
【答案解析】RHEL6默认的文件系统为ext4，RHEL7默认的文件系统为 xfs，Linux交换文件系统为swap，Windows一般为NTFS文件系统

47、【多选题】
把命令cp /ISO/1.txt /mnt无论状态如何，放入后台的命令是( )
A.快捷键Ctrl+z 
B.cp /ISO/1.txt  /mnt& 
C.cp /ISO/1.txt  /mnt $ 
D.Ctrl+C 
【正确答案】A,B
【答案解析】无

48、【多选题】
(多选题)在vim编辑器的（ ）工作模式中可以实现保存退出的操作
A.命令模式 
B.末行模式 
C.输入模式 
D.修改模式 
【正确答案】A,B
【答案解析】命令模式可以利用ZZ，末行模式为：wq

49、【多选题】
(多选题)Apache虚拟主机的类型包括（ ）
A.基于路由的虚拟主机 
B.基于域名的虚拟主机 
C.基于ip的虚拟主机 
D.基于端口的虚拟主机 
【正确答案】B,C,D
【答案解析】虚拟Web主机没有基于路由的类型

50、【多选题】
(多选题)selinux切换运行模式的方法（ ）
A.固定配置：/etc/selinux/selinux.cnf 
B.临时切换：setenforce  1或0 
C.临时切换：getenforce  1或0 
D.固定配置：/etc/selinux/config 文件 
【正确答案】B,D
【答案解析】修改SELinux模式，两个方面临时修改与固定修改，临时修改
通过命令setenforce而getenforce为查看不能达到修改，固定修改
需要修改/etc/selinux/config 文件

# NETWORK

## 01:计算机网络、网络通信参考模型、交换机命令行、交换机命令行配置、数据链路层解析



#### **什么是计算机网络**

硬件方面：通过线缆将网络设备和计算机连接起来

软件方面：操作系统，应用软件，应用程序通过通信线路互连

 

#### **网络的功能**

实现资源共享、信息传递、增加可靠性、提高系统处理能力

 

#### **网络的发展**

• 60年代

 分组交换

• 70-80年代

 TCP/IP

• 90代年后

 Web技术

 

#### **网络传输距离**

• 广域网（Wide-Area Network）

 范围:几十到几千千米 

 作用:用于连接远距离计算机网络

 典型应用:Internet（英特网）

• 局域网（Local-Area Network）

 范围:1千米左右 

 作用:用于连接较短距离内计算机

 典型应用:企业网,校园网

 

#### **标准化组织**

 ISO（国际标准化组织）

 IEEE（电气和电子工程师协会）

 

#### **网络重要设备**

路由器  用来连接两个不同的网络，比如内部的局域网与外部广域网的互联

交换机	 用来使设备接入网络，组建局域网

 

#### **局域网中常用的网络拓扑结构**

• 星型拓扑

易于实现

易于网络扩展

易于故障排查

• 网状拓扑结构

一个节点与其他多个节点相连

提供冗余性和容错性

可靠性高

组网成本高

 

#### **Tcp/ip五层参考模型以及对应的典型设备**

应用层		计算机

传输层		防火墙

网络层		路由器

数据链路层  交换机

物理层   网卡

 

#### **网络设备命令行视图**

```
<Huawei>				//用户视图

<Huawei> system-view		//进入系统视图

[Huawei]					//系统视图

[Huawei]interface ethernet0/0/1  //进入1号接口视图

[Huawei-Ethernet0/0/1]		//接口视图

[Huawei-Ethernet0/0/1]quit  //返回上一视图

[Huawei-Ethernet0/0/1]return  //返回用户视图(使用快捷

键crtl+z可以得到相同效果)

[Huawei]quit  //返回上一视图
```

 

#### **网络设备基本配置**

```
[Huawei]display version //查看系统的软硬件版本信息

[Huawei]sysname sw1  //修改主机名为sw1

[sw1]undo info-center enable   //关闭日志提示

[sw1]info-center enable  //开启日志提示

[sw1]display current-configuration  //查看大部分配置
```

 

#### **为设备添加用户并配置密码**

```
[Huawei]aaa   //进入可以管理账户的视图

[Huawei-aaa]local-user test01 password cipher 123456  //创

建用户名叫test01，密码是加密的123456

[Huawei-aaa]quit  //返回上一视图

[Huawei]user-interface console 0	//进入用户控制台

[Huawei-ui-console0]authentication-mode aaa  //激活刚刚

创建的账户

然后使用ctrl+] 退出系统，可以验证账户密码


<Huawei>save  //保存当前所有配置，过程中输入y，然后两次回车

<sw1>reboot  //重启设备，如果所有配置都保存，就会

询问是否重启，按y重启，如果有配置没保存，就会先询问

是否保存，然后在问是否重启
```

 

#### **网络中的地址：**

 

Ip地址  使用十进制标识

用来对用户所需的软件或者服务作为传递数据的标识，可以修改

192.168.0.1   0~9  

 

MAC地址(也叫 物理地址 或者 硬件地址) 使用十六进制标识

用来标识设备的唯一性，不可修改

54-89-98-B7-24-45   0~F  

 

#### **交换机工作原理**

学习  学习数据的源MAC地址

广播  向除了数据来源的所有接口发送寻找目标主机的信息

转发  1对1转发数据

更新 如果超过300秒没有数据传递，或者交换机所

​	 连接的设备断开，交换机都会清除对应的mac

​	 地址表记录

```
<Huawei>display mac-address  查看交换机mac地址表
```

#### **练习：**

1 请描述计算机网络的功能有哪些

```
数据通信、资源共享、增加可靠性、提高系统处理能力
```

2 计算机网络发展过程中，90年代诞生了什么标志性技术

```
web技术
```

3 标准化组织中ISO与IEEE分别是什么？

```
ISO（国际标准化组织）IEEE（电气和电子工程师学会）
```

4 局域网中常见网络拓扑结构有哪些？

```
星状 网状
```

5 TCP/IP的五层参考模型是哪几层，其中第二层的典型设备是什么？

```
物理层 数据链路层 网络层 传输层 应用层
第二层典型设备是 交换机
```

6 华为路由交换设备常见的命令行视图有哪些？

```
用户视图 系统视图 接口视图
```

7 通常以太网MAC地址使用什么进制？

```
十六进制 0~F
```

8 数据帧中数据部分的最大传输单元是多少字节？

```
1500 字节
```

9 交换机工作原理主要有哪几个步骤

```
学习 广播 转发 更新
```



## 02：VlAN技术及应用、TRUNK、网络层解析

### **广播域**

广播域指接收同样广播消息的节点的集合，如：在该集合中的任何一个节点传输一个广播帧，则所有其他能收到这个帧的节点都被认为是该广播帧的一部分

交换机的所有接口默认属于同一个广播域

 

### **Vlan**

#### • 什么是VLAN

 Virtual LAN（虚拟局域网）是物理设备上连接的不受物理位置限制的用户的一个逻辑组。

#### • 为什么引入VLAN

 交换机的所有接口默认属于同一个广播域

 随着接入设备的增多，网络中广播增多，降低了网络的效率

 为了分割广播域，引入了VLAN

 

### **VLAN的作用**

 广播控制

 增加安全性

 提高带宽利用

 降低延迟

 

### **VLAN的配置**

```
[Huawei]vlan 2		//创建vlan2

[Huawei-vlan2]display vlan  //查看vlan列表

[Huawei-vlan2]quit   

[Huawei]undo vlan 2  //删除vlan2

 

https://gitee.com/nsd-tedu/nsd2008  笔记连接地址

 

[Huawei-vlan2]interface Ethernet0/0/3  //进入3口

[Huawei-Ethernet0/0/3]port link-type access  //将3接口定义为接入

链路，接入链路表示该接口即将为某一个vlan传递数据

[Huawei-Ethernet0/0/3]port default vlan 2 //将3接口加入VLAN2,如

果加入了错误的vlan, 就在加一次（再输入一次加vlan的命令）正

确的vlan即可

[Huawei-Ethernet0/0/3]display vlan  //查看结果

 

[Huawei]undo vlan batch 10 to 20

[Huawei]vlan batch 2 3
```

 

### 使用接口组

```
[Huawei]port-group 1  //创建1号接口组

[Huawei-port-group-1]group-member Ethernet 0/0/3  Ethernet 0/0/4   # 多个使用to

//在该组添加成员，3口和4口

[Huawei-port-group-1]port link-type access  //将该组中所有接口配置为接

入链路

[Huawei-port-group-1]port default vlan 2  //将该组中所有接口加入VLAN2
```

 

```
[Huawei]port-group 2  //创建2号接口组

[Huawei-port-group-1]group-member Ethernet 0/0/5 Ethernet 0/0/6  

在该组添加成员，5口和6口

[Huawei-port-group-1]port link-type access  

[Huawei-port-group-1]port default vlan 3
```

 

**access  接入链路 可以承载1个vlan的数据**

**链路  可以承载多个vlan的数据**

 

两台交换机都按以下方式配置，即可实现仅仅使用一条线缆传递多个

Vlan的数据

```
[Huawei-Ethernet0/0/7]port link-type trunk  将7号接口配置为中继链路

[Huawei-Ethernet0/0/7]port trunk allow-pass vlan all  允许该接口放行所
```

有vlan的数据

注意！中继链路的线缆要在2台交换机都配置

排错：首先检查ip，再看vlan以及对应的接口，再检查两台交换机之间

的线路是否为trunk

最后测试，全网相同vlan的主机之间均可ping通即可

### **链路聚合**

多条线路负载均衡，带宽提高

容错，当一条线路失效时，不会造成全网中断

由于链路聚合配置需要在接口默认状态配置，所以要先清空

两台交换机的7号接口所有配置，相当于恢复默认

```
[Huawei]clear configuration interface Ethernet 0/0/7  //清空

7号接口的所有配置，途中输入y确认

[Huawei]interface Ethernet0/0/7  //进入7号口

[Huawei-Ethernet0/0/7]undo shutdown   //开启7号接口
```

 

然后在两台交换机做以下链路聚合的配置：

```
[Huawei]interface Eth-Trunk 1  //创建(进入)1号链路聚合接口

[Huawei-Eth-Trunk1]trunkport Ethernet 0/0/7 0/0/8  //将7号接

口与8号接口合并捆绑成一个接口，该接口的名字就叫做Eth-Trunk 1

[Huawei-Eth-Trunk1]port link-type trunk  //将链路聚合接口

配置为中继链路

[Huawei-Eth-Trunk1]port trunk allow-pass vlan all  //放行所有

Vlan的数据
```

###  **使用路由器连接不同网段：**

```
[Huawei]undo info-center enable  //关日志

[Huawei]interface gigabitEthernet0/0/0  //进入0号接口

[Huawei-GigabitEthernet0/0/0]ip address 192.168.1.254 24  //配置ip

[Huawei-GigabitEthernet0/0/0]in g0/0/1

[Huawei-GigabitEthernet0/0/1]ip address 192.168.2.1 24

[Huawei]display ip interface brief  //检查设备所有的ip地址配置情况

之后每个pc再配置对应网段的网关即可全网互通

192.168.1.1的网关是192.168.1.254

192.168.2.2的网关是192.168.2.1
```

 

### **ICMP  英特网控制报文协议**，

可以反馈网络中比如是否联通，花

费时间等信息

Ping  -t  持续ping

Ping  -l  1000  将ping包大小修改为1000字节

 

### **常见的ping反馈结果**

– 连接建立成功，Reply from 目标地址 .. ..

– 目标主机不可达，Destination host unreachable.

– 请求时间超时，Request timed out.

 

 

### **路由器是依靠路由表转发数据**

**路由表的产生方式：**

1， 直连路由，路由器接口配置好ip并开启则自动产生

2， 静态路由，由管理员手工配置，添加所要前往的地址

语法格式：ip route-static 目标网段地址 子网掩码  下一跳

 

第一台路由器：

```
[Huawei]ip route-static 192.168.3.0 24 192.168.2.2  //添加静态路由

使该路由设备可以前往3网段，下一跳地址是2.2

[Huawei]ip route-static 192.168.4.0 24 192.168.2.2

[Huawei]display ip routing-table | include /24  //查看路由表，已经

多出了3.0网段的路由

<Huawei>display  ip  interface  brief   //查看ip配置情况
```

 

第二台路由器：

```
[Huawei]ip route-static 192.168.1.0 24 192.168.2.1  //添加静态路由

使该路由设备可以前往1网段，下一跳地址是2.1
```



### **练习：**

1，VLAN的作用是什么？

```
广播控制（避免广播泛滥），增加安全性，提高带宽利用，降低延迟
```

2，TRUNK的作用是什么？

```
为数据帧打上VLAN标识，使不同VLAN数据可以用一条链路传递（单一链路可以承载多个vlan的数据）
```

3，链路聚合的作用是什么？

```
提供更高的带宽和增加可靠性
```

4，网络层的功能有哪些？

```
定义了基于IP协议的逻辑地址
连接不同的媒介类型
选择数据通过网络的最佳路径
```

5，ping工具与哪个协议有关？

```
ICMP
```

6，静态路由配置语法格式是？

```
ip route-static 目标网段 子网掩码 下一跳地址
```

7，路由设备依靠什么转发数据？

```
路由表
```

------

 

## 03：OSPF 、传输层、ACL

#### **三层交换机**

**同时具备交换机与路由器功能的强大网络设备**

**三层交换=二层交换+三层转发**

 

按图搭建拓扑，最上面的设备是s5700三层交换机

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7684\wps1.jpg) 

 

```
<Huawei>system-view 		//进入系统视图

[Huawei]undo info-center enable  //关日志

[Huawei]vlan batch 2 3  //创建vlan2与3

[Huawei]display vlan  //检查

[Huawei]interface GigabitEthernet 0/0/2  //进2口

[Huawei-GigabitEthernet0/0/2]port link-type access  //配置接口类型为access

[Huawei-GigabitEthernet0/0/2]port default vlan 2  //把2口加入vlan2

[Huawei-GigabitEthernet0/0/2]in g0/0/3

[Huawei-GigabitEthernet0/0/3]port link-type access  //配置接口类型为access

[Huawei-GigabitEthernet0/0/3]port default vlan 3  //把3口加入vlan3
```



 

**路由器的接口可以直接配置ip，但是三层交换机不行，需要在vlan接口配置**

**三层交换机接口配置ip思路：**

**1，** **创建对应vlan**

**2，** **进入vlan配置ip**

**3，** **再把打算配置ip的物理接口加入该vlan**

 

```
[Huawei]interface Vlanif 1		//进入vlan1的接口

[Huawei-Vlanif1]ip address 192.168.1.254 24   //配置ip，该ip可以作为vlan1的网关

[Huawei-Vlanif1]interface Vlanif 2  //进入vlan2的接口

[Huawei-Vlanif2]ip address 192.168.2.254 24  //配置ip，该ip可以作为vlan2的网关

[Huawei-Vlanif2]interface Vlanif 3  //进入vlan3的接口

[Huawei-Vlanif3]ip address 192.168.3.254 24  //配置ip，该ip可以作为vlan3的网关
```

再配置pc的网关即可实现全网互通

Pc1在vlan1中，所以网关是192.168.1.254

Pc2在vlan2中，所以网关是192.168.2.254

Pc3在vlan3中，所以网关是192.168.3.254

至此可以实现所有pc全网互通

 

然后按下图添加s3700交换机，用来连接pc与三层交换机：

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7684\wps2.jpg) 

在s3700交换机配置：

```
[Huawei]vlan batch 2 3   //首先创建vlan2与3

[Huawei]in e0/0/2

[Huawei-Ethernet0/0/2] port link-type access

[Huawei-Ethernet0/0/2] port default vlan 2   //将e0/0/2口加入vlan2

[Huawei-Ethernet0/0/2] in e0/0/3

[Huawei-Ethernet0/0/3] port link-type access

[Huawei-Ethernet0/0/3] port default vlan 3   //将e0/0/3口加入vlan3

[Huawei-Ethernet0/0/3] in e0/0/4

[Huawei-Ethernet0/0/4]port link-type trunk  //将4口配置为中继链路

[Huawei-Ethernet0/0/4]port trunk allow-pass vlan all  //放行所有数据
```



再回到s5700配置：

```
[Huawei-GigabitEthernet0/0/1]port link-type trunk    //把g0/0/1口也配置为中继链路

[Huawei-GigabitEthernet0/0/1]port trunk allow-pass vlan all  //放行所有vlan的数据
```

至此所有pc依然可以全网互通，而且只占用了一个三层交换机的接口

 

之后将拓扑延申，增加一台ar2220路由器，与pc一台，并按图配置好ip，pc的网关是192.168.5.254

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7684\wps3.jpg) 

路由器的接口分别配置192.168.4.2与192.168.5.254两个ip，配置命令此处省略

s5700的 2接口要按照三层交换机接口配置ip的思路进行：

```
[Huawei]vlan 4   //创建vlan4

[Huawei-vlan4]in vlan 4  //进入vlan4接口

[Huawei-Vlanif4]ip add 192.168.4.1 24    //为vlan4配置ip

[Huawei-Vlanif4]in g0/0/2   //进入2接口

[Huawei-GigabitEthernet0/0/2]port link-type access  //配置接口类型为access

[Huawei-GigabitEthernet0/0/2]port default vlan 4  //把2口加入vlan4
```



#### **动态路由**

基于某种路由协议实现

动态路由特点： 减少了管理任务

 

#### **动态路由的重要操作步骤：**

宣告，告知外界本机所直连的网段

 

子网掩码的不同写法：

十进制 255.255.255.0  /24

二进制 11111111. 11111111. 11111111.00000000

反掩码（子网掩码在某些工具中的特殊配置方式） 写时要把1变成0，0变成1

​	比如255.255.255.0 可以写成0.0.0.255

 

```
[Huawei]ospf			//进入ospf动态路由协议视图

[Huawei-ospf-1]area 0  //定义区域0，整个网络的第一个ospf区域

[Huawei-ospf-1-area-0.0.0.0]network 192.168.1.0 0.0.0.255  //依次宣告
```

自身所直连的网段

```
[Huawei-ospf-1-area-0.0.0.0]network 192.168.2.0 0.0.0.255

[Huawei-ospf-1-area-0.0.0.0]network 192.168.3.0 0.0.0.255

[Huawei-ospf-1-area-0.0.0.0]network 192.168.4.0 0.0.0.255
```

然后到ar2220路由器配置：

```
[Huawei]ospf

[Huawei-ospf-1]area 0

[Huawei-ospf-1-area-0.0.0.0]network 192.168.4.0 0.0.0.255

[Huawei-ospf-1-area-0.0.0.0]network 192.168.5.0 0.0.0.255
```



 

配置结束后，可以按以下方式查看ospf配置结果

```
[Huawei]ospf	

[Huawei-ospf-1]display this  //查看ospf配置

[Huawei]display ip routing-table | in /24  //或者使用查看路由表命令

验证是否学习到了路由，目前无论是三层交换机还是路由器都应该具有

1~5个网段的路由

最终该图需要实现所有设备全网互通。
```



\--------------------------------------------------------------------------------------------------

#### **传输层作用**

**传输层提供端到端的连接，定义了端口号**

 

**传输层协议**

**TCP（Transmission Control Protocol）**

**传输控制协议**

**可靠的、面向连接的协议**

**传输效率低**

 

#### **TCP的握手机制**

**三次握手  SYN（打算与对方建立连接）--- ACK（确认）+ SYN---ACK**

**四次断开  FIN（打算与对方断开连接）--- ACK--- FIN---ACK**

 

#### **使用了TCP的服务名称以及端口号**

 ![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7684\wps4.jpg)

 

#### **UDP（User Datagram Protocol）**

**用户数据报协议**

**不可靠的、无连接的服务**

**传输效率高**

 

#### 使用了UDP的服务名称以及端口号

 ![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7684\wps5.jpg)



**ACL  访问控制列表**

**可以控制网络设备传输数据的工具**

**在相同接口的相同方向，同一时刻只能应用一个acl列表**

 

#### **基本ACL**

**基于源IP地址过滤数据包**

**列表号是2000～2999**

 

#### **高级ACL**

**基于源IP地址、目的IP地址、源端口、目的端口、协议**

  **过滤数据包**

**列表号是3000～3999**

 

首先按下图创建拓扑，练习基本acl

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7684\wps6.jpg) 

 

路由器配置ip：

```
[Huawei]in g/0/0		//进入0口

[Huawei-GigabitEthernet0/0/0]ip add 192.168.1.254 24  //配置ip

[Huawei-GigabitEthernet0/0/0]in g0/0/1

[Huawei-GigabitEthernet0/0/1]ip add 192.168.2.254 24
```

之后所有的server与client都要按图配置ip

1网段的网关是1.254   2网段的网关是2.254

 

#### **反掩码使用规则：**

**0 匹配		1 不匹配   这里的1只的是二进制写法，十进制可以用255标识**

> 比如这样写 192.168.0.1  0.0.0.255  那么192.168.0.100来了就会执行acl规则，因为0.0.0.255是只要匹配192.168.0.1的前三位，192.168.0.100的前三位与之一致，如果是192.168.1.100来了就不执行。
>
> 如果这样写 192.168.0.1  0.0.255.255  就是匹配前两位， 那么 192.168.1.100来了就执行
>
> 如果这样写 192.168.0.1  0.0.0.0  那么只有192.168.0.1来了才执行

 

**禁止主机PC2与PC1通信，而允许所有其他的流量**

```
[Huawei]acl 2000   //创建acl 列表号是2000

[Huawei-acl-basic-2000]rule deny source 192.168.2.1 0.0.0.0  //创建规则
```

拒绝源地址是192.168.2.1的数据通过

```
[Huawei-acl-basic-2000]undo rule 5  //如果写错，就删除，5是第一个规则的号码，可以使用display this查看当前列表中有多少个规则，每个规则的号码都是多少。

[Huawei-acl-basic-2000]in g0/0/1  //进入1口

[Huawei-GigabitEthernet0/0/1]traffic-filter inbound acl 2000  //定义过滤

数据是入方向，并应用之前创建的acl2000

[Huawei-GigabitEthernet0/0/1]display acl all  //查看所有的acl
```

 

**允许主机pc2与pc1互通，而禁止其他设备访问pc1**

可以删除acl2000中的规则重新写，也可以新建acl列表

```
[Huawei-GigabitEthernet0/0/1]acl 2001  //创建新acl，列表号是2001

[Huawei-acl-basic-2001]rule permit source 192.168.2.1 0  //创建规则，允许2.1通过

[Huawei-acl-basic-2001]rule deny source any  //拒绝所有设备通过

[Huawei-GigabitEthernet0/0/1]undo traffic-filter inbound  //在接口取消之前的acl2000

[Huawei-GigabitEthernet0/0/1]traffic-filter inbound acl 2001  //应用新的acl
```



#### **练习：**

1，传输层有哪些协议，各有什么特点？

```
TCP 传输控制协议
可靠的、面向连接的协议 传输效率低
UDP 用户数据报协议
不可靠的、无连接的服务 传输效率高
```

2，描述TCP三次握手以及四次断开的基本过程

```
三次握手
1，用户发送syn给服务器
2，服务器发送ack与syn给用户
3，用户发送ack给服务器

四次断开
1，用户发送fin给服务器
2，服务器发送ack给用户
3，服务器发送fin给用户
4，用户发送ack给服务器
```

3，SMTP、DNS、SSH、TFTP、NTP分别是什么协议，使用了什么端口，在传输层使用什么协议？

```
SMTP 简单邮件传输协议 端口号25 tcp
DNS 域名系统 端口号53 tcp/udp
ssh 远程登录 端口号22 tcp 
TFTP 简单文件传输协议 端口号69 udp
NTP 网络时间协议 端口号123 udp
```

4，网络设备中的ACL技术常见类型有哪些，各有什么区别？

```
基本ACL
基于源IP地址过滤数据包
基本访问控制列表的列表号是2000~2999

高级ACL
基于源IP地址、目的IP地址、指定协议、端口来过滤数据包
高级访问控制列表的列表号是3000~3999
```

## 04：NAT 、VRRP

==================================

### **使用高级acl限制网络数据**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10436\wps1.jpg) 

**禁止2.1访问1.1的ftp**

```
[Huawei]acl 3000  //创建(进入)acl3000

[Huawei-acl-adv-3000]rule deny tcp source 192.168.2.1 0 destination

 192.168.1.1  0 destination-port eq 21  //拒绝2.1访问1.1的tcp的21端口

[Huawei-acl-adv-3000]in g0/0/1  //进入1接口

[Huawei-GigabitEthernet0/0/1]undo traffic-filter inbound  //取消之前的acl

[Huawei-GigabitEthernet0/0/1]traffic-filter inbound acl 3000  //启用新acl3000

此时测试2.1已经无法访问1.1的ftp，但是可以访问网站
```

 

**禁止2.2访问1.1的www如何做到**

```
[Huawei-GigabitEthernet0/0/1]acl 3000  //重新回到acl3000里

[Huawei-acl-adv-3000]rule deny tcp source 192.168.2.2 0 destination 

192.168.1.1 0 destination-port eq 80  //拒绝2.2访问1.1的tcp的80端口 

此时测试2.2已经无法访问1.1的网站，但是可以访问ftp
```

\---------------------------------------------------------------------------------------

 

### **NAT (Network Address Translation)，网络地址转换**

**通过将内部网络的私有IP地址翻译成全球唯一的公网IP地址，使内部网络可以连接到互联网等外部网络上。**

 

#### **NAT的优点**

**节省公有合法IP地址、处理地址重叠、增加安全**

#### **NAT的缺点**

**延迟增大、配置和维护的复杂性**

 

#### **私有ip地址范围**

A 10.0.0.0~10.255.255.255

B 172.16.0.0~172.31.255.255

C 192.168.0.0~192.168.255.255



#### 特殊地址

127.0.0.1  本机回环

169.254.xxx.xxx  无效的临时地址

 

Ipv4  32位长度  42亿+的地址空间

ipv6  128位长度  几乎无限的地址空间

 

**按图配置地址**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10436\wps2.jpg) 

配置路由器：

```
[Huawei]in g0/0/1

[Huawei-GigabitEthernet0/0/1]ip add 100.0.0.1 8

[Huawei-GigabitEthernet0/0/1]in g0/0/0

[Huawei-GigabitEthernet0/0/0]ip add 192.168.2.254 24
```

 

**静态转换** 1对1 1台内部主机可以利用1个公网ip访问外部网络

​		 通常有服务器设备发布服务到外网时使用，双向通信

**Easy ip**  多对1 多台内部主机可以利用1个公网ip访问外部网络

​	   通常办公室环境使用，单向通信 

 

**在路由器配置静态nat** 

```
[Huawei]in g0/0/1   //进入外网接口

[Huawei-GigabitEthernet0/0/1]nat static global 100.0.0.2 inside 192.168.2.1  //使用

静态nat技术，将内部的2.1与外部的公网地址100.0.0.2进行相互转换

[Huawei-GigabitEthernet0/0/1]nat static global 100.0.0.3 inside 192.168.2.2

之后效果是2.1与2.2可以利用外网地址ping通100.0.0.10

反之，100.0.0.10也可以ping通2.1与2.2的公网地址
```



 

**在路由器配置easy ip，让所有的内部主机仅仅利用唯一的一个公网地址100.0.0.1访问外网**

```
[Huawei]acl 2000  //通过acl定义允许访问外网的设备

[Huawei-acl-basic-2000]rule permit source any  //这里放行所有设备

[Huawei-acl-basic-2000]in g0/0/1  //进入1接口

[Huawei-GigabitEthernet0/0/1]undo nat static global 100.0.0.3 inside 192.168.2.2  //删除已有的静态nat

[Huawei-GigabitEthernet0/0/1]undo nat static global 100.0.0.2 inside 192.168.2.1

[Huawei-GigabitEthernet0/0/1]nat outbound 2000  //应用nat

[Huawei-GigabitEthernet0/0/1]undo nat outbound 2000  //如果nat无效，删除重新配置即可

之后效果是2.1与2.2可以利用外网地址ping通100.0.0.10

反之，100.0.0.10不可以ping通2.1与2.2的外网地址
```

\----------------------------------------------------------------------

### **VRRP是虚拟路由冗余协议**

**VRRP能够在不改变组网的情况下，将多台路由器虚拟成一个虚拟路由器，通过配置虚拟路由器的IP地址为默认网关，实现网关的备份**

 

#### **VRRP组成员角色**

**主（Master）路由器**

**备份（Backup）路由器**

**虚拟（Virtual）路由器**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10436\wps3.jpg) 

```
<Huawei>sys

[Huawei]sysname sw1		//修改主机名为sw1	

[sw1]undo info-center enable  //关闭日志

[sw1]in vlan 1  //进入vlan1

[sw1-Vlanif1]ip add 192.168.1.252 24  //配置ip

[sw1]vlan 2  //创建vlan2

[sw1-vlan2]in vlan 2  //进入vlan2接口

[sw1-Vlanif2]ip add 192.168.2.2 24  //配置ip

[sw1-Vlanif2]in g0/0/2  //进入2口

[sw1-GigabitEthernet0/0/2]port link-type access

[sw1-GigabitEthernet0/0/2]port default vlan 2  //将2口加入vlan2
```

另外一台s5700

```
<Huawei>sys

[Huawei]sysname sw2

[sw2]undo info-center enable 

[sw2]in vlan 1

[sw2-Vlanif1]ip add 192.168.1.253 24

[sw2]vlan 3

[sw2-vlan3]in vlan 3

[sw2-Vlanif3]ip add 192.168.3.2 24

[sw2-Vlanif3]in g0/0/2

[sw2-GigabitEthernet0/0/2]port link-type access

[sw2-GigabitEthernet0/0/2]port default vlan 3
```

 

路由器配置：

```
[Huawei]in g0/0/0

[Huawei-GigabitEthernet0/0/0]ip add 192.168.2.1 24

[Huawei-GigabitEthernet0/0/0]in g0/0/1

[Huawei-GigabitEthernet0/0/1]ip add 192.168.3.1 24

[Huawei-GigabitEthernet0/0/1]in g0/0/2

[Huawei-GigabitEthernet0/0/2]ip add 192.168.4.254 24

<Huawei>display ip interface brief
```

 

然后分别在路由器与三层交换机上配置ospf

```
[Huawei]ospf 

[Huawei-ospf-1]area 0

[Huawei-ospf-1-area-0.0.0.0]network 192.168.2.0 0.0.0.255

[Huawei-ospf-1-area-0.0.0.0]network 192.168.3.0 0.0.0.255

[Huawei-ospf-1-area-0.0.0.0]network 192.168.4.0 0.0.0.255

[sw1]ospf

[sw1-ospf-1]area 0

[sw1-ospf-1-area-0.0.0.0]network 192.168.1.0 0.0.0.255

[sw1-ospf-1-area-0.0.0.0]network 192.168.2.0 0.0.0.255

[sw2]ospf

[sw2-ospf-1]area 0

[sw2-ospf-1-area-0.0.0.0]network 192.168.1.0 0.0.0.255

[sw2-ospf-1-area-0.0.0.0]network 192.168.3.0 0.0.0.255
```

 

在三层交换机配置vrrp

```
[sw1]in vlan 1  //vrrp需要在接口中配置，进入vlan接口

[sw1-Vlanif1]vrrp vrid 1 virtual-ip 192.168.1.254  //开启vrrp功能，组号是1，虚拟设备的ip是1.254

<sw1>display vrrp brief  //查看vrrp状态

[sw1-Vlanif1]vrrp vrid 1 priority 105  //修改vrrp优先级，默认值是100，越高越优先成为主

[sw2]in vlan 1  //另外这台设备配置一样的内容

[sw2-Vlanif1]vrrp vrid 1 virtual-ip 192.168.1.254

<sw2>display vrrp brief
```



#### **通过配置实现vrrp的负载均衡**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml10436\wps4.jpg) 

1， 所有交换机修改主机名sw1~sw4，所有交换机创建vlan2

```
[Huawei]sysname sw1   //第1台s5700交换机（左）

[sw1]vlan 2

[Huawei]sysname sw2   //第2台s5700交换机

[sw2]vlan 2

[Huawei]sysname sw3   //第1台s3700交换机（左）

[sw3]vlan 2

[Huawei]sysname sw4   //第2台s3700交换机

[sw4]vlan 2
```

2， 将所有链路修改为trunk

```
[sw1]port-group 1

[sw1-port-group-1]group-member GigabitEthernet 0/0/1 to 

GigabitEthernet 0/0/3

[sw1-port-group-1]port link-type trunk

[sw1-port-group-1]port trunk allow-pass vlan all

 

[sw2]port-group 1

[sw2-port-group-1]group-member GigabitEthernet 0/0/1 to 

GigabitEthernet 0/0/3

[sw2-port-group-1]port link-type trunk

[sw2-port-group-1]port trunk allow-pass vlan all

 

[sw3]port-group 1

[sw3-port-group-1]group-member Ethernet 0/0/1 Ethernet 0/0/2

[sw3-port-group-1]port link-type trunk 

[sw3-port-group-1]port trunk allow-pass vlan all

 

[sw4]port-group 1

[sw4-port-group-1]group-member Ethernet 0/0/1 Ethernet 0/0/2

[sw4-port-group-1]port link-type trunk 

[sw4-port-group-1]port trunk allow-pass vlan all
```

 

然后按图配置三层交换机的ip

```
[sw1]in vlan 1

[sw1-Vlanif1]ip add 192.168.1.252 24

[sw1-Vlanif1]in vlan 2

[sw1-Vlanif2]ip add 192.168.2.252 24

[sw2]in vlan 1

[sw2-Vlanif1]ip add 192.168.1.253 24

[sw2-Vlanif1]in vlan 2

[sw2-Vlanif2]ip add 192.168.2.253 24
```

 

**如果要实现vrrp的负载均衡，需要按下列思路进行配置**

**Sw1  vlan1 主   vlan2备份**

**Sw2   vlan1 备份	 vlan2 主**

 

```
[sw1]in vlan 1

[sw1-Vlanif1]vrrp vrid 1 virtual-ip 192.168.1.254  //配置vlan1的vrrp

[sw1-Vlanif1]vrrp vrid 1 priority 105  //为了成为vlan1的主，修改了优先级

[sw1-Vlanif1]in vlan 2

[sw1-Vlanif2]vrrp vrid 2 virtual-ip 192.168.2.254  //vlan2仅仅开启vrrp功能即可

[sw2]in vlan 1

[sw2-Vlanif1]vrrp vrid 1 virtual-ip 192.168.1.254  //vlan1仅仅开启vrrp功能即可

[sw2-Vlanif1]in vlan 2

[sw2-Vlanif2]vrrp vrid 2 virtual-ip 192.168.2.254   //配置vlan2的vrrp

[sw2-Vlanif2]vrrp vrid 2 priority 105  //为了成为vlan2的主，修改了优先级

[sw2-Vlanif2]dis vrrp brief  //查看结果，一主一备即可
```

 

### 练习：

1，NAT的作用是什么，有哪些优点？

```
通过将内部网络的私网IP地址翻译成全球唯一的公网IP地址，使内部网络可以连接到互联网等外部网络上。
优点有节约公网ip、处理地址重叠(使用相同私网地址的主机不会冲突，可以利用不同的公网ip互通)、增加安全
```

2，私有IP地址分类有哪些？

```
A类 10.0.0.0~10.255.255.255
B类 172.16.0.0~172.31.255.255
C类 192.168.0.0~192.168.255.255
```

3，NAT常用实现方式有哪些，各有什么特点？

```
静态转换 可以实现1个私网地址对1个公网地址的转换 是双向通讯 服务器环境常用
Easy IP 可以实现多个私网地址对1个公网地址的转换 是单向通讯 办公室环境常用
```

4，VRRP是什么，具体的作用是什么？

```
vrrp是虚拟路由冗余协议
可以实现网关的冗余备份，可以保障网关设备出现故障的情况下不会对网络造成重大影响。
```

5，VRRP中设备的身份有哪些？

```
主(master)路由器，备份(backup)路由器，虚拟(virtual)路由器
```

6，VRRP通过什么定义路由设备的主备身份？

```
可以修改优先级来决定
```



## 05:综合项目、网络升级

==================================

### 查询命令回顾

```
<Huawei>display current-configuration  //查看大部分配置

<Huawei>display version  //查看软硬件版本

<Huawei>display ip interface brief  //查看接口ip

<Huawei>display vlan  //查看vlan列表

<Huawei>display mac-address  //查看mac地址表

<Huawei>display ip routing-table  //查看完整路由表

<Huawei>display ip routing-table | include /24  //查看只包含/24

的路由信息

<Huawei>display acl all  //查看所有acl列表

<Huawei>display acl 2000  //只查看列表是2000的acl

<Huawei>display this  //查看当前视图的配置

<Huawei>display vrrp brief  //查看vrrp摘要信息
```

 

### **组建大型企业网络**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7888\wps1.jpg) 

#### 步骤一：为3700交换机修改主机名，配置vlan

1.

```
[Huawei]sysname sw1  //依次将名称修改为sw1~sw4

[sw1]undo info-center enable  //关闭日志
```

2.

```
[sw1]vlan batch 10 20 30 40  //依次在4台3700创建4个vlan
```

#### 步骤二：将终端设备加入对应vlan，并将所有s3700的千兆接口配置为中继链路

1.

```
[sw1]in e0/0/1

[sw1-Ethernet0/0/1]port link-type access  //配置为接入链路

[sw1-Ethernet0/0/1]port default vlan 10   //将1口加入vlan10

[sw2]in e0/0/1

[sw2-Ethernet0/0/1]port link-type access 

[sw2-Ethernet0/0/1]port default vlan 20   //将1口加入vlan20

[sw3]in e0/0/1

[sw3-Ethernet0/0/1]port link-type access 

[sw3-Ethernet0/0/1]port default vlan 30   //将1口加入vlan30

[sw4]in e0/0/1

[sw4-Ethernet0/0/1]port link-type access 

[sw4-Ethernet0/0/1]port default vlan 40   //将1口加入vlan40

[sw4-Ethernet0/0/1]in e0/0/2

[sw4-Ethernet0/0/2]port link-type access

[sw4-Ethernet0/0/2]port default vlan 40   //将2口也加入vlan40
```

 

2, 配置trunk

```
[sw1-Ethernet0/0/1]in g0/0/1

[sw1-GigabitEthernet0/0/1]port link-type trunk  //配置中继链路

[sw1-GigabitEthernet0/0/1]port trunk allow-pass vlan all  //放行所有

[sw1-GigabitEthernet0/0/1]in g0/0/2

[sw1-GigabitEthernet0/0/2]port link-type trunk

[sw1-GigabitEthernet0/0/2]port trunk allow-pass vlan all

 

[sw2]port-group 1  //创建1号接口组

[sw2-port-group-1]group-member GigabitEthernet 0/0/1 

GigabitEthernet 0/0/2  //加成员是g1口与g2口

[sw2-port-group-1]port link-type trunk  //也同样配置为中继链路

[sw2-port-group-1]port trunk allow-pass vlan all  //放行所有

 

[sw3]port-group 1

[sw3-port-group-1]group-member GigabitEthernet 0/0/1 

GigabitEthernet 0/0/2

[sw3-port-group-1]port link-type trunk

[sw3-port-group-1]port trunk allow-pass vlan all

 

[sw4]port-group 1

[sw4-port-group-1]group-member GigabitEthernet 0/0/1 GigabitEthernet 0/0/2

[sw4-port-group-1]port link-type trunk

[sw4-port-group-1]port trunk allow-pass vlan all
```

 

#### 步骤三：添加两台s5700，并修改主机名为sw5与sw6，再创建所

有vlan

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7888\wps2.jpg) 

1，

```
[Huawei]sysname sw5			//该主机名

[sw5]undo info-center enable	//关闭日志
```

2，

```
[sw5]vlan batch 10 20 30 40  //批量创建4个vlan

[sw6]vlan batch 10 20 30 40
-----------------------------------
另外：如果发现某个接口配置混乱，可以恢复默认
[Huawei]clear configuration interface Ethernet 0/0/7  //清空
7号接口的所有配置，途中输入y确认
[Huawei]interface Ethernet0/0/7   //进入7号口
[Huawei-Ethernet0/0/7]undo shutdown    //开启7号接口
-----------------------------------
```

#### 步骤四：为两台s5700连接了s3700的接口配置中继链路，

然后在两台s5700之间连接两根链路，并配置为链路聚合

1，配置两台s5700的中继链路

```
[sw5]port-group 1  //由于需要配置g1~g4口，这里使用接口组

[sw5-port-group-1]group-member GigabitEthernet 0/0/1 to 

GigabitEthernet 0/0/4  //加g1~g4接口

[sw5-port-group-1]port link-type trunk  //配置为中继链路

[sw5-port-group-1]port trunk allow-pass vlan all  //放行所有

[sw6]port-group 1  //另外一台也是相同配置

[sw6-port-group-1]group-member GigabitEthernet 0/0/1 to 

GigabitEthernet 0/0/4

[sw6-port-group-1]port link-type trunk

[sw6-port-group-1]port trunk allow-pass vlan all
```

 

2，将每台s5700的5口和6口捆绑成链路聚合，并配置中继链路

```
[sw5]interface Eth-Trunk 1  //创建(进入)链路聚合接口

[sw5-Eth-Trunk1]trunkport GigabitEthernet 0/0/5 0/0/6  //捆绑5口

与6口

[sw5-Eth-Trunk1]port link-type trunk  //配置成中继链路

[sw5-Eth-Trunk1]port trunk allow-pass vlan all  //放行所有

[sw6]interface Eth-Trunk 1

[sw6-Eth-Trunk1]trunkport GigabitEthernet 0/0/5 0/0/6

[sw6-Eth-Trunk1]port link-type trunk 

[sw6-Eth-Trunk1]port trunk allow-pass vlan all

 
```

然后按规划将线缆连接好

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7888\wps3.jpg) 

依次为pc配置ip

10.1  20.1  30.1  40.1  40.2



#### 步骤五：为s5700配置ip地址

1，s5700的vlan配置不同ip

```
[sw5]in vlan 10

[sw5-Vlanif10]ip add 192.168.10.252 24

[sw5-Vlanif10]in vlan 20

[sw5-Vlanif20]ip add 192.168.20.252 24

[sw5-Vlanif20]in vlan 30

[sw5-Vlanif30]ip add 192.168.30.252 24

[sw5-Vlanif30]in vlan 40

[sw5-Vlanif40]ip add 192.168.40.252 24

 

[sw6]in vlan 10

[sw6-Vlanif10]ip add 192.168.10.253 24

[sw6-Vlanif10]in vlan 20

[sw6-Vlanif20]ip add 192.168.20.253 24

[sw6-Vlanif20]in vlan 30

[sw6-Vlanif30]ip add 192.168.30.253 24

[sw6-Vlanif30]in vlan 40

[sw6-Vlanif40]ip add 192.168.40.253 24

 

Sw5  vlan10、vlan20主  vlan30、vlan40备

Sw6  vlan10、vlan20备  vlan30、vlan40主
```



#### 步骤六：在s5700配置vrrp，并实现负载均衡

Sw5  vlan10、vlan20主  vlan30、vlan40备

Sw6  vlan10、vlan20备  vlan30、vlan40 主

 

```
[sw5]in vlan 10  //进入vlan10接口

[sw5-Vlanif10]vrrp vrid 10 virtual-ip 192.168.10.254  //开启vrrp

并配置虚拟路由器ip是10.254

[sw5-Vlanif10]vrrp vrid 10 priority 105  //修改优先级为105

[sw5-Vlanif10]in vlan 20

[sw5-Vlanif20]vrrp vrid 20 virtual-ip 192.168.20.254

[sw5-Vlanif20]vrrp vrid 20 priority 105

[sw5-Vlanif20]in vlan 30

[sw5-Vlanif30]vrrp vrid 30 virtual-ip 192.168.30.254

[sw5-Vlanif30]in vlan 40

[sw5-Vlanif40]vrrp vrid 40 virtual-ip 192.168.40.254

 

[sw6]in vlan 10

[sw6-Vlanif10]vrrp vrid 10 virtual-ip 192.168.10.254

[sw6-Vlanif10]in vlan 20

[sw6-Vlanif20]vrrp vrid 20 virtual-ip 192.168.20.254

[sw6-Vlanif20]in vlan 30

[sw6-Vlanif30]vrrp vrid 30 virtual-ip 192.168.30.254

[sw6-Vlanif30]vrrp vrid 30 priority 105		//sw6要成为vlan30的主，所以

要修改优先级	

[sw6-Vlanif30]in vlan 40

[sw6-Vlanif40]vrrp vrid 40 virtual-ip 192.168.40.254

[sw6-Vlanif40]vrrp vrid 40 priority 105  	//sw6要成为vlan40的主，所以

要修改优先级	

<sw5>display vrrp brief

将所有pc的网关按照所在vlan配置好对应的虚拟

路由器的ip，并测试全网互通效果
```



#### 步骤七：添加两台ar2220路由器，修改主机名为r1与r2，并配置ip地址

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7888\wps4.jpg) 

1，

```
[Huawei]sysname r1   //改名

[r1]in g0/0/0  //进入0接口

[r1-GigabitEthernet0/0/0]ip add 192.168.50.1 24   //配置ip

[sw5]vlan 50  //创建vlan50

[sw5-vlan50]in vlan 50   //进入vlan50

[sw5-Vlanif50]ip add 192.168.50.2 24   //配置ip

[sw5-Vlanif50]in g0/0/7  //进入7口

[sw5-GigabitEthernet0/0/7]port link-type access 

[sw5-GigabitEthernet0/0/7]port default vlan 50  //加入vlan50

<sw5>display ip interface brief  //查看ip配置情况

其他ip按上图配置，此处省略
```



#### 步骤八：在所有路由器以及s5700配置动态路由

1，

```shell
[sw5]ospf  //开启动态路由协议ospf

[sw5-ospf-1]area 0	  //进入区域0

[sw5-ospf-1-area-0.0.0.0]network 192.168.10.0 0.0.0.255  //宣告

直连网段

[sw5-ospf-1-area-0.0.0.0]network 192.168.20.0 0.0.0.255

[sw5-ospf-1-area-0.0.0.0]network 192.168.30.0 0.0.0.255

[sw5-ospf-1-area-0.0.0.0]network 192.168.40.0 0.0.0.255

[sw5-ospf-1-area-0.0.0.0]network 192.168.50.0 0.0.0.255

[sw5-ospf-1-area-0.0.0.0]network 192.168.70.0 0.0.0.255

[sw6-ospf-1]area 0

[sw6-ospf-1-area-0.0.0.0]network 192.168.10.0 0.0.0.255

[sw6-ospf-1-area-0.0.0.0]network 192.168.20.0 0.0.0.255

[sw6-ospf-1-area-0.0.0.0]network 192.168.30.0 0.0.0.255

[sw6-ospf-1-area-0.0.0.0]network 192.168.40.0 0.0.0.255

[sw6-ospf-1-area-0.0.0.0]network 192.168.60.0 0.0.0.255

[sw6-ospf-1-area-0.0.0.0]network 192.168.80.0 0.0.0.255

[r1]ospf  //然后在两台路由器上也配置ospf

[r1-ospf-1]area 0

[r1-ospf-1-area-0.0.0.0]network 192.168.50.0 0.0.0.255

[r1-ospf-1-area-0.0.0.0]network 192.168.60.0 0.0.0.255

[r2]ospf

[r2-ospf-1]area 0

[r2-ospf-1-area-0.0.0.0]network 192.168.70.0 0.0.0.255

[r2-ospf-1-area-0.0.0.0]network 192.168.80.0 0.0.0.255

然后测试全网互通的效果
```

#### 步骤九：最上端添加s3700一台充当外部网络设备，并配置三个外网ip

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml7888\wps5.jpg) 

1，

```
[Huawei]in vlan 1

[Huawei-Vlanif1]ip add 100.0.0.10 8

两台路由器的g0/0/2口也按图配置ip，配置步骤此处省略。
```

 

**默认路由 是一种特殊的静态路由 可以匹配任意网络,专门用于从**

**内部网络访问海量的外部设备**



#### 步骤十：配置默认路由

1，

```shell
[r1]ip route-static 0.0.0.0 0 100.0.0.10  //配置默认路由，可以访问

任意网络

[r1]ospf

[r1-ospf-1]default-route-advertise  //发布默认路由，相当于宣告，然后

下面的三层交换就就可以学习到该默认路由

[r2]ip route-static 0.0.0.0 0 100.0.0.10

[r2]ospf

[r2-ospf-1]default-route-advertise  //发布默认路由

display ip routing-table  //查看完整路由表
```



#### 步骤十一：配置nat

1，

```shell
[r1]acl 2000  //创建acl

[r1-acl-basic-2000]rule permit source any  //创建规则，放行所有

[r1-acl-basic-2000]in g0/0/2  //进入外网接口

[r1-GigabitEthernet0/0/2]nat outbound 2000  //开启nat

[r2]acl 2000  //第二台路由器配置一样的内容

[r2-acl-basic-2000]rule permit source any

[r2-acl-basic-2000]in g0/0/2

[r2-GigabitEthernet0/0/2]nat outbound 2000
```

# SHELL

## 01:Shell 概述、编写及执行脚本、Shell变量、数值运算

==================================

### **什么是shell**

在Linux内核与用户之间的解释器程序

通常指 /bin/bash

负责向内核翻译及传达用户/程序指令

相当于操作系统的“外壳”

 

### **Shell的使用方式**

交互式  —— 命令行

人工干预、智能化程度高

逐条解释执行、效率低

非交互式	—— 脚本

需要提前设计、智能化难度大

批量执行、效率高

方便在后台静悄悄地运行

 

### **什么是Shell脚本**

提前写好可执行语句，能够完成特定任务的文件

顺序、批量化处理

 

```shell
[root@svr7 ~]# cat /etc/shells  //查看所有解释器

[root@svr7 ~]# sh  //切换成sh解释器

sh-4.2# ls   //利用sh解释器输入命令

sh-4.2# exit  //退出sh解释器

[root@svr7 ~]#yum -y install ksh  //安装新解释器

[root@svr7 ~]#ksh  //进入新解释器
```

 

Bash的优点 : tab键、历史命令、快捷键、支

持别名、管道、重定向

 

### **脚本的编写规范**

1， 声明解释器（使用哪种解释器）

```shell脚本
#!/bin/bash
```

2， 注释，内容可以是脚本的功能、作用等介绍（或者是步骤、思路、用途、变量含义等）

\#这是一个测试脚本

3， 执行指令 

```shell
echo nb
```

  所有需要脚本执行的任务都可以逐行写在这里

 

### **脚本的执行方式**

1， 使用路径指向一个具有x权限的文件

2， 使用解释器，无需x权限，新开启解释器子进程

```shell
[root@svr7 opt]# bash test01.sh

nb
```

3， 使用source命令，无需x权限，不会开启解释器

子进程，而使用默认解释器进程

```shell
[root@svr7 opt]# source test01.sh

nb
```

 

[root@svr7 opt]# cat test01.sh   //可以利用该脚本测试，bash执行时看不到进入abc的效果，因为bash开启了子进程，执行完任务就退出了，父进程并没有进入abc目录，如果使用source执行该脚本就可以看到进入abc目录的效果，因为是父进程亲自进入没有开启子进程。  另外开一个命令行窗口使用pstree命令可以看到具体过程

```shell
\#!/bin/bash
```

\#这是一个测试脚本

```shell
echo nb

mkdir abc

cd abc

sleep 1000
```



### **编写部署网站的脚本，测试时需要临时关闭防火墙**

\#!/bin/bash

\#部署网站服务

```shell
yum -y install httpd

echo "web~test~~~~~!!" > /var/www/html/index.html

systemctl restart httpd
```



### **常量  固定不变的内容**

**变量  以固定名称存放，可能会变化的值**

​	 **提高脚本对任务需求、运行环境变化的适应能力**

​	 **方便在脚本中重复使用**

 

### **变量的种类**

1， 自定义变量，定义名称时可以用数字、大小写字母

下划线，不允许使用数字开头，不允许使用特殊字符

变量名称=变量的值

```shell
[root@localhost opt]# a=10  定义变量(赋值)

[root@localhost opt]# echo $a  调用变量

[root@localhost opt]# unset a 取消变量的定义

echo ${a}RMB  容易发生混淆的情况使用大括号
```



**2，环境变量，由系统提前定义好，使用时直接调用，无需用户定义**

USER当前用户名  HOME当前用户的家目录  

UID当前用户的id号  SHELL当前用户的解释器  

PWD当前位置  PATH 存储了执行指令的路径

PS1  一级提示符  PS2  二级提示符

 

3 预定义变量与位置变量

```shell
$*  $#  $$  $?  $1  $2  $3  …..
```

 

\#!/bin/bash

echo $1  执行脚本名称后面的第1个位置参数

echo $2  执行脚本名称后面的第2个位置参数

echo $3  执行脚本名称后面的第3个位置参数

echo $*  所有的位置参数

echo $#  所有的位置参数的个数

echo $$  随机的进程号

echo $?  判断上一条指令是否执行成功，0是成功

​		 非0是失败



**编写脚本，可以创建用户abcd，并且配置密码123456**

```shell
#!/bin/bash

useradd abcd  

echo 123456 | passwd --stdin abcd  
```

 

**改良版本，使用变量**

```shell
#!/bin/bash

useradd $1  //创建用户时调用第1个位置变量

echo "$2" | passwd --stdin $1  //配置密码时调用第2个位置变量
```

### **变量的扩展知识**

1.单引号  界定范围  可以屏蔽特殊符号

```shell
Touch ‘a b’  可以创建a空格b的文件

a=10

echo ‘$a’  无法调用变量，$是调用变量的特殊符号

其效果被屏蔽
```

双引号  界定范围

```shell
Touch “a b”  也可以创建a空格b的文件

echo “$a” 可以调用变量

` `反撇号  获取指令的执行结果 ，或者使用$()

a=date   定义变量时如果使用命令则不会直接识别

a=`date`  使用反撇号可以将命令的执行结果赋值给变量

a=$(date)  效果同上
```

2，使用read指令，将脚本变成交互式，使脚本可以从用户那里得到信息

用法：read -p “提示的信息”  变量名

```shell
#!/bin/bash

read -p "请输入用户名："  u

useradd $u

read -p "请输入密码："  p

echo $p | passwd --stdin $u
```

 

**stty  -echo  屏蔽回显**

**stty  echo  恢复回显**

**再次改良后的脚本，输入密码时屏蔽回显**

```shell
#!/bin/bash

read -p "请输入用户名："  u

useradd $u

stty -echo

read -p "请输入密码："  p

stty echo

echo "$p" | passwd --stdin $u
```

**1，export  定义全局变量，可以让子进程使用父进程定义的变量**

```shell
export b=20  创建变量b的同时发布为全局效果

export  a  将已有的变量发布为全局效果

export  -n  a  取消变量的全局效果

 
env 查看所有环境变量

set 查看所有变量
```

 

```shell
shell中的运算

1， 使用expr工具

expr  可以计算并输出，运算符号两边要有空格

expr 3 – 1  减法

expr 2  + 2   加法

expr 2  '*'  2   乘法

expr 2  \*  2   使用乘法时，这里使用\代表

转义符号，可以屏蔽之后1个字符的特殊效果

expr 4  / 2  除法

expr 10  % 3   取余数
```

 

```shell
2，方法二用$[ ]结构，配合echo输出，同样可以实

现加 减 乘 除 取余

echo $[1+1]

echo $[2-1]

echo $[2*2]

echo $[4/2]

echo $[5%3]
```

 

3 , 使用bc 计算器，可以进行小数运算

```shell
echo "1.1+1" | bc   //非交互的方式使用bc工具

echo "10/3" | bc

echo "scale=3;10/3" | bc  //scale可以定义小数点

后面的长度
```

### **练习题**：

1，如何执行Shell脚本？

```shell
方法一：添加x权限，然后使用路径运行
方法二：bash 脚本文件路径
方法三：source 脚本文件路径
```

2 自定义Shell变量时，有哪些注意事项？

```
可以包括数字、字母、下划线，不能以数字开头
赋值时等号两边不要有空格
尽量不要使用关键字和特殊字符
给同一个变量多次赋值时，最后一次的赋值生效
```

3 编写一个Shell脚本程序，用来报告当前用户的环境信息。

```shell
新建脚本文件report.sh，执行后能够输出当前的主机名、登录用户名、所在的文件夹路径。

#!/bin/bash
echo "当前的主机名是：$HOSTNAME"
echo "登录用户是：$USER"
echo "当前位于 $PWD 文件夹下"
```

4 简述预定义变量$$、$?、$#、$*的作用。

```shell
$$ 保存当前运行进程号
$? 保存命令执行结果的（返回状态）0是成功，非0是失败
$# 保存位置变量的（个数）
$* 保存所有位置变量的（值）
```

5 编写一个Shell脚本程序，能够部署ftp服务。

```shell
#!/bin/bash
yum -y install vsftpd &> /dev/null
systemctl restart vsftpd
systemctl enable vsftpd
chmod 777 /var/ftp/pub
```

6 简述单引号、双引号、反撇号在变量赋值操作中的特点。

```shell
双引号 " "：可以界定范围
单引号 ' '：可以界定范围，还可以屏蔽特殊符号，即便 $ 也视为普通字符
反撇号 ` `：将命令的执行输出作为变量值
```

## 02:条件测试、if选择结构、循环结构

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5CLINUXNSD_V01SHELLDAY02_003.png)

### **运算：**

使用let指令，不输出计算结果，专用于创建变量，或者对变量进行自增减

用法一：创建变量let a=1+1  创建变量a

用法二： 变量的自增减

常规写法		 主流写法

```shell
let x=x+1 	let x++    把x+1

let x=x-1 		let x—    把x-1

let x=x+3   let x+=3	  把x+3  

let x=x*3	  let x*=3   把x乘以3

let x=x/2   let x/=2   把x除以2

let x=x%3		let x%=3   用x除3取余数
```

\---------------------------------------------------------------------------------------

**条件测试： 可以为脚本提供智能判断的效果**

**使用方式： test 表达式	 或者	 [ 表达式 ]**

 

### **条件测试种类：**

#### **1对字符串进行判断**

可以使用的方式有： == 两边是否相等  != 两边是否不等

```shell
[ a == a ]  判断字符串a是否等于a，如果相等，返回值就是0

[ root == $USER ]  判断当前用户名是否叫root，如果是，返回值就是0

[ root != $USER ]  判断当前用户名是否不叫root，如果不叫root，返回值就是0

[ -z $a ] 判断变量a是否为空，如果是，返回值是0

[ ! -z $a ] 判断变量a是否非空，如果是，返回值是0
```

 

#### **2，逻辑符号**

&&  之前任务执行成功才执行之后任务

||  之前任务执行失败才执行之后任务

 

[ root == $USER ] || exit  如果当前用户不是管理员，则退出

ls || ls  只执行第1个ls

ls && ls 两个ls都执行

 

### **逻辑符号的组合应用**

**当2个逻辑符号连用时，第二个逻辑符号后面的任务是否执行不能只看前面一个任务，要看前面所有任务的组合，比如下列情况：**

touch a b c	创建3个测试文件

ls a && ls b && ls c   都显示，第一个ls执行成功，然后导致第二个ls也执行，并且可以成功，这样的话第一个和第二个任务都成功了，那么这个组合就算成功，然后会导致第二个逻辑符号&&后面的ls c 也执行并且成功。

ls a && ls b || ls c   显示a和b，第一个ls执行成功，然后导致第二个ls也执行，并且可以成功，这样的话第一个和第二个任务都成功了，那么这个组合就算成功，但是由于第二个逻辑符号是||，就不会执行最后的ls c任务了

ls a || ls b && ls c   显示a和c，第一个ls执行成功，第二个ls就不会执行了，这两个任务中间是|| ，那么只要有一个成功就算这个组合执行成功，所以就会导致第二个逻辑符号&&后面的ls c执行

ls a || ls b || ls c    显示a，第一个ls执行成功，第二个ls就不会执行了，这两个任务中间是|| ，那么只要有一个成功就算这个组合执行成功，由于这个组合算成功，所以就不会执行第二个||后面的任务了

 

**练习**

编写脚本安装ftp服务，但如果是非管理员执行该脚本则给出非管理员的提示并退出

```shell
#!/bin/bash

[ root != $USER ]  && echo "你不是管理员"  &&  exit

yum -y install vsftpd

systemctl restart vsftpd

systemctl enable vsftpd
```

 

#### **3，数字的条件测试**

-eq是否相等 -ne是否不等 -gt大于 -ge大于等于  -lt小于 -le小于等于

[ 1 -eq 1 ]  判断1是否等于1，判断成功的话返回值是0，判断失败返回值是非0

```shell
a=10	  

b=20

[ $a -eq $b ] && echo "ok" || echo "no"  判断变量a是否等于b ，是的话显示ok，否显示no

[ $a -gt $b ] && echo "ok" || echo "no"  判断变量a是否大于b ，是的话显示ok，否显示no
```

 

**练习：**

编写监控脚本，每2分钟检查服务器登录的用户数量如果超过3人，就给管理员发报警邮件

```shell
#!/bin/bash

x=$(who | wc -l)

[ $x -gt 3 ] && echo "有人入侵服务器！n老师扛着铁锤来了！！"  | mail -s test root
```

 

脚本写完后，执行下列指令：

```shell
rm -rf /var/spool/mail/root  清空邮箱(非必须)

[root@svr7 opt]#chmod +x test01.sh  给脚本添加执行权限

[root@svr7 opt]# crontab -e  编写计划任务

*/2 * * * * /opt/test01.sh   每2分钟执行脚本

然后故意多登陆几个账户，每2分钟就可以收到新邮件
```

 

#### **4，对文件进行条件测试**

-e是否存在不关心文件类型  -f是否存在且是普通文件 

-d是否存在且是目录 

-r判断当前用户对文件是否能读 ，对root无效

-w判断当前用户对文件是否能写 ，对root无效

-x 执行(文件)，进入(目录)

[ -e  a  ]  当前位置如果有a文件，不关心类型，则测试成功

[ -f  a  ]  当前位置如果有叫a的普通文件，则测试成功

[ -d  a  ]  当前位置如果有叫a的目录，则测试成功

[  -r  a  ]  当前用户如果对a文件有读权限，则测试成功

[  -w  a  ]  当前用户如果对a文件有写权限，则测试成功

[  -x  a  ]  当前用户如果对a文件有执行(目录是进入)权限，则测试成功

 

\-------------------------------------------------------------------------------------------------------

 

**虽然&&和||可以实现逻辑组合，但如果情况比较复杂就可能需要n多个&&或者||，会导致脚本难写，可读性差。此时就可以使用if分支**

 

### **if分支有三种：**

#### **1，if单分支**

```shell
if [条件测试];then	  //如果条件测试成功，那就执行下面的所有指令(指令可以有很多)

	指令1

	指令2

fi
```

 

#### **2，if双分支**

```shell
if 条件测试;then		  //如果条件测试成功，那就执行下面的指令1、2

	指令1

	指令2

  else				//如果上述条件测试失败，那就执行下面的指令3、4

	指令3

	指令4

	...

fi
```

**------------------------------------------------------------------------**

**ping命令应用在脚本中可以使用的选项：**

**ping -c ping次数  -i ping间隔时间(单位：秒) W 如果ping不通，多久反馈结果(单位：秒)**

**ping -c 3 -i 0.1 -W 1 192.168.4.7**

 

**练习：编写脚本测试某ip是否能ping通，但不要显示过程，仅仅显示通了或者不通即可**

```shell
ping -c 3 -i 0.1 -W 1 192.168.4.7 &> /dev/null  //ping的具体过程扔黑洞不看

  if [ $? -eq 0 ];then	 //仅仅使用$?可以判断上面的任务是否成功，如果等于0就是成功

    echo "通了"

  else

    echo "不通"

  fi
```

 

#### **3，if多分支，适合更复杂的情况，结果会有很多的情况**

```shell
if 条件测试;then			//首先判断，条件测试成功，就执行指令1、2

	指令1

	指令2

elif 条件测试;then   //上述测试失败，此处测试成功的话就执行指令3、4

	指令3

	指令4

else    //上述测试都失败的话就执行指令5、6

	指令5

	指令6

	...

fi
```

 

\---------------------------------------------------------------------------------------------------

### **循环：**

**有时我们需要某个或者某群任务反复在服务器中执行很多次，就可以使用循环命令写成脚本，而无需手工一次次执行**

 

#### **for循环 可以定义循环次数，有限的循环**

**基本语法格式：**

```shell
for 变量名 in 值1 值2 值3 ......   //此处变量名可以自定义，通常习惯用i，值的多少决定了下面do与done之间的任务执行多少次，每个值之间有空格，这里是有3个值，所以就循环执行指令3次

do

	指令   

done
```

\------------------------------------------------

```shell
#!/bin/bash

for i in a b c   //给了abc三个值，下面的echo任务就循环三次

do

  echo "nb"

done
```

 

\-----------------------------------------------

```shell
#!/bin/bash

for i in {1..100} 循环100次时无需填写100个值，用此格式即可，代表1到100，一共100个值，但不支持变量  

do

  echo "nb"

  echo "$i"   执行任务时，还可以调用变量，变量的值是所有值的轮询，由于这里给了1到100的值，那第一次循环$i就是1，第二次循环$i就是2，依次类推到第100次循环$i就是100

done
```

\-----------------------------------------------

```shell
#!/bin/bash

a=100

for i in $(seq $a)  循环100次，支持变量，seq命令可以帮我们创建数字序列，对于for循环来说，就是可以当是多个值

do

  echo "nb"

  echo "$i"

done
```

\-----------------------------------------------

编写脚本，测试192.168.4.1~192.168.4.15能否ping通，并且统计多少台通了，多少台不通

 

```shell
#!/bin/bash

x=0		//定义通了的数量

y=0   //定义没通的数量

for i in {1..15}   //循环15次

do

  ping -c 3 -i 0.1 -W 1 192.168.4.$i &> /dev/null   //每次循环$i的值就从1往后轮询

  if [ $? -eq 0 ];then

    echo "4.$i 通了"

    let x++   //每通了一次就把x+1

  else 

    echo "4.$i 不通"

    let y++   //每不通一次就把y+1

  fi

done

echo "通了$x台，不通$y台"   //最后喊出结果
```

 

\-----------------------------------------------------------------------------------



#### **while循环，**

**可以根据条件测试决定循环次数，可以实现无限循环**

 

##### **基本语法结构：**

```shell
while 条件测试   //如果条件测试得到成功的结果就执行下面的指令，然后再回来继续看条件测试能否成功，如果成功就继续执行指令，且可以实现无限循环，一旦发现条件测试失败了，就立刻终止循环

do

	指令

done
```

\-------------------------------

**另外如果想故意创造一个无限循环可以在while后面写冒号即可**

```shell
while :			//冒号代表测试永远正确

do

  echo nb		//循环任务

  sleep 0.1   //如果系统执行任务消耗cpu比较多，可以每次稍微休息一下

done
```

\--------------------------------

**练习：使用while编写猜数脚本**

```shell
#!/bin/bash

x=$[RANDOM%100]   //RANDOM是可以得到随机数的变量，除以100取余数可以得到零到99之间的随机数，并且存到变量x中

y=0   //这里还可以定义猜的次数，一次没猜时是0次

while :   //无限循环

do

let y++   //每猜一次，把y+1

read -p "请输入一个整数(0-99):" n    //将用户给的数字存到变量n中

if [ $n -eq$x ];then    //使用if多分枝加条件测试判断n是否等于x

    echo "恭喜！猜对了！猜了$y次"   //如果n等于x就喊出这句话

    exit

elif [ $n -gt $x ];then			//如果n比x大

    echo "猜大了！"

else							//还有最后一种情况

    echo "猜小了！"

fi

done
```

 

 

### **练习：**

1，列出常见的整数值比较操作，并说明各自作用。

 

2，运用条件测试操作，检查当前的用户是否为root。

 

3，绘图描述if双分支结构的执行流程。

 

4，[ -z $abc ] && echo "yes" || echo "no" 可以实现什么测试效果。

 

**参考答案**

1，列出常见的整数值比较操作，并说明各自作用。

```shell
-eq 等于

-ne 不等于

-ge 大于等于

-le 小于等于

-gt 大于

-lt 小于
```

2，运用条件测试操作，检查当前的用户是否为root。

```shell
[ $USER == "root" ] && echo "yes" || echo no
```

3，绘图描述if双分支结构的执行流程。

if双分支结构判断一次条件，当条件成立时执行分支1、若不成立则执行分支2，如图-1所示。

 ![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml18292\wps1.jpg)

图-1

4，[ -z $abc ] && echo "yes" || echo "no" 可以实现什么测试效果。

```
如果变量abc是空则显示yes，否则显示no
```

 



## 03：case语句、函数及中断控制、字符串处理



\------------------------------------------------------------------------------------------

 

### **case分支**

**功能类似if，不如if强大，语句比较精简**

基本语法格式：

```shell
case 调用变量名 in			//如果调用的变量内容与下面某个模式一致，就执行模式下面的指令

模式1)				//这里的模式可以有很多

	执行指令;;		//指令需要用双分号结尾，如果一个模式有多个指令，那只需在该模式的最后一条指令后加双分号即可

模式2)

	执行指令;;

…

*)			//如果上述模式都没有被匹配，那就匹配这个

	执行指令

esac
```

\------------------------------------------------

**测试case分支的实际应用**

```shell
#!/bin/bash

case $1 in		//使用执行脚本后的第1个位置变量作为匹配对象

t|T|tt)			//如果$1是t或者T或者tt，都可以算匹配

  touch $2;;	 //此处是创建文件的命令，后面是第二个位置变量的参数

m|M|mm)

  mkdir $2;;

r)

  rm -rf $2;;

*)

  echo "请输入t|m|r"

esac
```

\-------------------------------------------------

### **部署nginx服务**

**httpd是之前使用过的网站服务，除此之外nginx也可以实现搭建网站的任务**

 

**1，将lnmp_soft.tar.gz软件包从真实主机拖拽到虚拟机的管理员家目录，然后释放**

```shell
[root@svr7 ~]# tar -xf lnmp_soft.tar.gz  //释放到当前目录]() 

[root@svr7 ~]# cd lnmp_soft/   //然后到释放的目录中

[root@svr7 lnmp_soft]# cp nginx-1.17.6.tar.gz /opt   //将nginx拷贝到opt下
```

 

**2，安装nginx**

**由于nginx是源码包，所以需要源码编译安装**

**编写部署nginx服务的脚本思路：**

​	**1）安装依赖 gcc(编译工具)，pcre-devel，openssl-devel(后两个都是nginx所需依赖包)**

​	**2）释放nginx-1.17.6.tar.gz**

​	**3）进入nginx-1.17.6目录**

​	**4）configure   配置**

​	**5）make   编译**

​	**6）make install  安装**

 

**将上述过程编写成部署nginx服务的脚本**

```shell
#!/bin/bash

yum -y install gcc pcre-devel openssl-devel &> /dev/null   //安装依赖软件包

tar -xf nginx-1.17.6.tar.gz		//释放tar包

cd nginx-1.17.6   //进入nginx目录

./configure    //配置

make    //编译

make install   //安装
```

 

写完后保存退出，并执行脚本

```shell
Systemctl  stop  httpd   //之后关闭其他网站服务

/usr/local/nginx/sbin/nginx   //开启nginx服务

/usr/local/nginx/sbin/nginx -s stop   //关闭nginx服务

然后使用浏览器访问192.168.4.7可以看到欢迎界面则成功

提示：不要忘记关闭防火墙

systemctl stop firewalld
```

 

\--------------------------------------------------------------------------------------

### **编写脚本，使用case分支控制nginx服务**

```shell
#!/bin/bash

case $1 in		//使用执行脚本后的第1个位置变量作为匹配对象

s|start|kai)  //如果$1是s或start或kai ，那么就执行以下指令

  netstat -ntulp | grep -q nginx  //查询有没有开启nginx服务, -q是不输出查询结果

  [ $? -eq 0 ] && echo "nginx已经开启" && exit   //判断如果开了nginx就退出

  /usr/local/nginx/sbin/nginx;;   //如果没开nginx就开启

stop|guan)   //如果$1是stop或guan，那么就执行以下指令

  /usr/local/nginx/sbin/nginx -s stop;;   //关闭nginx

restart|cq)   //如果$1是restart或cq，那么就执行以下指令

  /usr/local/nginx/sbin/nginx -s stop  //关闭nginx

  /usr/local/nginx/sbin/nginx;;   //开启nginx，此处相当于重启nginx

status|cx)   //如果$1是status或cx，那么就执行以下指令

  netstat -ntulp | grep -q nginx  //查询有没有开启nginx服务, -q是不输出查询结果

  [ $? -eq 0 ] && echo "nginx正在运行中。。"  || echo "nginx未开启";;  //根据查询结果输出nginx正在运行或者nginx未开启的提示

*)

  echo "start|stop|restart"   //如果没有匹配任何模式就是喊出使用该脚本的提示，告诉使用者$1应该敲啥，而不能随意敲。

esac   //结尾，固定语法，不能少
```

 

**netstat命令可以查看系统中启动的端口信息，该命令常用选项如下：**

-n以数字格式显示端口号

-t显示TCP连接的端口

-u显示UDP连接的端口

-l显示服务正在监听的端口信息，如httpd启动后，会一直监听80端口

-p显示监听端口的服务名称是什么（也就是程序名称）



\----------------------------------------------------------------------------------------------

### **如果想在nginx中修改输出文字的颜色，可以使用下列方式**

echo -e "\033[32mABCD\033[0m"   //-e选项可以激活后面特殊字符的作用，相当于使用echo的扩展功能，\033[32m代表设置颜色为绿色，ABCD是输入内容，\033[0m代表还原颜色。

### **函数，可以将公共的语句块使用一个函数名来定义，方便后期反复调用，达到精简脚本，增加可读性的目的**

```shell
#!/bin/bash

a() {      //定义函数

echo abc

echo xyz

}

a  //调用函数，相当于执行上述两个echo任务

a  //可以反复调用
```

\---------------------------------------------------------------------------------

```shell
#!/bin/bash

a() {         //定义函数

echo -e "\033[$1m$2\033[0m"   //输出不同颜色的文本内容，并加入位置变量

}

a 31 ABCD   //调用时函数后面可以写位置变量的内容，31就是$1  ABCD是$2

a 32 XUEY 
```

\---------------------------------------------------------------------------------

### **循环的控制：**

**通常，在执行循环任务中途如果想退出可以用exit指令，但该指令不但会退出循环，连同脚本也会一并退出，此时可以使用break与continue指令更精细的控制循环。**

 

```
exit   可以终止循环，但同时退出脚本，如果循环之后还有任务则无法执行**

break  终止循环，继续执行循环之后的任务**

continue  终止当前循环，继续执行下一次循环
```

 

**练习：**

编写脚本，可以为用户进行整数求和，如果输入0则退出并显示

之前求和结果

```shell
#!/bin/bash

x=0		//先定义了一个x，表示用户给的整数之和，一个都没给时就是0

while :

do

read -p "请输入一个整数求和，0是结束" n  //问用户要数字

[ -z $n ] && continue		//如果n是空值，就重新循环

[ $n -eq 0 ] && break	//如果n是0，就退出循环

let x+=n   //将x+n

done

echo "整数之和是$x"  //喊出结果
```

 

\------------------------------------------------------

**linux中很多地方都需要这样或着那样的去使用、管理、操作字符，多掌握在linux中字符的控制方法直接决定能否写好脚本与更好的控制linux系统。**

 

**1，** **字符串的截取**

```shell
x=abcdef

${变量名:截取的位置:截取的位数}

echo ${x:1:2}  //截取bc，位置是从0开始计算，所以要从1开始

才能截取第二个字符b

echo ${x:1:1}  //从第2个字符截取，截取1位

echo ${x:0:2}  //从第1个字符截取，截取2位

echo ${x::2}  //效果同上，如果从第1位开始截取的话，0可以省略不写
```

**编写脚本，可以获取随机的8位字符（将来可以作为为用户配置随机密码时使用）**

```shell
#!/bin/bash

x=abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789   //定义变量

for i in {1..8}   //循环8次

do

n=$[RANDOM%62]  //得到0-61之间的随机数

a=${x:n:1}  //随机截取一个x中的字符存储到变量a中

pass=$pass$a  //将每次获取的随机字符存储到变量pass中

done

echo $pass  //循环完8次之后，喊出最终结果，就得到了1个8位的字符
```

\-------------------------------------------------------------------------

**请创建30个10位的密码，存放到一个文件中**

```shell
#!/bin/bash

x=abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ0123456789

for j in {1..30}		//将得到10位随机字符的过程执行30次

do

  for i in {1..10}   //将得到1个随机字符的过程执行10次

  do

    n=$[RANDOM%62]  //得到0-61之间的随机数

    a=${x:n:1}   //随机截取一个x中的字符存储到变量a中

    pass=$pass$a   //将每次获取的随机字符存储到变量pass中

  done

echo $pass >> /opt/pass.txt  //将每次得到的10位字符追加保存到pass.txt中

  pass=  //清空pass变量，避免下次叠加

done
```

 



#### **练习：**

1，简述Linux服务脚本中的case分支结构。

```
case 变量名 in 
模式1) 
执行指令 ;; 
模式2)
执行指令 ;; 
*)
执行指令
esac
```

2，简述定义一个Shell函数的任意一种方法。

```
函数名() {
执行指令
}
```

3，简述Shell环境常见的中断及退出控制指令。

```shell
break：跳出当前所在的循环，执行循环之后的语句。
continue:跳过循环内余下的语句，执行下一次循环。
exit:退出脚本
```

4，使用 while 循环,统计 1+2+3+4...+100的结果。

提示:可以用一个独立的变量a存放求和的值。

```shell
#!/bin/bash
a=0
for i in {1..100}
do
let a+=i
done
echo $a
```

5，编写脚本,通过 3 个 read 命令读取用户输入的三个任意数字,脚本对输入的三个数字求和输出。

```shell
#!/bin/bash
read -p "请输入数字" num1
read -p "请输入数字" num2
read -p "请输入数字" num3
echo $[num1+num2+num3]
```

6，判断当前系统启动的进程数量,如果进程数量超过 100 个,则发送邮件给 root 报警。

```shell
#!/bin/bash
num=`ps aux | wc -l`
[ $num -gt 100 ] && echo "进程超过100啦～" | mail -s Warning root
```

7， 编写脚本,测试当前用户对/etc/passwd 文件是否具有读、写、执行的权限,让脚本执行结果类似下面的效果。

```shell
#!/bin/bash
file=/etc/passwd
[ -r /etc/passwd ] && echo "当前用户对$file 有读权限" || echo "当前用户对$file 没有读权限"
[ -w /etc/passwd ] && echo "当前用户对$file 有写权限" || echo "当前用户对$file 没有写权限"
[ -x /etc/passwd ] && echo "当前用户对$file 有执行权限" || echo "当前用户对$file 没有执行权限"
```

## 04:正则表达式、sed基本用法、sed文本块处理

==================================

### **1，** **字符串的截取**

### **2，字符串的替换**

```shell
${变量名称/被替换内容/新内容}

a=1234		//定义素材

echo ${a/3/6}   //把3换成6

a=11223344   //定义素材

echo ${a/3/6}   //把3换成6,默认只换一个

echo ${a//3/6}  //使用两个/可以实现把所有3换成6

a=333444   //定义素材

echo ${a//3/}  //把所有3换成空，相当于删除
```

 

### **3，** **字符串的删除**

**${变量名称#被删除的内容}从左往右删除**

**${变量名称%被删除的内容} 从右往左删除**

```shell
a=abcdefghijklmn

echo ${a#abcdefgh}	 //从左往右删除到h

echo ${a#*h}		//效果同上，更精简

echo ${a#ab}  //从左往右删除到b

echo ${a#*b}  //效果同上，更精简

a=abcxyzabcxyz  

echo ${a##*b}  //从左往右删除到最后一个b
```

 

```shell
a=abcxyzabcxyz

 echo ${a%abcxyz}  //从右往左删除abcxyz

 echo ${a%a*}   //效果同上，更精简

 echo ${a%%a*}  //从右往左删除到最后一个a

 echo ${a%%y*}  //从右往左删除到最后一个y
```

编写脚本，实现批量修改文件的扩展名

```shell
touch abc{1..10}.txt  //创建10个文件作为素材
\#!/bin/bash

for i in $(ls *.txt)		//找到所有txt文件交给for循环

do

    n=${i%.*}  //先用去尾删除扩展名

    mv $i $n.doc  //再将原文件修改为doc扩展名

done
```

 

**变量初值（备用值）的定义**

${变量名:-初值}   //如果变量有值则使用本身的值，如果变

量为空，则使用初值

编写脚本，可以创建用户与配置密码，密码可以自定义，也

可以使用默认的123456

```shell
#!/bin/bash

read -p "请输入用户名：" n

useradd $n

read -p "请输入密码："  p

echo ${p:-123456} | passwd --stdin $n  //当用户没有输入密码时

密码就是123456 				
```



\--------------------------------------------------

### **正则表达式，使用若干符号配合某工具实现对文档的过滤、查、找、修改等功能**

```shell
head -5 /etc/passwd > user  //准备素材

 grep bin user  //找有bin的行

 grep ^bin user	//找以bin开头的行

 grep bash user  //找有bash的行

 grep bash$ user  //找以bash结尾的行

 vim user   //编辑文档添加空行

 grep  -n  ^$  user  //找空行，加n选项可以显示行号
```

 

```shell
grep "[root]" user  //找root四个字符任意一个

 grep "[rot]" user	 //效果同上，找rot任意一个字符

 grep "rot" user  //找连续的rot字符串

 grep "[a-z]" user  //找所有小写字母

 grep "[A-Z]" user  //找所有大写字母

 grep "[a-Z]" user  //找所有字母

 grep "[0-9]" user  //找所有数字

 grep "[^a-Z]" user  //找字母之外的内容，^写在[]里是取反效果
```

 

```shell
 grep "r..t" user  //找rt之间有2个任意字符的行

 grep "r...t" user  //找rt之间有3个任意字符的行		

 grep "*" user  //*号是匹配前一个字符任意次，不能单独使用

 grep "ro*t" user  //找rt，中间的o有没有都行

 grep "." user  //找任意单个字符

 grep ".*" user  //找任意  
```

 

```shell
grep "ro\{2,4\}t" user  //找rt，中间的o可以是2~4个

 grep "ro\{2,\}t" user	//找rt，中间的o可以是2个以及2个以

上

 grep "ro\{3,7\}t" user //找rt，中间的o可以是3~7个，没有匹

配条件就没有任何显示

 grep "ro\{3,\}t" user  //找rt，中间的o可以是3个以及3个以

上

 grep "ro\{2\}t" user  //找rt，中间的o必须是2个
```

 

```shell
 grep "ro\{1,\}t" user   //找1次以及1次以上的o

 egrep "ro{1,}t" user  //效果同上

 egrep "ro+t" user   //效果同上，最精简

grep "roo\{0,1\}t" user  //第二个o要出现0~1次

egrep "roo{0,1}t" user  //效果同上

egrep "roo?t" user  //效果同上，最精简

grep "ro\{2\}t" user   //找o出现2次的

egrep "ro{2}t" user   //效果同上
```

 

```shell
 egrep "^root|^bin" user  //找root或者以bin开头的行

 egrep "^(root|bin)" user  //效果同上

 egrep "\bthe\b" abc   //找the，前后不允许出现数

字，字母，下划线
```

 

\-------------------------------------------------------

### **sed 流式编辑器，可以对文档进行非交互式增删改查，逐行处理**

**适用方式：**

**1，前置指令 | sed 选项  定址符 指令**

**2，sed 选项  定址符 指令  被处理文档**

**选项 -n 屏蔽默认输出 -i写入文件  -r支持扩展正则**

**指令 p输出  d删除   s替换**

```shell
 sed -n '1p' user		//输出第1行

  sed -n '2p' user   //输出第2行

  sed -n '3p' user   //输出第3行

  sed -n '2,4p' user  //输出第2~4行

  sed -n '2,+1p' user  //输出第2行以及后面1行

  sed -n '2p;4p' user  //输出第2行，第4行
```

\------------------------------------------

```shell
sed -n '/^root/p' user  //在sed中使用正则表达式输出以root开

头的行

  grep "^root" user  //效果同上

 egrep "^root|^bin" user  //找root或者bin开头的行  

 sed -nr '/^root|^bin/p' user  //在sed中查找，-r使用扩展正

则，效果同上

  sed -n '=' user   //查看所有行号

 sed -n '$=' user  //查看最后一行的行号，相当于查看文档

总共有几行
```

\---------------------------------------------

```shell
 sed  '1d' user  //删第1行

 sed  'd' user  //删所有

 sed  '3d' user  //删第3行

 sed  '2,5d' user  //删2~5行

 sed  '4,+2d' user  //删4行以及后面2行

 sed  '1d;3d' user  //删第1行，第3行

sed  '$d' user  //删除最后一行

 sed -n '$p' user  //查看最后一行

sed -n '1!p' user  //查看除了第1行以外的行, !代表取反
```

 

\---------------------------------------------

练习：

regular_express.txt  是素材，拷贝到linux中

regular.pdf是题目，按题目使用正则表达式完成

题目要求

https://gitee.com/nsd-tedu/nsd2008



 

\------------------------------------------------

练习：

1 简述grep工具的-q选项的含义（egrep同样适用）。

2 正则表达式中的+、？、*分别表示什么含义？

3 如何编写正则表达式匹配11位的手机号？

4 简述sed定址符的作用及表示方式。

 

 

参考答案：

1 简述grep工具的-q选项的含义（egrep同样适用）。

```
选项-q的作用是静默、无任何输出，效果类似于正常的grep操作添加了&> /dev/null来屏蔽输出
```

2 正则表达式中的+、？、*分别表示什么含义？

```
这三个字符用来限制前面的关键词的匹配次数，含义分别如下：

•	+：最少匹配一次，比如a+可匹配a、aa、aaa等

•	？：最多匹配一次，比如a?可匹配零个或一个a

•	*：匹配任意多次，比如a*可匹配零个或任意多个连续的a
```

3 如何编写正则表达式匹配11位的手机号？

准备测试文件：

```shell
1.	[root@svr5 ~]# cat tel.txt 

2.	01012315

3.	137012345678

4.	13401234567

5.	10086

6.	18966677788

提取包含11位手机号的行：

1.	[root@svr5 ~]# egrep '^1[0-9]{10}$' tel.txt 

2.	13401234567

3.	18966677788
```

4 简述sed定址符的作用及表示方式。

```
作用：定址符（执行指令的条件）控制sed需要处理文本的范围；不加则逐行处理所有行

表示方式：定址符可以使用行号或正则表达式
```



## 05：sed高级应用、awk基本用法

==================================

### **sed中的替换，使用 s/old/new/**

```shell
vim test.txt   //准备素材,写入下列内容 

2017 2011 2018

2017 2017 2024

2017 2017 2017
```

 

```shell
sed 's/2017/8888/' test.txt  //替换所有行的第1个2017为8888

sed '1s/2017/8888/' test.txt  //替换第1行的第1个2017

sed '2s/2017/8888/' test.txt  //替换第2行

sed '1,2s/2017/8888/' test.txt  //替换1~2行

sed 's/2017/8888/2' test.txt  //替换所有行的第2个2017

sed 's/2017/8888/3' test.txt  //替换所有行的第3个2017

sed '/2011/s/2017/8888/' test.txt  //替换有2011的行的第1个2017

sed 's/2017/8888/g' test.txt  //替换所有行的所有个

sed -n 's/root/6666/p'  /etc/passwd  //替换每行第1个root，并只显示被替换的行

sed -n 's/root/6666/2p'  /etc/passwd  //替换每行第2个root，并只显示被替换的行

sed -n 's/root/6666/gp'  /etc/passwd //替换每行的所有root

sed '3s/2017/8888/;3s/2017/8888/' test.txt  //替换第3行的第1个和第2个2017
```

\------------------------------------------------------------

#### **尝试将user文档中的/bin/bash替换成/sbin/sh**

```shell
sed 's//bin/bash//sbin/sh/' user   //常规手段替换，内容会与替换 冲突，替换失败

sed 's/\/bin\/bash/\/sbin\/sh/' user  //使用\转义符号，可以成功，但不方便

sed 's!/bin/bash!/sbin/sh!' user  //更改替换的间隔符号是最理想方法

sed 's(/bin/bash(/sbin/sh(' user  //效果同上
```

 

### **Sed中s替换的高级应用**

#### **1）删除文件中每行的第二个、最后一个字符**

```shell
sed 's/.//2;s/.$//' test   分两个步骤完成，中间用分号

隔开，第一步将每行的第二个任意字符替换成空，第二

步将每行的最后一个任意字符替换成空即可
```

 

#### **2）删除文件中所有的数字**  

```shell
sed -i 's/[0-9]//g' test	先找到任意数字，然后都替换成空
```

#### **3）将文件中每行的第一个、倒数第1个字符互换**

```shell
echo abc > abc			//创建素材

sed -r 's/(a)(b)(c)/\3\2\1/' abc  //替换abc时复制每一个字符，后面替换的内容用\数字粘贴，可以任意调换位置

echo xyz >> abc  //追加内容

sed -r 's/(a)(b)(c)/\3\2\1/' abc  //再用之前的方法无法替换第2行

sed -r 's/(.)(.)(.)/\3\2\1/' abc  //将具体字符用 . 替代即可将文档中的xyz修改成xyaz时，上述方案失灵

sed -r 's/^(.)(.*)(.)$/\3\2\1/' abc  //再次升级，分别找到第1个字符和最后1个字符，中间可以是任意

sed -r 's/^(.)(.*)(.)$/\3\2\1/' test  //达成需求
```

 

#### **4）为文件中每个大写字母添加括号**

```shell
sed -r 's/([A-Z])/(\1)/g' test  //先找到任意大写字母，然后保留，最后替换成带括号的状态
```

 

**练习：**

**编写脚本，安装httpd服务，使用82号端口**

```shell
#!/bin/bash

yum -y install httpd

sed -i '/^Listen 80/s/80/82/' /etc/httpd/conf/httpd.conf  //找到有Listen 80开头的行，替换80为82

systemctl restart httpd
```

 

运行脚本之后，使用curl 192.168.4.7:82测试 或者火狐浏览器192.168.4.7:82

要关闭selinux与防火墙

```shell
setenforce 0   //如果脚本执行之前没关闭selinux，会报错

systemctl stop firewalld
```

\--------------------------------------------------------------------

### **sed中除了常用的p d s 三个指令，还有 a行下追加  i行上添加\  c替换整行**

```shell
sed 'a 666' user //在所有行下追加666

sed '1a 666' user //第1行下追加666

sed 'i 666' user  //所有行上添加666

sed '3i 666' user //第3行上添加666

sed '2a 666' user  //第2行下追加666

sed 'c 666' user  //所有行替换成666

sed '/root/c 666' user  //找到有root的行替换成666 
```

 

**练习：**

**找到使用bash做解释器的用户名**

```shell
sed -n "/bash$/s/:.*//p" /etc/passwd  //找到

使用bash的用户，将用户信息中从冒号到后面

的所有内容替换成空，留下的就是用户名
```

 

**练习：**

**编写脚本，找到使用bash解释器的用户，并按照 用户名 --> 密码” 的格式保存到log文件中**

```shell
#!/bin/bash

u=$(sed -n '/bash$/s/:.*//p' /etc/passwd)  //找到使用bash的人，并且将这些用户的名字存到变量u中

for i in $u  //将这些人交给for循环处理

do

    u1=$(grep $i: /etc/shadow)  //用每个人名找到密码文件中shadow中对应的信息

    u2=${u1#*:}  //然后掐头

    u3=${u2%%:*}  //再去尾，得到纯粹的密码

    echo "$i --> $u3"   //再按格式输出,如果需要保存就用 >> log 

done
```

\----------------------------------------------------------

 

**在linux中常用的三个处理文档的工具：**

**grep 模糊搜索**

**sed 增删改查**

**awk  精确搜索**

 

### **awk使用方式：**

#### **1，前置指令 | awk 选项 条件 指令**

#### **2，awk  选项 条件 指令  被处理文档**

**选项 -F 定义分隔符**  

**指令 print 输出**

```shell
vim test.txt   //准备素材，写入下列两行内容

hello the world

welcome to beijing
```

 

**awk的内置变量：  $1第1列  $2第2列  $3第3列  $0所有列  NR 行号  NF列号**

```shell
awk '{print}' test.txt  //输出test所有行所有列

awk '{print $1}' test.txt //输出test所有行第1列

awk '{print $2}' test.txt //输出test所有行第2列

awk '/world/{print $2}' test.txt  //找到有world的行，然后输出第2列

awk '{print $0,$1}' test.txt //找所有行的所有列和第1列

awk '{print NR}' test.txt //输出每行的行号

awk -F: '{print $1" 的解释器是 "$7}'  user  //使用冒号作为分隔符,输出第1列，第7列，中间加常量，常量要使用双引号
```

 

**利用awk提取本机的网络流量信息**

```shell
ifconfig eth0 | awk '/RX p/{print "eth0网卡的接收流量是"$5"字节"}'

ifconfig eth0 | awk '/TX p/{print "eth0网卡的发送流量是"$5"字节"}'
```

 

**使用awk提取根分区剩余容量**

```shell
df -h | awk '/\/$/{print "根分区剩余容量是"$4}'
```

 

**awk处理的时机，awk除了可以执行大括号中的逐行任务，还可以安排额外的任务**

**BEGIN{  }  执行1次，相当于额外任务**

**{  } 逐行任务，执行n次**

**END{  }  执行1次，又一个额外的任务**

 

**练习：**

**按下列各式要求输出信息**

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml16316\wps1.jpg) 

```shell
awk -F: ‘BEGIN{  }{  }END{  }’  user  //首先分析，写出基本各式

awk 'BEGIN{print "User\tUID\tHome"}'  //第一个是BEGIN任务就是输入表头信息,\t是制表符，相当于在文档中敲tab键，可以在一定程度上让文档自动空格排列整齐

awk -F: '{print $1"\t"$3"\t"$6}' user  //第二个是逐行任务，找到用户名，id号，家目录

awk -F: 'END{print "总计"NR"行"}' user  //最后的任务是输出一共多少行，NR是变量可以显示行号，在END任务中就是显示最后一行的行号

awk -F: 'BEGIN{print "User\tUID\tHome"}{print $1"\t"$3"\t"$6}END{print "总计"NR"行"}' user  //将上述命令敲成一行，完成需求
```

\-----------------------------------------------------------------------------------------------------------------

## 06：awk高级应用、综合案例

**在awk中，使用好条件是能否精确输出信息的关键，awk准备了4种条件，下面一一说明。**

**awk中的条件有：**

### **1，** **使用正则作为条件**

**~ 包含  !~ 不包含**

```shell
awk -F: '/bin/{print $1}' user   //输出有bin的行的第1列

awk -F: '$5~/bin/{print $1}' user  //输出第5列包含bin的行的第1列

awk -F: '$5!~/bin/{print $1}' user  //输出第5列不包含bin的行的第1列
```

 

### **2，** **使用数字、字符串**

**==  !=  >  <  >=  <=**

```shell
awk -F: 'NR==3{print}' /etc/passwd  //输出第3行

awk -F: '$3<10{print}' /etc/passwd  //输出UID小于10的行

awk -F: '$3>=1000{print}' /etc/passwd //输出UID大于等于1000的行

awk -F: '$7=="/bin/bash"{print}' /etc/passwd  //输出使用/bin/bash的用户

awk -F: '$7!="/bin/bash"{print}' /etc/passwd  //输出没使用/bin/bash的用户

awk -F: 'NR<11{print $1}' /etc/passwd  //查看前10行，并显示用户名

awk -F: '$7==" /bin/bash"{print $6}' /etc/passwd //查看使用/bin/bash解释器的用户，并显示家目录
```

 

### 3，**逻辑组合  &&并且  ||或者**

```shell
awk -F: '$3<10&&$7~/bash/{print}' /etc/passwd  //找第3列小于10并且第7列包含bash的行，{print}可以省略

awk -F: '$3>=10&&$3<=20{print}' /etc/passwd  //找第3列大于等于10并且小于等于20的行

awk -F: 'NR>=2&&NR<=10{print}' /etc/passwd  //找2~10行


awk -F: '$3<5||$3>1000{print}' /etc/passwd  //找id号是小于5的或者大于1000的 
```

  

### **4，使用运算作为条件**

```shell
seq 200 | awk '$1%7==0&&$1~/7/{print}'  //在一个有200行从1~200的数字序列的文档中找能被7整除的行,并且包含7
```

\---------------------------------------------------------------------------------------

**在awk中使用if分支**

**单分支，如果满足条件就执行指令，不满足就不执行任何指令**

**{if(条件){指令}}**

```shell
awk -F: 'BEGIN{x=0}{if($7~/bash/){x++}}END{print x}' /etc/passwd //首先定义变量x=0，然后使用if判断如果每找到一行的$7包含bash，就把x+1，所有逐行任务结束后，最终使用end任务输出x的值，也就是找系统中使用bash作为解释器的用户数量
```

 

**双分支， 如果满足条件就执行指令，不满足就执行else后面的指令**

**{if (条件){指令}else{指令}}**

awk -F: 'BEGIN{x=0;y=0 }{if($7~/bash/){x++}else{y++}}END{print x,y}' /etc/passwd  //统计系统中使用bash作为解释器的用户，和没有使用bash的用户数量,使用if判断如果每找到一行的$7包含bash，就把x+1，否则y+1，最后使用end输出x与y的值

 

**多分支**

**{if (条件){指令}else if (条件){指令}else{指令}}**

```
awk -F: '{if($7~/bash/){x++}else if($7~/nologin/){y++}else{z++}}END{print x,y,z}' /etc/passwd  //统计系统中使用bash作为解释器的用户，使用nologin的用户，还有其他用户的数量
```

\------------------------------------------------------------------------------------------------

**数组，相当于可以存储多个值的特殊变量**

**数组名[下标]=该数组下标对应的值**

```shell
a[1]=10

a[2]=20
```

**在awk中使用for循环遍历数组**

**for(变量名称 in数组名称){print 变量名称 }**

 

**基本用法示例1：**

```shell
awk 'BEGIN{a[1]=10;a[2]=20;for(i in a){print i}}'  //首先创建数组，名字叫a，并且有1与2两个下标，还有对应的10与20两个值，然后为了方便查看该数组中所有内容，使用了for循环，可以循环显示所有数组a的下标，然后输入变量i，此时的变量i就可以分别显示数组a的所有下标
```

 

**基本用法示例**2：

```shell
awk 'BEGIN{a[1]=10;a[2]=20;for(i in a){print a[i]}}'  //定义好了数组之后，循环显示数组的值

awk 'BEGIN{abc["a"]="aaa";abc["b"]="bbb";abc["c"]="ccc";for(i in abc){print i,abc[i]}}'  //定义好了数组之后循环显示数组的下标与值
```

 

**基本用法示例3：**

准备素材

```vim
vim test

abc

xyz

opq

abc

abc

xyz
```

 

\-------------------------------------

使用awk的数组进行逐行任务时收集数据的思路过程：

```shell
abc   a[abc]  a[abc]=1

xyz		a[xyz]  a[xyz]=1

opq   a[opq]  a[opq]=1

abc   a[abc]   a[abc]=2

abc   a[abc]   a[abc]=3

xyz		a[xyz]	a[xyz]=2
```

\---------------------------------------------------------------------------------

**实际应用1：**

**使用awk统计网站访问量**

```shell
yum -y remove httpd  //如果httpd有问题可以先删除

yum -y install httpd	 //安装httpd

systemctl restart httpd  //开启服务

netstat -ntulp | grep :80  //查询当前80端口状态

echo "web_test~~~~" > /var/www/html/index.html  //定义网站页面

yum -y install curl  //安装curl工具

curl 192.168.4.7  //查看网站内容，防火墙要关闭

cd /var/log/httpd  //进入httpd日志目录

tail -1 access_log  //查看httpd日志的最后一行，也就是最新记录，然后多用不同主机访问该网站，可以让该日志多产生记录
```

 

```shell
awk '{ip[$1]++}END{for(i in ip){print ip[i],i} }' access_log  //创建数组名叫ip，下标匹配日志文件中每行的第1列，然后收集数据，也就是收集那些ip地址曾经访问过你的网站，最后在END任务中使用for循环显示这些用户的访问次数与ip
```

 

**实际应用2：**

**使用awk统计多少ip曾经尝试登陆你的服务器**

```shell
awk '/Failed pas/{ip[$11]++}END{for(i in ip){print ip[i],i} }' /var/log/secure  //找到安全日志secure中含有Failed pas的行，该行表示有用户登录服务器时输入错误了密码，从该行的第11列可以筛选出对方的ip，并通过数组进行收集，然后通过for循环显示有多少ip(人)尝试登录过几次我的服务器
```

 

\----------------------------------------------------

**练习：**

**编写脚本，收集系统中各种信息，方便查看**

```shell
#!/bin/bash

while :

do

uptime | awk '{print "cpu的15分钟平均负载是"$NF}'

ifconfig eth0 | awk '/RX p/{print "eth0网卡的接收流量是"$5"字节"}'

free -h | awk '/^Mem/{print "剩余内存是"$4}'

df -h | awk '/\/$/{print "磁盘根分区剩余容量是"$4}'

awk 'END{print "账户总数是"NR"个"}' /etc/passwd

echo "当前开启的进程数量是$(ps aux | wc -l)个"

echo "当前登录的用户数量是$(who | wc -l)个"

echo "总共安装的软件包数量是$(rpm -qa | wc -l)个"

sleep 3			//休息3秒

clear 			//清屏

done
```

# SHELL-周考

1、(单选题)awk使用什么设置读取文件前执行的指令?
A.END{} 
B.BEGIN{} 
C.BEGIN() 
D.START{} 
【正确答案】B
【答题时间】2020-10-15 07:17:57
【答案解析】无

2、(单选题)使用bc计算器运算时，使用什么指令可以指定
小数位个数？
A.float 
B.int 
C.cale 
D.scale 
【正确答案】D
【答题时间】2020-10-15 07:17:57
【答案解析】无

3、(单选题)正则表达式中哪个符号代表任意单个
字符?
A.. 
B.* 
C.# 
D.$ 
【正确答案】A
【答题时间】2020-10-15 07:17:57
【答案解析】无

4、(单选题)可以将字符串abc替换成789的是？
A.${变量名%abc%789} 
B.${变量名/abc/789} 
C.${变量名abc:789} 
D.${变量名#abc#789} 
【正确答案】B
【答题时间】2020-10-15 07:17:57
【答案解析】

5、(单选题)在linux系统中使用ping命令，可以定义次数与间隔时间的选项是？
A.-c , -w 
B.-c , -i 
C.-i , -c 
D.-i , -W 
【正确答案】B
【答题时间】2020-10-15 07:17:57
【答案解析】

6、(单选题)执行i=2;let i++;echo $i命令后，i的值
是多少？
A.4 
B.1 
C.2 
D.3 
【正确答案】D
【答题时间】2020-10-15 07:17:57
【答案解析】无

7、(单选题) 从左向右，一直删除到最后一个x的是？
A.${变量名%%x*} 
B.${变量名##*x} 
C.${变量名#*x} 
D.${变量名%x*} 
【正确答案】B
【答题时间】2020-10-15 07:17:57
【答案解析】

8、(单选题)下列哪个命令是跳出循环体，执行循环之后的任务?
A.quit 
B.continue 
C.break 
D.exit 
【正确答案】C
【答题时间】2020-10-15 07:17:57
【答案解析】

9、(单选题)取消变量的命令是什么?
A.set 
B.define 
C.unset 
D.undefine 
【正确答案】C
【答题时间】2020-10-15 07:17:57
【答案解析】无

10、(单选题)将标准输出重定向到文件的符号是什么?
A.>< 
B.< 
C.<> 
D.> 
【正确答案】D
【答题时间】2020-10-15 07:17:57
【答案解析】无

11、(单选题)sed命令的哪个选项可以直接修改源文件?
A.-n 
B.-r 
C.-u 
D.-i 
【正确答案】D
【答题时间】2020-10-15 07:17:57
【答案解析】无

12、(单选题)当a=10,b=20时下列说法错误的是？
A.[ $a –eq $b ] ; echo $? 结果是非0 
B.[ $a –ge $b ] ; echo $? 结果是非0 
C.[ $a –lt $b ] ; echo $? 结果是非0 
D.[ $a –ne $b ] ; echo $? 结果是0 
【正确答案】C
【答题时间】2020-10-15 07:17:57
【答案解析】


13、(单选题)一个刚刚安装好的centos系统，在未做任何修改的情况下执行下列命令，结果为0的是?
A.[ -e /etc ] || echo $? 
B.[ -f /etc ] && echo $? 
C.[ -r /etc ] || echo $? 
D.[ -d /etc ] && echo $? 
【正确答案】D
【答题时间】2020-10-15 07:17:57
【答案解析】


14、(单选题)哪条命令行可以查看系统中的解释器？
A.cat /etc/bash 
B.cat /etc/shell 
C.cat /etc/shells 
D.cat /var/shells 
【正确答案】C
【答题时间】2020-10-15 07:17:57
【答案解析】


15、(单选题)正则表达式中哪个符号代表开始?
A.^ 
B.$ 
C.# 
D.u 
【正确答案】A
【答题时间】2020-10-15 07:17:57
【答案解析】无

16、(单选题)扩展正则中哪个符号代表前面的符号
出现了至少1次？
A.+ 
B.? 
C.* 
D.() 
【正确答案】A
【答题时间】2020-10-15 07:17:57
【答案解析】无

17、(单选题) 双引号与单引号的区别是？
A.双引号内的特殊符号会被屏蔽，单引号不会 
B.写法不同，无其他区别 
C.两者都具有屏蔽特殊符号的效果 
D.单引号内的特殊符号会被屏蔽，双引号不会 
【正确答案】D
【答题时间】2020-10-15 07:17:57
【答案解析】

18、(单选题)awk使用什么选项可以自定义分隔符?
A.-a 
B.-F 
C.-Q 
D.-R 
【正确答案】B
【答题时间】2020-10-15 07:17:57
【答案解析】无

19、(单选题)重定向输入的符号是什么?
A.< 
B.> 
C.>< 
D.<> 
【正确答案】A
【答题时间】2020-10-15 07:17:57
【答案解析】无

20、(单选题)哪个是合格的自定义变量？
A.abc#=100 
B.abc_123=100 
C.abc-123=100 
D.123a=100 
【正确答案】B
【答题时间】2020-10-15 07:17:57
【答案解析】

21、【多选题】
(多选题)A && B || C,什么时候会执行C命令？
A.A执行成功，B执行成功时 
B.A执行失败，B执行成功时 
C.B执行，但失败时 
D.A执行，但失败时 
【正确答案】C,D
【答题时间】2020-10-15 07:17:57
【答案解析】无

22、【多选题】
(多选题)想要查看5乘以5的运算结果，哪个方式是错的？
A.echo "5*5" | bc 
B.let 5*5 
C.echo $[5*5] 
D.expr 5 * 5 
【正确答案】B,D
【答题时间】2020-10-15 07:17:57
【答案解析】

23、【多选题】
(多选题)sed可以通过操作指令对文件进行增、删、改、
查的操作，下列哪些指令是sed不支持的?
A.a 
B.k 
C.p 
D.yy 
【正确答案】B,D
【答题时间】2020-10-15 07:17:57
【答案解析】无

24、【多选题】
(多选题)sed可以通过操作指令对文件进行增、删、改、查的操作，下列哪些指令是sed支持的?
A.s 
B.d 
C.p 
D.a 
【正确答案】A,B,C,D
【答题时间】2020-10-15 07:17:57
【答案解析】无

25、【多选题】
(多选题)在Shell脚本中可以实现循环功能的语句有哪些？
A.if 
B.for 
C.case 
D.while 
【正确答案】B,D
【答题时间】2020-10-15 07:17:57
【答案解析】无

# OPERATION

## 01：Nginx安装、用户认证、Nginx虚拟主机、HTTPS加密网站

**回顾：**

()  正则  保留  $( )  获取命令的执行结果

$(( ))  运算  if(){ }  for(){ }

$[ ]  运算  [条件测试]   

a=10

echo ${a}XXX 变量名容易混淆时

${变量名称:}  截取

${变量名称/}  替换

${变量名称#}  掐头

${变量名称%}  去尾

${变量名称:-}  定义初值

awk  BEGIN{ }{ }END{  }

\-----------------------------------------------

**Nginx（"engine x"）**

**是俄罗斯人编写的十分轻量级的HTTP服务器**

**是一个高性能的HTTP和反向代理服务器，同时也是一个IMAP/POP3/SMTP 代理服务器**

**官方网站：http://nginx.org/**

 

**下面使用proxy主机配置nginx：**

### **1，准备工作**

```shell
ip add show  //查看ip
```

**安装常用工具：**

```shell
yum -y install bash-completion  //安装支持tab键的工具包，安装完毕之后，要退出终端重新登录才生效

yum -y install vim  //安装vim编辑器

yum provides  XXX //查xxx工具来自哪个软件包

yum -y install net-tools  //安装网络相关工具，比如ifconfig查询ip地址

yum -y install psmisc  //安装支持killall命令的软件包

nmcli connection modify ens33 connection.autoconnect yes  //网卡开机自启
```

 

### **2，Nginx环境搭建：** 

1，找到lnmp_soft.tar.gz，拷贝到虚拟机的root家目录，并释放到原地

2，释放lnmp_soft目录中的nginx-1.17.6.tar.gz

```shell
yum -y install gcc //安装编译工具

yum -y install pcre-devel  //安装让nginx支持正则的软件包

yum -y install openssl-devel  //让nginx搭建基于ssl（安全加密）

的网站
```

 

### **3.编译安装**

```shell
./configure  --with-http_ssl_module  //配置，添加安全模块

make  //编译

make install  //安装

/usr/local/nginx/sbin/nginx  //开启服务		

./configure --help | grep http_ssl  //另外，可以用该方式搜索与http_ssl有关的模块，--help可以看配置nginx时的配置选项与模块
 
cd /usr/local/nginx   //进入nginx安装目录

ls   //查看
```

#### **Nginx中的主要目录:**

**conf 存放配置文件**

**html 存放网页文件**

**sbin 存放主程序**

**logs 存放日志**

 

### **4，使用nginx服务：**

```shell
/usr/local/nginx/sbin/nginx  -V  //查看版本已经添加的功能模块

/usr/local/nginx/sbin/nginx  //开启

/usr/local/nginx/sbin/nginx  -s stop  //关闭

/usr/local/nginx/sbin/nginx  -s reload  //重新加载配置文件，服务必须是开启状态

systemctl stop firewalld  //关闭防火墙

[root@proxy nginx]# cd ~/lnmp_soft/

[root@proxy lnmp_soft]# yum -y install unzip  //安装解压缩工具

unzip www_template.zip  //解压缩网页模板文件

cp -r www_template/* /usr/local/nginx/html/  拷贝网站模板的文件到nginx的页面目录，会询问是否覆盖index.html，回答y然后使用浏览器访问192.168.2.5可以看到该网站
```

\------------------------------------------------------------------------------------

 

#### **为nginx增加网站认证功能**

**通常情况下网站搭建好之后，只要知道ip或者域名，那么任何用户都可以访问该网站，如果仅仅想让某些用户访问就可以使用该功能**

 

1，	首先打开nginx主配置文件,在第42行，43行添加

```shell
vim /usr/local/nginx/conf/nginx.conf

 auth_basic  "password:";  //提示信息，用户登录网站时看到的

 auth_basic_user_file  "/usr/local/nginx/pass";  //存放用户名密码的文件路径
```

 

2，yum -y install httpd-tools  //安装网站工具包，支持htpasswd命令

```shell
htpasswd -c  /usr/local/nginx/pass  tom  //创建网站的用户与密码文件，第1个用户名为tom（可以自定义），之后输入2次密码

cat /usr/local/nginx/pass  //查看pass文件
```

 

3，/usr/local/nginx/sbin/nginx -s reload  //如果nginx服务已经开启，就重加载配置文件

```shell
/usr/local/nginx/sbin/nginx  //如果nginx服务没开启，就开启使用火狐浏览器打开192.168.2.5发现已经需要用户名和密码认证

htpasswd  /usr/local/nginx/pass abc  //追加新账户，无需c选项

如果要反复测试该功能，需要清空浏览器的历史记录
```

\------------------------------------

**还原nginx配置：**

**在conf目录中存放了nginx.conf.default，这是配置文件的备份，在重新做实验或者配置文件被破坏需要还原是可以用该文件拷贝覆盖nginx.conf**

```shell
cd conf/

[root@proxy conf]#

[root@proxy conf]# cp  nginx.conf.default  nginx.conf

cp：是否覆盖"nginx.conf"？ y
```

\-----------------------------------------------------

 

**通常使用一台服务器开启一个nginx服务就可以开启一个网站，但是如果公司需要很多不同域名的网站，而每个网站的业务量不大时，不必购买多台服务器，使用一台服务器利用虚拟主机技术既可以实现。**

 

**回顾虚拟主机**

**在httpd中配置：**

```shell
<virtualhost *:80>

 	Servername [www.a.com](http://www.a.com)

	Documentroot /var/www/html

</ virtualhost>
```

 

**在nginx中配置(基本框架)：**

```shell
http {

	server {

	listen :80;   //监听端口号

	server_name [www.a.com](http://www.a.com); //网站域名

	root html;   //网站页面文件存储的位置

	index index.html  //默认页面

	}

}
```

\-----------------------------------------------------------------



### **正式配置**

#### **1，修改主配置文件，在34~\39行开始添加以下内容**

```shell
34   server {

35     listen 80;  //监听端口

36     server_name www.b.com;  //域名

37     root b;  //网页文件存放地

38     index index.html;  //默认页文件名

39    }
```

 

#### **2，准备测试页面**

```shell
cd /usr/local/nginx

mkdir b  //创建b网站的页面存放目录

echo "proxy_nginx_web_b~~~~~"  > b/index.html  //b网站内容

echo "proxy_nginx_web_a~~~~~"  > html/index.html  //a网站内容

vim /etc/hosts  添加域名与ip的映射关系

192.168.2.5 www.a.com www.b.com www.c.com

curl www.b.com		测试b网站

curl www.a.com  	测试a网站
```

 

如果在windows环境测试域名访问网站，需要修改hosts文件，添加一样的内容（hosts文件的权限需要设置为完全控制）

C:\Windows\System32\drivers\etc\hosts

设置hosts的权限要先右键---属性---安全---编辑---users---完全控制勾选，然后右键该文件---打开方式---选择文本方式打开在最后一行下面写入与之前linux一样的内容

192.168.2.5  www.a.com  www.b.com  www.c.com

然后使用火狐浏览器访问www.a.com或者www.b.com

\-------------------------------------------------------------------------------

### **搭建基于ssl技术的安全网站**

 

#### **1，了解加密算法**

 **对称加密，适合单机环境**

加密和解密是相同密码

 **非对称加密，适合网络数据传递**  

加密和解密分别使用公钥和私钥

证书（包含公钥），可以用来加密

私钥 ，可以用来解密

 **信息摘要，数据校验**

md5sum  nginx.conf  //使用md5工具计算nginx配置文件随机校验值，以后可以根据该校验值判断文件是否被篡改

 

#### **2，修改主配置文件第103行左右，找安全网站的虚拟主机的配置，将所有注释去掉，可以使用:103,120s/#//**

```shell
103   server {

104     listen    443 ssl;

105     server_name  www.c.com;

106

107     ssl_certificate    cert.pem;  //证书文件

108     ssl_certificate_key  cert.key;   //私钥文件

109

110     ssl_session_cache   shared:SSL:1m; 

111     ssl_session_timeout  5m;

112

113     ssl_ciphers  HIGH:!aNULL:!MD5;

114     ssl_prefer_server_ciphers  on;

115

116     location / {

117       root  c; 

118       index  index.html index.htm;

119     }

120   }
```

\------------------------------------------------------------------

#### **3，创建私钥与证书**

```shell
cd /usr/local/nginx/conf

openssl genrsa > cert.key  创建私钥

openssl req -new -x509 -key cert.key > cert.pem  根据刚刚创建的私钥，再创建证书(包含了公钥),生成过程会询问诸如你在哪个国家之类的问题，可以随意回答，但要走完全过程

Country Name (2 letter code) [XX]:dc			国家名称

State or Province Name (full name) []:dc		省份名称

Locality Name (eg, city) [Default City]:dc     城市名称

Organization Name (eg, company) [Default Company Ltd]:dc   公司名称

Organizational Unit Name (eg, section) []:dc   部门名称

Common Name (eg, your name or your server's hostname) []:dc   服务器名称

Email Address []:dc@dc.com   邮件地址
```

\------------------------------------------------------

最后测试

```shell
[root@proxy nginx]# sbin/nginx -s reload  重新加载配置

使用火狐浏览器访问https://www.c.com/  看到提示---高级---接收风险

或者使用curl -k https://www.c.com/ 用命令行的方式访问，使用-k选项可以忽略风险提示直接看网页内容

netstat -ntulp | grep nginx  //查看nginx可以看到443端口已经开放
```

##   02：部署LNMP、Nginx+FastCGI、Nginx高级技术

==================================

**静态网站 在不同环境下，浏览网站的内容不会发生变化**

**动态网站 在不同环境下，浏览网站的内容有可能会发生变化，该种类网站显示内容效果更好，会让用户体验更好，更适合目前市场环境**

**----------------------------------------------------**

**部署LNMP环境，有了该环境，nginx就可以很便利的支持动态网站，这也是主流的企业网站平台之一**

**L：Linux操作系统**

**N：Nginx网站服务软件**

**M：MySQL、MariaDB数据库**

**P：网站开发语言**

 

### **LNMP（Linux、Nginx、MySQL、PHP）**

**部署LNMP环境**

#### **1，准备nginx**

```shell
rm -rf /usr/local/nginx/  //删除原有环境

netstat -ntulp | grep :80  //查询80端口的占用情况

killall nginx  //如果nginx还在运行，可以杀掉

cd lnmp_soft/nginx-1.17.6/

./configure --help | grep http_ssl  //查询模块名称

./configure --with-http_ssl_module  //配置

make  //编译

make install  //安装
```

 

#### **2，安装其他相关软件包**

```shell
yum -y install mariadb mariadb-server mariadb-devel  //安装

数据库的客户端、服务端、依赖包

yum -y install php  //安装php解释器程序

yum -y install php-mysql  //安装php与数据关联的软件包

yum -y install php-fpm  //安装让nginx具有动态网站解析能力的软件包

systemctl  restart  mariadb  //开启数据库

systemctl  restart  php-fpm	//开启php-fpm

netstat -ntulp | grep :3306   //查看数据库端口

netstat -ntulp | grep :9000		//查看php-fpm端口
```

 

#### **3，测试效果，目前还无法让nginx解析动态网站**

```shell
cd  /root/lnmp_soft/php_scripts

cat test.php  //查看文件，有普通的网站语言(html)，也有php语言

cp test.php /usr/local/nginx/html/  //拷贝动态网站页面到nginx的html目录下，使用火狐浏览器访问192.168.2.5/test.php可以看到下载文件的提示
```

 

#### **4，分析没有看到动态网站的原因：Nginx默认只支持静态页面**

用户如果访问静态页面，nginx会直接将该页面传递给用户的主机，用户再使用浏览器解析该页面内容

用户如果访问动态页面（如php语言编写的test.php页面），nginx要先将该页面扔给后台的php-fpm,该程序就会利用php解释器翻译php语言编写的网站页面，然后发给nginx程序，nginx再转发给用户，最终用户才能看到动态页面

 

```shell
cat /etc/redhat-release

CentOS Linux release 7.5.1804 (Core)    
```

 

#### **5，nginx实现动静分离**

**为了让nginx支持动态网站的解析，要先修改配置文件**

```shell
第65到71行去掉注释，69行不用去，才可以实现动态页面解析

65     location ~ \.php$ {  //~是使用正则表达式，匹配以.php结尾

66      root      html;

67      fastcgi_pass  127.0.0.1:9000;  //一旦用户访问了.php结尾的文件，就让nginx找后台的php-fpm（端口号9000）

68      fastcgi_index  index.php;

69     #  fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi  

 _script_name;

70      include     fastcgi.conf;  //这里需要修改名称

71     }

\-----------------------------

[root@proxy nginx]# sbin/nginx -s reload  //重新加载nginx配置文件

再使用火狐浏览器访问192.168.2.5/test.php可以看具体页面内容了
```

 

#### **6，再测试调用数据库的网页**

首先拷贝页面

```shell
cd ~/lnmp_soft/php_scripts/

cp mysql.php /usr/local/nginx/html/

再用火狐访问http://192.168.2.5/mysql.php
```



**测试数据库内容发生变化之后网页是否变化**

```shell
mysql		登录数据库，手工创建dc账户

MariaDB [(none)]> create user dc@localhost identified by '123';

再用刷新http://192.168.2.5/mysql.php页面，会看到dc账户
```

 

\----------------------------------------------------

### **进一步了解php-fpm服务：**

**php-fpm 是fastCGI的进程管理器**

**fastCGI  快速公共网关接口，可以用来关联网站服务与解释器**

 

**了解php相关配置文件，目前无需配置**

```shell
vim /etc/php-fpm.d/www.conf  //php有关的配置文件

listen = 127.0.0.1:9000   //此处配置决定了php-fpm服务针对什么ip与什么端口

pm.start_servers = 5   //一上来开启的进程数量，pstree可以查看php-fpm的进程数量，如果修改了需要重启php-fpm服务

pm.max_children = 50  //开启的fastCGI进程最大数量
```

 

\-------------------------------------------------------

#### **地址重写：**

**可以实现在用户访问网站页面时推送其他页面的内容，或者跳转域名**

 

比如用户访问a.html页面  看到的是b.html页面

或者访问[www.abcd1234.com](http://www.abcd1234.com)  看到的是  [www.abc.com](http://www.abc.com)

 

**地址重写语法格式：**

```shell
rewrite  regex        replacement    flag 

rewrite 旧地址(支持正则)   新地址      [选项]
```

\----------------------------------------------------

 

**准备素材**

```shell
[root@proxy nginx]# echo "nginx_web_a~" > html/a.html

[root@proxy nginx]# echo "nginx_web_b~" > html/b.html
```

 

**恢复配置文件为默认状态**

```shell
[root@proxy nginx]# cd conf/

[root@proxy conf]# cp nginx.conf.default nginx.conf

cp：是否覆盖"nginx.conf"？ y
```

 

**地址重写测试1： 相同网站内的页面跳转，地址栏不变**

打开nginx主配置文件，在第42行添加

```shell
rewrite  ^/a.html$ /b.html;   当访问a页面时可以看到b页面的内容,此处的a.html匹配可以使用正则没有添加^和$之前，可以匹配/xyz/a.html 或 /a.htmlxyz添加了正则符号之后匹配的更精准，只针对/a.html进行重写。

sbin/nginx -s reload  重加载配置文件

使用火狐浏览器访问192.168.2.5/a.html 但看到了b.html的内容
```

 

**地址重写测试2： 相同网站内的页面跳转，地址栏发生变化**

```shell
打开nginx主配置文件，在第42行添加

rewrite  /a.html$  /b.html  redirect;  //添加了redirect（重定向）选项

sbin/nginx -s reload  重加载配置文件

使用火狐浏览器访问192.168.2.5/a.html，可以看到页面换成b.html的同时，浏览器地址栏也发生了变化
```

 

**地址重写测试3：不同网站的地址跳转**

```shell
打开nginx主配置文件，在第42行添加

rewrite  /  http://www.tmooc.cn;  访问老网站，跳转到新的

sbin/nginx -s reload  重加载配置文件

使用火狐浏览器访问192.168.2.5/a.html 会跳到tmooc.cn
```

 

**地址重写测试4：不同网站的相同页面的地址跳转**

```shell
打开nginx主配置文件，在第42行添加

rewrite  ^/(.*)$  http://www.tmooc.cn/$1;  访问老网站的某个页面时，跳转到新网站对应的相同页面。前面使用正则表达式匹配用户输入的任意页面，并保存起来（小括号在正则中的效果是保留，相当于保存复制），后面使用$1将之前保存的页面地址粘贴到新网站

sbin/nginx -s reload  重加载配置文件

使用火狐浏览器访问192.168.2.5/a.html
```

 

**地址重写测试5：根据用户的情况决定跳转到什么样的页面**

```shell
cd  /usr/local/nginx/html

mkdir  firefox  //创建火狐浏览器专属文件的目录

echo "proxy_nginx_firefox~" > firefox/test.html  //准备火狐专用页面

cd ..

echo "proxy_nginx_other~"  > html/test.html  //准备普通浏览器使用的页面

vim conf/nginx.conf  //删除原有地址重写的配置，然后在第46行添加

if ($http_user_agent ~* firefox) {  //如果用户的浏览器使用了火狐，就执行下面的rewrite任务，~代表匹配正则，*是不区分大小写，$http_user_agent是nginx的内置变量，存储了用户的信息，比如用的什么浏览器

rewrite ^/(.*)$  /firefox/$1;   //就跳转到火狐专用目录的页面

}

sbin/nginx -s reload  重加载配置文件

分别使用火狐浏览器与其他浏览器访问192.168.2.5/test.html，可以得到两个不同页面内容则成功
```

## 03:Nginx代理服务器、Nginx优化

### **地址重写相关选项：**

last 不再读其他rewrite

break 不再读其他语句，结束请求

redirect 临时重定向

permanent 永久重定向

\--------------------------------------

**测试一：** 

**redirect 临时重定向(http状态码302)**

**permanent 永久重定向(http状态码301)**

 

打开nginx主配置文件，在42行添加

```shell
rewrite  /a.html  /b.html  redirect; 
```

然后开启或者重加载nginx服务

```shell
curl 192.168.2.5/a.html		//此时看到的页面是b
```

 

再次打开主配置文件，在42行修改

```shell
rewrite  /a.html  /b.html  permanent;

sbin/nginx -s reload  //重加载nginx服务

curl 192.168.2.5/a.html  //此时看到的页面也是b，说明redirect与permanent效果在客户机看来是一样的，但是状态码不一样，对于搜索引擎来说更关心301的
```

 

**测试二：** 

**last 不再读其他rewrite**

**break 不再读其他语句，结束请求**

 

```shell
[root@proxy nginx]# echo nginx_web_c~ > html/c.html  //准备c页面

打开主配置文件，在42行修改

rewrite /a.html /b.html;

rewrite /b.html /c.html;

sbin/nginx -s reload  //重加载nginx服务

使用火狐访问192.168.2.5/a.html 看到的是c.页面
```

 

```shell
rewrite /a.html /b.html last;  //然后再修改配置添加last可以实现不继续跳转

sbin/nginx -s reload  //重加载nginx服务

使用火狐访问192.168.2.5/a.html 看到的是b.html
```

 

再次按下图修改配置文件，删除原有rewrite语句，如果使用last无法阻止第

二个location中的rewrite语句，而break可以

 ![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml4568\wps1.jpg)

开启或者重加载服务

使用火狐访问192.168.2.5/a.html 看到的是b.html

 

\-----------------------------------------------------------

### **用nginx实现网站代理功能**

**一台服务器的能力是有限的，如果客户访问量比较大，可以利用nginx的代理功能组建集群，集群中的服务器越多集群整体性能就越强**

 

#### **1，集群中服务器的准备工作，这里使用web1 与web2**

在web1与web2安装常用工具

```shell
yum -y install vim

yum -y install bash-completion   //tab键补全软件包

yum -y install net-tools  //网络工具软件包，支持ifconfig等命令
```

 

在web1与web2安装网站服务

```shell
yum -y install httpd

echo web1 > /var/www/html/index.html  //这里如果是web2主机要改成echo  web2

systemctl start httpd

systemctl stop firewalld
```

 

使用proxy测试web1与web2

```shell
[root@proxy nginx]# curl 192.168.2.100

web1

[root@proxy nginx]# curl 192.168.2.200

web2
```

#### **2，在proxy主机添加创建集群配置**

首先是34~37行

```shell
 upstream web {		 //创建nginx集群，名称是web

   server 192.168.2.100:80;   //这里是集群中的服务器ip与端口
   server 192.168.2.200:80;

 }

然后在47行

47     proxy_pass http://web;  //调用web集群
```

 

```
sbin/nginx -s reload  //重加载nginx服务

使用火狐访问192.168.2.5  不断刷新，看到的页面内容是web1与web2之间切换

或者使用curl 192.168.2.5
```

 

**集群优化，在集群中的主机ip与端口后面加入以下参数，可**

**以实现不同效果。**

```shell
server 192.168.2.100:80 weight=2;  //权重，值越大，工作量越大

server 192.168.2.100:80 max_fails=2 fail_timeout=30;  //检测2次如果失败，则认为集群中的服务器故障,认为集群中的服务器故障之后等待30秒才会再次链接

server 192.168.2.100:80  down;  加down标记，使集群服务器暂时不参与集群的任务轮询
```

```shell
ip_hash  //相同客户机访问相同服务器
```

```
tcp/ip  物理层  数据链路层  网络层  传输层tcp/udp 应用层s
```

 

在proxy主机：停止nginx服务，并删除nginx

回到家目录下的lnmp_soft的nginx目录重新编译安装nginx，

将上述两个模块都添加上，其中--with-stream是四层代理模块

可以让nginx组建其他业务(非web)的集群，另外一个模块可以

查看网站后台数据。

```shell
./configure --with-stream --with-http_stub_status_module

make

make install

sbin/nginx  -V

sbin/nginx  开启服务

web1与web2的root密码要设置成一致

proxy的家目录下的.ssh目录中known_hosts文件记录了都远程

登录过哪些机器，可以先删除
```

 

打开nginx主配置文件，在16行左右(http上面)，添加以下内容

```shell
16 	stream {				//使用新业务

17   	upstream backend {   //创建名叫backend的集群

18     		server 192.168.2.100:22;  //集群中的主机使用22端口对外提供服务

19     		server 192.168.2.200:22;

20 		}

21   	server {

22     		listen 12345;   //监听端口号

23    	 	proxy_pass backend;   //调用集群

24 		}

25 }
```

写完后启动服务或者重新加载配置

```shell
[root@proxy nginx]# rm -rf ~/.ssh/known_hosts  //先删除远程连接的主机记录，之后每次连接测试都先删除该文件

[root@proxy nginx]# ssh 192.168.2.5 -p 12345  //使用12345端口号连接代理服务器此处使用自己连接自己测试，如果使用client主机就远程连接192.168.4.5
```

 

ss命令可以查看系统中启动的端口信息，该命令常用选项如下：

-a显示所有端口的信息

-n以数字格式显示端口号

-t显示TCP连接的端口

-u显示UDP连接的端口

-l显示服务正在监听的端口信息，如httpd启动后，会一直监听80端口

-p显示监听端口的服务名称是什么（也就是程序名称）

注意：在RHEL7系统中可以使用ss命令替代netstat命令，功能一样，选

项一样。

 

\---------------------------------------------------

### **Nginx常见问题的处理**

#### **1，404报错优化：**

首先修改配置文件 59行

```
error_page  404     /test.jpg;  //如果客户访问了不存在的页面 就显示test.jpg的内容
```

保存退出

找一张图片，内容随意，保存成test.jpg格式，然后拷贝到proxy主机

的/usr/local/nginx/html目录下

重新加载nginx配置

使用浏览器随意访问不存在的页面192.168.2.5/XXXX.html 

 

```shell
location /status {  //当用户输入的地址后面跟了/status之后

    stub_status on;  //开启网站后台状态信息查看功能

	allow 192.168.2.5;  //仅仅允许2.5查看

    deny all;  //拒绝其他所有主机

}

   error_page  404     /test.jpg;
```

```shell
curl http://192.168.2.5/status  //查看测试，仅仅2.5可以看

页面中各个字段的含义：

Active connections：当前活动的连接数量（当前有多少用户访问该网站）。

Accepts：已经接受客户端的连接总数量。

Handled：已经处理客户端的连接总数量。

Requests：客户端发送的请求数量。

 
Reading：当前服务器正在读取客户端请求头的数量。

Writing：当前服务器正在写响应信息的数量。

Waiting：当前多少客户端在等待服务器的响应。
```

#### **2，配置nginx缓存数据的功能：**

**客户在访问服务器时，有可能随时需要重复的文件，如果反复从服务器获取会造成资源浪费，还耽误时间，可以通过配置将常用的或者比较大的文件在用户访问一次之后就缓存在客户机中，下次客户访问时不用再找服务器而是从本机获取。**

修改配置文件 在默认的location的下面添加一个新的location

```react
location ~* \.(jpg|png|mp4|html)$ {  //当用户访问的是这几种类型的

文件时

expires  30d;  //都会缓存在客户机上30天

}
```

 

然后使用火狐浏览器，先清空历史记录，然后地址栏输入about:cache

查看disk文件的列表，找到被访问文件看最后倒数第2列信息显示多

久超时

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13848\wps1.jpg) 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13848\wps2.jpg) 

## 04：Session与Cookie、部署memcached、Session共享

### **1，优化Nginx数据包头缓存，支持更长的地址，默认情况下nginx无法**

**支持长地址栏，会报414错误**

打开配置文件，在默认的虚拟主机上面添加：

```shell
client_header_buffer_size   200k;  //存储地址栏等信息的空间大小

是200k

large_client_header_buffers  4 200k;  //如果不够再给4个200k
```

配置完毕后重加载nginx

```shell
cd /root/lnmp_soft

vim  buffer.sh  //修改脚本，将里面的4.5修改为2.5(非必须操作)，该脚本的效果是可以产生一个超长的地址

./buffer.sh  //执行测试脚本，可以支持超长地址栏并看到页面内容，而不是414报错
```

###  **2，nginx并发访问的优化**

**并发：多数用户同时对网站发起访问，并发量支持的越高，说明网站性能越强。**

**默认情况下nginx并发仅仅支持1\024个，需要修改配置才能增加**

yum -y install httpd-tools  //安装支持压力测试命令的软件包

ab -c 1000 -n 1000 http://192.168.2.5/  //使用压力测试工具模拟1000人，一共1000次, 相当于每人访问1次，看到100%的提示说明成功，但是增加到2000之后就不行了

\-------------

**打开nginx配置文件修改第3行，第13行**

```shell
 worker_processes  2;  //开启的nginx进程数量，通常是随cpu的核心数一致

  worker_connections  50000;  //每个nginx进程支持的并发访问量
```

之后重加载nginx

\-----------------------------

**另外，除了nginx本身对并发量有限制，linux系统本身对文件的访问也有限制，默认情况下linux系统仅允许一个文件同时被打开1024次，普通情况下够用，但是作为网站服务器时，网站页面被N多用户同时访问时相当于同时打开，仅仅支持1024显然不够。**

 

**永久修改文件访问限制**

```shell
vim /etc/security/limits.conf  //修改53、54行，将下列两项内容修改为10万

\*    soft   nofile    100000

\*    hard   nofile    100000

重启虚拟机才能生效

ulimit  -n  //检查系统对文件打开数量的值，默认1024，之后则显示10万
```

\-----------------------------------

临时修改限制，修改为支持10万(如果已经配置过永久则无需再执行该步骤)

```shell
ulimit  -Hn  100000  

ulimit  -Sn  100000
```

\------------------------------------

**注意：上述的文件访问限制也需要在测试主机(比如web1)上配置，另外所有主机的selinux也要都关闭**

```shell
[root@web1 ~]# ab -c 2000 -n 2000 http://192.168.2.5/   //最后再次使用测试主机web1去访问2.5，发现已经成功突破1024的限制
```

\----------------------------------------------------------------------------------------------

### **解决集群主机过多而导致用户重复登陆网站的问题**

**在一个集群中，如果网站需要用户输入用户名和密码登陆之后才能继续访问，那么当用户登陆其中一台集群主机之后，随着继续访问页面，请求可能被代理服务器轮询到另外一台服务器上，那么对于另外一台服务器来说用户并没有登陆，想查看登陆之后的页面还需要再次登陆，这样集群主机越多需要客户重复登陆的次数就越多，想要解决该问题就要从Session与Cookies入手**

 

**Session：存储在服务器端，保存用户名、登陆状态等信息。**

**Cookies：由服务器下发给客户端，保存在客户端的一个文件里。**

 

#### **1，在web1与web2主机部署lnmp环境：**

```shell
yum -y install  mariadb  mariadb-server  mariadb-devel

yum -y install  php  php-mysql  php-fpm

[root@web1 ~]# systemctl start php-fpm

[root@web1 ~]# systemctl start mariadb

ss -ntulp | grep 3306

ss -ntulp | grep 9000
```

 

```shell
[root@proxy ~]# scp lnmp_soft.tar.gz 192.168.2.100:  //在proxy主机拷贝文件到web1

[root@web1 ~]# tar -xf lnmp_soft.tar.gz  //回web1释放文件

[root@web1 ~]# cd lnmp_soft/

[root@web1 lnmp_soft]# tar -xf nginx-1.17.6.tar.gz  //之后进行nginx部署工作

[root@web1 lnmp_soft]# cd nginx-1.17.6/

yum -y install  gcc  pcre-devel  openssl-devel  //安装依赖包

./configure

make

make install 
```

 

#### **2，修改nginx配置文件65~71行，实现动静分离**

```shell
  location ~ \.php$ {

      root      html;

      fastcgi_pass  127.0.0.1:9000;

      fastcgi_index  index.php;

    \#   fastcgi_param  SCRIPT_FILENAME  /scripts$fastcgi_script_name;

      include     fastcgi.conf;

    }
```

保存退出，关闭防火墙，开启nginx服务，并使用火狐浏览器测试

 

#### **3，在web1与web2主机访问测试页**

```shell
cd /root/lnmp_soft/php_scripts

tar -xf php-memcached-demo.tar.gz

cp -r php-memcached-demo/* /usr/local/nginx/html/
```

 

使用浏览器访问192.168.2.100/index.php

使用浏览器访问192.168.2.200/index.php

 

**排错**

**看不到动态页面，可能由于以下原因**

1， 关闭httpd服务

2， 防火墙

3， Php-fpm服务

4， 如果删除nginx重新安装需要杀死nginx进程

然后重新开启服务

5， 缺少依赖包  pcre-devel openssl-devel

6， 配置文件

 

#### **4，在proxy主机配置集群，注意该主机不能有动静分离的配置**

```shell
upstream web {

    server 192.168.2.100:80;

    server 192.168.2.200:80;

}

 

location / {

      proxy_pass http://web;

      root  html;
```

http://192.168.2.5/index.php //之后测试效果，不断刷新页面，会看到web1与web2的登录界面(需要提前在web1与web2的index.php与home.php页面进行标记)

然后将web1与web2的/var/lib/php/session目录中的所有session文件删除，然后再删除浏览器的历史记录(Cookies)，再次登录，发现必须登录两次才能成功。

\-----------------------------------------------------------------

**上述实验由于web1与web2都是在各自的/var/lib/php/session目录中存储session，所以造成客户需要重复登录，为了统一session存储的位置（该存储方式通常被称为session共享），需要安装专门的数据库工具**

###  session共享

#### **1，安装memcache数据库**

```shell
yum -y install memcached  //安装数据库工具

systemctl start memcached  //启动服务

yum -y install telnet  //安装远程登录工具，为了测试memcache
```

 

#### **2，连接测试**

```shell
telnet 127.0.0.1 11211   //使用远程工具连接到本机的11211端口，该端口就是memcached服务

set abc 0 100 3  //测试创建或者覆盖abc变量，0是不压缩数据，数据存储时间是100秒，存储3个字符

get abc  //获取变量abc的值

add abc 0 100 3  //仅仅创建，如果已经有abc变量则

无法覆盖

replace abc 0 100 3  //覆盖现有变量的数据

delete abc  //删除变量

flush_all  //清空所有数据

quit  //退出，通过以上命令可以证明memcached服务一切正常
```

 

#### **3，在web1与web2主机修改session存储的位置，实现session共享**

```shell
yum -y install php-pecl-memcache  //安装php与memcached服务关联的软件包

vim /etc/php-fpm.d/www.conf  //修改配置

php_value[session.save_handler] = memcache   //这里改成memcache

php_value[session.save_path] = tcp://192.168.2.5:11211  //session存储位置

systemctl  restart  php-fpm  //重启fpm服务，让上述配置生效
```

**所有服务器关闭selinux**  

最后清空浏览器的历史记录，再访问http://192.168.2.5/index.php仅仅登录一次即可成功



## 05：Tomcat服务器、Tomcat应用案例、Varnish代理服务器

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5CLINUXNSD_V01OPERATIONDAY05_003.png)

**使用tomcat搭建网站服务**

**由于tomcat的运行需要依赖java，要先安装jdk工具包**

### **1，配置java环境并拷贝tomcat程序到指定目录(该目录位置可以自定义)**

```shell
yum -y install java-1.8.0-openjdk   //首先安装java环境软件包

cd  ~/lnmp_soft

tar -xf apache-tomcat-8.0.30.tar.gz  //在lnmp_soft目录下释放tomcat软件包

cp -r apache-tomcat-8.0.30 /usr/local/tomcat

cd /usr/local/tomcat/  
```

 

**tomcat目录介绍**

bin 存放tomcat主要程序

logs 日志

conf 存放配置文件

work 存放动态网站(页面)被解析时的临时文件

webapps  存放网站页面

 

```shell
bin/startup.sh  //开启tomcat服务

bin/shutdown.sh  //关闭tomcat服务
```

 

### **2，运行前准备**

**由于tomcat运行需要random中有海量随机数，有时随机数不足会导致8005端口无法启动**

**解决方案一：**

```shell
mv /dev/random /dev/random.bak  //备份原有random文件

ln -s /dev/urandom /dev/random  //使用urandom创建软连接替代random即可

[root@web1 tomcat]# bin/shutdown.sh  //关闭tomcat

yum -y install psmisc 

killall java  //如果tomcat异常时就杀死java程序

ss -ntulp | grep java

[root@web1 tomcat]# bin/startup.sh  //重新开启tomcat服务

ss -ntulp | grep java  //查询8005端口是否开启，该端口在服务关闭时需要，如果没有启动则服务不能使用，另外还有8080端口是提供网站服务的端口，8009端口可以做内部测试使用，也可以连接其他网站服务，目前的实验不使用，但必须看到这些端口都开启才说明tomcat服务正常
```

 

**解决方案二：**

```shell
yum -y install rng-tools  //如果8005端口依然无法开启就安装该软件包

[root@web1 ~]# systemctl start rngd  //开启服务
```

 

### **3，测试tomcat服务**

```
http://192.168.2.100:8080/  //使用浏览器访问tomcat默认页，由于tomcat没有使用默认的80端口而是8080，所以地址后面不要忘记写
```

 

#### **测试tomcat自定义静态页面与动态页面**

```shell
vim webapps/ROOT/test.jsp   //编写基于java语言的动态页面

<html>

<body>

<center>

Now time is: <%=new java.util.Date()%>    //显示服务器当前时间

</center>

</body>

</html>

http://192.168.2.100:8080/test.jsp  //使用浏览器访问可以看到当前时间
```

 

\-------------------------------------------------------------------------------------------

#### **利用tomcat创建虚拟主机**

**回顾：**

**httpd的创建方法是写多个virtualhost**

```shell
<VirtualHost *:80>

	Servername [www.a.com](http://www.a.com)

	Documentroot /var/www/html

</virtualhost>
```

#### **nginx的创建方法是写多个server**

```shell
http {

	server {

	listen :80;

	server_name [www.a.com](http://www.a.com);

	root html;

	index index.html;

	}

}
```

 

**Tomcat的创建方法是写多个Host**

```shell
<Host name=www.a.com appbase=webapps>

</Host>
```

\----------------------------------------------

#### **在tomcat中创建虚拟主机实际操作**

```shell
[root@web1 tomcat]# vim conf/server.xml  //打开tomcat主配置文件，在122~124行添加以下内容

122  <Host name="www.b.com" appBase="web_b"   //name后面写域名，appbase后面写网站的页面存放目录，另外在后面第125行也就是默认的虚拟主机中的name由localhost修改为www.a.com

123  unpackWARs="true" autoDeploy="true">

124  </Host>
```

 

```shell
[root@web1 tomcat]# mkdir -p web_b/ROOT   //创建b网站的目录

echo "web_b/ROOT/index.html" > web_b/ROOT/index.html  //编写b网站默认页面

echo "web_a/ROOT/index.html" > webapps/ROOT/index.html  //编写a网站的默认页面

vim /etc/hosts  /修改本机hosts文件

192.168.2.100 www.a.com www.b.com www.c.com

curl www.b.com:8080   //测试

curl www.a.com:8080
```

 

如果用windows测试：

```shell
C:\Windows\System32\drivers\etc\hosts

192.168.2.100 www.a.com www.b.com www.c.com

使用浏览器访问 [www.a.com:8080](http://www.a.com:8080) 或者 www.b.com:8080
```

\-------------------------------------------------------------------

**另外，在虚拟主机中还有autoDeploy和unpackWARs其功能解释如下：**

**autoDeploy  //自动更新网站功能，有助于开发工程师**

**unpackWARs  自动解war包，通常开发工程师习惯将网站文件打成war包(类似tar包)上传到服务器，但是还需要解包很麻烦，但有了这个功能就可以自动解开**

**测试自动解war包功能：**

```shell
yum -y install java-1.8.0-openjdk-devel  //安装创建war包的工具

jar -cf xyz.war /var/log  //到/下使用jar命令创建war包，名字是xyz.war，内容是/var/log

mv xyz.war /usr/local/tomcat/web_b  //把war包扔到虚拟主机的网页目录下

ls /usr/local/tomcat/web_b  //查看b网站目录里面会自动解开xyz.war包，并产生xyz目录，前提是tomcat服务正常开启中
```

\------------------------------------------------------------------

#### **tomcat页面路径测试**

**默认情况下，tomcat网站页面的文件存放在webapps目录的ROOT下，如果需要自定义路径可以按以下几种方式进行配置**

**种类1:** 

在虚拟主机配置中添加Context path等内容当docBase为空时，访问页面会直接在web_b目录中

 ![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13464\wps1.jpg)

```shell
echo "web_b/test.html" > web_b/test.html  //创建测试页
```

重启tomcat服务

```
http://www.b.com:8080/test.html  //测试，看到的是web_b中的页面，而不是web_b/ROOT下
```

 

**种类2:** 

当docBase=”bbb”时，访问页面会在web_b/bbb目录中

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13464\wps2.jpg) 

```shell
[root@web1 tomcat]# mkdir web_b/bbb  创建测试目录

echo "web_b/bbb/index.html" > web_b/bbb/index.html  创建测试页面

重启tomcat服务

www.b.com:8080  访问测试，看到的是web_b/bbb中的页面
```

 

**种类3:** 

当docBase=”/b”时，访问页面会在/b目录中

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13464\wps3.jpg) 

```shell
[root@web1 tomcat]# mkdir /b  创建测试目录

[root@web1 tomcat]# echo " /b/index.html" > /b/index.html  创建测试页面

重启tomcat服务

www.b.com:8080  访问测试，看到的是/b中的页面
```

 

**种类4:** 

当context path=”/abc”时，docBase=”/b”时，访问页面www.b.com:8080/abc/ 会显示/b目录中的页面

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13464\wps4.jpg) 

```shell
重启tomcat服务

www.b.com:8080/abc/   访问测试，看到的是/b中的页面

www.b.com:8080  访问测试，看到的是web_b/ROOT中的页面

ss -ntulp | grep java  
```

**种类5:** 

当context path=”/abc”时，docBase=”bbb”时，访问页面www.b.com:8080/abc/ 会显示web_b/bbb/目录中的页面

<img src="file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13464\wps5.jpg" alt="img" style="zoom:150%;" /> 

```shell
重启tomcat服务

curl www.b.com:8080/abc/  访问测试，看到的是web_b/bbb/中的页面

curl www.b.com:8080  访问测试，看到的web_b/ROOT/中的页面

[root@web1 tomcat]# ss -ntulp | grep java  如果实验失败要先查询服务状态
```

\-------------------------------------------------

### **练习：**

下列需求如何实现？

访问www.b.com:8080  看到的是/usr/local/tomcat/abc/a中的内容

访问www.b.com:8080/abc/ 看到是/var/www/html中的内容

 

**答案：**

```shell
<Host name="www.b.com" appBase="abc"

unpackWARs="true" autoDeploy="true">

<Context path="" docBase="a" />

<Context path="/abc" docBase="/var/www/html" />

</Host>
```

\----------------------------------------------------

### **使用tomcat开启安全加密效果**

首先修改配置文件，添加下图内容

<img src="file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13464\wps6.jpg" alt="img" style="zoom:200%;" /> 

```shell
keytool -genkeypair -alias tomcat  -keyalg RSA -keystore /usr/local/to

mcat/keystore   //在创建秘钥对文件，命令输入完毕后，先输入两次123456的密码，然后回答问题，最后y确认，然后密码不用输入直接回车。-genkeypair是创建密钥对，-alias是别名，-keyalg是用什么算法，RSA是一种非对称加密算法，-keystore是密钥对文件的存储路径，如果忘记该敲什么内容可以用—help查询

重启tomcat 服务

ss -ntulp | grep java  可以看到8443端口

curl -k https://www.b.com:8443/  查看安全加密页面
```

\---------------------------------------------------------------

**为b网站虚拟主机添加日志**

**tomcat只为默认的虚拟主机添加了日志功能，如果新建的虚拟主机需要该功能就按下列方式配置：**

打开配置文件，添加日志功能<Valve  .....  />(该配置从默认的虚拟主机中复制即可，最后一页)，修改prefix日志名字，suffix日志后缀

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13464\wps7.jpg) 

之后保存退出，重启tomcat服务，然后访问几次b网站

```shell
tail -1 logs/web_b加tab键可以找到新日志并查看最后一行内容
```



## 06:版本控制、Git基础、Cit进阶、RPM打包

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5CLINUXNSD_V01OPERATIONDAY06_003.png)



### **使用Varnish加速Web**

**有时网站服务器搭建好了客户会因为距离较远而访问效果不好，出现这种情况就可以用varnish工具在距离客户比较近的地区搭建缓存服务器，然后客户访问缓存服务器即可，缓存服务器会从原始站点获得数据并缓存，随着被访问与被缓存的数据越来越多，客户的访问速度就可以加快了，但由于这种方式不是一般企业可以做到，通常有需求时可以去购买cdn （内容分发网络）服务。**

 

**以下实验仅用来感受该服务效果，了解理念即可**

#### **1，安装varnish服务**

首先使用web1主机开启httpd服务

```shell
[root@web1 ~]# ss -ntulp | grep :80   //可以先查询80端口是否被占用

killall nginx   //如果nginx占用就杀掉

[root@web1 ~]# systemctl start httpd  //仅仅启动httpd
```

在使用proxy测试web1的页面

```shell
[root@proxy ~]# curl 192.168.2.100

[root@proxy ~]# ss -ntulp | grep :80

[root@proxy ~]# killall nginx  //如果有服务占用80端口就杀死

[root@proxy ~]#cd  ~/ lnmp_soft

[root@proxy lnmp_soft]# tar -xf varnish-5.2.1.tar.gz

[root@proxy lnmp_soft]# cd varnish-5.2.1/

yum -y install gcc readline-devel pcre-devel python-docutils  //安装varnish所需依赖包

./configure

make

make install

useradd -s /sbin/nologin varnish   //创建varnish所需账户
```

 

#### **2，修改配置**

```shell
cp etc/example.vcl /usr/local/etc/default.vcl  //拷贝配置文件

vim /usr/local/etc/default.vcl  //修改配置文件17、18行

  .host = "192.168.2.100";  //原始服务器的ip

  .port = "80";					//原始服务器的端口号

varnishd  -f  /usr/local/etc/default.vcl  //指定配置文件路径并启动varnish服务
```

 

#### **3，测试效果**

```shell
[root@proxy varnish-5.2.1]# curl 192.168.2.5  #测试访问proxy的页面，可以看到原始服务器web1的内容
```

 

\------------------------------------------------------

### **版本管理工具：**

**svn 集中式用户使用该服务时，需要时刻与服务器保持在线状态，数据统一保存在svn服务器中**

**git 分布式  用户使用该服务时，不需要时刻与服务器保持在线状态，仅仅传递数据时需要联网，数据保存在git服务器与git客户端**

 

https://gitee.com/

https://github.com/

 

![img](file:///C:\Users\BJTT\AppData\Local\Temp\ksohtml13464\wps8.jpg) 

 

 

#### **使用git管理数据**

##### **1，基本操作**

首先在web1与web2安装git工具

```shell
[root@web1 ~]# yum -y install git

[root@web2 ~]# yum -y install git

[root@web1 ~]# mkdir /var/lib/git

[root@web1 ~]# git init /var/lib/git/project --bare  //创建空仓库，叫Project

[root@web2 ~]#git clone 192.168.2.100:/var/lib/git/project  //在客户机克隆服务器的仓库

[root@web2 ~]#cd  project  //进入仓库

[root@web2 project]# echo "web2_01" > web2_01.txt  //创建测试文件  

[root@web2 project]# git add .  //提交到暂存区

[root@web2 project]# git commit -m "web2_01.txt"  //将文件保存到仓库中，-m后面的内容是日志提示信息，首次保存会失败，按照下面2条命令输入邮箱和用户名即可

 git config --global user.email "you@example.com"

 git config --global user.name "Your Name"

[root@web2 project]# git commit -m "web2_01.txt"  再次提交文件保存到仓库中

[root@web2 project]#git push 将本地仓库中的数据推送到远程服务器

[root@web2 project]# git config --global push.default simple  配置使用习惯

[root@web2 project]#git push
```

 

**所有通过commit提交的记录都可以通过日志查看**

**git log  //查看完整日志**

**git log --pretty=oneline  //查看精简日志**

**git log --oneline  //查看最精简日志**

**git reflog  //看本机操作记录**

 

##### **2，head指针**

**如果需要还原到之前的版本(时间节点)，可以利用head指针对应日志记录中的随机字符串指向需要的版本**

```shell
[root@web2 project]# git log --oneline  //查看日志，开头的部分就是不同版本的随机字符串

[root@web2 project]# git  reset  xxxx  --hard  //回到过去的某个记录，
其中 xxxx是日志中显示的时间节点信息，要根据实际修改

[root@web2 project]# git reflog  //查看回复记录之后的日志记录，head@{0}代表当前所在版本位置
```

 

**回复到过去的时间节点，找回数据思路：**

1，	git log --oneline  查看日志，找到旧数据所在时间节点

2，	git  reset  xxxx  --hard  回到过去，xxxx是时间节点的记录

3，	把需要找回的数据，从仓库中拷贝到另外一个目录

4，	git  reset  xxxx  --hard  回到现在

5，	在之前的目录找回旧数据

 

\--------------------------------------------------------------

##### **3，git分支**

**当项目内容比较多时，可以在git中使用分支，不同分支的文件可以互不干扰而不用创建多个仓库**

```shell
[root@web2 project]# git branch  //查看当前分支，*是所在位置

[root@web2 project]# git branch hotfix  //创建hotfix分支

[root@web2 project]# git checkout hotfix  //切换到hotfix分支

[root@web2 project]# echo "hotfix_01" > hotfix_01.txt   //编写测试文件

[root@web2 project]# git add .   //提交到暂存区

[root@web2 project]# git commit -m "hotfix_01.txt"   //提交到仓库保持

[root@web2 project]# git checkout master  //切换到master分支

[root@web2 project]# echo "master_01" > master_01.txt   //编写测试文件

[root@web2 project]# git add .   //提交到暂存区

[root@web2 project]# git commit -m "hotfix_01.txt"  //提交到仓库保持

git merge hotfix   //把hotfix分支的文件合并到当前分支
```

 

**如果分别在不同分支，创建同名文件，内容不同，再进行合并时，会发生冲突，此时需要手工修改冲突文件，修改完之后，就可以解决冲突**

```shell
git checkout hotfix  //先切换到hotfix分支

echo abc > abc.txt  //创建文件

git add .  //提交到暂存区

git commit -m "abc.txt"  //提交到仓库保存

git checkout master  //再切换到主分支

echo xyz > abc.txt  //创建同名文件，但内容不同

git add .   //提交到暂存区

git commit -m "abc.txt"   //提交到仓库保存

git merge hotfix   //合并时会发生冲突，此时修改abc.txt文件之后即可解决冲突
```

 

**练习：把目前仓库删除**

**1，** **在web1重新创建仓库，名称自定义**

**2，** **在web2克隆仓库，并多次创建文件添加commit记录**

**3，** **将web2中的数据同步到web1服务器中**

 

\----------------------------------------------------------------------------

##### **配置ssh秘钥，实现无密码访问git服务器**

```shell
ssh-keygen -f /root/.ssh/id_rsa -N ''  //在客户端创建秘钥秘钥没有密码

ssh-copy-id 192.168.2.100  //传入服务器

git clone 192.168.2.100:/var/lib/git/abc  //克隆git服务器的仓库，已经无需密码

cd abc  //进入仓库

echo abc > abc.txt   //创建测试文件 

git add .  //提交到暂存区

git commit -m "abc"  //提交到仓库保存

git push  //推送到git服务器，也不需要密码了
```

**git服务的使用方式：**

**1，使用ssh方式，上次课程一直在用，这里不多描述**

**2，使用git协议**

Web1主机：

```shell
yum -y install git-daemon //安装git协议软件包

systemctl start git.socket  //开启服务

setenforce 0

vim /usr/lib/systemd/system/git@.service

[root@web1 ~]# vim /usr/lib/systemd/system/git@.service 修改git服务的配置，在第7行末尾加--enable=receive-pack选项，允许对仓库服务器写入数据，否则是只读

[root@web1 ~]# systemctl restart git.socket //开启服务

[root@web1 ~]# setenforce 0 //关闭selinux，(防火墙也关)

[root@web1 ~]#chmod -R 777 /var/lib/git/abc //开放仓库权限

[root@web2 ~]#rm -rf project  //删除原有仓库

[root@web2 ~]#git clone git://192.168.2.100/abc //使用git协议从新克隆

[root@web2 ~]#cd abc //进入仓库，可以正常使用仓库

[root@web2 abc]# echo 123 > abc //创建测试文件

[root@web2 abc]# git add .  //提交到暂存区

[root@web2 abc]# git commit -m "abc" //提交到仓库

[root@web2 project]# git push //推送到远程服务器
```

 

**3，使用http访问git(只读)**

```shell
[root@web1 ~]# yum -y install httpd gitweb 安装软件包

[root@web1 ~]# vim +10 /etc/gitweb.conf 进入配置文件的第10行删除注释即可，其中/var/lib/git路径必须是仓库的上级目录，如果不一致要修改

[root@web1 ~]# systemctl restart httpd 启动网站服务

关闭selinux与防火墙

使用火狐访问http://192.168.2.100/git/  
```

\------------------------------------------------------

### **将源码包转换为rpm包**

**rpm**  **使用便利**  **更新速度慢**

**源码**  **使用繁琐**  **更新速度快**

```shell
yum -y install rpm-build //安装rpm制作工具

[root@web1 ~]# rpmbuild -ba nginx.spec  //制作rpm包，但是没有配置文件会报错，报错也需要敲，会产生所需的目录

[root@web1 ~]#vim rpmbuild/SPECS/nginx.spec  //创建配置文件，并按下描述修改

Name:nginx   软件包名

Version:1.17.6     软件包版本号

Release:1          发布rpm包的版本号

Summary:test  简单描述

\#Group:

License:GPL        授权协议

URL:www.abc.com  网站地址

Source0:nginx-1.17.6.tar.gz  源码包完整文件名

\#BuildRequires: 

\#Requires:

%description  详细描述

test test test

 
%post             可选项，分配额外执行的任务

useradd nginx  安装rpm包同时做哪些操作

yum -y install openssl-devel pcre-devel

 
%prep

%setup -q

%build

./configure  --user=nginx  修改%

make %{?_smp_mflags}

%install

make install DESTDIR=%{buildroot}

%files

%doc

/usr/local/nginx/*            定义打包的文件所在目录

%changelog


cp lnmp_soft/nginx-1.17.6.tar.gz  rpmbuild/SOURCES/

rpmbuild -ba rpmbuild/SPECS/nginx.spec //制作rpm包

rpm -qpi rpmbuild/RPMS/x86_64/nginx-1.17.6-1.x86_64.rpm //查信息

rpm -ivh rpmbuild/RPMS/x86_64/nginx-1.17.6-1.x86_64.rpm //装包
```



## 07：VPN服务器、systemd

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5CLINUXNSD_V01OPERATIONDAY07_003.png)

### **vpn** **虚拟专用网络**

#### 方式一：使用gre技术实现vpn(两台linux)

Web1主机配置：

```shell
modprobe ip_gre  //在内核中开启gre模块功能

[root@web1 ~]# lsmod | grep ip_gre //查询

[root@web1 ~]#ip tunnel add tun0 mode gre remote 192.168.2.200 local 192.168.2.100 //创建vpn隧道，名字叫tun0，使用gre技术，与2.200连接，自身ip是2.100

[root@web1 ~]#ip link show //查看

[root@web1 ~]#ip addr add 10.10.10.10/24 peer 10.10.10.5/24 dev tun0 //在tun0隧道中使用私有ip地址，本机是10.10，远程主机是10.5

[root@web1 ~]# ip addr show //查看

[root@web1 ~]# ip link set tun0 up //激活之前的配置

[root@web1 ~]# ip tunnel del tun0 //如果配置错误，要删除重来
```

 

web2主机也按照上述配置创建vpn，但是ip地址要反着写

 

测试：

selinux都要关闭，相互ping 10网段的ip

 

\-----------------------------------------------------------------------

#### 方式二：搭建pptp vpn

```shell
cd ~/lnmp_soft/vpn

yum -y install pptpd-1.4.0-2.el7.x86_64.rpm

[root@web1 vpn]# vim /etc/pptpd.conf 修改102、103行

localip 192.168.2.100   本机ip

remoteip 10.10.10.10-18  客户机分配的ip范围

[root@web1 vpn]# vim /etc/ppp/options.pptpd  在66行定义用户的dns服务器

地址

ms-dns 8.8.8.8

[root@web1 vpn]# vim /etc/ppp/chap-secrets

tom * 123456 *


systemctl restart pptpd

[root@web1 vpn]# ss -ntulp | grep pptpd
```

 

之后使用windows系统连接服务器

用户名tom下面的密码是123456

![image-20201023173350042](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20201023173350042.png)

![image-20201023173356745](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20201023173356745.png)

#### 方式三：L2TP+IPSec

```shell
[root@web1 vpn]# yum -y install libreswan

[root@web1 vpn]# cp myipsec.conf /etc/ipsec.d/

[root@web1 vpn]# vim /etc/ipsec.d/myipsec.conf

修改第16vim行为本机ip

left=192.168.2.100

[root@web1 vpn]# vim /etc/ipsec.secrets

192.168.2.100  %any:  PSK "randpass"

2.100是本机ip，%any:是任何客户端可以连接本机，PSK预共享

秘钥，密码是randpass

[root@web1 vpn]# yum -y install xl2tpd-1.3.8-2.el7.x86_64.rpm

[root@web1 vpn]# vim /etc/xl2tpd/xl2tpd.conf  //修改32、33行

ip range = 9.9.9.9-9.9.9.18 //分配给客户端的IP池

local ip = 192.168.2.100 

[root@web1 vpn]# vim /etc/ppp/options.xl2tpd  //修改配置，把

10与16行注释掉，21行删除注释与空格

[root@web1 vpn]# vim /etc/ppp/chap-secrets //如果添加账户，修改

该文件

tom * 123456 *

[root@web1 vpn]# systemctl start ipsec

[root@web1 vpn]# systemctl start xl2tpd

 ss -ntulp | grep xl2tpd

 ss -ntulp | grep :500
```

 

然后使用Windows链接，预共享密钥使用randpass，后面的用

户名和密码使用tom的即可

![image-20201023173437488](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20201023173437488.png)

\---------------------------------------------------------------------

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5CLINUXNSD_V01OPERATIONDAY07_033.png)

### systemd

```shell
vim /usr/lib/systemd/system/crond.service

复制内容

vim /usr/lib/systemd/system/test.service

粘贴到新文件中

[Unit]

Description=test  //描述

After=time-sync.target //在哪个服务启动之后再启动test服务

[Service]

ExecStart=/opt/test.sh //如果执行了systemctl start test之后就运

行/opt/test.sh程序，提前要设置x权限

ExecReload=/bin/kill -HUP $MAINPID //如果执行了systemctl reload 

test 之后，就利用kill程序发送不停止服务仅仅更新配置的信号，其

效果相当于重新加载配置

KillMode=process //如果关闭服务，就停止主进程，比如在输入systemctl stop test 时。

[Install]

WantedBy=multi-user.target  //支持开机自启


```

```
systemctl start test

systemctl status test
```

\-------------------------------------------------------------

#### 配置systemctl管理nginx服务

```shell
cd /usr/lib/systemd/system/

[root@web1 system]# cp httpd.service nginx.service

[root@web1 system]#vim nginx.service

[Unit]

Description=nginx  描述

After=network.target remote-fs.target nss-lookup.target  在网络服务、远程文件系统服务、域名相关服务启动之后再开启nginx

[Service]

Type=forking  由于nginx是多进程服务，要设置forking

ExecStart=/usr/local/nginx/sbin/nginx 当执行systemctl start nginx时，所执行的命令

ExecReload=/usr/local/nginx/sbin/nginx -s reload 当执行systemctl reload nginx时，所执行的命令

ExecStop=/bin/kill -s QUIT ${MAINPID} 当执行systemctl stop nginx时，所执行的命令,-s QUIT是发送退出信号，${MAINPID}是nginx的主进程号

[Install]

WantedBy=multi-user.target   支持开机自启
```

\----------------------------------------------

```shell
[root@web1 system]# systemctl start nginx  开启nginx

如果不好用就重启服务器

[root@web1 system]# systemctl start nginx 开启

[root@web1 system]# systemctl status nginx  查看状态
```

# 第二阶段月考

1、【单选题】
(单选题)启动nginx程序时，其命令选项（    ）可用于查看版本信息？
A.-s 
B.-V 
C.-t 
D.-c 
【正确答案】B
【答题时间】2020-10-29 07:02:37
【答案解析】-V选项用于查看版本信息以及编译选项的信息

2、【单选题】
(单选题)版本控制软件的核心任务是（    ）
A.协作编辑和数据共享 
B.升级软件 
C.软件测试 
D.木马查杀 
【正确答案】A
【答题时间】2020-10-29 07:02:37
【答案解析】版本控制的核心目的是多人协作编辑代码、共享代码

3、【单选题】
使用git命令查看版本库中代码的修改历史，需要的具体指令是什么 （ ）？
A.his 
B.info 
C.history 
D.log 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】git log可以查看版本控制的修改历史

4、【单选题】
(单选题)若执行 head -5 /etc/passwd | awk '{i++}END{print i}'  操作，
输出的结果是（  ）。
A.没有值 
B.0 
C.5 
D.1 
【正确答案】C
【答题时间】2020-10-29 07:02:37
【答案解析】awk读取一行执行一次i++，读取5行后i的值为5

5、【单选题】
(单选题)Linux操作系统对能够打开的最大文件数量进行了限制，默认为1024，
通过哪个命令可以调整这个限制（    ）？
A.climit 
B.limit 
C.glimit 
D.ulimit 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】ulimit -Hn可以修改最大文件数量


6、【单选题】
(单选题)编写完shell脚本/opt/test.sh之后，不能直接使用的执行方法是？
A.. /opt/test.sh 
B.source /opt/test.sh 
C./opt/test.sh 
D.bash /opt/test.sh 
【正确答案】C
【答题时间】2020-10-29 07:02:37
【答案解析】使用相对或者绝对路径执行脚本前需要添加x权限

7、【单选题】
(单选题)在命令行中执行如下命令 
#sed  -i  '1~2d' a.txt  
关于最后的执行结果，以下描述正确的是（  ）。
A.删除文件中的第1行和第2行 
B.删除文件中的前2行 
C.删除文件中的奇数行 
D.删除文件中的第2行 
【正确答案】C
【答题时间】2020-10-29 07:02:37
【答案解析】sed使用行定位操作对象时，1~2表示1，3，5，7…
2是步长

8、【单选题】
(单选题)若执行如下命令 
x=10;unset x;y=${x:-30};echo $y  
则最后的输出结果是（  ）。
A.无值 
B.10 
C.30 
D.0 
【正确答案】C
【答题时间】2020-10-29 07:02:37
【答案解析】${x:-30}这个是看x有没有值，有值就返回x的值，没有就返回30

9、【单选题】
(单选题)在命令行中执行如下命令： 
#sed '2d' a.txt 
关于最后的执行结果，以下描述正确的是（  ）
A.删除文件中的第1~2行 
B.共删除1行 
C.从文件的第2行开始删除行 
D.命令语法格式错误 
【正确答案】B
【答题时间】2020-10-29 07:02:37
【答案解析】2d代表删除第2行

10、【单选题】
(单选题)在ansible中可以通过什么关键词实现循环调用模块？
A.case 
B.while 
C.for 
D.loop 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】

11、【单选题】
(单选题)grep "[^0-9]"可以搜索到什么内容？
A.可以搜索含有数字的行 
B.不可以搜索到数字0和9 
C.可以搜索含有数字之外内容的行 
D.可以搜索到数字0和9 
【正确答案】C
【答题时间】2020-10-29 07:02:37
【答案解析】[ ] 在正则表达式中代表集合，内加^代表取反查找　

12、【单选题】
(单选题)Tomcat中（     ）负责将用户的请求调度给具体的Host虚拟主机
A.Engine 
B.server 
C.service 
D.host 
【正确答案】A
【答题时间】2020-10-29 07:02:37
【答案解析】所有的host都在Engine中，Engine是所有host的调度器，
根据用户请求的不同域名调度给具体的host

13、【单选题】
(单选题)Shell脚本中，使用什么语句可以直接退出脚本（  ）？
A.kill 
B.q 
C.quit 
D.exit 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】break中断整个循环，continue中断当前一次循环，exit中断整个脚本

14、【单选题】
(单选题)若执行如下命令 
#head  -5  /etc/passwd  |  awk -F: 'END{print NR,NF}'   
则最后输出的结果是（  ）。
A.1   7 
B.4   7 
C.3   7 
D.5   7 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】awk的END{}指令仅在读取完文件后才执行，所以NR当前行的
行号为5，NF为列共7列

15、【单选题】
(单选题)awk '$4~/test/ && $3==100'的含义是？
A.找出第4列包含test或第3列等于100的行 
B.找出第4列等于test并且第3列等于100的行 
C.找出第4列等于test或第3列等于100的行 
D.找出第4列包含test并且第3列等于100的行 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】在awk使各种条件进行内容匹配的过程中~代表包含，&&代表并且，==代表等于

16、【单选题】
(单选题)命令行如下命令：
x=10;y=${x:-30};echo $y，其输出结果是什么（ ）？
A.无值 
B.0 
C.30 
D.10 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】${x:-30}这个是看x有没有值，有值就返回x的值，没有就
返回30


17、【单选题】
(单选题)执行ls -l /opt/test.txt 命令后显示的结果是
---------- 1 root root 33139 12-11 10:43 /opt/test.txt
则以下哪条命令会显示ok ？
A.[root@svr5 ~]# [ -r "/opt/test.txt" ] || echo "ok" && echo "no" 
B.[root@svr5 ~]# [ -x "/opt/test.txt" ] && echo "ok" || echo "no" 
C.[toor@svr5 ~]$ [ -r "/opt/test.txt" ] && echo "ok" || echo "no" 
D.[root@svr5 ~]# [ -r "/opt/test.txt" ] && echo "ok" || echo "no" 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】读写权限对root无限制

18、【单选题】
(单选题)使用sed修改test.txt可以实现永久效果的是？
A.sed -i 's/a/b/' test.txt 
B.sed -n 's/a/b/' test.txt 
C.sed -r 's/a/b/' test.txt 
D.sed -F 's/a/b/' test.txt 
【正确答案】A
【答题时间】2020-10-29 07:02:37
【答案解析】在sed中-i选项可以修改并保存入文件

19、【单选题】
(单选题)使用test进行条件判断，测试两个数字的关系时，小于用（  ）表示。
A.-ge 
B.-gt 
C.-eq 
D.-lt 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】-lt是小于等于，-gt是大于，-ge是大于等于，-eq是等于

20、【单选题】
在memcached服务器写数据的指令是什么（）？
A.new
B.write
C.set
D.flush
【正确答案】C
【答题时间】2020-10-29 07:02:37
【答案解析】set写数据，get查数据。

21、【单选题】
(单选题)使用test进行条件判断，测试两个数字的关系时，大于或等于用（  ）表示。
A.-gt 
B.-le 
C.-eq 
D.-ge 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】-le是小于等于，-gt是大于，-ge是大于等于，-eq是等于

22、【单选题】
(单选题)Shell脚本中可以进行小数运算的命令工具是（   ）？
A.ac 
B.bc 
C.gc 
D.tc 
【正确答案】B
【答题时间】2020-10-29 07:02:37
【答案解析】bc命令支持小数运算

23、【单选题】
(单选题)Shell脚本中使用哪个命令可以对数据进行排序（  ）？
A.more 
B.uniq 
C.sed 
D.sort  
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】Linux中sort命令可以将数据排序

24、【单选题】
(单选题)memcached服务默认监听的端口是（　  ）
A.11211 
B.11221 
C.22121 
D.22112 
【正确答案】A
【答题时间】2020-10-29 07:02:37
【答案解析】memcached默认端口为11211

25、【单选题】
(单选题)使用awk –F[/b] '{print $5}' 处理一行文档root:x:0:0:root:/root:/bin/bash则显示？
A.输出结果为空 
B.ash 
C.bin 
D.root 
【正确答案】A
【答题时间】2020-10-29 07:02:37
【答案解析】/与b都成为分隔符的情况下，如果连续出现则之间也算一列，内容为空

26、【单选题】
(单选题)使用（    ）工具可以对Web服务器进行压力测试
A.ab 
B.web 
C.press 
D.test 
【正确答案】A
【答题时间】2020-10-29 07:02:37
【答案解析】对web进行压力测试的软件很多，ab是其中之一

27、【单选题】
(单选题)以下（    ）选项可以重新加载nginx配置文件？
A.stop 
B.reload 
C.start 
D.restart 
【正确答案】B
【答题时间】2020-10-29 07:02:37
【答案解析】nginx -s reload

28、【单选题】
使用（ ）命令可以创建git版本仓库？
A.svnadmin
B.svncreate
C.init
D.svn
【正确答案】C
【答题时间】2020-10-29 07:02:37
【答案解析】git init /var/git/xyz可以创建仓库


29、【单选题】
(单选题)使用stty –echo命令后，以下错误的是？
A.stty echo可以恢复正常 
B.敲击任何按键将无任何输出 
C.不影响其他命令的执行结果 
D.仅输入命令时无输出，但执行命令后可以看到结果 
【正确答案】B
【答题时间】2020-10-29 07:02:37
【答案解析】输入命令后按回车键可以看到输出


30、【单选题】
(单选题)Varnish代理Web服务器一般会将端口修改为什么（   ）？
A.8000 
B.6081 
C.80 
D.65535 
【正确答案】C
【答题时间】2020-10-29 07:02:37
【答案解析】代理服务器一般会将端口修改为web的80端口

31、【单选题】
(单选题)关于命令sed -n '/bash$/!p' /etc/passwd的执行结果，以下描述正确的是（  ）。
A.查看解释器中含有bash字样的用户信息 
B.查看不使用bash的用户信息 
C.查看所有信息 
D.查看使用bash的用户信息 
【正确答案】B
【答题时间】2020-10-29 07:02:37
【答案解析】/ bash$/是匹配的正则表达式，p是输出，加！代表取反

32、【单选题】
(单选题)在Shell脚本中，若要屏蔽终端的输出默认显示功能，可以执行（  ）命令？
A.stty -echo 
B.stty echo 
C.-echo 
D.set  tty   -echo 
【正确答案】A
【答题时间】2020-10-29 07:02:37
【答案解析】read -p默认读取的密码为明文，通过stty -echo可以防止密码输出

33、【单选题】
(单选题)Shell脚本中使用，什么命令可以取消一个已经定义的变量(    )？
A.unset 变量名 
B.clear 变量名 
C.delete 变量名 
D.set 变量名 
【正确答案】A
【答题时间】2020-10-29 07:02:37
【答案解析】取消变量可以使用unset命令

34、【单选题】
(单选题)Linux命令行中，对多个命令进行逻辑分隔时，仅前一个命令成功才执行
下一个命令，应该使用什么分隔符（  ）？
A.% 
B.& 
C.&& 
D.| 
【正确答案】C
【答题时间】2020-10-29 07:02:37
【答案解析】&&仅前一个命令成功才执行后一个命令
||仅前一个命令失败才执行后一个命令

35、【单选题】
(单选题)若执行seq 70 | awk '$1%3==0 && $1~/3/'操作，输出的结果是?
A.70以内包含3的数字 
B.70以内能整除3或包含3的数字 
C.70以内能整除3并且不包含3的数字 
D.70以内能整除3并且包含3的数字 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】awk中可以使用运算当做匹配条件，%代表取余数，~代表包含，&&代表并且，==代表等于

36、【单选题】
(单选题)使用什么（  　）指令可以清空memcached数据库中的所有数据。
A.delete_all 
B.flush_all 
C.flush 
D.delete 
【正确答案】B
【答题时间】2020-10-29 07:02:37
【答案解析】执行flush_all命令可以清空所有memcached数据

37、【单选题】
将git版本仓库中的代码下载到本地副本的指令是（ ）
A.import 
B.download 
C.upload 
D.clone
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】git clone URL

38、【单选题】
(单选题) 如何查看119除以6的余数？
A.echo $[119/6] 
B.echo $(()119/6) 
C.let 119%6 
D.expr 119 % 6 
【正确答案】D
【答题时间】2020-10-29 07:02:37
【答案解析】取余的运算符号是%，let不会显示运算结果　

39、【单选题】
(单选题)shell中的if语句不可以实现？
A.单分支 
B.循环 
C.双分支 
D.多分支 
【正确答案】B
【答题时间】2020-10-29 07:02:37
【答案解析】for与while才可以实现循环

40、【单选题】
(单选题)以下哪个选项（  ）可以删除文件中所有包含数字的行？
A.sed  -i  '/[0-9]/d'  a.txt 
B.sed  -i  '0-9d'  a.txt 
C.sed  -i  '/0-9/d'  a.txt 
D.sed  -i  '[0-9]d'  a.txt 
【正确答案】A
【答题时间】2020-10-29 07:02:37
【答案解析】正则[0-9]代表任意数字

41、【多选题】
(多选题)目前支持JAVA的Web服务器有哪些（   ）
A.Jboss 
B.Weblogic 
C.Websphere 
D.Tomcat 
【正确答案】A,B,C,D
【答题时间】2020-10-29 07:02:37
【答案解析】Tomcat（apache），JBoss（Redhat），Websphere（IBM），Weblogic（Oracle）

42、【多选题】
(多选题) 已知tomcat配置文件的一个虚拟主机配置如下，描述正确的是？
<Host name="www.a.com"  appBase="a"
            unpackWARs="true" autoDeploy="true">
        <Context path="/test"  docBase="/var/www/html"  />
</Host>
A.访问www.a.com:8080/test时会显示/var/www/html目录下页面 
B.访问www.a.com:8080/test时会显示/test目录下页面 
C.访问www.a.com:8080时会显示a目录下页面 
D.访问www.a.com:8080时会显示a/ROOT目录下页面 
【正确答案】A,D
【答题时间】2020-10-29 07:02:37
【答案解析】

43、【多选题】
(多选题)如下哪条命令（  ），可以对变量i进行自加2的操作。
A.let ++i 
B.let i+=2 
C.let i=i+2 
D.let i++  
【正确答案】B,C
【答题时间】2020-10-29 07:02:37
【答案解析】let i+=2是let i=i+2的简写，两者都支持自加2

44、【多选题】
(多选题)sed操作描述正确的是？
A.sed '/^$/d'  可以删除所有空行 
B.sed '$=d' 删除文档的最后一行 
C.sed '/^root/!d' 可以删除以root开头之外的行 
D.sed '$d' 删除文档的最后一行 
【正确答案】A,C,D
【答题时间】2020-10-29 07:02:37
【答案解析】d在sed 中是删除行的指令，加!代表取反

45、【多选题】
(多选题)常见的版本控制软件有哪些（    ）？
A.git 
B.Subversion 
C.version 
D.soft 
【正确答案】A,B
【答题时间】2020-10-29 07:02:37
【答案解析】svn与git都是目前主流的版本控制软件

46、【多选题】
(多选题)awk命令支持有条件地执行某些指令，仅当条件满足时才执行{}中的指令，awk支持如下哪些判断条件(    )？
A.文件大小判断 
B.正则判断 
C.数字判断 
D.字符判断 
【正确答案】B,C,D
【答题时间】2020-10-29 07:02:37
【答案解析】awk支持==,!=,>,>=,<,<=对字符数字判断，以及//正则判断

47、【多选题】
(多选题)Varnish支持将缓存数据存储在哪些设备（   ）？
A.内存 
B.硬盘 
C.CPU一级缓存 
D.显存 
【正确答案】A,B
【答题时间】2020-10-29 07:02:37
【答案解析】Varnish既可以将数据存硬盘也可以将缓存存内存中

48、【多选题】
(多选题)Shell脚本中使用如下哪些语句可以实现循环功能（  ）？
A.if 
B.while 
C.for 
D.case 
【正确答案】B,C
【答题时间】2020-10-29 07:02:37
【答案解析】在shell脚本中可以使用for或while执行循环


49、【多选题】
(多选题)客户端可以通过哪些方式访问git版本库（   ）？
A.通过FTP共享 
B.通过http服务 
C.通过本地访问 
D.通过git服务 
【正确答案】B,C,D
【答题时间】2020-10-29 07:02:37
【答案解析】git可以通过本地、git服务器、http服务器方式访问

50、【多选题】
(多选题)下列关于Shell脚本中的if判断语句，说法正确的是（ ）？
A.仅支持单分支条件判断 
B.支持单分支条件判断 
C.不支持多分支条件判断 
D.支持多分支条件判断 
【正确答案】B,D
【答题时间】2020-10-29 07:02:37
【答案解析】shell的if判断支持单分支、双分支、多分支判断

# AUTOMATION

## 01: ansible基础、Ansible ad-hoc

### 1 案例1：部署Ansible

#### 1.1 问题

本案例要求先快速搭建好一个Ansible平台，并测试环境，要求如下：

- 创建实验主机（控制端和被控制端）
- 配置SSH实验环境
- 安装Ansible自动化软件
- 修改Ansible配置

#### 1.2 方案

准备如表-1所示的实验环境，操作系统为RHEL8，配置主机名称、IP地址、YUM源。

表-1 主机列表

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable00124)

ansible原理：

控制端主机自带很多模块（模块就是脚本）；

ansible通过ssh远程被管理主机，将控制端的模块（脚本）或命令传输到被管理主机；

在被管理端主机执行模块（脚本）或命令，执行不同的模块或命令可以实现不同的功能；

最后ansible退出ssh远程。

绝大多数模块（脚本）都需要参数才能执行成功！！！类似于shell脚本的位置变量！

拓扑结构如图-1所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00123)

图-1

提醒：全天的实验不需要死记硬背每个模块的每个参数，所有参数都可以查看帮助！

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：准备基础环境

控制节点要求：

- 域名解析（为了方便后期操作，可以不做）
- 配置SSH密钥（ansible是基于ssh实现远程控制）
- 安装Ansible软件

###### 1）Control控制节点

修改/etc/hosts，在文件中手动添加如下内容，修改该文件的目的是做域名解析。

```shell
[root@control ~]# vim  /etc/hosts        #修改文件，手动添加如下内容（不要删除文件原来的内容）
192.168.4.253    control    
192.168.4.11    node1    
192.168.4.12    node2    
192.168.4.13    node3    
192.168.4.14    node4    
192.168.4.15    node5
```

如何验证？

```shell
[root@control ~]# ping  node1               #可以使用ping命令依次ping所有域名    
```

配置SSH密钥实现免密码登录（非常重要）

Ansible是基于SSH远程的原理实现远程控制，如果控制端主机无法免密登录被管理端主机，后续的所有试验都会失败！！

```shell
[root@control ~]#  ssh-keygen        #生成ssh密钥
[root@control ~]#  for i in node1 node2 node3 node4 node5
dossh-copy-id   $i 
done
#拷贝密钥到远程主机#提示：拷贝密钥到远程主机时需要输入对方电脑的账户密码才可以！！#拷贝密钥到node1就需要输入node1对应账户的密码，拷贝密钥到node2就需要输入node2对应的密码
```

如何验证？

警告：如果有任何一台主机远程还需要密码，就不要往下继续操作，后面实验都会失败！！！

```shell
[root@control ~]# ssh  node1            #使用ssh命令依次远程所有主机都可以免密码登录
[root@node1 ~]# exit          #退出ssh远程登录 
```

###### 2)部署Ansible软件（仅Control主机操作，软件包在ansible_soft目录）。

```shell
[root@control ~]# tar -xf   ansible_soft.tar.gz
[root@control ~]# cd ansible_soft
[root@control ansible_soft]# dnf  -y  install   *
```

被控制节点要求：

- Ansible默认通过SSH协议管理机器
- 被管理主机要开启SSH服务，并允许控制主机登录
- 被管理主机需要安装有Python

##### 步骤二：修改配置文件

主配置文件说明：

主配置文件ansible.cfg（主配置文件的内容可以参考/etc/ansible/ansible.cfg）

ansible配置文件查找顺序

首先检测ANSIBLE_CONFIG变量定义的配置文件（默认没有这个变量）

其次检查当前目录下的./ansible.cfg文件

再次检查当前用户家目录下~/ansible.cfg文件

最后检查/etc/ansible/ansible.cfg文件

###### 1) 修改主配置文件。

```shell
[root@control ~]# mkdir  ~/ansible
[root@control ~]# vim  ~/ansible/ansible.cfg
[defaults]
inventory = ~/ansible/inventory            
#主机清单配置文件（inventory可以是任意文件名），英语词汇：inventory（清单、财产清单）
#forks = 5          #ssh并发数量
#ask_pass = True        #使用密钥还是密码远程，True代表使用密码
#host_key_checking = False      #是否校验密钥（第一次ssh时是否提示yes/no）
```

###### 2) 修改主机清单文件（清单文件名必须与主配置文件inventory定义的一致）。

```shell
[root@control ~]# vim  ~/ansible/inventory
[test]        #定义主机组（组名称任意）
node1         #定义组中的具体主机，组中包括一台主机node1
[proxy]         #定义主机组（组名称任意），英语词汇：proxy（代理人，委托人）
node2          #proxy组中包括一台主机node2
[webserver]
node[3:4]        #这里的node[3:4]等同于node3和node4
[database]
node5
[cluster:children]      #嵌套组（children为关键字），不需要也可以不创建嵌套组
webserver            #嵌套组可以在组中包含其他组
database
```



### 2 案例2：Ansible ad-hoc应用一

#### 2.1 问题

沿用练习一，练习Ansible ad-hoc具体应用，要求如下：

- 测试主机列表中的主机是否可以ping通
- 查看被管理主机的服务器信息（如时间、版本、内存等）
- 学习ansible-doc命令的用法
- 测试command与shell模块的区别
- 使用script模块在远程主机执行脚本（装软件包、启服务）

#### 2.2 方案

Ansible ad-hoc是一种通过命令行批量管理的方式，命令基本格式如下：

格式：ansible 主机集合 -m 模块名 -a "参数"

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：测试环境

###### 1）查看主机列表

```shell
[root@control ~]# cd  ~/ansible          #非常重要
[root@control ansible]# ansible  all  --list-hosts           #查看所有主机列表# --list-hosts是ansible这个命令的固定选项，如同ls -a一样（-a是ls命令的固定选项）#英语词汇：list（列表，清单）、host（主机、主办、主人）
```

###### 2) 测试远程主机是否能ping通。

当需要远程多个主机或者多个组时，中间使用逗号分隔！！！

```shell
[root@control ansible]# ansible  node1  -m  ping              #调用ping模块
[root@control ansible]# ansible  node1,webserver  -m  ping
```

常见报错（有问题可以参考，没问题可以忽略）：

```shell
node1 | UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: Permission denied (publickey,gssapi-keyex,gssapi-with-mic,password).", "unreachable": true}问题分析：英语词汇：Failed（失败），connect（连接），to（到），host（主机），via（通过）permission（权限），denied（被拒绝）Failed to connect to host via ssh（通过ssh远程连接到主机失败）Permission denied（因为无法连接，所以报错说权限被拒绝）解决办法：手动ssh其他主机（如node1），看看是否可以实现免密码登录。           
Ansible的原理是基于ssh远程管理，如果无法实现免密码登录，后面的实验无法成功！           
如何实现免密码登录，可以参考案例上面的命令，或者第一阶段知识。
```

提示：该模块虽然叫ping，但是它不会发送任何ICMP协议的ping数据包，控制端主机仅仅是ssh远程被管理端主机，检查其是否有python环境，能顺利远程并且有Python环境就会返回正确的提示信息，否则报错。拓扑如图-2所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00122)

图-2

###### 3）快速入门。

模块就是脚本（多数为Python脚本），多数脚本都支持参数，默认模块为command。

```shell
[root@control ansible]# ansible  node1  -m  command  -a   "uptime"     #查看CPU负载
[root@control ansible]# ansible  node1  -m command -a  "uname -r"      #查看内核版本
[root@control ansible]# ansible  node1   -a   "ip a s"                  #查看网卡信息
[root@control ansible]# ansible  all   -a   "date"                      #查看时间
```

拓扑如图-3所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00121)

图-3

通过ansible-doc获取帮助。

```shell
[root@control ansible]# ansible-doc  -l      #列出所有模块
[root@control ansible]# ansible-doc -l | grep yum      #在所有模块中过滤关键词
[root@control ansible]# ansible-doc yum        #查看模块帮助
```

###### 4）Shell模块。

command和shell模块的区别，command不支持bash的特性（bash有哪些特性可以参考Shell课程第一天的PPT），如管道和重定向等功能，但是shell模块可以支持。

不可以使用shell模块执行交互命令，如vim、top等。

```shell
[root@control ansible]# ansible test -m command -a "ps | wc -l"      #报错
[root@control ansible]# ansible test -m command -a  "ls &"        #报错
[root@control ansible]# ansible test -m shell -a  "ps aux | wc -l"       #进程数量
[root@control ansible]# ansible test -m shell -a  "who"                   #登陆信息
[root@control ansible]# ansible test -m shell -a  "touch /tmp/txt.txt"  #使用shell模块创建文件会有Warning警告提示，正常！！！
```

5）script模块

script模块会把-a后面的脚本拷贝到被管理端主机，然后执行这个脚本。

```shell
[root@control ansible]# vim  ~/ansible/test.sh  
#!/bin/bash
dnf -y install httpd
systemctl start httpd
[root@control ansible]# ansible  test  -m script  -a  "./test.sh"    #test是主机组的名称，-m调用script模块，-a后面的./test.sh是上面创建脚本的相对路径和文件名#./是当前目录的意思，在当前目录下有个脚本叫test.sh
```

拓扑如图-4所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00120)

图-4

如何验证？

因为ansible远程的是node1，所以打开node1这台电脑，查看下是否安装了httpd软件、是否启动了服务。

```shell
[root@node1 ~]# rpm -q  httpd
[root@node1 ~]# systemctl  status  httpd
```

### 3 案例3：Ansible ad-hoc应用二

#### 3.1 问题

沿用练习二，继续练习Ansible ad-hoc应用案例，具体要求如下：

- 远程目标主机新建文件和目录、修改文件或目录的权限
- 在远程目标主机创建链接文件
- 删除远程目标主机上的文件或目录
- 将控制端本地的文件拷贝到被管理端
- 从被管理端下载文件到本地
- 修改远程目标主机上的文件内容

#### 3.2 方案

很多ansible模块都具有幂等性的特征。

幂等性：任意次执行所产生的影响均与一次执行的影响相同。

##### 步骤一：file模块

file模块可以创建文件、目录、链接；修改权限与属性等（ansible-doc file）

```shell
[root@control ansible]# ansible  test  -m  file  -a  "path=/tmp/file.txt state=touch"         
#远程test组中所有主机，新建文件，path后面指定要创建的文件或目录的名称#state=touch是创建文件，state=directory是创建目录## 验证： 到node1主机，使用ls /tmp/file.txt看看文件是否被创建成功   ##
```

拓扑如图-5所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00115)

图-5

常见报错（有问题可以参考，没问题可以忽略）：

```shell
node1 | FAILED! => {   … …    "changed": false,    "msg": "value of state must be one of: absent, directory, file, hard, link, touch, got: touc"}英语词汇：value（值），must（必须），be（是），of（…的），one（一个）value of state must be one of:【state的值必须是后面给出的其中一个值】解决办法：检查state的值是否有字母错误,上面报错例子中输入的是touc，不是touch。
```

常见错误（有问题可以参考，没问题可以忽略）：

```shell
node1 | FAILED! => {   … …   "msg": "Unsupported parameters for (file) module: nmae Supported parameters include: _diff_peek, _original_basename, access_time, access_time_format, attributes, backup, content, delimiter, directory_mode, follow, force, group, mode, modification_time, modification_time_format, owner, path, recurse, regexp, remote_src, selevel, serole, setype, seuser, src, state, unsafe_writes"}英语词汇：unsupported（不支持的），parameters（参数），supported（支持的）include(包括)问题分析：file模块不支持nmae这个参数，它支持的参数包括哪些，后面有提示.解决办法：检查模块的参数是否有字母错误，上面错误案例将name错写为nmae。
```

更多file模块的案例：

```shell
[root@control ansible]# ansible  test  -m  file  \-a  "path=/tmp/mydir state=directory"       
#远程test组中所有主机，创建目录，path后面指定要创建的文件或目录的名称## 验证：到node1主机，使用ls /tmp/看看tmp目录下是否有mydir子目录

[root@control ansible]# ansible  test  -m  file \-a  "path=/tmp/file.txt owner=sshd group=adm mode=0777"  
#修改文件或目录权限，path后面指定要修改的文件名或目录名称，owner后面指定用户，group后面指定组，mode后面指定要修改的权限（0777中第一个0代表的是无特殊权限，如SUID、SGID等）## 验证：到node1主机，使用ls -l /tmp/file.txt查看文件的详细信息是否正确

[root@control ansible]# ansible test -m file -a "path=/tmp/mydir state=absent"#state=absent代表删除（删除目录）

[root@control ansible]# ansible test -m file -a "path=/tmp/file.txt state=absent"# state=absent代表删除（删除文件）

[root@control ansible]# ansible test -m file \-a "src=/etc/hosts  path=/tmp/host.txt state=link"  #给/etc/hosts文件创建一个链接文件/tmp/host.txt（src指定源文件，path是软链接文件名）#相当于执行命令 ln -s  /etc/hosts  /tmp/host.txt## 验证：到node1主机使用ls -l  /tmp/hosts查看文件是否为软链接
```

##### 步骤二：copy模块

copy模块可以将文件拷贝到远程主机 (ansible-doc copy)。

```shell
[root@control ansible]# echo AAA > ~/a3.txt                   #新建测试文件
[root@control ansible]# ansible test -m copy -a "src=~/a3.txt dest=/root/"#把管理端本机的a3.txt文件，拷贝到test组中所有主机的/root/目录#src代表源文件，dest代表目标文件## 验证：到node1主机使用ls /root/a3.txt查看是否有该文件
```

拓扑如图-6所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00114)

图-6

##### 步骤三：fetch模块

fetch模块与copy类似，但是作用相反,可以将其他主机的文件拷贝到本地(ansible-doc fetch)。

```shell
[root@control ansible]# ansible test -m fetch -a "src=/etc/hostname   dest=~/"#将远程test组中所有主机的hostname文件下载到本地家目录#src代表源文件，dest代表目标文件
[root@control ansible]# ls  ~/          #使用ls查看下是否下载成功#不能下载目录，如果需要下载目录，可以先打包后再下载
```

拓扑如图-7所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00113)

图-7

##### 步骤四：lineinfile|replace模块

在修改单个文件的单行内容时可以使用lineinfile模块(ansible-doc lineinfile)。

```shell
[root@control ansible]# ansible test -m lineinfile  \-a "path=/etc/issue line='hello world'"         #在/etc/issue文件中添加一行内容hello world，默认添加到最后，line后面跟的是需要添加的文件内容## 验证：到node1主机执行命令cat /etc/issue查看文件内容是否正确

[root@control ansible]# ansible test -m lineinfile \-a "path=/etc/issue line='hello world'" #基于幂等原则，重复执行，不会创建多行内容

[root@control ansible]# ansible test -m lineinfile \-a "path=/etc/issue line='insert' insertafter='Kernel'"    #将line后面的内容插入到/etc/issue文件中Kernel行的后面#英语词汇：insert（插入），after（在…后面）## 验证：到node1主机执行命令cat /etc/issue查看文件内容是否正确
```

lineinfile会替换一整行，replace可以替换关键词(ansible-doc replace)。

```shell
[root@control ansible]# ansible test -m replace \-a "path=/etc/issue.net regexp=Kernel replace=Ocean" 
#将node1主机中/etc/issue.net文件全文所有的Kernel替换为Ocean#regexp后面是需要替换的旧内容；replace后面是需要替换的新内容## 验证：到node1主机执行命令cat /etc/issue.net查看文件内容是否正确
```

### 4 案例4：Ansible ad-hoc应用三

#### 4.1 问题

沿用练习三，继续练习Ansible ad-hoc应用案例，具体要求如下：

- 远程目标主机创建、删除系统账户；设置系统账户属性、修改账户密码
- 为目标主机创建、删除yum源配置文件；远程目标主机安装、卸载软件包
- 使用service模块管理远程主机的服务
- 创建、删除逻辑卷

##### 步骤一：user模块

user模块可以实现Linux系统账户管理(ansible-doc user)。

```shell
[root@control ansible]# ansible test -m user -a "name=tuser1" 
#远程test组中的所有主机并创建系统账户tuser1，默认state的值为present，代表创建用户
## 验证：到node1主机执行命令id  tuser1查看是否有该用户
```

拓扑如图-8所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00112)

图-8

```shell
[root@control ansible]# ansible test -m user -a "name=tuser2 uid=1010 group=adm groups=daemon,root home=/home/tuser2"  
#创建账户并设置对应的账户属性，uid指定用户ID号，group指定用户属于哪个基本组
#groups指定用户属于哪些附加组，home指定用户的家目录
## 验证： 到node1主机执行命令id tuser2查看是否有该用户
```

拓扑如图-9所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00111)

图-9

```shell
[root@control ansible]# ansible test -m user \
-a "name=tuser1 password={{'abc'| password_hash('sha512')}}"  
#修改账户密码，用户名是tuser1，密码是abc，密码经过sha512加密

[root@control ansible]# ansible test -m user \
-a "name=tuser1 state=absent"   
#删除账户tuser1，state=absent代表删除账户的意思，name指定要删除的用户名是什么#账户的家目录不会被删除，相当于执行userdel tuser1

[root@control ansible]# ansible test -m user \
-a "name=tuser2 state=absent remove=true"  
#删除tuser2账户同时删除家目录、邮箱，相当于执行userdel  -r  tuser2
```

##### 步骤二：yum_repository模块

使用yum_repository可以创建或修改yum源配置文件（ansible-doc yum_repository）。

```shell
[root@control ansible]# ansible test -m yum_repository \
-a "name=myyum description=hello baseurl=ftp://192.168.4.254/centos gpgcheck=no"   
#新建一个yum源配置文件/etc/yum.repos.d/myyum.repo
#yum源文件名为myyum，该文件的内容如下：[myyum]baseurl = ftp://192.168.4.254/centos gpgcheck = 0 name = hello
## 验证：到node1主机ls /etc/yum.repos.d/查看该目录下是否有新的yum文件

[root@control ansible]# ansible test -m yum_repository \
-a "name=myyum description=test baseurl=ftp://192.168.4.254/centos gpgcheck=yes gpgkey=…"   
#修改yum源文件内容

[root@control ansible]# ansible test -m yum_repository -a "name=myyum state=absent"  #删除yum源文件myyum
```

##### 步骤三：yum模块

使用yum模块可以安装、卸载、升级软件包（ansible-doc yum），

state: present(安装)|absent(卸载)|latest(升级)。

```shell
[root@control ansible]# ansible test -m yum -a "name=unzip state=present"  #安装unzip软件包，state默认为present，也可以不写## 验证：到node1主机执行命令rpm -q unzip查看是否有该软件

[root@control ansible]# ansible test -m yum -a "name=unzip state=latest"  #升级unzip软件包，软件名称可以是*，代表升级所有软件包
[root@control ansible]# ansible test -m yum -a "name=unzip state=absent"  #调用yum模块，卸载unzip软件包，state=absent代表卸载软件## 验证：到node1主机执行命令rpm -q unzip查看该软件是否已经被卸载
```

##### 步骤四：service模块（ansible-doc service）

service为服务管理模块（启动、关闭、重启服务等），

state:started|stopped|restarted，

enabled:yes设置开机启动。

```shell
[root@control ansible]# ansible test -m yum -a "name=httpd"  #调用yum模块，安装httpd软件包## 验证：到node1主机执行命令rpm -q httpd查看该软件是否被安装

[root@control ansible]# ansible test -m service -a "name=httpd state=started"  #调用service模块，启动httpd服务## 验证：到node1主机执行命令systemctl  status  httpd查看服务状态

[root@control ansible]# ansible test -m service -a "name=httpd state=stopped" #调用service模块，关闭httpd服务## 验证：到node1主机执行命令systemctl  status  httpd查看服务状态

[root@control ansible]# ansible test -m service -a "name=httpd state=restarted" #调用service模块，重启httpd服务  

[root@control ansible]# ansible test -m service -a "name=httpd enabled=yes"  #调用service模块，设置httpd服务开机自启
```

##### 步骤五：逻辑卷相关模块（ansible-doc lvg、ansible-doc lvol）

提示：做实验之前需要给对应的虚拟机添加额外磁盘，并创建磁盘2个分区

提示：可以使用前面学习过的parted或fdisk命令给磁盘创建分区

提示：这里的磁盘名称仅供参考，不要照抄！！！

lvg模块:创建、删除卷组(VG)，修改卷组大小，

state:present(创建)|absent(删除)。

```shell
 [root@control ansible]# ansible test -m yum -a "name=lvm2" #安装lvm2软件包，安装了lvm2软件后，才有pvcreate、vgcreate、lvcreate等命令
 
 [root@control ansible]# ansible test -m lvg -a "vg=myvg pvs=/dev/sdb1" #创建名称为myvg的卷组，该卷组由/dev/sdb1组成#注意：这里的磁盘名称要根据实际情况填写## 验证：到node1主机执行命令pvs和vgs查看是否有对应的PV和VG
 
 [root@control ansible]# ansible test -m lvg -a "vg=myvg pvs=/dev/sdb1,/dev/sdb2" #修改卷组大小，往卷组中添加一个设备/dev/sdb2
```

lvol模块:创建、删除逻辑卷(LV)，修改逻辑卷大小，

state:present(创建)|absent(删除)。

```shell
[root@control ansible]# ansible test -m lvol -a "lv=mylv vg=myvg size=2G" #使用myvg这个卷组创建一个名称为mylv的逻辑卷，大小为2G## 验证：到node1主机执行命令lvs查看是否有对应的LV逻辑卷

[root@control ansible]# ansible test -m lvol -a "lv=mylv vg=myvg size=4G" #修改LV逻辑卷大小

[root@control ansible]# ansible test -m lvol -a "lv=mylv vg=myvg state=absent force=yes" #删除逻辑卷，force=yes是强制删除

[root@control ansible]# ansible test -m lvg -a "vg=myvg state=absent" #删除卷组myvg
```

附加思维导图，如图-10所示：

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00110)

图-10

附加思考题（假设在没有创建ssh密钥的情况下）：

在没有创建ssh密钥的情况下，如果node1需要ssh远程node2是否需要输入密码？

如果node1需要ssh远程node2，应该输入谁的用户名和密码？

node1使用自己系统的账户和密码能否ssh远程node2，node2可以被随便登录还安全吗？

路人甲能否使用自己家的钥匙，去路人乙家（开路人乙家的门）？

node1执行命令ssh root@192.168.4.12，这里的root是谁的账户名？输入谁的密码？

如果使用真机windows的Xshell去ssh远程node2虚拟机，需要在windows也有一个root用户吗？

## 02：sudo提权、Ansible配置、Ansible Playbook、Ansible进阶

### 1 案例1：配置sudo权限

#### 1.1 问题

本案例要求使用sudo提升普通用户的权限，要求如下：

- 给所有被管理主机创建系统账户
- 账户名称为alice，密码为123456
- 修改sudo配置，让alice可以执行任何管理命令

#### 1.2 方案

sudo（superuser or another do）让普通用户可以以超级管理员或其他人的身份执行命令。

sudo基本流程如下：

1. 管理员需要先授权（修改/etc/sudoers文件）
2. 普通用户以sudo的形式执行命令

修改/etc/sudoers的方法如下：

1. visudo（带语法检查，默认没有颜色提示）
2. vim /etc/sudoers（不带语法检查，默认有颜色提示）

授权格式如下：

用户或组 主机列表=(提权身份) [NOPASSWD]:命令列表

注意事项：命令需要写绝对路径，对组授权需要在组名称前面加%。

```shell
[root@control ~]# cat  /etc/sudoers         #不要改，下面仅仅是语法格式的示例（例子）
… …
root           ALL=(ALL)       ALL
tom            ALL=(root)      /usr/bin/systemctl
%wheel    	 ALL=(ALL)       ALL
```

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：配置sudo提权

###### 1）远程所有被管理主机批量创建系统账户，账户名称为alice，密码为123456。

```shell
[root@control ansible]# ansible all -m user -a "name=alice \
password={{'123456' | password_hash('sha512')}}"
```

###### 2）配置alice账户可以提权执行所有命令（control批量授权，node1主机验证）。

使用lineinfile模块修改远程被管理端主机的/etc/sudoers文件，line=后面的内容是需要添加到文件最后的具体内容。

等于是在/etc/sudoers文件末尾添加一行:alice ALL=(ALL) NOPASSWD:ALL

```shell
[root@control ansible]# ansible all -m lineinfile \
-a "path=/etc/sudoers line='alice  ALL=(ALL) NOPASSWD:ALL'"
[root@control ansible]# ssh alice@node1
```

如何验证？可以在node1电脑上面使用alice用户执行sudo重启服务的命令看看是否成功。

```shell
[alice@node1 ansible]$ sudo systemctl restart sshd  #不需要输入密码
```

### 2 案例2：修改Ansible配置

#### 2.1 问题

沿用练习一，修改ansible配置实现使用普通用户远程被控制端主机，具体要求如下：

- 修改主配置文件
- 设置ansible远程被管理端主机账户为alice
- 设置ansible远程管理提权的方式为sudo
- 修改主机清单文件
- 修改主机清单配置文件，添加SSH参数

#### 2.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：配置普通用户远程管理其他主机

###### 1）修改主配置文件，配置文件文件的内容可以参考/etc/ansible/ansible.cfg。

```shell
[root@control ansible]# vim ~/ansible/ansible.cfg
[defaults]
inventory = ~/ansible/inventory
remote_user = alice				#以什么用户远程被管理主机（被管理端主机的用户名）
[privilege_escalation]
become = true					#alice没有特权，是否需要切换用户提升权限
become_method = sudo				#如何切换用户（比如用su就可以切换用户，这里是sudo）
become_user = root				#切换成什么用户（把alice提权为root账户）
become_ask_pass = no				#执行sudo命令提权时是否需要输入密码
```

思考：

如果A主机ssh远程访问B主机，应该输入哪个主机的用户名和对应的密码？

如果张三要去李四家，应该使用谁家的钥匙，打开谁家的门？

###### 2)远程被管理端主机的alice用户，需要提前配置SSH密钥。

```shell
[root@control ansible]# for i in node1  node2  node3  node4  node5
do
  ssh-copy-id    alice@$i
done
```

验证效果：

```shell
[root@control ansible]# ssh alice@node1            #依次远程所有主机看看是否需要密码
#注意：是远程登录node1，应该输入的是node1电脑上面alice账户的密码，control没有alice用户
[root@control ansible]# ansible all -m command -a  "who"              #测试效果
[root@control ansible]# ansible all -m command -a  "touch /test"     #测试效果
```

常见报错（有问题可以参考，没问题可以忽略）：

```shell
node1 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: alice@node1: Permission denied (publickey,gssapi-keyex,gssapi-with-mic,password).",
    "unreachable": true
}
问题分析：
英语词汇：Failed（失败），connect（连接），to（到），host（主机），via（通过）
permission（权限），denied（被拒绝）
Failed to connect to host via ssh alice@node1（通过ssh使用alice远程连接到主机失败）
Permission denied（因为无法连接，所以报错说权限被拒绝）
解决办法：手动ssh alice@主机名（如node1），看看是否可以实现免密码登录。
          Ansible的原理是基于ssh远程管理，如果无法实现alice免密码登录，则实验会失败！
		如何实现免密码登录，可以参考案例上面的命令，或者第一阶段相关知识。
```

###### 3）修改inventory主机清单配置文件（参考即可，不需要操作）。

如果个别主机的账户不同，该如何处理呢？

如果有些主机需要使用密码远程呢？如果有些主机的SSH端口不是22呢？

```shell
[root@control ~]# cat  ~/ansible/inventory
[test]					
node1	       ansible_ssh_port=端口号	          		#自定义远程SSH端口
[proxy]
node2           ansible_ssh_user=用户名					#自定义远程连接的账户名
[webserver]
node[3:4]       ansible_ssh_pass=密码				     #自定义远程连接的密码
[database]
node5
[cluster:children]				
webserver
database
```

### 3 案例3：Playbook应用案例

#### 3.1 问题

沿用练习二，编写Ansible Playbook剧本，使用Playbook完成自动化操作，具体要求如下：

- 熟悉Playbook语法格式
- 编写Playbook管理系统账户
- 编写Playbook管理逻辑卷
- 编写Playbook管理软件包

#### 3.2 方案

Ansible ad-hoc可以通过命令行形式远程管理其他主机，适合执行一些临时性简单任务。另外还有一种远程管理的方式叫Playbook，Ansible Playbook中文名称叫剧本,它将经常需要执行的任务写入一个文件，这个文件就叫剧本。

- 剧本中可以包含多个任务
- 剧本写后，我们随时根据剧本，执行相关的任务命令
- Playbook剧本要求按照YAML格式编写
- 适合执行周期性经常执行的复杂任务

YAML是什么？

- YAML是一个可读性高、用来表达数据序列的格式语言
- YAML：YAML Ain't a Markup Language
- YAML以数据为中心，重点描述数据的关系和结构

YAML的格式要求如下：

- "#"代表注释，一般第一行为三个横杠（---）
- 键值（key/value）对使用":"表示，数组使用"-"表示，"-"后面有空格
- key和value之间使用":"分隔
- ":"后面必须有空格
- 一般缩进由两个或以上空格组成
- 相同层级的缩进必须对齐，缩进代表层级关系
- 全文不可以使用tab键
- 区分大小写
- 扩展名为yml或者yaml
- 跨行数据需要使用>或者|，其中|会保留换行符

##### YAML示例展示：

###### 1）demo1

```yaml
---
"诗仙": "李白"
或者
"诗仙": 
   "李白"
```

###### 2）demo2

```yaml
#数组的例子
---
- "李白"
- "杜甫"
- "白居易"
- "唐僧"
```

###### 3）demo3

```yaml
#使用一行表示数组的例子
---
"诗人": ["李白","杜甫","白居易"]
```

###### 4)demo4

```yaml
#键值对和数组符合例子：
---
"诗人":
  - "李白"
  - "杜甫"
  - "白居易"
```

###### 5)demo5

```yaml
#复杂案例
---
- "诗人":
    - 唐代:
         - "李白"
         - "杜甫"
    - 宋代:
         - "苏轼"
         - "李清照"
```

###### 6）demo6

```yaml
#喜欢的电影
---   
- 芳华
- 战狼
- 霸王别姬
```

###### 7）demo7

```yaml
#人物描述
---   
- 姓名: 李白
  年龄: 61
  作品: 蜀道难
  好友: 汪伦
```

###### 8）demo8

```yaml
#跨行文本（计算机理解为一行）
---  
自我介绍:  >
  字太白,号青莲居士,
  唐代诗人,祖籍陇西郡,
  今甘肃省平凉市
```

###### 9）demo9

```yaml
#跨行文本（计算机理解为多行）
---  
自我介绍:  |
  字太白,号青莲居士,
  唐代诗人,祖籍陇西郡,
  今甘肃省平凉市 
```

###### 10）demo10

注意-和:后面必须有空格。

```yaml
#一张发票
--- 
发票编号: 34843
日期: 2028-12-12
商品:
  - 商品编号: BL394D
    描述: 足球
    价格: 100
  - 商品编号: BL4438H
    描述: 棒球
    价格: 200
税费: 10.00
总价: 310.00
备注: >
    本次采购商品均
    属于球类运动商品.   
```

###### 11）demo11

```yaml
#错误日志
---
时间: 2028-10-01  15:01:42
用户: ed
错误信息: 
  - 文件: nginx.conf
    行号: 23
    错误编码: "0x3D5FF1"
  - 文件: test.php
    行号: 12
    错误代码: "0xA4C51E"
警告信息: |
    你有两个错误信息需要查看,
    一条是配置文件错误,
    一条是脚本语法错误,
    具体内容参考错误信息.   
```

#### Playbook语法格式要求如下：

- playbook采用YAML格式编写
- playbook文件中由一个或多个play组成
- 每个play中可以包含:
- hosts(主机)、tasks(任务)、vars(变量)等元素组成
- 使用ansible-playbook命令运行playbook剧本
- 
- 

#### 步骤一：测试Playbook语法格式

###### 1）编写第一个Playbook（剧本）

hosts、tasks、name是关键词（不可修改），ping是模块，调用不同模块完成不同任务。

```yaml
[root@control ansible]# vim ~/ansible/test.yml 
---
- hosts: all								#hosts定义要远程谁？
  tasks:									#tasks定义远程后要执行的任务有哪些？
      - name: This is my first playbook      #name后面的具体内容可以任意
        ping:
[root@control ansible]# ansible-playbook ~/ansible/test.yml
```

执行效果如图-1所示。

<img src="C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00109" alt="img" style="zoom: 200%;" />

图-1

###### 2）定义多个主机和任务的剧本

hosts由一个或多个组或主机组成，逗号分隔，tasks由一个或多个任务组成，多个任务按顺序执行，执行ansible-playbook命令可以使用-f选项自定义并发量。

```yaml
[root@control ansible]# vim ~/ansible/test.yml 
- hosts: test,webserver
  tasks:
      - name: This is my first playbook     #name后面的内容可以任意
        ping:
      - name: Run a shell command
        shell: touch ~/shell.txt
#hosts定义需要远程哪些被管理主机，hosts是关键词
#tasks定义需要执行哪些任务，tasks是关键词
#第一个任务调用ping模块,该模块没有参数
#第二个任务调用shell模块在被管理主机创建一个空文件~/shell.txt

[root@control ansible]# ansible-playbook ~/ansible/test.yml  -f 5
## 验证：到node1、node3、node4主机分别执行命令ls /root/shell.txt查看是否有该文件
```

###### 3）多个play的Playbook文件

```yaml
[root@control ansible]# vim ~/ansible/test.yml
#第一个play剧目
---
- hosts: test
  tasks:
      - name: This is first play
        ping:
#第二个play剧目
- hosts: webserver
  tasks:
      - name: This is second play
        ping:
```

#### 步骤二：Playbook应用案例

###### 1）用户管理，创建系统账户、账户属性、设置密码（ansible-doc user）。

```yaml
[root@control ansible]# vim ~/ansible/test_john.yml
---
- hosts: webserver
  tasks:
    - name: Add the user 'johnd' 
      user:
        name: johnd
        uid: 1040
        group: daemon
        password: "{{ '123' | password_hash('sha512') }}"
#hosts定义需要远程的对象是webserver组，hosts是关键词
#tasks定义需要执行的任务，tasks是关键词
# name是第一个任务的描述信息，描述信息可以任意
# user是第一个任务需要调用的模块，user下面的缩进内容是给user模块的参数
# name是需要创建的用户名，uid是用户ID号
# group是用户属于哪个基本组
# password是用户的密码，密码是123，密码经过sha512算法加密

[root@control ansible]# vim ~/ansible/user_james.yml
---
- hosts: webserver
  tasks:    
    - name:  Add 'james' with a bash shell
      user:
        name: james
        shell: /bin/bash
        groups: bin,adm
        password: "{{ '123' | password_hash('sha512') }}" 
#与上一个案例类似，groups指定用户属于哪些附加组.

[root@control ansible]# vim ~/ansible/user_johnd.yml
---
- hosts: webserver
  tasks:
    - name: Remove the user 'johnd'
      user:
        name: johnd
        state: absent
#删除系统账户johnd，state的值设置为absent是删除用户
```

###### 2）使用playbook管理逻辑卷

准备工作：给node2主机再添加一块磁盘（以下实验磁盘名称仅为参考，不要照抄）。

（ansible-doc parted，ansible-doc lvg，ansible-doc lvol）

```yaml
[root@control ansible]# vim ~/ansible/lvm.yml
---
- hosts: node2							#远程node2主机
  tasks:
    - name: Create a new primary partition with a size of 1GiB  #任务的描述信息
      parted:                                 #调用parted模块进行分区         
        device: /dev/sdb                     #对/dev/sdb磁盘进行分区(磁盘名称不要照抄)
        label: gpt                          #分区表类型为gpt，或msdos
        number: 1                           #分区编号(创建第几个分区)
        state: present                     #present是创建分区,absent是删除分区
        part_start: 1MiB                   #分区的开始位置（默认从最开始位置分区）
        part_end: 1GiB                     #分区的结束位置（不写就分到磁盘最后位置）
    - name: Create a volume group on top of /dev/sdb1     #第二个任务的描述信息
      lvg:                                  #调用lvg模块,创建VG卷组
        vg: my_vg                          #要创建的卷组名称
        pvs: /dev/sdb1                     #使用哪个分区创建PV
    - name: Create a logical volume of 512m          #第三个任务的描述信息
      lvol:                                 #调用lvol模块创建LV
        vg: my_vg                          #使用哪个VG创建LV
        lv: my_lv                          #需要创建的LV名称
        size: 512m                         #要创建的LV大小,可以不指定单位，默认单位m
```

###### 3）使用playbook管理软件（ansible-doc yum）

RHEL或CentOS系统中的软件有组包的概念，使用yum grouplist或者dnf grouplist可以查看组包的名称。

```yaml
[root@control ansible]# vim ~/ansible/package.yml
---
- hosts: webserver                        #需要远程的主机是谁
  tasks:                                   #定义剧本需要执行的任务
    - name: Install a list of packages  #第一个任务的描述信息 
      yum:                                 #调用yum模块安装软件
        name:                              #安装软件的名字，它的值有多个，使用数组-
          - httpd                          #安装httpd软件
          - mariadb                        #安装mariadb软件
          - mariadb-server                #安装mariadb-server
    - name: install the 'RPM Development Tools' package group   #第二个任务的描述信息
      yum:                                  #调用yum模块安装软件组包
        name: "@RPM Development Tools"        #安装哪个组包，@是关键词
    - name: update software               #第三个任务的描述信息
      yum:                                  #调用yum模块升级软件
        name: '*'                           #需要升级哪些软件
        state: latest                       #latest代表升级软件
#备注:state的值可以是(present|absent|latest)
#present代表安装软件(默认是present)；absent代表卸载软件
#latest代表升级软件
```

### 4 案例4：Playbook应用案例

#### 4.1 问题

沿用练习三，继续练习Ansible 特殊模块并掌握自定义变量的方式，具体要求如下：

- 熟悉setup与debug模块
- 熟悉各种常见的变量定义方式

##### 步骤一：Ansible特殊模块

###### 1）setup模块

ansible_facts用于采集被管理设备的系统信息，所有收集的信息都被保存在变量中，每次执行playbook默认第一个任务就是Gathering Facts，使用setup模块可以查看收集到的facts信息。

```shell
[root@control ansible]# ansible test -m setup
192.168.4.10 | SUCCESS => {
"ansible_facts": {
   "ansible_all_ipv4_addresses": [
… 省略部分内容…
```

试试自己找出下列变量：

- ansible_all_ipv4_addresses #IP地址
- ansible_bios_version #主板BIOS版本
- ansible_memtotal_mb #总内存
- ansible_hostname #主机名
- ansible_fqdn #主机的域名
- ansible_devices.sda.partitions.sda1.size #某个磁盘分区的大小

###### 2）debug模块

debug模块可以显示变量的值，可以辅助排错，通过msg可以显示变量的值，变量需要使用{{}}扩起来。

```yaml
[root@control ansible]# vim ~/ansible/debug.yml
---
- hosts: test
  tasks:
    - debug:
        msg: "主机名是:{{ ansible_hostname }}"
    - debug:
        msg: "总内存大小:{{ ansible_memtotal_mb }}"
#备注调用debug模块显示某些具体的变量值
#debug模块可以显示变量的值，可以辅助排错
```

##### 步骤二：定义变量的方法

Ansible支持十几种定义变量的方式，这里我们仅介绍其中一部分变量。

下面是根据优先级排序的定义方式：

1. Inventory变量
2. Host Facts变量
3. Playbook变量
4. 变量文件

###### 1）Inventory变量(在主机清单配置文件中定义变量）。

```shell
[root@control ansible]# vim ~/ansible/inventory
[test]
node1  iname="nb" 
[proxy]
node2
[webserver]
node[3:4]
[webserver:vars]
iname="dachui"
#备注，在node1主机后面给该主机添加变量iname,值为nb.
#给webserver组定义变量,vars是关键词不可以改变,webserver是上面定义的组
#给这个组定义变量iname="dachui"
```

下面编写剧本调用刚才的变量：(在剧本中需要调用变量是要使用{{}})

```yaml
[root@control ansible]# vim ~/ansible/inventory_var.yml
---
- hosts: node1,webserver                         #定义需要远程管理的主机是谁               
  tasks:                                           #剧目要完成哪些任务
    - name: create a user with var.              #剧目中的第一个任务描述信息
      user:                                        #调用user模块创建用户
        name: "{{ iname }}"                      #需要创建的用户名是iname这个变量
#注意事项：
#在ansible剧本中当调用变量时，开始位置就调用变量,就需要在{{}}外面加双引号
#如果是在后面或者中间位置调用变量{{}}外面可以不加双引号
#如:
#  "{{ iname }}"
#  nihao {{ iname }}
```

###### 2）Host Facts变量（可以直接调用ansible收集的系统信息）

```yaml
[root@control ansible]# vim ~/ansible/facts_var.yml
---
- hosts: test
  tasks:
    - name: create user.
      user:
        name: "{{ansible_hostname}}"
#定义剧本，远程所有被管理主机，调用user模块，创建用户
#需要创建的用户名ansible_hostname是一个ansible_facts变量
#验证： 到node1主机查看是否有一个与主机名同名的用户
```

###### 3）Playbook变量(使用vars关键词可以在playbook内定义变量）。

```yaml
[root@control ansible]# vim ~/ansible/playbook_var.yml
---
- hosts: test
  vars:                                     #vars是关键词，用来定义变量用的
    iname: heal                            #具体变量名是iname，值是heal
    ipass: '123456'                       #再定义一个变量名是ipass，值是123456
#注意密码必须是字符串，需要引号                           
  tasks:                                   #tasks定义需要执行的任务
    - name: Use variables create user.  #给任务写个描述信息   
      user:                                #调用user模块创建用户
        name: "{{ iname }}"               #用户名的是前面定义的变量
        password: "{{ ipass | password_hash('sha512') }}"
#密码是前面定义好的ipass,管道给password_hash把密码加密.
```

###### 4）单独定义个变量文件，在playbook中用vars_files调用该文件。

```yaml
[root@control ansible]# vim ~/ansible/file_var.yml
---
- hosts: test
  vars_files: variables.yml             #当变量比较多时，专门定义一个文件用来存变量
  tasks:
    - name: create user.
      user:
        name: "{{ iname }}"
        password: "{{ ipass | password_hash('sha512') }}"
#调用user模块创建用户
#用户名是变量文件variables.yml中定义的变量iname，密码也是变量文件中定义的变量
[root@control ansible]# vim  ~/ansible/variables.yml
---
iname: cloud
ipass: '123456'
```

### 附加思维导图

如图-2所示：

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00108)



## 03：Ansible进阶、Ansible Vault、Ansible Roles、综合练习

### 1 案例1：ansible应用案例

#### 1.1 问题

本案例要求掌握Ansible更多高级语法知识，具体要求如下：

- 熟悉firewalld和template模块的使用
- 熟悉error处理机制
- 熟悉handlers任务
- 熟悉when条件判断
- 熟悉block任务块
- 熟悉loop循环的使用方法

#### 1.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：firewalld模块

使用firewalld模块可以配置防火墙策略。

```yaml
[root@control ~]#  vim ~/ansible/firewall.yml
---
- hosts: test                           #hosts定义需要远程的主机  
  tasks:                                 #tasks定义需要执行哪些任务    
      - name: install firewalld.         #name为第一个任务定义描述信息      
        yum:                               #第一个任务调用yum模块安装软件        
           name: firewalld                 #需要安装的软件名称为firewalld        
           state: present                  #state等于present代表安装软件    
      - name: run firewalld.             #定义第二个任务的描述信息      
        service:                          #第二个任务调用service模块启动服务        
           name: firewalld                #启动的服务名称为firewalld        
           state: started                 #state等于started代表启动服务        
           enabled: yes                    #enabled等于yes是设置服务为开机自启动    
      - name: set firewalld rule.       #第三个任务的描述信息      
        firewalld:                        #第三个任务调用firewalld模块设置防火墙规则        
        port: 80/tcp                    #在防火墙规则中添加一个放行tcp，80端口的规则        
        permanent: yes                  #permaenent 是设置永久规则        
        immediate: yes                  #immediate 是让规则立刻生效        
        state: enabled                  #state等于enabled是添加防火墙规则#最终：在默认zone中添加一条放行80端口的规则
```

##### 步骤二：template模块

copy模块可以将一个文件拷贝给远程主机，但是如果希望每个拷贝的文件内容都不一样呢？如何给所有web主机拷贝index.html内容是各自的IP地址？

Ansible可以利用Jinja2模板引擎读取变量，之前在playbook中调用变量，也是Jinja2的功能，Jinja2模块的表达式包含在分隔符"{{ }}"内。

###### 这里，我们给webserver主机拷贝首页，要求每个主机内容不同。

```shell
[root@control ansible]# mkdir ~/ansible/template
[root@control ansible]# vim ~/ansible/template/index.html
Welcome to {{ansible_hostname}} on {{ ansible_eth0.ipv4.address }}. 
#注意网卡名称根据实际情况填写，不可以完全照抄，不知道网卡名可以通过ip a s查询！
#{{ansible_hostname}}和{{ ansible_eth0.ipv4.address }}是ansible自动的facts变量。                
```

###### 2）编写Playbook将网页模板文件拷贝到远程主机。

```yaml
[root@control ansible]# vim ~/ansible/template.yml
---
- hosts: webserver  
  tasks:    
     - name: use template copy index.html to webserver.      
       template:        
          src: ~/ansible/template/index.html        
          dest: /tmp/index.html
#hosts定义需要远程的目标主机是谁；tasks定义需要执行的任务是什么#- name定义任务的描述信息；任务需要调用的模块是template模块#template模块需要两个参数，src指定需要拷贝的源文件，dest指定需要拷贝的目标位置#src: ~/ansible/template/index.html是上面创建的文件,文件中包含变量#dest: /tmp/index.html拷贝到目标主机放在/tmp目录下
```

##### 步骤三：Ansible高级语法应用

###### 1）error错误处理

默认ansible在遇到error会立刻停止playbook，使用ignore_errors可以忽略错误，继续后续的任务。

如果一个剧本里面有20个任务，执行到第3个时失败，则不再往下执行。

下面这个这个Playbook在执行时会意外中断。

```yml
[root@control ansible]# vim ~/ansible/error.yml
---
- hosts: test  
  tasks:    
  	- name: start a service that does not exist.      
  	  service:        
  	  name: hehe         #注意：没有这个服务（启动一个不存在的服务）                                               		  state: started    
  	- name: touch a file.      
  	  file:        
  	    path: /tmp/service.txt        
  	    state: touch
```

下面这个Playbook在执行时因为忽略了错误（针对某一个任务），不会被中断。

```yaml
[root@control ansible]# vim ~/ansible/error.yml
---
- hosts: test  
  tasks:    
  	- name: start a service that does not exist.      
  	  service:        
  	  	name: hehe        
  	  	state: started      
  	  	ignore_errors: true       #针对某一个任务忽略错误(ignore_errors是关键词)                              - 		  name: touch a file.      
  	  file:        
  	  		path: /tmp/service.txt        
  	  		state: touch
```

下面这个Playbook在执行时因为忽略了错误，不会被中断。

```yaml
[root@control ansible]# cat ~/ansible/error.yml
---
- hosts: test  
  ignore_errors: true      #针对playbook全局忽略错误                               
  tasks:    
  	- name: start a service that does not exist.      
  	  service:        
  		name: hehe        
  		state: started    
  	- name: touch a file.      
  	  file:        
  	  	path: /tmp/service.txt        
  	  	state: touch
```

###### 2）handlers

在剧本中tasks用来定义任务（一定会执行），handlers也可以定义任务（不一定执行），handlers任务要想执行必须要被别人触发才能执行。

```yaml
实例草稿：---
- hosts: test  
  tasks:    
     - 任务1      
       notify: 任务5    
     - 任务2  
  handlers:    
     - 任务5    
     - 任务6
```

可以通过handlers定义一组任务，仅当某个任务触发(notify)handlers时才执行相应的任务，如果有多个notify触发执行handlers任务，也仅执行一次。

仅当任务的执行状态为changed时handlers任务才执行，handlers任务在所有其他任务都执行后才执行。

下面编写一个通过notify触发执行handlers任务的案例。

```yaml
[root@control ansible]# vim ~/ansible/handlers.yml
---
- hosts: test  
  tasks:    
	- name: create directory.           #多次执行playbook该任务状态不再是changed      
	  file:                               #调用file模块创建目录        
	     path: /tmp/parents/subdir/      #需要创建的具体目录名称        
	     state: directory                #state等于directory代表创建目录      
	     notify: touch file                #notify后面名称必须和handlers中的任务名称一致            
  handlers:                              #通过handlers再定义一组任务    
	- name: touch file                  #给任务写描述信息（任务的名字，名字可以任意）      
	  file:                              #调用file模块创建文件        
	  	 path: /tmp/parents/subdir/new.txt    #需要创建的文件名        
	  	 state: touch                           #state等于touch代表创建文件#备注：仅当file模块执行成功，#并且状态为changed时才会通过notify触发执行handlers下面的任务，#所以多次执行该剧本时，handlers任务不会被重复执行,#notity后面的名称必须和handlers下面name定义的任务名称一致（名称可以任意）。
```

###### 3）when条件判断

when可以定义判断条件，条件为真时才执行某个任务。

常见条件操作符有：==、!=、>、>=、<、<=。

多个条件可以使用and(并且)或or（或者）分割，when表达式中调用变量不要使用{{ }}。

下面编写Playbook，远程主机剩余内存不足700M则关闭NetworkManager服务

```yml
[root@control ansible]# vim ~/ansible/when_1.yml
---
- hosts: test  
  tasks:    
  	  - name: check memory size.      
  	    service:        
  	       name: NetworkManager        
  	       state: stopped      
  	       when: ansible_memfree_mb < 700
#被管理端主机剩余内存不足700M则关闭NetworkManager服务(也可以关闭别的不需要的服务)
#ansible_memfree_mb这个是ansible自带的facts变量,代表剩余内存的容量。
```

下面再编写一个Playbook，判断操作系统是RedHat8则创建测试文件。YAML的语法格式中>支持多行输入，但不保留换行符。

```yaml
[root@control ansible]# vim ~/ansible/when_2.yml
---
- hosts: test  
  tasks:    
     - name: touch a file      
       file:        
          path: /tmp/when.txt        
          state: touch      
  when:  >        
     ansible_distribution == "RedHat"                
           and        
     ansible_distribution_major_version == "8"
#判断操作系统是RedHat8则创建测试文件#YAML的语法格式中>支持多行输入，但不保留换行符（计算机会认为实际是一行内容）#ansible_distribution和ansible_distribution_major_version都是自带的facts变量
#可以使用setup模块查看这些变量
```

###### 4）block任务块

如果我们需要当条件满足时执行N个任务,我们可以给N个任务后面都加when判断(但是很麻烦),此时可以使用block定义一个任务块,当条件满足时执行整个任务块.

任务块就是把一组任务合并为一个任务组，使用block语句可以将多个任务合并为一个任务组。

```yaml
[root@control ansible]# vim ~/ansible/block_1.yml---
- hosts: test  
  tasks:    
  	- name: define a group of tasks.      
  	  block:                                          #block是关键词，定义任务组        
  	    - name: install httpd                       #任务组中的第一个任务          
  	      yum:                                        #调用yum模块安装httpd软件包            
  	        name: httpd            
  	        state: present        
  	    - name: start httpd                          #任务组中的第二个任务          
  	      service:                                    #调用service模块启动httpd服务            
            name: httpd            
            state: started      
       when: ansible_distribution == "RedHat"       
#仅当条件满足再执行任务组
#注意:when和block是对齐的,他们在一个级别,当条件满足时要执行的是任务组（不是某一个任务）
#判断条件是看远程的目标主机使用的Linux发行版本是否是RedHat.
```

对于block任务块，我们可以使用rescue语句定义在block任务执行失败时要执行的其他任务，还可以使用always语句定义无论block任务是否成功，都要执行的任务。

下面编写一个包含rescue和always的示例。

```yaml
[root@control ansible]# vim ~/ansible/block_2.yml
---
 	- hosts: test  
	  tasks:    
	  	- block:        
	  		- name: touch a file test1.txt          
	  		  file:            
	  			name: /tmp/test1.txt      #如果修改为/tmp/xyz/test1.txt就无法创建成功                                       	     state: touch      
	  	  rescue:        
	  	  	 - name: touch a file test2.txt          
	  	  	   file:            
	  	  	     name: /tmp/test2.txt            
	  	  	   	 state: touch      
	  	  always:        
	  	  	 - name: touch a file test3.txt          
	  	  	   file:            
	  	  	     name: /tmp/test3.txt            
	  	  	     state: touch
#默认在/tmp/目录下创建test1.txt会成功，所以不执行rescue(创建test2.txt)#如果我们把block中的任务改为创建/tmp/xyz/test1.txt（因为没有xyz目录所以会失败)#当block默认任务失败时就执行rescue任务(创建test2.txt)#但是不管block任务是否成功都会执行always任务(创建test3.txt)
```

###### 5）loop循环

相同模块需要反复被执行怎么处理？使用loop循环可以避免重复。

编写Playbook，循环创建目录。

```yaml
[root@control ansible]# vim ~/ansible/simple_loop.yml
---
- hosts: test  
  tasks:    
		- name: mkdir multi directory.      
		  file:        
		  	path=/tmp/{{item}}       #注意，item是关键字，调用loop循环的值                                        		    state=directory      
		  loop:                       #loop是关键词,定义循环的值,下面是具体的值        
		   	- School        
		   	- Legend        
		   	- Life
#最终在/tmp目录下创建三个子目录.file模块被反复执行了三次。
#mkdir  /tmp/School;  mkdir  /tmp/Legend;   mkdir  /tmp/Life。
```

编写Playbook，循环创建用户并设置密码。

```yaml
[root@control ansible]# vim ~/ansible/complex_loop.yml
---
- hosts: test  
  tasks:    
		- name: create multi user.      
		  user:        
		  	name: "{{item.iname}}"        
		  	password: "{{item.ipass | password_hash('sha512')}}"      
		  	loop:        
		  		- { iname: 'term', ipass: '123456' }        
		  		- { iname: 'amy' , ipass: '654321' }
#loop循环第一次调用user模块创建用户,user模块创建用户会读取loop里面的第一个值.
#loop第一个值里面有两个子值,iname和ipass#创建用户item.iname就是loop第一个值里面的iname=term
#修改密码item.ipass就是loop第一个值里面的ipass=123456#loop循环第二次调用user模块创建用户,user模块创建用户会读取loop里面的第二个值.
#loop第二个值里面有两个子值,iname和ipass#创建用户item.iname就是loop第二个值里面的iname=amy#修改密码item.ipass就是loop第二个值里面的ipass=654321
```

### 2 案例2：加密敏感数据

#### 2.1 问题

本案例要求，使用ansible-vault对敏感数据进行加密处理，具体要求如下：

- 使用ansible-vault管理敏感数据

#### 2.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：使用ansible-vault处理敏感数据

###### 1）加密敏感数据。

encrypt（加密）、decrypt（解密）、view（查看）。

```shell
[root@control ansible]# echo 123456 > data.txt               #新建测试文件
[root@control ansible]# ansible-vault encrypt data.txt      #加密文件
[root@control ansible]# cat data.txt[root@control ansible]# ansible-vault view data.txt         #查看加密文件
```

###### 2）修改密码（rekey）

```shell
[root@control ansible]# ansible-vault rekey data.txt             #修改密码
Vault password: <旧密码>New 
Vault password: <新密码>
Confirm New Vault password:<确认新密码>
```

###### 3）解密文件

```shell
[root@control ansible]# ansible-vault decrypt data.txt      #解密文件
[root@control ansible]# cat data.txt
```

###### 4）使用密码文件

加密、解密每次都输入密码很麻烦，可以将密码写入文件。

```shell
[root@control ansible]# echo "I'm secret data" > data.txt       #需要加密的敏感数据
[root@control ansible]# echo 123456 > pass.txt                   #加密的密码
[root@control ansible]# ansible-vault  encrypt --vault-id=pass.txt  data.txt 
[root@control ansible]# cat data.txt
[root@control ansible]# ansible-vault decrypt --vault-id=pass.txt data.txt
[root@control ansible]# cat data.txt
```

### 3 案例3：Ansible Roles

#### 3.1 问题

学习Ansible Roles基本概念，掌握Roles应用案例，具体要求如下：

- 自定义Ansible Role
- 编写playbook调用role
- 使用ansible-galaxy管理Roles

#### 3.2 方案

在实际生产环境中，为了实现不同的功能，我们会编写大量的playbook文件。而且，每个playbook还可能会调用其他文件（如变量文件），对于海量的、无规律的文件，管理起来非常痛苦！

Ansible从1.2版本开始支持Role（角色），Role（角色）是管理ansible文件的一种规范（目录结构），Role（角色）会按照标准的规范，自动到特定的目录和文件中读取数据。

如果我们创建了一个名称为user.example的Role（角色），则其标准的目录结构如下图-1所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00107)

图-1

Roles目录结构中主要文件的作用是什么呢？

- defualts/main.yml：定义变量的缺省值，优先级较低
- files目录：存储静态文件的目录，如tar包、音乐、视频等
- handlers/main.yml:定义handlers
- meta/main.yml:写作者、版本等描述信息
- README.md:整个角色(role)的描述信息
- tasks/main.yml:定义任务的地方
- templates目录：存放动态数据文件的地方（文件中包含了变量的模板文件）
- vars/main.yml:定义变量，优先级高

##### 步骤一：Role应用案例

###### 1）创建Roles

下面这个案例目的：编写一个包含变量的模板文件，编写任务调用template模块，将模板文件拷贝给被管理端主机。

ansible-galaxy命令可以创建、管理自己的roles。

```shell
[root@control ansible]# mkdir ~/ansible/roles
[root@control ansible]# ansible-galaxy init  ~/ansible/roles/issue
#创建一个Role，该Role的目的是拷贝自己新建的一个模板文件到远程主机的/etc/issue
[root@control ansible]# tree  ~/ansible/roles/issue/
#查看目录结构，如果没有tree命令则需要使用yum安装该软件
```

###### 2）修改Role文件

定义名称为myfile.txt的模板文件（该文件包含变量,因此必须放置templates目录）

```shell
[root@control ansible]# vim ~/ansible/roles/issue/templates/myfile.txt
This is the system {{ansible_hostname}}
Today's date is:{{ansible_date_time.date}}Contact to {{ admin }}
```

自定义变量文件（前面调用了admin这个变量，这里需要定义admin变量并赋值）

```yaml
[root@control ansible]# vim ~/ansible/roles/issue/vars/main.yml
---
# vars file for /root/ansible/roles/issue
admin: yoyo@tedu.cn #变量名为admin，变量的值为yoyo@tedu.cn
```

文件准备好了，计算机不会自动将文件拷贝给被管理端主机！需要编写任务调用模块实现拷贝的功能。

修改任务文件，任务文件中不需要tasks关键词，Role的各个文件之间相互调用不需要写文件的路径。

```yaml
[root@control ansible]# vim ~/ansible/roles/issue/tasks/main.yml
---
# tasks file for /root/ansible/roles/issue
-  name: delever issue file   
   template:     src: myfile.txt     
   dest: /etc/issue
   #调用template模块将myfile.txt文件拷贝给被管理端主机.
```

###### 3）在Playbook中调用Role

Role创建好了，role不会自己运行，需要编写一个剧本调用上面的role。

编写playbook剧本文件,通过roles关键词调用role。

```yaml
[root@control ansible]# vim  ~/ansible/issue.yml
---
- hosts: test  
  roles:    
    - issue
#   - role2              #支持加载多个role
```

修改ansible.cfg配置文件，定义roles目录。

```shell
[root@control ansible]# vim  ~/ansible/ansible.cfg 
[defaults]inventory = ./inventory
roles_path = ./roles                    #指定到哪个目录下找
roleremote_user = alice
[privilege_escalation]
become=True
become_method=sudo
become_user=root
become_ask_pass=False
```

##### 步骤二：ansible-galaxy命令

公共Roles仓库(https://galaxy.ansible.com)管理。

```shell
[root@control ansible]# ansible-galaxy  search 'httpd' #联网搜索roles
[root@control ansible]# ansible-galaxy info acandid.httpd #查看roles基本信息
[root@control ansible]# ansible-galaxy install acandid.httpd -p ~/ansible/roles/
#下载roles到特定的目录，-p可以指定下载到哪个目录
```

使用ansible-galaxy install可以直接下载Role，也可以编写requirements.yml文件下载Role。

```shell
[root@control ansible]# vim ~/ansible/roles/requirements.yml 
#格式一：可以直接从Ansible Galaxy官网下载- src: acandid.httpd
#格式二：可以从某个git服务器下载- src: http://gitlab.com/xxx/xxx.git  scm: git  version: 56e00a54  name: nginx-acme
#格式三：可以指定位置下载tar包，支持http、https、file- src:  http://example.com/myrole.tar  name:  myrole
[root@control ansible]# ansible-galaxy install \-r ~/ansible/roles/requirements.yml \-p roles
# -r后面跟文件名,该文件中包含了需要下载哪些role以及他们的链接位置# -p 指定将下载的role保存到哪个目录
```

### 4 案例4：综合练习（自动化部署Web集群）

#### 4.1 问题

晚自习课外综合练习题，创建一个名为cluster的role，完成一个综合项目，具体要求如下：

- 创建Role，通过Role完成项目
- 部署Nginx调度器
- 部署2台http服务器

#### 4.2 方案

晚自习综合练习题实验所需主机清单如表-1所示。

表-1

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable00106)

##### 步骤一：部署两台后端web服务器

###### 1）创建role角色

```shell
[root@control ansible]# ansible-galaxy  init  ~/ansible/roles/http
```

###### 2）修改role配置文件，准备2台http网站的素材

安装httpd，拷贝一个网页文件。

```yaml
[root@control ansible]# vim roles/http/tasks/main.yml
---
- name: install httpd  
  yum:    
  	name: httpd    
    state: present
- name: create index.html  
	copy:    
		content: "{{ansible_hostname}}"    
		dest: /var/www/html/index.html
- name: set firewalld  
  firewalld:    
  	service: http    
  	state: enabled    
  	permanent: yes    
  	immediate: yes
- name: start httpd  
  service:    
  	name: httpd    
  	state: started    
  	enabled: yes
#文件中包含多个任务，每个任务可以设置一个name名字（也可以没有name）
#第一个任务调用yum模块安装httpd软件包
#第二个任务调用copy模块创建一个新的网页文件(index.html)
#调用copy模块时可以在没有源文件的情况下，直接使用content指定文件的内容
#将该内容直接拷贝到被管理主机的某个文件中(/var/www/html/index.html)
#第三个任务调用firewalld模块，设置防火墙规则，允许访问http服务
#第四个任务调用service模块将httpd服务启动，并设置开机自启。
```

###### 3）编写Playbook调用role，并执行Playbook。

```yaml
[root@control ansible]# vim web.yml
---
- hosts: webserver  
  roles:    	
  		- http
[root@control ansible]# ansible-playbook web.yml
```

##### 步骤二：部署nginx代理服务器

###### 1）创建role角色

```shell
[root@control ansible]# ansible-galaxy  init  ~/ansible/roles/proxy
```

###### 2）准备代理服务器需要的素材

拷贝Nginx源码包，编写一个源码编译安装nginx的shell脚本。

```shell
[root@control ansible]# cp  lnmp_soft/nginx-1.17.6.tar.gz  ~/ansible/roles/proxy/files/
[root@control ansible]# vim ~/ansible/roles/proxy/files/nginx_install.sh
#!/bin/bash
yum -y install gcc pcre-devel openssl-devel make
cd /tmp
tar -xf /tmp/nginx-1.17.6.tar.gz
cd nginx-1.17.6./configure --with-http_ssl_modulemakemake 
install
```

新建一个Nginx代理服务器的配置文件模板。

```shell
[root@control ansible]# vim ~/ansible/roles/proxy/files/nginx.conf
worker_processes  2;
#error_log  logs/error.log;
events {    
	worker_connections  65535;
}
http {    
	include       mime.types;    
	default_type  application/octet-stream;    
	sendfile        on;    
	tcp_nopush     on;    
	keepalive_timeout  65;    
	#gzip  on;
	upstream webs {   
		server 192.168.4.13;   
		server 192.168.4.14;
	}    
	server {        
		listen       80;        
		server_name  localhost;        
		location / {            
			proxy_pass http://webs;            
			root   html;            index  index.html index.htm;        
		}        
		error_page  404              /404.html;        
		error_page   500 502 503 504  /50x.html;        
		location = /50x.html {            
			root   html;        
		}    
	}
}
```

###### 3）修改role配置文件。

```yaml
[root@control ansible]# vim roles/proxy/tasks/main.yml
---
- name: copy nginx-1.17.6.tar.gz to proxy.  
  copy:    src: nginx-1.17.6.tar.gz    
  dest: /tmp/#拷贝源码包软件
- name: install nginx through shell script.  
  script: nginx_install.sh  
  args:    
  	creates: /usr/local/nginx/sbin/nginx
#执行源码编译安装脚本，如果已经安装nginx，则不再执行安装脚本.#args是关键词，设置script模块的参数，通过creates参数做判断，creates也是关键词#creates后面跟文件名，如果creates判断文件存在的话就不再执行script模块对应的命令。
- name: copy nginx.conf to destination host.  
  copy:    
  	src: nginx.conf    
  	dest: /usr/local/nginx/conf/nginx.conf
- name: run nginx service.  
  shell: /usr/local/nginx/sbin/nginx  
  args:    
  	creates: /usr/local/nginx/logs/nginx.pid   #nginx.pid存在，说明nginx已经启动。如果该文件存在，则不再启动nginx。
```

###### 4）编写Playbook调用role,并执行Playbook。

```yaml
[root@control ansible]# vim proxy.yml
---
- hosts: proxy  
  roles:    
      - proxy
[root@control ansible]# ansible-playbook proxy.yml
```

### 附加思维导图

如图-2所示：

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00105)

# CLUSTER

## 01:集群及LVS简介、LVS-NAT集群、LVS-DR集群

### 1 案例1：ipvsadm命令用法

#### 1.1 问题

准备一台Linux服务器，安装ipvsadm软件包，练习使用ipvsadm命令，实现如下功能：

- 使用命令添加基于TCP一些的集群服务
- 在集群中添加若干台后端真实服务器
- 实现同一客户端访问，调度器分配固定服务器
- 会使用ipvsadm实现规则的增、删、改
- 保存ipvsadm规则

#### 1.2 方案

安装ipvsadm软件包，关于ipvsadm的用法可以参考man ipvsadm资料。

常用ipvsadm命令语法格式如表-1及表-2所示。

表－1 ipvsadm命令选项

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable00104)

表－2 ipvsadm语法案例

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable00103)

### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：使用命令增、删、改LVS集群规则

###### 1）创建LVS虚拟集群服务器（算法为加权轮询：wrr）

```shell
[root@proxy ~]# yum -y install ipvsadm
[root@proxy ~]# ipvsadm -A -t 192.168.4.5:80 -s wrr
[root@proxy ~]# ipvsadm -Ln
IP Virtual Server version 1.2.1 (size=4096)
Prot LocalAddress:Port Scheduler Flags
   -> RemoteAddress:Port           Forward Weight ActiveConn InActConn
TCP  192.168.4.5:80 wrr
```

###### 2）为集群添加若干real server

```shell
[root@proxy ~]# ipvsadm -a -t 192.168.4.5:80 -r 192.168.2.100 
[root@proxy ~]# ipvsadm -Ln
IP Virtual Server version 1.2.1 (size=4096)
Prot LocalAddress:Port Scheduler Flags
    -> RemoteAddress:Port           Forward Weight ActiveConn InActConn
TCP  192.168.4.5:80 wrr  
    -> 192.168.2.100:80             router    1      0          0
[root@proxy ~]# ipvsadm -a -t 192.168.4.5:80 -r 192.168.2.200 -m -w 2
[root@proxy ~]# ipvsadm -a -t 192.168.4.5:80 -r 192.168.2.201 -m -w 3
[root@proxy ~]# ipvsadm -a -t 192.168.4.5:80 -r 192.168.2.202 -m -w 4
```

###### 3）修改集群服务器设置(修改调度器算法，将加权轮询修改为轮询)

```shell
[root@proxy ~]# ipvsadm -E -t 192.168.4.5:80 -s rr
[root@proxy ~]# ipvsadm -Ln
IP Virtual Server version 1.2.1 (size=4096)
Prot LocalAddress:Port Scheduler Flags
    -> RemoteAddress:Port         Forward Weight ActiveConn InActConn
TCP  192.168.4.5:80 rr  
	-> 192.168.2.100:80             router    1      0          0           
	-> 192.168.2.200:80             masq      2      0          0           
	-> 192.168.2.201:80             masq      2      0          0           
	-> 192.168.2.202:80             masq      1      0          0
```

###### 4）修改read server（使用-g选项，将模式改为DR模式）

```shell
[root@proxy ~]# ipvsadm -e -t 192.168.4.5:80 -r 192.168.2.202 -g
```

###### 5）查看LVS状态

```shell
[root@proxy ~]# ipvsadm -Ln
```

###### 6）创建另一个集群（算法为最少连接算法；使用-m选项，设置工作模式为NAT模式）

```shell
[root@proxy ~]# ipvsadm -A -t 192.168.4.5:3306 -s lc
[root@proxy ~]# ipvsadm -a -t 192.168.4.5:3306 -r 192.168.2.100 -m
[root@proxy ~]# ipvsadm -a -t 192.168.4.5:3306 -r 192.168.2.200 -m
```

###### 7）永久保存所有规则（非必须的操作）

```shell
[root@proxy ~]# ipvsadm-save -n > /etc/sysconfig/ipvsadm
```

注意：永久规则需要确保ipvsadm服务为开机启动服务才可以。

（systemctl enable ipvsadm）。

###### 8）清空所有规则

```shell
[root@proxy ~]# ipvsadm -C
```

### 2 案例2：部署LVS-NAT集群

#### 2.1 问题

使用LVS实现NAT模式的集群调度服务器，为用户提供Web服务：

- 集群对外公网IP地址为192.168.4.5
- 调度器内网IP地址为192.168.2.5
- 真实Web服务器地址分别为192.168.2.100、192.168.2.200
- 使用加权轮询调度算法，真实服务器权重任意

#### 2.2 方案

实验拓扑结构主机配置细节如表-3所示，注意下面的网卡名称仅为参考，不能照抄。

表-3

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable00102)

使用4台虚拟机，1台作为Director调度器、2台作为Real Server、1台客户端，拓扑结构如图-1所示，注意：web1和web2必须配置网关地址。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00101)

图-1

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：配置基础环境

###### 1）设置Web服务器

```shell
[root@web1 ~]# yum -y install httpd        #安装软件
[root@web1 ~]# echo "192.168.2.100" > /var/www/html/index.html    #创建网页文件[root@web1 ~]# firewall-cmd --set-default-zone=trusted            #设置防火墙[root@web1 ~]# setenforce  0
[root@web1 ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config  [root@web2 ~]# yum -y install httpd        #安装软件
[root@web2 ~]# echo "192.168.2.200" > /var/www/html/index.html    #创建网页文件[root@web2 ~]# firewall-cmd --set-default-zone=trusted            #设置防火墙[root@web2 ~]# setenforce  0
[root@web2 ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
```

###### 2）启动Web服务器软件

```shell
[root@web1 ~]# systemctl restart httpd
[root@web2 ~]# systemctl restart httpd
```

如何验证？

完成后可以使用proxy主机测试下是否可以访问web1和web2

```shell
[root@proxy ~]# curl http://192.168.2.100
[root@proxy ~]# curl http://192.168.2.200
```

###### 3）配置网关，将web1和web2的网关设置为192.168.2.5（不能照抄网卡名称）

如果有4网段的IP，则临时将该网卡关闭nmcli con down 网卡名称

```shell
[root@web1 ~]# nmcli connection modify ens33 \ipv4.method manual ipv4.gateway 192.168.2.5#备注:网卡名称不能照抄,需要自己查看下2.100的网卡名称
[root@web1 ~]# nmcli connection up ens33
[root@web1 ~]# ip route show                #查看默认网关
default via 192.168.2.5 dev ens33          #提示：这里default后面的IP就是默认网关#英语词汇：default（默认，预设值）
… …
[root@web2 ~]# nmcli connection modify ens33 \
ipv4.method manual ipv4.gateway 192.168.2.5
#备注:网卡名称不能照抄,需要自己查看下2.200的网卡名称
[root@web2 ~]# nmcli connection up ens33
[root@web2 ~]# ip route show        #查看默认网关，default后面的IP就是默认网关
```

为什么需要配置网关？

实验拓扑如图-2所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00100)

图-2

为了方便下面所有的IP都采用简写,如4.10代表192.168.4.10，2.100代表192.168.2.100。

英语词汇：source（src）代表源地址，destination（dest或dst）代表目标地址。

LVS采用的是路由器的NAT通讯原理！通讯流程如下：

1.客户端发送请求数据包(src:4.10,dst:4.5)

2.数据包被发送给LVS调度器，调度器做NAT地址转换（外网转内网，内网转外网）

a)数据包被修改为src:4.10,dst:2.100(dst也有可能被修改为2.200，随机的）

b)LVS调度器把数据包转发给后端真正的web服务器（2.100）

3.web1收到数据包开始回应数据（rsc:2.100，dst:4.10）

备注：谁访问就给谁回复数据，因为src是4.10，所以应该给4.10回应数据！

但是，自己是2.100，对方是4.10，跨网段默认无法通讯，如何解决？？？

Web1和web2都需要设置默认网关（也就是192.168.2.5）

4）web1想发送数据给4.10但是又无法与其通讯，所以数据包被交给默认网关

5）LVS调度器（软路由）收到后端web发送过来的数据后，再次做NAT地址转换

a)数据包被修改为src:4.5,dst:4.10

b)LVS调度器把数据包转发给客户端主机

6）客户端接收网页数据内容

注意：客户端访问的是4.5，最后是4.5给客户端回复的网页数据！！！！

##### 步骤二：部署LVS-NAT模式调度器

###### 1)确认调度器的路由转发功能(如果已经开启，可以忽略)

```shell
[root@proxy ~]# echo 1 > /proc/sys/net/ipv4/ip_forward    #开启路由转发，临时有效
[root@proxy ~]# cat /proc/sys/net/ipv4/ip_forward          #查看效果1
[root@proxy ~]# echo "net.ipv4.ip_forward = 1" >> /etc/sysctl.conf
#修改配置文件，设置永久规则，英语词汇：forward（转寄，转发，发送，向前）
```

###### 2）创建集群服务器

```shell
[root@proxy ~]# yum -y install ipvsadm
[root@proxy ~]# ipvsadm -A -t 192.168.4.5:80 -s wrr
# -A(add)是创建添加虚拟服务器集群
# -t(tcp)后面指定集群VIP的地址和端口，协议是tcp协议
# -s后面指定调度算法，如rr（轮询）、wrr（加权轮询）、lc（最少连接）、wlc（加权最少连接）等等
```

###### 3）添加真实服务器

```shell
[root@proxy ~]# ipvsadm -a -t 192.168.4.5:80 -r 192.168.2.100 -w 1 -m
[root@proxy ~]# ipvsadm -a -t 192.168.4.5:80 -r 192.168.2.200 -w 1 -m
#-a(add)往虚拟服务器集群中添加后端真实服务器IP,指定往-t 192.168.4.5:80这个集群中添加
#-r(real)后面跟后端真实服务器的IP和端口，这里不写端口默认是80端口
#-w(weight)指定服务器的权重，权重越大被访问的次数越多，英语词汇：weight（重量，分量）
#-m指定集群工作模式为NAT模式，如果是-g则代表使用DR模式，-i代表TUN模式
```

###### 4）查看规则列表（L是list查看，n是number数字格式显示）

```shell
[root@proxy ~]# ipvsadm -Ln
```

5)设置防火墙，SELinux

```shell
[root@proxy ~]# firewall-cmd --set-default-zone=trusted
[root@proxy ~]# setenforce  0
[root@proxy ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
```

##### 步骤三：客户端测试

客户端client主机使用curl命令反复连接http://192.168.4.5，查看访问的页面是否会轮询到不同的后端真实服务器。



### 3 案例3：部署LVS-DR集群

#### 3.1 问题

使用LVS实现DR模式的集群调度服务器，为用户提供Web服务：

- 客户端IP地址为192.168.4.10
- LVS调度器VIP地址为192.168.4.15
- LVS调度器DIP地址设置为192.168.4.5
- 真实Web服务器地址分别为192.168.4.100、192.168.4.200
- 使用加权轮询调度算法，权重可以任意

说明：

CIP是客户端的IP地址；

VIP是对客户端提供服务的IP地址；

RIP是后端服务器的真实IP地址；

DIP是调度器与后端服务器通信的IP地址（VIP必须配置在虚拟接口）。

#### 3.2 方案

使用4台虚拟机，1台作为客户端、1台作为Director调度器、2台作为Real Server，拓扑结构如图-3所示。实验拓扑结构主机配置细节如表-4所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0099)

图-3

表-4

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable0098)

为什么本实验中web1和web2要采用4网段IP？如图-4所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0097)

图-4

LVS NAT实验请求数据包从LVS调度器进，web的相应数据包也从LVS调度器出，那么LVS调度器就需要承载所有数据的压力，会成为整个集群的瓶颈！！

本实验LVS DR模式的核心需求是希望web1和web2可以不走调度器返回数据！

但是如如-3所示，如果web1和web2采用2.100和2.200这样2网段的IP，又不希望给4.10回复数据走LVS调度器（也就是不给web1和web2配置默认网关为2.5），最后是无法跨网段通讯的！！！

怎么办？核心需求是希望web1和web2可以直接返回数据给客户端！！！

想让web1和web2可以直接返回数据给客户端，可以给web1和web2配置4网段IP，如图-5所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0096)

图-5

这样就可以了吗？答案是否定的！！！网络中的基本原则是A访问B，必须是B返回数据给A，现在4.10访问4.5，最终4.100给4.10返回网页数据，所有数据包都会被丢弃！！！

那怎么办呢？地址欺骗！

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0095)

图-6

如图-6所示，我们给web1和web2再额外添加一个伪装的IP地址，这个IP地址因为是用来做地址欺骗用的，假的就是假的，不能暴露（必须配置在lo本地回环网卡上面）。

lo网卡上面默认配置的IP是127.0.0.1。

如果你家里有非法的1000W，你会天天出去跟别人说你有1000W吗?

#### 3.3 步骤

实现此案例需要按照如下步骤进行。

说明：

CIP是客户端的IP地址；

VIP是对客户端提供服务的IP地址（本案例为192.168.4.15）；

VIP必须配置在虚拟接口（目的是防止地址冲突）；

RIP是后端服务器的真实IP地址（本案例为192.168.4.100和192.168.4.200）；

DIP是调度器与后端服务器通信的IP地址（本案例为192.168.4.5）。

##### 步骤一：配置实验网络环境

###### 1）设置Proxy服务器的VIP和DIP

注意：为了防止冲突，VIP必须要配置在网卡的虚拟接口，网卡名称不能照抄！！！

```shell
[root@proxy ~]# cd /etc/sysconfig/network-scripts/
[root@proxy ~]# cp ifcfg-eth0  ifcfg-eth0:0
[root@proxy ~]# vim ifcfg-eth0:0
TYPE=Ethernet
#网卡类型为：以太网卡
BOOTPROTO=none
#none手动配置IP，或者dhcp自动配置
IPNAME=eth0:0
#网卡名称
DEVICE=eth0:0
#设备名称
ONBOOT=yes
#开机时是否自动激活该网卡
IPADDR=192.168.4.15
#IP地址
PREFIX=24
#子网掩码
[root@proxy ~]# systemctl restart network        #重启网络服务
[root@proxy ~]# ip  a  s             #会看到一个网卡下面有两个IP地址
```

常见问题：RHEL7和Centos7系统中有两个管理网络的服务，有可能冲突？

解决方法：关闭NetworkManager服务后重启network即可。

###### 2）设置Web1服务器网络参数（不能照抄网卡名称）

```shell
[root@web1 ~]# nmcli connection modify eth0 ipv4.method manual \
ipv4.addresses 192.168.4.100/24 connection.autoconnect yes
[root@web1 ~]# nmcli connection up eth0
```

接下来给web1配置VIP地址。

注意：这里的子网掩码必须是32（也就是全255），网络地址与IP地址一样，广播地址与IP地址也一样。

```shell
[root@web1 ~]# cd /etc/sysconfig/network-scripts/
[root@web1 ~]# cp ifcfg-lo  ifcfg-lo:0
[root@web1 ~]# vim ifcfg-lo:0
DEVICE=lo:0
#设备名称
IPADDR=192.168.4.15
#IP地址
NETMASK=255.255.255.255
#子网掩码
NETWORK=192.168.4.15
#网络地址BROADCAST=192.168.4.15
#广播地址ONBOOT=yes
#开机是否激活本网卡
NAME=lo:0
#网卡名称
```

防止地址冲突的问题：

这里因为web1也配置与调度器一样的VIP地址，默认肯定会出现地址冲突；

sysctl.conf文件写入这下面四行的主要目的就是访问192.168.4.15的数据包，只有调度器会响应，其他主机都不做任何响应，这样防止地址冲突的问题。

```shell
[root@web1 ~]# vim /etc/sysctl.conf
#文件末尾手动写入如下4行内容,英语词汇：ignore（忽略、忽视），announce（宣告、广播通知）
net.ipv4.conf.all.arp_ignore = 1
net.ipv4.conf.lo.arp_ignore = 1
net.ipv4.conf.lo.arp_announce = 2
net.ipv4.conf.all.arp_announce = 2
#当有arp广播问谁是192.168.4.15时，本机忽略该ARP广播，不做任何回应（防止进站冲突）
#本机不要向外宣告自己的lo回环地址是192.168.4.15（防止出站冲突）
[root@web1 ~]# sysctl -p
```

重启网络服务

```shell
[root@web1 ~]# systemctl restart network        #重启网络服务
[root@web1 ~]# ip  a   s           #会看到一个网卡下面有两个IP地址
```

常见错误：如果重启网络后未正确配置lo:0，有可能是NetworkManager和network服务有冲突，关闭NetworkManager后重启network即可。（非必须的操作）

```shell
[root@web1 ~]# systemctl stop NetworkManager
[root@web1 ~]# systemctl restart network
```

###### 3）设置Web2服务器网络参数（不能照抄网卡名称）

```shell
[root@web2 ~]# nmcli connection modify eth0 ipv4.method manual \
ipv4.addresses 192.168.4.200/24 connection.autoconnect yes
[root@web2 ~]# nmcli connection up eth0
```

接下来给web2配置VIP地址

注意：这里的子网掩码必须是32（也就是全255），网络地址与IP地址一样，广播地址与IP地址也一样。

```shell
[root@web2 ~]# cd /etc/sysconfig/network-scripts/
[root@web2 ~]# cp ifcfg-lo  ifcfg-lo:0
[root@web2 ~]# vim ifcfg-lo:0
DEVICE=lo:0
#设备名称
IPADDR=192.168.4.15
#IP地址
NETMASK=255.255.255.255
#子网掩码
NETWORK=192.168.4.15
#网络地址
BROADCAST=192.168.4.15
#广播地址
ONBOOT=yes
#开机是否激活该网卡NAME=lo:0#网卡名称
```

防止地址冲突的问题：

这里因为web1也配置与调度器一样的VIP地址，默认肯定会出现地址冲突；

sysctl.conf文件写入这下面四行的主要目的就是访问192.168.4.15的数据包，只有调度器会响应，其他主机都不做任何响应，这样防止地址冲突的问题。

```shell
[root@web2 ~]# vim /etc/sysctl.conf
#手动写入如下4行内容，英语词汇：ignore（忽略、忽视），announce（宣告、广播通知）
net.ipv4.conf.all.arp_ignore = 1
net.ipv4.conf.lo.arp_ignore = 1
net.ipv4.conf.lo.arp_announce = 2
net.ipv4.conf.all.arp_announce = 2
#当有arp广播问谁是192.168.4.15时，本机忽略该ARP广播，不做任何回应（防止进站冲突）
#本机不要向外宣告自己的lo回环地址是192.168.4.15（防止出站冲突）
[root@web2 ~]# sysctl -p
```

重启网络服务

```shell
[root@web2 ~]# systemctl restart network        #重启网络服务
[root@web2 ~]# ip a  s                 #会看到一个网卡下面有两个IP地址
```

常见错误：如果重启网络后未正确配置lo:0，有可能是NetworkManager和network服务有冲突，关闭NetworkManager后重启network即可。（非必须的操作）

```shell
[root@web1 ~]# systemctl stop NetworkManager
[root@web1 ~]# systemctl restart network
```

##### 步骤二：proxy调度器安装软件并部署LVS-DR模式调度器

###### 1）安装软件（如果已经安装，此步骤可以忽略）

```shell
[root@proxy ~]# yum -y install ipvsadm
```

###### 2）清理之前实验的规则，创建新的集群服务器规则

```shell
[root@proxy ~]# ipvsadm -C                                
#清空所有规则
[root@proxy ~]# ipvsadm -A -t 192.168.4.15:80 -s wrr
## -A(add)是创建添加虚拟服务器集群
# -t(tcp)后面指定集群VIP的地址和端口，协议是tcp协议
# -s后面指定调度算法，如rr（轮询）、wrr（加权轮询）、lc（最少连接）、wlc（加权最少连接）等等
```

###### 3）添加真实服务器(-g参数设置LVS工作模式为DR模式，-w设置权重)

```shell
[root@proxy ~]# ipvsadm -a -t 192.168.4.15:80 -r 192.168.4.100 -g -w 1
[root@proxy ~]# ipvsadm -a -t 192.168.4.15:80 -r 192.168.4.200 -g -w 1
#-a(add)往虚拟服务器集群中添加后端真实服务器IP,指定往-t 192.168.4.15:80这个集群中添加
#-r(real)后面跟后端真实服务器的IP和端口，这里不写端口默认是80端口
#-w(weight)指定服务器的权重，权重越大被访问的次数越多，英语词汇：weight（重量，分量）
#-m指定集群工作模式为NAT模式，如果是-g则代表使用DR模式，-i代表TUN模式
```

4）查看规则列表（L代表list查看规则，n代表number数字格式显示）

```shell
[root@proxy ~]# ipvsadm -Ln
TCP  192.168.4.15:80 wrr  
	-> 192.168.4.100:80             Route   1      0          0           
	-> 192.168.4.200:80             Route   1      0          0
```

步骤三：客户端测试

客户端使用curl命令反复连接http://192.168.4.15，查看访问的页面是否会轮询到不同的后端真实服务器。

注意：本实验不可以在proxy主机（LVS调度器）使用curl访问网页验证！！！

为什么？请思考图-7示意图。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0094)

图-7

扩展知识：默认LVS不带健康检查功能，需要自己手动编写动态检测脚本，实现该功能：(参考脚本如下，仅供参考)

```shell
[root@proxy ~]# vim check.sh
#!/bin/bash
VIP=192.168.4.15:80
RIP1=192.168.4.100
RIP2=192.168.4.200
while :
do   
	for IP in $RIP1 $RIP2   
	do           
		curl -s http://$IP &>/dev/null
		if [ $? -eq 0 ];then            
			ipvsadm -Ln |grep -q $IP || ipvsadm -a -t $VIP -r $IP        
		else             
			ipvsadm -Ln |grep -q $IP && ipvsadm -d -t $VIP -r $IP        
		fi   
	done
	sleep 1
done
```



### 附加思维导图

如图-8所示：

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0093)

图-8

[^0-9]: 

## 02：Keepalived热备、Keepalived+LVS、HAProxy服务器

### 1 案例1：Keepalived高可用服务器

#### 1.1 问题

准备三台Linux服务器，两台做Web服务器，并部署Keepalived高可用软件，一台作为客户端主机，实现如下功能：

- 使用Keepalived实现web服务器的高可用
- Web服务器IP地址分别为192.168.4.100和192.168.4.200
- Web服务器的浮动VIP地址为192.168.4.80
- 客户端通过访问VIP地址访问Web页面

#### 1.2 方案

使用3台虚拟机，2台作为Web服务器，并部署Keepalived、1台作为客户端，拓扑结构如图-1所示，主机配置如表-1所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0092)

图-1

表-1

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable0091)

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：配置网络环境（如果在前面课程已经完成该配置，可以忽略此步骤）

###### 1）设置Web1服务器网络参数、配置Web服务（不能照抄网卡名称）

```shell
[root@web1 ~]# nmcli connection modify eth0 ipv4.method manual ipv4.addresses 192.168.4.100/24 connection.autoconnect yes
[root@web1 ~]# nmcli connection up eth0
[root@web1 ~]# yum -y install httpd        #安装软件
[root@web1 ~]# echo "192.168.4.100" > /var/www/html/index.html    #创建网页文件
[root@web1 ~]# systemctl restart httpd        #启动服务器
```

###### 2）设置Web2服务器网络参数、配置Web服务（不能照抄网卡名称）

```shell
[root@web2 ~]# nmcli connection modify eth0 ipv4.method manual ipv4.addresses 192.168.4.200/24 connection.autoconnect yes
[root@web2 ~]# nmcli connection up eth0
[root@web2 ~]# yum -y install httpd        #安装软件
[root@web2 ~]# echo "192.168.4.200" > /var/www/html/index.html    #创建网页文件
[root@web2 ~]# systemctl restart httpd        #启动服务器
```

###### 3）配置proxy主机的网络参数（如果已经设置，可以忽略此步骤）

备注：这个实验，我们使用proxy当作客户端主机，网卡名称不能照抄。

```shell
[root@proxy ~]# nmcli connection modify eth0 ipv4.method manual ipv4.addresses 192.168.4.5/24 connection.autoconnect yes
[root@proxy ~]# nmcli connection up eth0
```

##### 步骤二：安装Keepalived软件

注意：两台Web服务器做相同的操作。

```shell
[root@web1 ~]# yum install -y keepalived
[root@web2 ~]# yum install -y keepalived 
```

##### 步骤三：部署Keepalived服务

###### 1）修改web1服务器Keepalived配置文件

```shell
[root@web1 ~]# vim /etc/keepalived/keepalived.conf
global_defs {  
	router_id  web1           #12行，设置路由ID号（实验需要修改）    
	vrrp_iptables           #13行，清除防火墙的拦截规则（实验需要修改，手动添加该行）
}
vrrp_instance VI_1 {  
	state MASTER              #21行，主服务器为MASTER（备服务器需要修改为BACKUP）  
	interface eth0            #22行，VIP配在哪个网卡（实验需要修改，不能照抄网卡名）  
	virtual_router_id 51      #23行，主备服务器VRID号必须一致  
	priority 100              #24行，服务器优先级,优先级高优先获取VIP  
	advert_int 1  
	authentication {    
		auth_type pass    
		auth_pass 1111                         
	}  
	virtual_ipaddress {       #30~32行，谁是主服务器谁获得该VIP（实验需要修改）
	192.168.4.80/24 
	}    
}
```

###### 2）修改web2服务器Keepalived配置文件

```shell
[root@web2 ~]# vim /etc/keepalived/keepalived.conf
global_defs {  
	router_id  web2           #12行，设置路由ID号（实验需要修改）  
	vrrp_iptables             #13行，清除防火墙的拦截规则（实验需要修改，手动添加该行） 
}
vrrp_instance VI_1 {  
	state BACKUP              #21行，备服务器为BACKUP（实验需要修改）  
	interface eth0            #22行，VIP配在哪个网卡（实验需要修改，不能照抄网卡名）  
	virtual_router_id 51      #23行，主辅VRID号必须一致  
	priority 50               #24行，服务器优先级（实验需要修改）  
	advert_int 1  
	authentication {     
		auth_type pass     
		auth_pass 1111                     
	}  
	virtual_ipaddress {       #30~32行，谁是主服务器谁配置VIP（实验需要修改）
	192.168.4.80/24  
	}   
}
```

###### 3）启动服务

```shell
[root@web1 ~]# systemctl start keepalived
[root@web2 ~]# systemctl start keepalived
```

###### 4）配置防火墙和SELinux

```shell
[root@web1 ~]# firewall-cmd --set-default-zone=trusted
[root@web1 ~]# sed -i  '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@web1 ~]# setenforce 0
[root@web2 ~]# firewall-cmd --set-default-zone=trusted
[root@web2 ~]# sed -i  '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@web2 ~]# setenforce 0
```

##### 步骤四：测试

###### 1）登录两台Web服务器查看VIP信息

```shell
[root@web1 ~]# ip addr show
[root@web2 ~]# ip addr show
```

###### 2) 客户端访问

客户端使用curl命令连接http://192.168.4.80，查看Web页面；给Web1关机，客户端再次访问http://192.168.4.80，验证是否可以正常访问服务。

### 2 案例2：Keepalived+LVS服务器

#### 2.1 问题

使用Keepalived为LVS调度器提供高可用功能，防止调度器单点故障，为用户提供Web服务：

- LVS1调度器真实IP地址为192.168.4.5
- LVS2调度器真实IP地址为192.168.4.6
- 服务器VIP地址设置为192.168.4.15
- 真实Web服务器地址分别为192.168.4.100、192.168.4.200
- 使用加权轮询调度算法，真实web服务器权重不同

#### 2.2 方案

使用5台虚拟机，1台作为客户端主机、2台作为LVS调度器、2台作为Real Server，实验拓扑环境结构如图-2所示，基础环境配置如表-2所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0090)

图-2

表-2

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable0089)

注意：所有主机都需要配置IP地址与有效的YUM源，网卡名称仅供参考。

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：配置网络环境

###### 1）关闭服务（把案例1中给web1和web2安装的keepalived关闭）

警告：请先将案例1中web1和web2的keepalived关闭！！！

```shell
[root@web1 ~]# systemctl  stop   keepalived
[root@web2 ~]# systemctl  stop   keepalived
```

###### 2）设置Web1服务器的网络参数（不能照抄网卡名称）

```shell
[root@web1 ~]# nmcli connection modify eth0 ipv4.method manual \ipv4.addresses 192.168.4.100/24 connection.autoconnect yes
[root@web1 ~]# nmcli connection up eth0
```

接下来给web1配置VIP地址

注意：这里的子网掩码必须是32（也就是全255），网络地址与IP地址一样，广播地址与IP地址也一样。

```shell
[root@web1 ~]# cd /etc/sysconfig/network-scripts/
[root@web1 ~]# cp ifcfg-lo  ifcfg-lo:0
[root@web1 ~]# vim ifcfg-lo:0
DEVICE=lo:0 #设备名称
IPADDR=192.168.4.15 #IP地址
NETMASK=255.255.255.255 #子网掩码
NETWORK=192.168.4.15 #网络地址
BROADCAST=192.168.4.15 #广播地址
ONBOOT=yes #开机是否激活该网卡
NAME=lo:0 #网卡名称
```

注意：这里因为web1也配置与调度器一样的VIP地址，默认肯定会出现地址冲突。

写入下面这四行的主要目的就是访问192.168.4.15的数据包，只有调度器会响应，其他主机都不做任何响应。

```shell
[root@web1 ~]# vim /etc/sysctl.conf #手动写入如下4行内容，英语词汇：ignore（忽略、忽视），announce（宣告、广播通知）net.ipv4.conf.all.arp_ignore = 1
net.ipv4.conf.lo.arp_ignore = 1
net.ipv4.conf.lo.arp_announce = 2
net.ipv4.conf.all.arp_announce = 2
#arp_ignore(防止进站冲突)
#arp_announce(防出站冲突)
[root@web1 ~]# sysctl  -p                #刷新，让配置文件立刻生效
```

重启网络服务

```shell
[root@web1 ~]# systemctl restart network      #重启网络服务
[root@web1 ~]# ip  a   s                     #查看IP地址
```

###### 3）设置Web2服务器的网络参数（不能照抄网卡名称）

```shell
[root@web2 ~]# nmcli connection modify eth0 ipv4.method manual \ipv4.addresses 192.168.4.200/24 connection.autoconnect yes
[root@web2 ~]# nmcli connection up eth0
```

接下来给web2配置VIP地址

注意：这里的子网掩码必须是32（也就是全255），网络地址与IP地址一样，广播地址与IP地址也一样。

```shell
[root@web2 ~]# cd /etc/sysconfig/network-scripts/
[root@web2 ~]# cp ifcfg-lo  ifcfg-lo:0
[root@web2 ~]# vim ifcfglo:0 
DEVICE=lo:0
IPADDR=192.168.4.15
NETMASK=255.255.255.255
NETWORK=192.168.4.15
BROADCAST=192.168.4.15
ONBOOT=yes
NAME=lo:0
```

注意：这里因为web2也配置与代理一样的VIP地址，默认肯定会出现地址冲突。

写入这四行的主要目的就是访问192.168.4.15的数据包，只有调度器会响应，其他主机都不做任何响应。

```shell
[root@web2 ~]# vim /etc/sysctl.conf #手动写入如下4行内容，英语词汇：ignore（忽略、忽视），announce（宣告、广播通知）net.ipv4.conf.all.arp_ignore = 1
net.ipv4.conf.lo.arp_ignore = 1
net.ipv4.conf.lo.arp_announce = 2
net.ipv4.conf.all.arp_announce = 2
#arp_ignore(防止进站冲突)
#arp_announce(防出站冲突)
[root@web2 ~]# sysctl  -p             #刷新，让配置文件立刻生效
```

重启网络服务

```shell
[root@web2 ~]# systemctl restart network     #重启网络服务
[root@web2 ~]# ip a  s                        #查看IP地址
```

###### 4）配置proxy主机的网络参数(不配置VIP，VIP由keepalvied自动配置)

把前面课程创建VIP的网卡配置文件直接删除。

备注：不能照抄网卡名称。

```shell
[root@proxy ~]# nmcli connection modify eth0 ipv4.method manual \ipv4.addresses 192.168.4.5/24 connection.autoconnect yes
[root@proxy ~]# nmcli connection up eth0
```

###### 5）配置proxy2主机的网络参数(不配置VIP，VIP由keepalvied自动配置)

注意：按照前面的课程环境，默认没有该虚拟机，需要重新建一台虚拟机proxy2。

备注：不能照抄网卡名称。

```shell
[root@proxy2 ~]# nmcli connection modify eth0 ipv4.method manual \ipv4.addresses 192.168.4.6/24 connection.autoconnect yes
[root@proxy2 ~]# nmcli connection up eth0
```

##### 步骤二：配置后台web服务

###### 1）安装软件，自定义Web页面（web1和web2主机）

```shell
[root@web1 ~]# yum -y install httpd
[root@web1 ~]# echo "192.168.4.100" > /var/www/html/index.html
[root@web2 ~]# yum -y install httpd
[root@web2 ~]# echo "192.168.4.200" > /var/www/html/index.html
```

###### 2）启动Web服务器软件(web1和web2主机)

```shell
[root@web1 ~]# systemctl start httpd ; systemctl enable httpd
[root@web2 ~]# systemctl start httpd ; systemctl enable httpd
```

##### 步骤三：调度器安装Keepalived与ipvsadm软件

注意：两台LVS调度器执行相同的操作（如何已经安装软件，可忽略此步骤）。

安装软件

```shell
[root@proxy ~]# yum install -y keepalived
[root@proxy ~]# systemctl enable keepalived
[root@proxy ~]# yum install -y ipvsadm
[root@proxy ~]# ipvsadm -C
[root@proxy2 ~]# yum install -y keepalived
[root@proxy2 ~]# systemctl enable keepalived
[root@proxy2 ~]# yum install -y ipvsadm
[root@proxy2 ~]# ipvsadm -C
```

##### 步骤四：部署Keepalived实现LVS-DR模式调度器的高可用

###### 1）LVS1调度器设置Keepalived，并启动服务（在192.168.4.5主机操作）

```shell
[root@proxy ~]# vim /etc/keepalived/keepalived.conf
global_defs {  
	router_id  lvs1          #12行，设置路由ID号(实验需要修改)  
	vrrp_iptables            #13行，清除防火墙的拦截规则（实验需要修改，手动添加）   
}
vrrp_instance VI_1 {  
	state MASTER             #21行，主服务器为MASTER  
	interface eth0           #22行，定义网络接口（不能照抄网卡名）  
	virtual_router_id 51     #23行，主辅VRID号必须一致  
	priority 100             #24行，服务器优先级  
	advert_int 1  
	authentication {    
	auth_type pass    
	auth_pass 1111                         
	}  
	virtual_ipaddress {      #30~32行，配置VIP（实验需要修改）
		192.168.4.15/24  
	}   
}
virtual_server 15 80 {        #设置ipvsadm的VIP规则（实验需要修改）  
	delay_loop 6                          #默认健康检查延迟6秒  
	lb_algo rr                            #设置LVS调度算法为RR  
	lb_kind DR                            #设置LVS的模式为DR（实验需要修改）  
	#persistence_timeout 50               #（实验需要删除）#注意persistence_timeout的作用是保持连接#开启后，客户端在一定时间内(50秒)始终访问相同服务器  
	protocol TCP                          #TCP协议  
	real_server 192.168.4.100 80 {        #设置后端web服务器真实IP（实验需要修改）    
		weight 1                            #设置权重为1    
		TCP_CHECK {                         #对后台real_server做健康检查（实验需要修改）    
			connect_timeout 3                   #健康检查的超时时间3秒    
			nb_get_retry 3                      #健康检查的重试次数3次        
			delay_before_retry 3            #健康检查的间隔时间3秒    
		}  
	} 
	real_server 192.168.4.200 80 {         #设置后端web服务器真实IP（实验需要修改）    
		weight 2                            #设置权重为2    
		TCP_CHECK {                         #对后台real_server做健康检查（实验需要修改）         
			connect_timeout 3              #健康检查的超时时间3秒    
			nb_get_retry 3                      #健康检查的重试次数3次    
			delay_before_retry 3                #健康检查的间隔时间3秒    
		}  
	}
}
[root@proxy1 ~]# systemctl start keepalived
[root@proxy1 ~]# ipvsadm -Ln           #查看LVS规则
[root@proxy1 ~]# ip a  s               #查看VIP配置
```

###### 2）LVS2调度器设置Keepalived（在192.168.4.6主机操作）

```shell
[root@proxy2 ~]# vim /etc/keepalived/keepalived.conf
global_defs {   
	router_id  lvs2                     #12行，设置路由ID号（实验需要修改） 
	vrrp_iptables                       #13行，清除防火墙的拦截规则（实验需要修改，手动添加）   
}
vrrp_instance VI_1 {  
	state BACKUP                          #21行，从服务器为BACKUP（实验需要修改）  
	interface eth0                        #22行，定义网络接口（不能照抄网卡名）  
	virtual_router_id 51                  #23行，主辅VRID号必须一致  
	priority 50                           #24行，服务器优先级（实验需要修改）  
	advert_int 1  
	authentication {    
		auth_type pass    
		auth_pass 1111  
	}  
	virtual_ipaddress {                   #30~32行，设置VIP（实验需要修改）
		192.168.4.15/24  
	}  
}
virtual_server 192.168.4.15 80 {        #自动设置LVS规则（实验需要修改）  
	delay_loop 6  lb_algo  rr                           #设置LVS调度算法为RR  
	lb_kind DR                            #设置LVS的模式为DR（实验需要修改） 
	# persistence_timeout 50               #（实验需要删除该行）
	#注意persistence_timeout的作用是保持连接
	#开启后，客户端在一定时间内(50秒)始终访问相同服务器  
	protocol TCP                          #TCP协议  
	real_server 192.168.4.100 80 {        #设置后端web服务器的真实IP（实验需要修改）    
	weight 1                            #设置权重为1    
	TCP_CHECK {                         #对后台real_server做健康检查（实验需要修改）      
	connect_timeout 3                   #健康检查的超时时间3秒    
	nb_get_retry 3                      #健康检查的重试次数3次    
	delay_before_retry 3                #健康检查的间隔时间3秒    
	}  
} 
real_server 192.168.4.200 80 {          #设置后端web服务器的真实IP（实验需要修改）    
	weight 1                             #设置权重为1，权重可以根据需要修改    
	TCP_CHECK {                          #对后台real_server做健康检查（实验需要修改）      
	connect_timeout 3                    #健康检查的超时时间3秒    
	nb_get_retry 3                       #健康检查的重试次数3次    
	delay_before_retry 3                 #健康检查的间隔时间3秒    
	}  
}
[root@proxy2 ~]# systemctl start keepalived
[root@proxy2 ~]# ipvsadm -Ln             #查看LVS规则
[root@proxy2 ~]# ip  a   s               #查看VIP设置
```

##### 步骤五：客户端测试

客户端使用curl命令反复连接http://192.168.4.15，查看访问的页面是否会轮询到不同的后端真实服务器。

### 3 案例3：配置HAProxy负载平衡集群

#### 3.1 问题

准备4台Linux服务器，两台做Web服务器，1台安装HAProxy，1台做客户端，实现如下功能：

- 客户端访问HAProxy，HAProxy分发请求到后端Real Server
- 开启HAProxy监控页面，及时查看调度器状态
- 设置HAProxy为开机启动

#### 3.2 方案

使用4台虚拟机，1台作为HAProxy调度器、2台作为Real Server、1台作为客户端，拓扑结构如图-3所示，具体配置如表-3所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0088)

图-3

表-3

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable0087)

为什么Haproxy的实验不需要开启路由，不需要给web服务器配置网关？

Hapoxy是代理服务器（帮你干活的人或物就是你的代理），通讯流程如图-4所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0086)

图-4

#### 3.3 步骤

实现此案例需要按照如下步骤进行。

web1配置本地真实IP地址（不能照抄网卡名）。

```shell
[root@web1 ~]# nmcli connection modify eth1 ipv4.method manual \
ipv4.addresses 192.168.2.100/24 connection.autoconnect yes
[root@web1 ~]# nmcli connection up eth1
```

Web2配置本地真实IP地址（不能照抄网卡名）。

```shell
[root@web2 ~]# nmcli connection modify eth1 ipv4.method manual \
ipv4.addresses 192.168.2.200/24 connection.autoconnect yes
[root@web2 ~]# nmcli connection up eth1
```

proxy关闭keepalived服务，清理LVS规则，不能照抄网卡名。

```shell
[root@proxy ~]# systemctl stop keepalived
[root@proxy ~]# systemctl disable keepalived
[root@proxy ~]# ipvsadm -C
[root@proxy ~]# nmcli connection modify eth0 ipv4.method manual \
ipv4.addresses 192.168.4.5/24 connection.autoconnect yes
[root@proxy ~]# nmcli connection up eth0
[root@proxy ~]# nmcli connection modify eth1 ipv4.method manual \
ipv4.addresses 192.168.2.5/24 connection.autoconnect yes
[root@proxy ~]# nmcli connection up eth1
```

##### 步骤一：配置后端Web服务器

设置两台后端Web服务（如果已经配置完成，可忽略此步骤）

```shell
[root@web1 ~]# yum -y install httpd
[root@web1 ~]# systemctl start httpd
[root@web1 ~]# echo "192.168.2.100" > /var/www/html/index.html
[root@web2 ~]# yum -y install httpd
[root@web2 ~]# systemctl start httpd
[root@web2 ~]# echo "192.168.2.200" > /var/www/html/index.html
```

##### 步骤二：部署HAProxy服务器

###### 1）配置网络，安装软件

```shell
[root@proxy ~]# yum -y install haproxy
```

###### 2）修改配置文件

```shell
[root@proxy ~]# vim /etc/haproxy/haproxy.cfg
global 
log 127.0.0.1 local2   ##[err warning info debug] 
pidfile /var/run/haproxy.pid ##haproxy的pid存放路径 
user haproxy 
group haproxy 
daemon                    ##以后台进程的方式启动服务defaults 

mode http               ##默认的模式mode { tcp|http|health } 
option dontlognull      ##不记录健康检查的日志信息 
option httpclose        ##每次请求完毕后主动关闭http通道 
option httplog          ##日志类别http日志格式 
option redispatch       ##当某个服务器挂掉后强制定向到其他健康服务器 timeout client 300000   ##客户端连接超时，默认毫秒，也可以加时间单位 timeout server 300000   ##服务器连接超时 
maxconn  3000           ##最大连接数 
retries  3              ##3次连接失败就认为服务不可用，也可以通过后面设置  
listen  websrv-rewrite 0.0.0.0:80             
	balance roundrobin   
	server  web1 192.168.2.100:80 check inter 2000 rise 2 fall 5     	 
	server  web2 192.168.2.200:80 check inter 2000 rise 2 fall 5
#定义集群,listen后面的名称任意，端口为80
#balance指定调度算法为轮询（不能用简写的rr）
#server指定后端真实服务器，web1和web2的名称可以任意
#check代表健康检查，inter设定健康检查的时间间隔，rise定义成功次数，fall定义失败次数
listen stats *:1080        #监听端口    
	stats refresh 30s             #统计页面自动刷新时间    
	stats uri /stats              #统计页面url    
	stats realm Haproxy Manager   #进入管理解面查看状态信息    
	stats auth admin:admin       #统计页面用户名和密码设置
```

###### 3）启动服务器并设置开机启动

```shell
[root@proxy ~]# systemctl restart haproxy
[root@proxy ~]# systemctl enable haproxy
```

##### 步骤三：客户端验证

客户端配置与HAProxy相同网络的IP地址，并使用火狐浏览器访问http://192.168.4.5，测试调度器是否正常工作，客户端访问http://192.168.4.5:1080/stats测试状态监控页面是否正常。访问状态监控页的内容，参考图-5所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0085)

图-5

备注：

Queue队列数据的信息（当前队列数量，最大值，队列限制数量）；

Session rate每秒会话率（当前值，最大值，限制数量）；

Sessions总会话量（当前值，最大值，总量，Lbtot: total number of times a server was selected选中一台服务器所用的总时间）；

Bytes（入站、出站流量）；

Denied（拒绝请求、拒绝回应）；

Errors（错误请求、错误连接、错误回应）；

Warnings（重新尝试警告retry、重新连接redispatches）；

Server(状态、最后检查的时间（多久前执行的最后一次检查）、权重、备份服务器数量、down机服务器数量、down机时长)。

### 附加思维导图，如图-6所示：

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0084)



## 03：Ceph概述、部署Ceph集群、Ceph块存储

### 1 案例1：实验环境

#### 1.1 问题

准备四台虚拟机，其三台作为存储集群节点，一台安装为客户端，实现如下功能：

- 创建1台客户端虚拟机
- 创建3台存储集群虚拟机
- 配置主机名、IP地址、YUM源
- 修改所有主机的主机名
- 配置无密码SSH连接
- 配置NTP时间同步
- 创建虚拟机磁盘

#### 1.2 方案

使用4台虚拟机，1台客户端、3台存储集群服务器，拓扑结构如图-1所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0083)

图-1

所有主机的主机名及对应的IP地址如表-1所示。

注意：所有主机基本系统光盘的YUM源必须提前配置好。

表－1 主机名称及对应IP地址表

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable0082)

Ceph组件架构如图-2所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0081)

图-2

Ceph会对数据进行切割处理，如图-3所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0080)

图-3

Ceph随机读写数据的思路，如图-4所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0079)

图-4

Ceph集群结构如图-5所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0078)

图-5

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：安装前准备

###### 1）为所有节点配置yum源服务器。

把四台虚拟机全部关机；每台虚拟机都添加一个光驱；

做如下相同操作:

右击虚拟机,选【设置】---【添加】---【CD|DVD驱动器】--【完成】；

点击刚刚新建的光盘[CD|DVD],勾选使用ISO映像文件--[浏览]；

找到自己真机的ceph10.iso加载即可。

添加磁盘：

除了客户端，所有3台ceph服务器都添加2块20G磁盘。

启动所有虚拟机后，查看磁盘情况:

易错点：看清楚哪个是系统光盘，哪个是ceph光盘，光盘是否有顺序错乱！

```shell
[root@client ~]# lsblk
[root@node1 ~]# lsblk
[root@node2 ~]# lsblk
[root@node3 ~]# lsblk
```

###### 2）所有主机设置防火墙和SELinux

```shell
[root@client ~]# firewall-cmd --set-default-zone=trusted
[root@client ~]# sed -i '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@client ~]# setenforce 0
[root@node1 ~]# firewall-cmd --set-default-zone=trusted
[root@node1 ~]# sed -i '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@node1 ~]# setenforce 0
[root@node2 ~]# firewall-cmd --set-default-zone=trusted
[root@node2 ~]# sed -i '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@node2 ~]# setenforce 0
[root@node3 ~]# firewall-cmd --set-default-zone=trusted
[root@node3 ~]# sed -i '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@node3 ~]# setenforce 0
```

###### 3）所有主机挂载ceph光盘和系统光盘

易错点：【不能照抄、不能照抄、不能照抄】，需要根据实际情况操作，

案例假设是将系统光盘挂载到/media目录，将ceph光盘挂载到/ceph目录。

```shell
[root@client ~]# umount /dev/sr0
[root@client ~]# umount /dev/sr1             #未挂载的话会报错
[root@client ~]# mkdir  /ceph
[root@client ~]# vim  /etc/fstab    
/dev/sr0    /ceph     iso9660   defaults   0  0       #需要根据实际情况挂载（看清楚哪个是ceph光盘，该挂载到哪个目录）  /dev/sr1    /media    iso9660   defaults   0  0       #需要根据实际情况挂载（看清楚那额是系统光盘，该挂载到哪个目录）
#切记不能照抄，切记！！切记！！切记！！切记！！
[root@client ~]# mount -a
[root@client ~]# lsblk
[root@node1 ~]# umount /dev/sr0
[root@node1 ~]# umount /dev/sr1
[root@node1 ~]# mkdir /ceph
[root@node1 ~]# vim /etc/fstab    
/dev/sr0    /ceph     iso9660   defaults   0  0      #需要根据实际情况挂载（看清楚哪个是ceph光盘，该挂载到哪个目录）    /dev/sr1    /media    iso9660   defaults   0  0      #需要根据实际情况挂载（看清楚那额是系统光盘，该挂载到哪个目录）
#切记不能照抄，切记！！切记！！切记！！切记！！
[root@node1 ~]# mount -a
[root@node2 ~]# umount /dev/sr0
[root@node2 ~]# umount /dev/sr1
[root@node2 ~]# mkdir /ceph
[root@node2 ~]# vim /etc/fstab     
/dev/sr0    /ceph     iso9660   defaults   0  0       #需要根据实际情况挂载（看清楚哪个是ceph光盘，该挂载到哪个目录）  /dev/sr1    /media    iso9660   defaults   0  0       #需要根据实际情况挂载（看清楚那额是系统光盘，该挂载到哪个目录）
#切记不能照抄，切记！！切记！！切记！！切记！！
[root@node2 ~]# mount -a
[root@node3 ~]# umount /dev/sr0
[root@node3 ~]# umount /dev/sr1
[root@node3 ~]# mkdir /ceph
[root@node3 ~]# vim /etc/fstab   
/dev/sr0    /ceph     iso9660   defaults   0  0        #需要根据实际情况挂载（看清楚哪个是ceph光盘，该挂载到哪个目录）  /dev/sr1    /media    iso9660   defaults   0  0        #需要根据实际情况挂载（看清楚那额是系统光盘，该挂载到哪个目录）
#切记不能照抄，切记！！切记！！切记！！切记！！
[root@node3 ~]# mount -a
```

###### 4）配置无密码连接(包括自己远程自己也不需要密码)，在node1操作。

```shell
[root@node1 ~]# ssh-keygen   -f /root/.ssh/id_rsa    -N ''
#-f后面跟密钥的文件名称（希望创建密钥到哪个文件）
#-N ''代表不给密钥配置密钥（不能给密钥配置密码）
[root@node1 ~]# for i in 10  11  12  13 
do     
ssh-copy-id  192.168.4.$i 
done
#通过ssh-copy-id将密钥传递给192.168.4.10、192.168.4.11、192.168.4.12、192.168.4.13
```

###### 5）修改/etc/hosts并同步到所有主机。

注意：/etc/hosts解析的域名要与本机主机名一致！！！！

```shell
 [root@node1 ~]# vim /etc/hosts     #修改文件，手动添加如下内容（不要删除文件原有内容）
 ... ...
 192.168.4.10     client
 192.168.4.11     node1
 192.168.4.12     node2
 192.168.4.13     node3
```

提示：/etc/hosts解析的域名必须与本机主机名一致！！！

将/etc/hosts文件拷贝给所有其他主机（client、node1、node2、node3）

```shell
[root@node1 ~]# for i in client node1  node2  node3
do
scp  /etc/hosts   $i:/etc/
done
```

###### 6）修改所有节点都需要配置YUM源，并同步到所有主机。

```shell
[root@node1 ~]# vim /etc/yum.repos.d/ceph.repo    #新建YUM源配置文件，内容如下
[mon]
name=mon
baseurl=file:///ceph/MON
gpgcheck=0
[osd]
name=osd
baseurl=file:///ceph/OSD
gpgcheck=0
[tools]
name=tools
baseurl=file:///ceph/Tools
gpgcheck=0
[root@node1 ~]# yum clean all               #清空缓存
[root@node1 ~]# yum repolist                
#验证YUM源软件数量源标识            源名称                    状态
Dvd                redhat                    9,911
Mon                mon                        41
Osd                osd                        28
Tools            tools                    33
repolist: 10,013
[root@node1 ~]# for i in  client  node1  node2  node3
do
scp  /etc/yum.repos.d/ceph.repo   $i:/etc/yum.repos.d/
done
```

###### 7）给所有节点安装ceph相关软件包。

```shell
[root@node1 ceph-cluster]# for i in node1 node2 node3
do    
ssh  $i "yum -y install ceph-mon ceph-osd ceph-mds ceph-radosgw"
done 
```

###### 8）Client主机配置NTP服务器。

```shell
[root@client ~]# yum -y install chrony
[root@client ~]# vim /etc/chrony.conf    
allow 192.168.4.0/24        #修改26行    
local stratum 10            #修改29行(去注释即可)
[root@client ~]# systemctl restart chronyd
```

###### 9）node1，node2，node3修改NTP客户

```shell
[root@node1 ~]# vim /etc/chrony.conf
server 192.168.4.10   iburst              #配置文件第二行，手动添加一行新内容
[root@node1 ~]# systemctl restart chronyd
[root@node1 ~]# chronyc sources -v        
#查看同步结果，应该是^*
[root@node2 ~]# vim /etc/chrony.conf
server 192.168.4.10   iburst              #配置文件第二行，手动添加一行新内容
[root@node2 ~]# systemctl restart chronyd
[root@node2 ~]# chronyc sources -v            
#查看同步结果，应该是^*
[root@node3 ~]# vim /etc/chrony.conf
server 192.168.4.10   iburst              #配置文件第二行，手动添加一行新内容
[root@node3 ~]# systemctl restart chronyd
[root@node3 ~]# chronyc sources -v       
#查看同步结果，应该是^*
```



### 2 案例2：部署ceph集群

#### 2.1 问题

沿用练习一，部署Ceph集群服务器，实现以下目标：

- 安装部署工具ceph-deploy
- 创建ceph集群
- 准备日志磁盘分区
- 创建OSD存储空间
- 查看ceph状态，验证

#### 2.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：安装部署软件ceph-deploy

###### 1）在node1安装部署工具，学习工具的语法格式。

```shell
[root@node1 ~]#  yum -y install ceph-deploy
[root@node1 ~]#  ceph-deploy  --help
[root@node1 ~]#  ceph-deploy mon --help
```

###### 2）创建目录（目录名称可以任意，推荐与案例一致）

```shell
[root@node1 ~]#  mkdir ceph-cluster
[root@node1 ~]#  cd ceph-cluster/
```

##### 步骤二：部署Ceph集群

###### 1）创建Ceph集群配置,在ceph-cluster目录下生成Ceph配置文件（ceph.conf）。

在ceph.conf配置文件中定义monitor主机是谁。

```shell
[root@node1 ceph-cluster]# ceph-deploy new node1 node2 node3
```

###### 2）初始化所有节点的mon服务，也就是启动mon服务。

拷贝当前目录的配置文件到所有节点的/etc/ceph/目录并启动mon服务。

```shell
[root@node1 ceph-cluster]# ceph-deploy mon create-initial
#配置文件ceph.conf中有三个mon的IP，ceph-deploy脚本知道自己应该远程谁
```

###### 3) 在每个node主机查看自己的服务(注意每台主机服务名称不同)

```shell
[root@node1 ceph-cluster]# systemctl status ceph-mon@node1
[root@node2 ~]# systemctl status ceph-mon@node2
[root@node3 ~]# systemctl status ceph-mon@node3
#备注:管理员可以自己启动（start）、重启（restart）、关闭（stop），查看状态（status）.
#提醒:这些服务在30分钟只能启动3次,超过就报错. 
#StartLimitInterval=30min
#StartLimitBurst=3
#在这个文件中有定义/usr/lib/systemd/system/ceph-mon@.service
#如果修改该文件，需要执行命令
# systemctl  daemon-reload重新加载配置
```

###### 4）查看ceph集群状态（现在状态应该是health HEALTH_ERR）

```shell
[root@node1 ceph-cluster]# ceph -s
```

常见错误及解决方法（非必要操作，有错误可以参考）：

如果提示如下错误信息：（如何无法修复说明环境准备有问题，需要重置所有虚拟机）

```shell
[node1][ERROR ] admin_socket: exception getting command descriptions: [Error 2] No such file or directory
```

解决方案如下（仅在node1操作）：

1）先检查自己的命令是否是在ceph-cluster目录下执行的！！！！如果确认是在该目录下执行的create-initial命令，依然报错，可以使用如下方式修复。

```shell
[root@node1 ceph-cluster]# vim ceph.conf      
#文件最后追加以下内容public_network = 192.168.4.0/24
```

2）修改后重新推送配置文件:

```shell
[root@node1 ceph-cluster]# ceph-deploy --overwrite-conf config push node1 node2 node3
[root@node1 ceph-cluster]# ceph-deploy --overwrite-conf mon  create-initial
```

3）如果还出错，可能是准备实验环境时配置的域名解析和主机名不一致！！！

##### 步骤三：创建OSD

###### 1) 初始化清空磁盘数据（仅node1操作即可）。

初始化磁盘，将所有磁盘分区格式设置为GPT格式（根据实际情况填写磁盘名称）。

```shell
[root@node1 ceph-cluster]# ceph-deploy disk  zap  node1:sdb   node1:sdc   
[root@node1 ceph-cluster]# ceph-deploy disk  zap  node2:sdb   node2:sdc
[root@node1 ceph-cluster]# ceph-deploy disk  zap  node3:sdb   node3:sdc  
#相当于ssh 远程node1，在node1执行parted /dev/sdb  mktable  gpt
#其他主机都是一样的操作
#ceph-deploy是个脚本，这个脚本会自动ssh远程自动创建gpt分区
```

思考题？

```shell
# vim test.sh
#!/bin/bash
case $1 in
user)     
	useradd -u 1000 $2;;
disk)     
	parted  /dev/$2  mktable  gpt;;
esac
# chmod +x test.sh
# ./test.sh  user  jerry
# ./test.sh  disk  sdc
```

执行上面的脚本没有指定账户UID，为什么会自动创建一个UID为1000的用户？

执行上面的脚本没有指定磁盘分区表类型，为什么创建的分区表类型为gpt类型？

上面的脚本如果执行时不给位置变量的参数为怎么样？

###### 2）创建OSD存储空间（仅node1操作即可）

重要：很多同学在这里会出错！将主机名、设备名称输入错误！！！

远程所有node主机，创建分区，格式化磁盘，挂载磁盘，启动osd服务共享磁盘。

```shell
[root@node1 ceph-cluster]# ceph-deploy osd create node1:sdb  node1:sdc
#每个磁盘都会被自动分成两个分区；一个固定5G大小；一个为剩余所有容量
#5G分区为Journal日志缓存；剩余所有空间为数据盘。
[root@node1 ceph-cluster]# ceph-deploy osd create node2:sdb  node2:sdc
[root@node1 ceph-cluster]# ceph-deploy osd create node3:sdb  node3:sdc
```

提醒：ceph-deploy是个脚本，脚本会自动创建分区、格式化、挂载！

怎么验证分区了？怎么验证格式化？怎么验证挂载了？

```shell
[root@node1 ~]# df -Th
[root@node2 ~]# df -Th
[root@node3 ~]# df -Th
```

思考题：请问lsblk和df命令的区别？

###### 3）在三台不同的主机查看OSD服务状态，可以开启、关闭、重启服务。

```shell
[root@node1 ~]# systemctl status ceph-osd@0
[root@node2 ~]# systemctl status ceph-osd@2
[root@node3 ~]# systemctl status ceph-osd@4
#备注:管理员可以自己启动（start）、重启（restart）、关闭（stop），查看状态（status）.
#提醒:这些服务在30分钟只能启动3次,超过就报错.
#StartLimitInterval=30min
#StartLimitBurst=3
#在这个文件中有定义/usr/lib/systemd/system/ceph-osd@.service
#如果修改该文件，需要执行命令
# systemctl  daemon-reload重新加载配置
```

常见错误及解决方法（非必须操作）。

使用osd create创建OSD存储空间时，如提示下面的错误提示：

```shell
[ceph_deploy][ERROR ] RuntimeError: bootstrap-osd keyring not found; run 'gatherkeys'
```

可以使用如下命令修复文件，重新配置ceph的密钥文件：

```shell
[root@node1 ceph-cluster]#  ceph-deploy gatherkeys node1 node2 node3 
```

##### 步骤四：验证测试

###### 1) 查看集群状态。

```shell
[root@node1 ~]#  ceph  -s
[root@node1 ~]#  ceph   osd   tree
```

###### 2）常见错误（非必须操作）。

如果查看状态包含如下信息：

```shell
health: HEALTH_WARN        
		clock skew detected on  node2, node3…  
```

clock skew表示时间不同步，解决办法：请先将所有主机的时间都使用NTP时间同步！！！

Ceph要求所有主机时差不能超过0.05s，否则就会提示WARN。

如果状态还是失败，可以尝试执行如下命令，重启所有ceph服务：

```shell
[root@node1 ~]#  systemctl restart ceph.target
```

### 3 案例3：创建Ceph块存储

#### 3.1 问题

沿用练习一，使用Ceph集群的块存储功能，实现以下目标：

- 创建块存储镜像
- 客户端映射镜像
- 删除镜像

#### 3.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：创建镜像

###### 1）查看存储池，默认存储池名称为rbd。

```shell
[root@node1 ~]# ceph osd lspools
0 rbd,
#查看结果显示，共享池的名称为rbd，这个共享池的编号为0，英语词汇：pool（池塘、水塘）
```

###### 2）创建镜像、查看镜像

```shell
[root@node1 ~]# rbd create demo-image --image-feature  layering --size 10G
#创建demo-image镜像，这里的demo-image创建的镜像名称，名称可以为任意字符。
#size可以指定镜像大小
[root@node1 ~]# rbd create rbd/jacob  --image-feature  layering --size 10G
#在rbd池中创建名称为jacob的镜像（rbd/jacob），镜像名称可以任意
```

\#--image-feature参数指定我们创建的镜像有哪些功能，layering是开启COW功能。

\#提示：ceph镜像支持很多功能，但很多是操作系统不支持的，我们只开启layering。

```shell
[root@node1 ~]# rbd list                    #列出所有镜像
[root@node1 ~]# rbd info demo-image        #查看demo-image这个镜像的详细信息
rbd image 'demo-image':
	size 10240 MB in 2560 objects    
	order 22 (4096 kB objects)    
	block_name_prefix: rbd_data.d3aa2ae8944a    
	format: 2    
	features: layering
```

##### 步骤二：动态调整

###### 1）扩容容量

```shell
[root@node1 ~]# rbd resize --size 15G jacob             
#调整jacob镜像的大小，jacob是镜像的名称，size指定扩容到15G
[root@node1 ~]# rbd info jacob
```

##### 2）缩小容量

```shell
[root@node1 ~]# rbd resize --size 7G jacob --allow-shrink
#英文词汇：allow（允许），shrink（缩小）
[root@node1 ~]# rbd info jacob#查看jacob这个镜像的详细信息（jacob是前面创建的镜像）
```

##### 步骤三：通过KRBD访问

Linux内核可用直接访问Ceph块存储，KVM可用借助于librbd访问Ceph块存储。

客户端访问结构如图-6所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0077)

图-6

###### 1）客户端通过KRBD访问

```shell
#客户端需要安装ceph-common软件包#拷贝配置文件（否则不知道集群在哪）
#拷贝连接密钥（否则无连接权限）
[root@client ~]# yum -y  install ceph-common
[root@client ~]# scp 192.168.4.11:/etc/ceph/ceph.conf  /etc/ceph/
[root@client ~]# scp 192.168.4.11:/etc/ceph/ceph.client.admin.keyring /etc/ceph/
[root@client ~]# rbd map  jacob          #客户端访问映射服务器的jacob共享镜像
[root@client ~]#  lsblk                   #查看结果（会多一块磁盘）
[root@client ~]# rbd showmapped          #查看磁盘名和共享镜像名称的对应关系
id pool image snap device    
0  rbd  jacob -    /dev/rbd0
```

###### 2) 客户端格式化、挂载分区

```shell
[root@client ~]# mkfs.xfs /dev/rbd0                     #格式化，格式为xfs
[root@client ~]# mount /dev/rbd0 /mnt/                  #挂载（可以挂载到任意目录）
[root@client ~]# echo "test" > /mnt/test.txt           #写入数据
```

##### 步骤四：删除镜像

###### 1） 客户端撤销磁盘映射

```shell
[root@client ~]# umount /mnt                      #卸载
[root@client ~]# rbd showmapped                  #查看磁盘名和共享镜像名称的对应关系
id pool image        snap device    
0  rbd  jacob        -    /dev/rbd0
[root@client ~]# rbd unmap /dev/rbd0            #撤销磁盘映射
```

### 附加信息：Ceph操作思路（知识总结）

#### 一、准备工作：

IP，主机名，hosts解析，ssh密钥，时间同步，yum源，防火墙，selinux

#### 二、部署ceph：

##### 1.安装软件

```shell
  ceph-deploy(脚本)  
  ceph-mon  ceph-osd  ceph-mds  ceph-radosgw(集群)
```

##### 2.修改配置启动服务mon

```shell
  mkdir  目录；cd 目录  
  ceph-deploy  new  node1   node2   node3  (生成配置文件)  
  ceph-deploy  mon  create-initial  (拷贝配置文件并启动mon服务)
```

##### 3.启动osd服务共享硬盘

```shell
  ceph-deploy  disk  zap   主机名:磁盘名  ...  ...  
  ceph-deploy  osd  create  主机名:磁盘   ...  ...
```

#### 三、使用Ceph的思路:

##### 1.块共享

```shell
  服务器: rbd  create  创建一个共享镜像  
  客户端: 安装cpeh-common;  cp 配置文件和密钥          
  		 rbd  map  |  rbd  unmap
```

附加知识（如何删除某个OSD，下面的假设是删除osd.4）

```shell
ceph osd tree
ceph osd out osd.4
ceph osd treeceph -s
ceph osd crush remove osd.4
ceph auth del osd.4
ceph -sceph osd rm osd.4
最后要找到对应的主机，umount把osd.4对应的磁盘卸载
```



## 04：块存储应用案例、分布式文件系统、对象存储

### 1 案例1：块存储应用案例

#### 1.1 问题

延续Day03的实验内容，演示块存储的应用案例，实现以下功能：

- 创建镜像快照
- 使用快照还原数据
- 使用快照克隆镜像
- 删除快照

#### 1.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一、创建镜像快照

###### 1) 查看镜像快照（默认所有镜像都没有快照）。

```shell
 [root@node1 ~]# rbd snap ls jacob
 #查看某个镜像有没有快照，jacob是镜像的名称，ls是list查看
```

###### 2) 给镜像创建快照。

```shell
[root@node1 ~]# rbd snap create jacob --snap jacob-snap1
#为jacob镜像创建快照，--snap指定快照名称，快照名称为jacob-snap1，快照名称可以任意
[root@node1 ~]# rbd snap ls jacobSNAPID NAME            SIZE      4 jacob-snap1 15360 MB
```

###### 3) 删除客户端写入的测试文件

```shell
[root@client ~]# rm  -rf   /mnt/test.txt[root@client ~]# umount  /mnt
```

###### 4) 还原快照

```shell
[root@node1 ~]# rbd snap rollback jacob --snap jacob-snap1
# rollback是回滚的意思，使用jacob-snap1快照回滚数据，对jacob镜像进行回滚数据
[root@client ~]# mount /dev/rbd0 /mnt/        #客户端重新挂载分区
[root@client ~]# ls  /mnt                      #查看数据是否被恢复
```

##### 步骤二：创建快照克隆

###### 1）克隆快照

```shell
[root@node1 ~]#  rbd snap protect jacob --snap jacob-snap1    
#保护快照#jacob是镜像名称，jacob-snap1是前面创建的快照（被保护的快照，不可以被删除）
[root@node1 ~]#  rbd snap rm jacob --snap jacob-snap1    #删除被保护的快照，会失败
[root@node1 ~]#  rbd clone jacob --snap jacob-snap1 jacob-clone --image-feature layering
#使用jacob镜像的快照jacob-snap1克隆一个新的名称为jacob-clone的镜像#新镜像名称可以任意
```

###### 2）查看克隆镜像与父镜像快照的关系

```shell
[root@node1 ~]#  rbd info jacob-clone
rbd image 'jacob-clone':    
	size 15360 MB in 3840 objects    
	order 22 (4096 kB objects)    
	block_name_prefix: rbd_data.d3f53d1b58ba    
	format: 2    
	features: layering    
	flags:     
	parent: rbd/jacob@jacob-snap1
#克隆镜像的很多数据都来自于快照链(相当于文件的软链接的概念)#如果希望克隆镜像可以独立工作，就需要将父快照中的数据，全部拷贝一份，但比较耗时！！！
[root@node1 ~]#  rbd flatten jacob-clone        #让新克隆的镜像与快照脱离关系
[root@node1 ~]#  rbd info jacob-clone            #查看镜像信息
rbd image 'jadob-clone':    
	size 15360 MB in 3840 objects    
	order 22 (4096 kB objects)    
	block_name_prefix: rbd_data.d3f53d1b58ba    
	format: 2    
	features: layering    
	flags:                                #注意，父快照信息没了！
```

###### 3）删除快照

```shell
[root@node1 ~]#  rbd snap unprotect jacob --snap jacob-snap1     #取消快照保护
[root@node1 ~]#  rbd snap rm jacob --snap jacob-snap1            #可以删除快照
```

### 2 案例2：Ceph文件系统

#### 2.1 问题

延续前面的实验，实现Ceph文件系统的功能。具体实现有以下功能：

- 部署MDSs节点
- 创建Ceph文件系统
- 客户端挂载文件系统

#### 2.2 方案

前面的块共享，仅允许同时一个客户端访问，无法实现多人同时使用块设备。

而Ceph的文件系统共享则允许多人同时使用。

下面假设使用虚拟机node3，部署MDS节点。

主机的主机名及对应的IP地址如表-1所示。

表－1 主机名称及对应IP地址表

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable0076)

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 1）添加一台虚拟机node3，要求如下：

IP地址:192.168.4.13

主机名:node3

配置yum源（包括操作系统的源、ceph的源）

与Client主机同步时间

node1允许无密码远程node3

修改node1的/etc/hosts，并同步到所有node主机

##### 2）部署元数据服务器

登陆node3，安装ceph-mds软件包（如果前面课程已经安装，此步骤可以忽略）

```shell
[root@node3 ~]# yum -y install ceph-mds 
```

登陆node1部署节点操作

```shell
[root@node1 ~]# cd  /root/ceph-cluster 
#该目录，是最早部署ceph集群时，创建的目录
[root@node1 ceph-cluster]# ceph-deploy mds create node3 
#远程nod3，拷贝集群配置文件，启动mds服务
```

##### 3）创建存储池

备注：一个文件系统是由inode和block两部分组成，效果如图-1所示。

inode存储文件的描述信息（metadata元数据），block中存储真正的数据。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0075)

图-1

```shell
[root@node3 ~]# ceph osd pool create cephfs_data 64
#创建存储池，共享池的名称为cephfs_data，对应有64个PG#共享池名称可以任意
[root@node3 ~]# ceph osd pool create cephfs_metadata 64
#创建存储池，共享池的名称为cephfs_metadata，对应有64个PG
```

PG拓扑如图-2所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0074)

图-2

PG是一个逻辑概念，没有对应的物质形态，是为了方便管理OSD而设计的概念。

为了方便理解，可以把PG想象成为是目录，可以创建32个目录来存放OSD，也可以创建64个目录来存放OSD。

##### 4）创建Ceph文件系统

```shell
[root@node3 ~]# ceph fs new myfs1 cephfs_metadata cephfs_data
#myfs1是名称，名称可以任意，注意，先写metadata池，再写data池
#fs是filesystem的缩写，filesystem中文是文件系统
#默认，只能创建1个文件系统，多余的会报错

[root@node3 ~]# ceph fs ls
name: myfs1, metadata pool: cephfs_metadata, data pools: [cephfs_data ]
```

##### 5）客户端挂载（客户端需要安装ceph-common，前面的课程已经安装）

```shell
[root@client ~]# mount -t ceph 192.168.4.11:6789:/  /mnt  \
-o name=admin,secret=AQBTsdRapUxBKRAANXtteNUyoEmQHveb75bISg==
#注意:-t（type）指定文件系统类型，文件系统类型为ceph
#-o（option）指定mount挂载命令的选项，选项包括name账户名和secret密码
#192.168.4.11为MON节点的IP（不是MDS节点），6789是MON服务的端口号
#admin是用户名,secret后面是密钥
#密钥可以在/etc/ceph/ceph.client.admin.keyring中找到
```

拓扑如图-3所示

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0073)

图-3

思考题：

1)根分区有100G，如果mkdir /{a,b}，则/a和/b存储空间分别是多少？

2)请问lsblk和df命令的区别？

3)如果做NFS的实验，客户端不安装nfs-utils是否可以mount成功？

\##扩展知识：创建ceph用户，查看用户##

```shell
[root@node1 ~]# ceph auth get-or-create client.nb \
osd  'allow *' \
mds  'allow *' \
mon  'allow *'      > 文件名
# >是重定向导出，后面的文件名可以任意，没有文件会创建，有文件则会覆盖文件的内容[root@node1 ~]# ceph auth list              #查看所有用户列表
```

### 3 案例3：创建对象存储服务器

#### 3.1 问题

延续前面的实验，实现Ceph对象存储的功能。具体实现有以下功能：

- 安装部署Rados Gateway
- 启动RGW服务
- 设置RGW的前端服务与端口
- 客户端测试

#### 3.2 步骤

##### 步骤一：部署对象存储服务器

###### 1）准备实验环境，要求如下：

IP地址:192.168.4.13

主机名:node3

配置yum源（包括操作系统的源、ceph的源）

与Client主机同步时间

node1允许无密码远程node3

修改node1的/etc/hosts，并同步到所有node主机

###### 2）部署RGW软件包

```shell
[root@node3 ~]# yum -y install ceph-radosgw
```

###### 3）新建网关实例

拷贝配置文件，启动一个rgw服务

```shell
[root@node1 ~]# cd /root/ceph-cluster
[root@node1 ~]# ceph-deploy rgw create node3        #远程mode3启动rgw服务
```

登陆node3验证服务是否启动

```shell
[root@node3 ~]# ps aux |grep radosgw
ceph      4109  0.2  1.4 2289196 14972 ?       Ssl  22:53   0:00 /usr/bin/radosgw -f --cluster ceph --name client.rgw.node3 --setuser ceph --setgroup ceph
[root@node3 ~]# systemctl  status ceph-radosgw@\*
```

###### 4）修改服务端口

登陆node3，RGW默认服务端口为7480，修改为8000或80更方便客户端记忆和使用

```shell
[root@node3 ~]#  vim  /etc/ceph/ceph.conf
[client.rgw.node3]
host = node3
rgw_frontends = "civetweb port=8000"
#node3为主机名#civetweb是RGW内置的一个web服务
[root@node3 ~]# systemctl  restart ceph-radosgw@\*
```

##### 步骤二：客户端测试（扩展选做实验）

###### 1）curl测试

```shell
[root@client ~]# curl  192.168.4.13:8000
```

###### 2）使用第三方软件访问

登陆node3（RGW）创建账户

```shell
[root@node3 ~]#  radosgw-admin user create \
--uid="testuser" --display-name="First User"
… …"keys": [        
		  {            
		  		"user": "testuser",            
		  		"access_key": "5E42OEGB1M95Y49IBG7B",            
		  		"secret_key": "i8YtM8cs7QDCK3rTRopb0TTPBFJVXdEryRbeLGK6"        
		   }    
		 ],
[root@node5 ~]# radosgw-admin user info --uid=testuser
//testuser为用户名，access_key和secret_key是账户密钥
```

###### 3）客户端安装软件（软件需要自己上网搜索下载）

```shell
[root@client ~]#  yum install s3cmd-2.0.1-1.el7.noarch.rpm
```

修改软件配置（注意，除了下面设置的内容，其他提示都默认回车）

```shell
[root@client ~]#  s3cmd --configure
Access Key: 5E42OEGB1M95Y49IBG7BSecret Key: i8YtM8cs7QDCK3rTRopb0TTPBFJVXdEryRbeLGK6
S3 Endpoint [s3.amazonaws.com]: 192.168.4.13:8000
[%(bucket)s.s3.amazonaws.com]: %(bucket)s.192.168.4.13:8000
Use HTTPS protocol [Yes]: No
Test access with supplied credentials? [Y/n] n
Save settings? [y/N] y#注意，其他提示都默认回车
```

###### 4）创建存储数据的bucket（类似于存储数据的目录）

```shell
[root@client ~]# s3cmd ls
[root@client ~]# s3cmd mb s3://my_bucket
Bucket 's3://my_bucket/' created
[root@client ~]# s3cmd ls
2018-05-09 08:14 s3://my_bucket

[root@client ~]# s3cmd put /var/log/messages s3://my_bucket/log/

[root@client ~]# s3cmd ls s3://my_bucket
DIR s3://my_bucket/log/
[root@client ~]# s3cmd ls s3://my_bucket/log/
2018-05-09 08:19 309034 s3://my_bucket/log/messages 
```

###### 5）测试下载功能

```shell
[root@client ~]# s3cmd get s3://my_bucket/log/messages /tmp/
```

###### 6）测试删除功能

```shell
[root@client ~]# s3cmd del s3://my_bucket/log/messages
```

### 附加知识总结：（Ceph操作思路）

#### 一、准备工作：

IP，主机名，hosts解析，ssh密钥，时间同步，yum源，防火墙，selinux

#### 二、部署ceph：

##### 1.安装软件

```shell
  ceph-deploy(脚本)  
  ceph-mon  ceph-osd  ceph-mds  ceph-radosgw(集群)
```

##### 2.修改配置启动服务mon

```shell
  mkdir  目录；cd 目录  
  ceph-deploy  new  node1   node2   node3  (生成配置文件)  
  ceph-deploy  mon  create-initial  (启动服务)
```

##### 3.启动osd共享硬盘

```shell
  ceph-deploy  disk  zap   主机名:磁盘名  ...  ...  
  ceph-deploy  osd  create  主机名:磁盘   ...  ...
```

#### 三、使用Ceph思路:

##### 1.块共享

```shell
  服务器: rbd  create  创建一个共享镜像  
  客户端: 安装cpeh-common;  cp 配置文件和密钥          
  		  rbd  map  |  rbd  unmap
```

##### 2.文件系统共享(文件系统由inode和block)

服务器: 创建两个共享池(名称任意)

使用两个共享池合并一个文件系统

安装ceph-mds软件，并启动服务(ceph-deploy mds create node3)

```shell
  客户端： mount  -t  MON的IP:6789:/   /挂载点   -o  name=用户名,secret=密码
```

##### 3.对象存储

服务器启动一个radosgw即可(RGW)

```shell
   ceph-deploy  rgw  create  node3
```

#### 四、ceph-deploy脚本用法：

```shell
   ceph-deploy  new   node1  node2  node3    #生成配置文件   
   ceph-deploy  mon   create-initial         #远程所有主机启动mon服务   
   ceph-deploy  disk  zap  主机名:磁盘名       #初始化磁盘   
   ceph-deploy  osd   create  主机名:磁盘名   #远程主机并启动osd服务   
   ceph-deploy  mds   create   主机名        #远程主机并启动mds服务   
   ceph-deploy  rgw   0create  主机名          #远程主机并启动RGW服务
```

### 附加知识（如何删除某个OSD，下面的假设是删除osd.4）

```shell
ceph osd tree
ceph osd out osd.4
ceph osd tree
ceph -s
ceph osd crush remove osd.4
ceph auth del osd.4
ceph -s
ceph osd rm osd.4
最后要找到对应的主机，umount把osd.4对应的磁盘卸载
```

# Cluster-周考

1、【单选题】
(单选题)ipvsadm命令使用什么选项添加真实服务器?
A.-r 
B.-g 
C.-a 
D.-A 
【正确答案】C
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

2、【单选题】
(单选题)ipvsadm命令使用什么选项设置NAT工作模式?
A.-g 
B.-n 
C.-i 
D.-m 
【正确答案】D
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

3、【单选题】
(单选题)下面哪个关键词用来描述集群后端的真实
服务器IP地址？
A.RIP 
B.CIP 
C.VIP 
D.DIP 
【正确答案】A
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

4、【单选题】
(单选题)keepalived的配置文件中使用什么表示主服务器?
A.MASTER 
B.SLAVE 
C.MAIN 
D.BACKUP 
【正确答案】A
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

5、【单选题】
(单选题)CentOS7系统中ISCSI属于哪种类型的存储?
A.块存储
B.直连存储
C.对象存储
D.文件系统存储
【正确答案】A
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

6、【单选题】
(单选题)使用什么工具可以自动化部署ceph集群环境?
A.ceph-install 
B.ceph-deploy 
C.ceph-admin 
D.ceph-push 
【正确答案】B
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

7、【单选题】
(单选题)ipvsadm命令使用什么选项创建虚拟服务器?
A.-g 
B.-a 
C.-A 
D.-r 
【正确答案】C
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

8、【单选题】
(单选题)keepalived的配置文件中使用什么表示从服务器?
A.BACKUP 
B.MAIN 
C.SLAVE 
D.MASTER 
【正确答案】A
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

9、【单选题】
(单选题)ipvsadm命令使用什么选项设置DR工作模式?
A.-g 
B.-n 
C.-i 
D.-m 
【正确答案】A
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

10、【多选题】
(多选题)HaProxy支持下面哪些调度?
A.2层调度
B.7层调度
C.3层调度
D.4层调度
【正确答案】B,D
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 
11、【多选题】
(多选题)Ceph组件有哪些?
A.MDs 
B.ntp 
C.Monitors 
D.OSDs 
【正确答案】A,C,D
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

12、【多选题】
(多选题)LVS常见调度算法有哪些?
A.最少连接 
B.RSA算法 
C.轮询 
D.加权轮询 
【正确答案】A,C,D
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

13、【多选题】
(多选题)下面哪些HTTP状态码表示连接被重定向?
A.302 
B.500 
C.200 
D.301 
【正确答案】A,D
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

14、【多选题】
(多选题)keepalived支持哪些健康检查?
A.对服务名称检查 
B.对mac地址检查 
C.对TCP连接检查 
D.对URL检查 
【正确答案】C,D
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

15、【多选题】
(多选题)LVS有哪些工作模式?
A.NAT模式 
B.TUN模式 
C.PAT模式 
D.DR模式 
【正确答案】A,B,D
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

16、【多选题】
（多选题)常见的存储类型有哪些？
A.对象存储
B.文件系统存储
C.块存储
D.无盘存储
【正确答案】A,B,C
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

17、【多选题】
(多选题)常见的集群分类有哪些？
A.高配置集群 
B.高性能集群 
C.负载均衡集群 
D.高可用集群 
【正确答案】B,C,D
【答题时间】2020-11-05 07:05:29
【答案解析】无
　 

18、【多选题】
(多选题)Ceph支持哪些存储类型?
A.NFS存储 
B.块存储 
C.文件系统存储 
D.对象存储 
【正确答案】B,C,D
【答题时间】2020-11-05 07:05:29
【答案解析】无

# PROJECT1

## 01:服务器硬件、部署LNMP动态网站

### 1 案例1：服务器硬件

#### 1.1 问题

服务器硬件品牌有哪些，服务器硬件组成结构分析：

- 常见服务器品牌介绍
- 服务器硬件组成
- 配置服务器硬件RAID
- Dell服务器iDRAC远程管理配置

#### 1.2 方案

参考视频：http://www.tmooc.cn/course/300254.shtml。

常见服务器品牌包括：IBM服务器、Dell服务器、HP服务器、浪潮服务器、华为服务器。

与普通电脑一样，服务器也是由主板、内存、CPU、磁盘、网卡、显卡、电源、主机箱等硬件设备组成。

服务器分为塔式服务器、机架式服务器、刀片服务器。

RAID是Redundant Arrays of Independent Drives（独立冗余磁盘阵列）的简称，RAID分为很多级别，常用级别有RAID0、RAID1、RAID5、RAID6、RAID10、RAID01。

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：常见服务器品牌

###### 1）Dell服务器是目前IDC机房中普遍采用的服务器品牌。

Dell入门级塔式服务器PowerEdge T340，如图-1所示，该服务器的目标应用是文件/打印，协作/共享，邮件/讯息，备份/恢复，视频监控等。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0072)

图-1 PowerEdge T340服务器

产品配置如下：

- 4核和6核英特尔至强E-2100处理器
- 4个DIMM插槽(高达64GB的内存容量)
- 8个3.5英寸热插拔HDD硬盘
- 4个PCIe 3.0插槽
- 2个1GbE
- 单个或冗余的双495W电源或者单个350W有线电源

Dell高性能塔式服务器PowerEdge T640，如图-2所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0071)

图-2 PowerEdge T640服务器

产品配置如下：

- 双路英特尔至强CPU，每个处理器支持28个内核
- 24个DIMM内存插槽，最高支持192GB内存，仅支持ECC DDR4
- 电源750W、1100W、1600W、2000W、2400W

Dell入门级单路机架式服务器PowerEdge R330（1U=44.45mm=4.45cm），如图-3所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0070)

图-3 PowerEdge R330机架式服务器

产品配置如下：

- 1路CPU，英特尔至强、英特尔奔腾、英特尔酷睿CPU
- 4个DIMM，最高支持64GB内存
- 2.5或3.5寸硬盘，STATA或SAS接口
- 双电源

Dell机架式服务器PowerEdge R740（2u=88.9mm=8.89cm），如图-4所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0069)

图-4 PowerEdge R740服务器

产品配置如下：

- 双路CPU，每个CPU支持28个核心
- 24个DIMM内存插槽，最高192GB，ECC DDR4
- 双电源

###### 2）IBM服务器

IBM机架式服务器X3250M6（1U），如图-5所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0068)

图-5 IBM X3250M6服务器

产品配置如下：

- 1路CPU，英特尔至强处理器
- 4个DIMM内存插槽，最大64G内存
- 4个3.5寸磁盘位，默认无硬盘，最大可配24TB
- 支持RAID 0，1，5
- 一个300W固定电源

###### 3）HP服务器

HPE ProLiant DL380 Gen10 服务器（2U），如图-6所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0067)

图-6 HPE ProLiant DL380 Gen10 服务器

产品配置如下：

- 2路CPU，英特尔至强
- 24个DIMM插槽，支持最大3T DDR4内存
- 24个磁盘接口
- iLO远程管理
- 4个网卡接口

##### 步骤二：服务器硬件组成

###### 1）CPU

英特尔：酷睿八代（i3,i5,i7,i9），酷睿九代(i3,i5,i7,i9)，酷睿十代

至强E（标准版），至强W（高功耗版）

奔腾处理器

AMD： 家用版（锐龙、速龙）

服务器版本（皓龙、霄龙）

###### 2) 内存

常见品牌：金士顿、三星

家用普通内存不具有数据校验功能

服务器配置带ECC数据校验功能的内存条

规格：DDR1、DDR2、DDR3、DDR4、DDR5

###### 3）硬盘

常见品牌：三星、英特尔、希捷、西部数据

家用磁盘接口：SATA

服务器磁盘接口：SAS

SSD固态硬盘

大小：2.5寸、3.5寸

###### 4）远程管理设备

Dell： iDRAC

HP： iLO

IBM： Tivoli/ˈtɪvəli/

##### 步骤三：配置服务器硬件RAID

###### 1）RAID5

服务器开机后根据提示快速按Ctrl+R组合键即可进入RAID配置界面，如图-7所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0066)

图-7

进入RAID配置界面可以看到所有未配置的磁盘列表，主菜单包含：VD Mgmt、PD Mgmt、Ctrl Mgmt、Properties，如图-8所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0065)

图-8

Ctrl+N进入下一页菜单，Ctrl+P进入上一页菜单，通过F2可以进入配置菜单，如图-9所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0064)

图-9

正式配置RAID之前可以使用Clear Config清空所有配置，然后选择Create New VD创建新的RADID磁盘阵列，如图-10所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0063)

图-10

在RAID Level中选择RAID级别，如RAID5（最少需要三块磁盘），并在右侧Physical Disks中选择使用哪些物理磁盘组合RAID，如图-11所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0062)

图-11

点击OK确定后，可以在主菜单中看到刚刚创建的磁盘阵列，按F2选择Properties可以配置该磁盘阵列的高级属性，如图-12所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0061)

图-12

点击Advanced高级，如图-13所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0060)

图-13

在高级属性中开启磁盘缓存，默认未unchanged，需要设置为enable，并可以设置缓存策略：Write Through直写和Write Back回写，write through模式时数据同时被写入缓存和磁盘，安全，但是写入速度慢，write back模式时数据先写入缓存，再写入磁盘，写入速度快，但数据写入缓存时突发断电会导致数据丢失。配置菜单如图-14所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0059)

图-14

创建完RADID后还需要初始化磁盘，菜单如图-15所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0058)

图-15

###### 2）RAID故障恢复

将损坏的磁盘拔掉，替换一块新的磁盘即可，注意需要将新磁盘插入损坏的磁盘相同接口。磁盘大小、品牌尽可能一致。恢复数据时界面会提示Rebuild，效果如图-16所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0057)

图-16

###### 3）配置Hot Spare磁盘

热备磁盘是提前准备一块备用的磁盘（当前并不使用），当RAID磁盘阵列出现损坏后，系统自动使用该热备磁盘，替代损坏的磁盘，从而不需要人工插拔磁盘即可自动修复。

创建新的RAID磁盘阵列时，不要使用完所有磁盘，留一块磁盘做热备磁盘，点击Advanced高级选项即可配置热备磁盘，如图-17所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0056)

图-17

勾选Configure Hot Spare配置热备磁盘，如图-18所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0055)

图-18

在弹出的对话框中勾选需要的热备磁盘即可完成配置，如图-19所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0054)

图-19

###### 4）其他级别的磁盘阵列

其他级别的磁盘阵列配置方式类似，可以根据自己的需要进行配置如RAID10，RAID6等，但是都需要磁盘阵列卡支持才可以配置。

##### 步骤四：Dell服务器iDRAC远程管理配置

###### 1）配置端口重定向

iDRAC（Integrated Dell Remote Access Controller），是戴尔服务器集成的远程控制卡。

iDRAC需要授权使用，有授权的情况下可以直接通过浏览器访问：http://服务器IP，远程管理服务器，没有授权的情况下可以通过端口重定向将服务器上的显示内容重定向到远程管理端的电脑上（一般是用自己的笔记本远程服务器），这种方式不需要授权。

开启服务器后根据提示快速按F2键进入BIOS界面，如图-20所示。





![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0053)

图-20

进入BIOS Settings后，选择Serial Communication菜单，如图-21所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0052)

图-21

将控制台重定向到com2，设置Serial Device=com1，Serial Device=com2，效果如图-22所示。





![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0051)

图-22

###### 2）初始化清空iDRAC设置

进入iDRAC Setting界面选择Rest iDRAC configuration to defaults，如图-23所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0050)

图-23

###### 3）配置iDRAC网络

进入iDRAC Setting界面选择network，如图-24所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0049)

图-24

选择网卡并配置IP地址，如图-25和图-26所示，网段需要根据实际情况自行配置。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0048)

图-25

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0047)

图-26

开启IPMI智能平台管理接口（配置后可以通过命令行管理服务器），客户端安装ipmitool软件包，如图-27所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0046)

图-27

###### 4）配置远程管理账户

进入iDRAC Setting界面选择User Configuration，如图-28所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0045)

图-28

配置账户名称root，并设置密码，如图-29所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0044)

图-29

###### 5）远程管理端主机配置，安装ipmitool软件包

```
[root@centos7 ~]# yum -y install ipmitool
```

常用命令操作列表如下。

```shell
[root@centos7 ~]# ipmitool -I lanplus -U root -H 服务器IP  power status
#查看服务器电源状态
[root@centos7 ~]# ipmitool -I lanplus -U root -H 服务器IP  power on
#开启服务器电源
[root@centos7 ~]# ipmitool -I lanplus -U root -H 服务器IP  power off
#关闭服务器电源
[root@centos7 ~]# ipmitool -I lanplus -U root -H 服务器IP  power reset
#重启服务器电源
[root@centos7 ~]# ipmitool -I lanplus -U root -H 服务器IP  sol activate
#远程管理
```



### 2 案例2：部署LNMP动态网站

#### 2.1 问题

部署LNMP动态网站，实现以下目标：

1. 安装LNMP平台相关软件
2. 配置Nginx实现动静分离
3. 配置数据库，创建账户与密码
4. 上线Wordpress代码
5. 使用Wordpress后台管理界面，调整Wordpress版式

#### 2.2 方案

实验拓扑如图-30所示，做具体实验前请先配置好环境。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0043)

图-30

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：安装部署LNMP软件

备注：mariadb（数据库客户端软件）、mariadb-server（数据库服务器软件）、mariadb-devel（其他客户端软件的依赖包）、php（解释器）、php-fpm（进程管理器服务）、php-mysql（PHP的数据库扩展包）。

###### 1）安装软件包

```shell
[root@centos7 ~]# yum -y install gcc openssl-devel pcre-devel   #安装依赖包
[root@centos7 ~]# tar -xf nginx-1.12.2.tar.gz
[root@centos7 ~]# cd nginx-1.12.2
[root@centos7 nginx-1.12.2]# ./configure   \--with-http_ssl_module   \--with-http_stub_status_module
[root@centos7 nginx-1.12.2]# make && make install
[root@centos7 ~]# yum -y install   mariadb   mariadb-server   mariadb-devel
[root@centos7 ~]# yum -y install   php        php-mysql        php-fpm
```

###### 2)启动服务(nginx、mariadb、php-fpm)

```shell
[root@centos7 ~]# /usr/local/nginx/sbin/nginx             #启动Nginx服务
[root@centos7 ~]# echo "/usr/local/nginx/sbin/nginx" >> /etc/rc.local
[root@centos7 ~]# chmod +x /etc/rc.local
[root@centos7 ~]# ss -utnlp | grep :80                    #查看端口信息
[root@centos7 ~]# systemctl start   mariadb               #启动mariadb服务器
[root@centos7 ~]# systemctl enable  mariadb                #设置开机自启               
[root@centos7 ~]# systemctl start  php-fpm               #启动php-fpm服务
[root@centos7 ~]# systemctl enable php-fpm                #设置开机自启
```

备注：设置防火墙与SELinux.

```shell
[root@centos7 ~]# firewall-cmd --set-default-zone=trusted
[root@centos7 ~]# setenforce  0
[root@centos7 ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
```

附加知识：systemd！！！

源码安装的软件默认无法使用systemd管理，如果需要使用systemd管理源码安装的软件需要手动编写服务的service文件（编写是可以参考其他服务的模板文件）。以下是nginx服务最终编辑好的模板。

Service文件存储路径为/usr/lib/systemd/system/目录。

```shell
[root@centos7 ~]# vim /usr/lib/systemd/system/nginx.service
[Unit]
Description=The Nginx HTTP Server 
#描述信息
After=network.target remote-fs.target nss-lookup.target
#指定启动nginx之前需要其他的其他服务，如network.target等

[Service]
Type=forking
#Type为服务的类型，仅启动一个主进程的服务为simple，需要启动若干子进程的服务为forking
ExecStart=/usr/local/nginx/sbin/nginx
#设置执行systemctl start nginx后需要启动的具体命令.
ExecReload=/usr/local/nginx/sbin/nginx -s reload
#设置执行systemctl reload nginx后需要执行的具体命令.
ExecStop=/bin/kill -s QUIT ${MAINPID}
#设置执行systemctl stop nginx后需要执行的具体命令.

[Install]
WantedBy=multi-user.target
```

###### 3）修改Nginx配置文件，实现动静分离

修改配置文件，通过两个location实现动静分离，一个location匹配动态页面，一个loation匹配其他所有页面。

注意修改默认首页为index.php!！！！

```shell
[root@centos7 ~]# vim /usr/local/nginx/conf/nginx.conf 
...省略部分配置文件内容...
location / {            
	root   html;            
	index  index.php index.html index.htm;        
}
...省略部分配置文件内容...
location ~ \.php$ {            
	root           html;            
	fastcgi_pass   127.0.0.1:9000;            
	fastcgi_index  index.php;            
	include        fastcgi.conf;        
}
...省略部分配置文件内容...
[root@centos7 ~]# /usr/local/nginx/sbin/nginx -s reload            #重新加载配置
```

###### 4）配置数据库账户与权限

为网站提前创建一个数据库、添加账户并设置该账户有数据库访问权限。

```shell
[root@centos7 ~]# mysql
MariaDB [(none)]> create database wordpress character set utf8mb4;
#创建数据库，数据库名称为wordpress，该数据库支持中文（character set utf8mb4）
MariaDB [(none)]> grant all on wordpress.* to wordpress@'localhost' identified by 'wordpress';
#语法格式：grant 权限 on 数据库名.表名  to 用户名@客户端主机 identified by 密码
#创建用户并授权，用户名为wordpress，该用户对wordpress数据库下的所有表有所有权限
#wordpress用户的密码是wordpress，授权该用户可以从localhost主机登录数据库服务器
#all代表所有权限（wordpress用户可以对wordpress数据库中所有表有所有权限）
#wordpress.*代表wordpress数据库中的所有表
MariaDB [(none)]> grant all on wordpress.* to wordpress@'192.168.2.11' identified by 'wordpress';
MariaDB [(none)]> flush privileges;
#刷新权限
MariaDB [(none)]> exit
#退出数据库如何验证？看看是否可以使用新创建的账户登录数据库服务器：
[root@centos7 ~]# mysql -uwordpress -pwordpress -h 192.168.2.11 wordpress
#-u指定数据库账户名称，-p指定数据库账户的密码，-h指定需要远程数据库的IP地址
#最后的wordpress为数据库的名称
```

##### 步骤二：上线wordpress代码

###### 1）上线PHP动态网站代码（wordpress.zip在lnmp_soft目录中）

```shell
[root@centos7 ~]# yum -y install unzip
[root@centos7 ~]# unzip wordpress.zip
[root@centos7 ~]# cd wordpress
[root@centos7 wordpress]# tar -xf wordpress-5.0.3-zh_CN.tar.gz
[root@centos7 wordpress]# cp -r  wordpress/*  /usr/local/nginx/html/
[root@centos7 wordpress]# chown -R apache.apache  /usr/local/nginx/html/ #
```

提示：动态网站运行过程中，php脚本需要对网站目录有读写权限，而php-fpm默认启动用户为apache。（chown所有所有者和所属组时，使用:或者.都可以）

###### 2)初始化网站配置（使用客户端访问web服务器IP）

```
客户端浏览器访问： firefox http://192.168.2.11/
```

第一次访问服务器会自动进入config配置页面，效果如图-31所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0042)

图-31

开发人员在写代码的时候并不知道未来数据库服务器的IP、端口、数据库名称、账户等信息，该配置页面主要的作用就是动态配置数据库信息，根据前面步骤配置的数据库信息填空即可，效果如图-32所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0041)

图-32

点击提交即可完成数据库的初始化工作，php动态脚本会自动在wordpress数据库中创建若干数据表，后期网站的数据都会写入对并的数据表中。效果如图-33所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0040)

图-33

第一次使用Wordpress需要给你的网站设置基本信息，如网站标题、网站管理员账户与密码等信息，配置完成后点击安装wordpress即可，如图-34所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0039)

图-34

##### 步骤三：网站后台管理

###### 1）访问192.168.2.11服务器，进入并熟悉后台管理界面

通常情况下，开发人员会开发一个后台管理界面，当代码上线后，普通用户就可以管理和配置网站页面（需要使用网站的超级管理员身份才可以进入后台界面）。

```
客户端使用浏览器访问： firefox http://192.168.2.11                
```

访问首页后点击如图-35所示的登陆菜单，输入账户和密码进入后台管理界面。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0038)

图-35

或者直接在地址栏中输入后台管理界面的具体URL。

```
客户端使用浏览器访问： firefox  http://192.168.2.11/wp-login.php
```

输入管理员用户名和密码，效果如图-36所示。登陆后台管理界面效果如图-37所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0037)

图-36

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0036)

图-37

###### 2）修改网站主题

Wordpress主题会影响网站的整体外观，我们可以使用默认自带的若干主题。

后台修改网站主题的菜单为<外观>--<主题>，使用默认主题，点击启用即可，如图-38所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0035)

图-38

如果需要更多更新的主题，则可以去官网下载更多新的主题，默认下载的主题格式为zip压缩包。

官方网站主题链接：（https://cn.wordpress.org/themes/browse/popular/）。

将主题下载到服务器本地后，可以在后台管理界面添加主题，<外观>--<主题>--<添加>--<上传主题>--<浏览>--<现在安装>，如图-39所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0034)

图-39

部署新主题的另一种方法是，直接将下载的zip主题包拷贝到wordpress代码的特定目录，如/usr/local/nginx/html/wp-content/themes/目录，然后使用unzip解压主题即可，效果如图-40所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0033)

图-40

###### 3）修改网站小工具

小工具是首页中的各种常用功能菜单，可以添加和删除。

首先可以删除一些不需要的小工具，如最近文章、最近评论等，如图-41所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0032)

图-41

可以通过小工具为网站添加导航功能，使用鼠标将导航菜单拖动到合适的位置即可，默认没有导航菜单，需要自定义创建，如图-42所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0031)

图-42

创建导航菜单后，可以继续创建页面，并将页面添加到导航菜单中。<页面>--<新建页面>即可添加新的页面，如图-43和图-44所示。新的页面内容可以是段落、图像、列表、引语等（每个人根据自己的需要自由发挥）。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0030)

图-43

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0029)

图-44

新的页面添加完成后，可以将其添加到菜单中使用，如图-45所示。访问网站首页即可查看导航菜单的效果，如图-46所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0028)

图-45

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0027)

图-46

###### 4）扩展其他问题

其他有关wordpress的使用方法与技巧，可以参考官方网站的文档资料，文档链接：https://codex.wordpress.org/zh-cn:Main_Page。

### 附加知识（常见面试题）

#### 1）描述raid 0、1、5的特点和优点?

答：Raid0条带卷，可以高效读写，硬盘空间利用率100%，raid1是复制卷可以实现数据的高可靠读写，硬盘空间利率50%，raid5兼得以上两种优点，硬盘空间利用率N-1，仅可用损坏一块硬盘。

#### 2）将目录/opt/bjca3打包备份排除/opt/bjca3/logs目录，传递到远程主机192.168.1.8的/backup目录下？

答：使用--exclude选项在打包时可用排除特定的目录，但是要注意，使用tar 的--exclude 排除打包的时候，不能加“/”，否则还是会把logs目录以及其下的文件打包进去。

错误写法：

```
tar -czvf bjca3.tar.gz --exclude=/opt/bjca3/logs/ /opt/bjca3
```

正确写法：

```
tar -czvf bjca3.tar.gz --exclude=/opt/bjca3/logs /opt/bjca3
```



#### 3) 如何远程查看Linux服务192.168.1.7运行了多少时间？

答：

```
ssh root@192.168.1.7 uptime
```



#### 4）虚拟机常用有几种网络模式？请简述其工作原理或你个人的理解？

答：有桥接模式、隔离模式、NAT模式、路由模式，如图-47所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0026)

图-47

桥接模式：Guest与Host连接到同一个交换机上；通过桥接物理网卡，相当于直连到Host所在网络。（备注：Guest是虚拟机，Host是真实主机）

隔离模式：允许Guest访问同一虚拟交换机上的其他Guest；但是不能访问Host所在的外部网络。

NAT模式（默认）：将Guest虚拟机的默认网关指向Host物理机的虚拟网桥接口的IP地址；Guest共享真机的网络连接，以地址转换的方式访问外网。

路由模式：由Host物理机充当路由器，开启转发；需要额外设置外网与Guest虚拟机之间互访的路由条目，Guest以路由转发的方式访问外网（需要在真机配置iptables规则）。

#### 5）在11月份内，每天的早上6点到12点中，每隔2小时执行一次 /usr/bin/httpd.sh，怎么实现？

答：

```
0 6-12/2 * 11 * /usr/bin/httpd.sh
```



#### 6）如何查看当前系统是否有监听6666端口？

答：

```
netstat -untlp | grep 6666或者ss -nutlp | grep 6666
```



#### 7) 如何显示CPU占用率最高的进程？

答：

```
top，输入大写的P
```



#### 8）用什么命令可以查看上一次服务器启动时间、上一次谁登陆过服务器?

答：

```
last（历史登陆记录），uptime（系统累计运行的时间），who -b(上次启动系统的时间)
```

## 02:网站架构演变、LNP+Mariadb数据库分离、Web服务器集群

### 1 案例1：网站架构演变

#### 1.1 问题

学习从单机架构到集群架构的演变之路：

- 单机版LNMP
- 独立数据库服务器
- Web服务器集群与Session保持
- 动静分离、数据库集群
- 各种缓存服务器
- 业务模型

#### 1.2 步骤

此案例主要是学习网站架构演变的过程，以拓扑图和理论为主，具体实现还需要结合具体的软件。

##### 步骤一：单机版LNMP

单机版网站，拓扑如图-1所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0025)

图-1 单机版网站服务器

用户量少时使用，简单、成本低、存在单点故障。

##### 步骤二：独立数据库服务器

独立数据库服务器是将网站静态文件、代码文件等资料与数据库分离的架构，当用户量增加时单机的处理能力有限，PHP或JAVA代码的执行需要消耗大量CPU资源，数据库的增删改查需要调用大量的内存资源，将两者分离可以减轻服务器的压力，其拓扑结构如图-2所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0024)

图-2 web服务器与数据库分离

Web服务器和数据库服务器的压力都可以得到有效改善，访问量有所增加。但是服务器依然存在单点故障问题。

##### 步骤三：Web服务器集群与Session保持

我们可以通过Nginx、Haproxy代理服务器实现Web负载均衡集群，也可以使用LVS调度器实现Web负载均衡集群。部署完Web集群后还需要考虑如何进行Session会话保持，方法很多，如：根据源IP保持，代理服务器重写Cookie信息，共享文件系统保存session，使用数据库共享session等等。

该架构拓扑如图-3所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0023)

图-3

但是如果只有一台调度器依然会导致单点故障的问题，因此还需要使用Keepalived或Heartbeat之类的软件进行高可用配置，如图-4所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0022)

图-4

对于网站内容而言可以分离为动态页面和静态页面，静态页面就需要数据文件，动态页面则需要CPU解析代码，需要消耗大量的CPU资源，因此可以将静态和动态分离为两组服务器，动态页面有脚本代码组成，是一种基于网页的应用程序，因此这一组服务器也称为应用服务器，其架构如图-5所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0021)

图-5

##### 步骤四：动静分离、数据库集群

随着服务器的增加，虽然性能与并发量得到了明显的提升，但是数据的一致性、管理的便利性成为了新的问题，因此就需要增加统一的存储服务器，实现数据的同步一致，可以使用NFS，GlusterFS、Ceph等软件实现该功能，其架构如图-6所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00119)

图-6

此时所有应用服务器都连接一台数据库服务器进行读写操作，而且后期随着数据库中的数据不断增加，会导致数据库成为整个网站的瓶颈！这就需要我们对数据进行分库分表，创建数据库主从或者数据库集群，实现读写分离，其拓扑如图-7所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00118)

图-7

##### 步骤五：缓存服务器与业务模型

对于静态数据我们可以通过varnish、squid或者nginx进行缓存，将数据缓存到距离用户更近的位置，构建CDN（内容分发网络）架构。

对于传统的SQL数据库而言，我们也可以通过增加NoSQL数据库，实现数据缓存的功能，提升数据库的访问速度。

备注：数据库相关知识在第三阶段课程有详细介绍，第二阶段项目暂时不做数据库优化。

最后，基于前面的架构，我们还可以将网站按照公司的业务进行分离，每个业务都可以是一个独立的集群，如图-8所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00117)

图-8



### 2 案例2：LNP+Mariadb数据库分离

#### 2.1 问题

部署LNP+Mariadb实现数据库与Web服务器分离，实现以下目标：

- 将旧的数据库备份，迁移到新的服务器
- 修改配置调用新的数据库服务器

#### 2.2 方案

实验拓扑如图-9所示，做具体实验前请先配置好环境。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage00116)

图-9

主机配置如表-1所示。

表-1

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable00115)

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：部署数据库服务器

###### 1）准备一台独立的服务器，安装数据库软件包

```shell
[root@database ~]# yum -y install mariadb mariadb-server mariadb-devel
[root@database ~]# systemctl start mariadb
[root@database ~]# systemctl enable mariadb
[root@database ~]# firewall-cmd --set-default-zone=trusted
[root@database ~]# setenforce  0
[root@database ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
```

###### 2)将之前单机版LNMP网站中的数据库迁移到新的数据库服务器。

登陆192.168.2.11主机，备份数据库并拷贝给新的服务器，关闭旧的数据库服务：

```shell
[root@centos7 ~]# mysqldump wordpress > wordpress.bak     #备份数据库到文件（备份的文件名和扩展名任意）
[root@centos7 ~]# scp wordpress.bak 192.168.2.21:/root/    #拷贝备份文件到远程主机
[root@centos7 ~]# systemctl stop mariadb
[root@centos7 ~]# systemctl disable mariadb
```

登陆192.168.2.21主机，创建空数据库，使用备份文件还原数据库：

```mysql
 [root@database ~]# mysql
 MariaDB [(none)]> create database wordpress character set utf8mb4;
 #创建数据库wordpress，该数据库支持中文
 MariaDB [(none)]> exit
```

使用备份文件还原数据：

```mysql
[root@database ~]# mysql wordpress < wordpress.bak        #使用备份文件导入数据到wordpress数据库
```

重新创建账户并授权访问：

```mysql
[root@database ~]# mysql
MariaDB [(none)]> grant all on wordpress.* to wordpress@'%' identified by 'wordpress';
#语法格式：grant 权限 on 数据库名.表名  to 用户名@客户端主机 identified by 密码
#创建用户并授权，用户名为wordpress，该用户对wordpress数据库下的所有表有所有权限
#wordpress用户的密码是wordpress，授权该用户可以从localhost主机登录数据库服务器
#all代表所有权限（wordpress用户可以对wordpress数据库中所有表有所有权限）
#wordpress.*代表wordpress数据库中的所有表
MariaDB [(none)]> flush privileges;#刷新权限
MariaDB [(none)]> exit
```

\#备注：在MySQL和MariaDB中%代表所有，这里是授权任何主机都可以连接数据库。

###### 3）修改wordpress网站配置文件，调用新的数据库服务器。

Wordpress在第一次初始化操作时会自动生产配置文件：wp-config.php，登陆192.168.2.11修改该文件即可调用新的数据库服务。

```shell
[root@centos7 ~]# vim /usr/local/nginx/html/wp-config.php
修改前内容如下：define('DB_HOST', '192.168.2.11');
修改后内容如下：define('DB_HOST', '192.168.2.21');
```

##### 步骤二：客户端测试

###### 1）客户端使用浏览器访问wordpress网站。

```
客户端浏览器访问 firefox http://192.168.2.11
```



### 3 案例3：Web服务器集群

#### 3.1 问题

使用HAProxy部署Web服务器集群，实现以下目标：

- 部署三台Web服务器
- 迁移网站数据，使用NFS实现数据共享
- 部署HAProxy代理服务器实现负载均衡
- 部署DNS域名解析服务器

#### 3.2 方案

实验拓扑如图-10所示，做具体实验前请先配置好环境。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0114)

图-10

备注：实际操作中DNS服务代理服务器部署在同一台主机上（节约虚拟机资源）。

主机配置如表-2所示。

表-2

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable0013)

#### 3.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：部署web2和web3服务器

###### 1）安装LNP软件包

```shell
[root@web2 ~]# yum -y install gcc pcre-devel openssl-devel 
[root@web2 lnmp_soft]# tar -xf nginx-1.12.2.tar.gz
[root@web2 lnmp_soft]# cd nginx-1.12.2/
[root@web2 nginx-1.12.2]# ./configure \--with-http_ssl_module \--with-http_stub_status_module
[root@web2 nginx-1.12.2]# make && make install
[root@web2 ~]# yum -y install php php-fpm php-mysql mariadb-devel
[root@web3 ~]# yum -y install gcc pcre-devel openssl-devel 
[root@web3 lnmp_soft]# tar -xf nginx-1.12.2.tar.gz
[root@web3 lnmp_soft]# cd nginx-1.12.2/
[root@web3 nginx-1.12.2]# ./configure \--with-http_ssl_module \--with-http_stub_status_module
[root@web3 nginx-1.12.2]# make && make install
[root@web3 ~]# yum -y install php php-fpm php-mysql mariadb-devel
```

###### 2）修改nginx配置实现动静分离（web2和web3操作）

web2修改默认首页index.php，配置两个location实现动静分离。

```shell
[root@web2 ~]# vim /usr/local/nginx/conf/nginx.conf
location / {            
	root   html;            
	index  index.php index.html index.htm;        
}
location ~ \.php$ {            
	root            html;            
	fastcgi_pass   127.0.0.1:9000;            
	fastcgi_index  index.php;            
	include         fastcgi.conf;        
}
```

web3修改默认首页index.php，配置两个location实现动静分离。

```shell
[root@web3 ~]# vim /usr/local/nginx/conf/nginx.conf
location / {            
		root   html;            
		index  index.php index.html index.htm;        
}
location ~ \.php$ {            
		root            html;            
		fastcgi_pass   127.0.0.1:9000;            
		fastcgi_index  index.php;            
		include         fastcgi.conf;        
}
```

###### 3）启动相关服务、设置防火墙和SELinux

```shell
[root@web2 ~]# echo "/usr/local/nginx/sbin/nginx" >> /etc/rc.local
[root@web2 ~]# chmod +x /etc/rc.local
[root@web2 ~]# /usr/local/nginx/sbin/nginx
[root@web2 ~]# systemctl start  php-fpm                   #启动php-fpm服务
[root@web2 ~]# systemctl enable php-fpm                   #设置服务开启自启
[root@web2 ~]# firewall-cmd --set-default-zone=trusted
[root@web2 ~]# setenforce  0
[root@web2 ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
[root@web3 ~]# echo "/usr/local/nginx/sbin/nginx" >> /etc/rc.local
[root@web3 ~]# chmod +x /etc/rc.local
[root@web3 ~]# /usr/local/nginx/sbin/nginx
[root@web3 ~]# systemctl start  php-fpm                   #启动php-fpm服务
[root@web3 ~]# systemctl enable php-fpm                #设置服务开机自启
[root@web3 ~]# firewall-cmd --set-default-zone=trusted
[root@web3 ~]# setenforce  0
[root@web3 ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
```

附加知识：systemd！！！

源码安装的软件默认无法使用systemd管理，如果需要使用systemd管理源码安装的软件需要手动编写服务的service文件（编写是可以参考其他服务的模板文件）。以下是nginx服务最终编辑好的模板。

Service文件存储路径为/usr/lib/systemd/system/目录。

```shell
[root@centos7 ~]# vim /usr/lib/systemd/system/nginx.service
[Unit]
Description=The Nginx HTTP Server
#描述信息
After=network.target remote-fs.target nss-lookup.target
#指定启动nginx之前需要其他的其他服务，如network.target等
[Service]Type=forking
#Type为服务的类型，仅启动一个主进程的服务为simple，需要启动若干子进程的服务为forking
ExecStart=/usr/local/nginx/sbin/nginx
#设置执行systemctl start nginx后需要启动的具体命令.ExecReload=/usr/local/nginx/sbin/nginx -s reload
#设置执行systemctl reload nginx后需要执行的具体命令.ExecStop=/bin/kill -s QUIT ${MAINPID}
#设置执行systemctl stop nginx后需要执行的具体命令.[Install]WantedBy=multi-user.target
```

##### 步骤二：部署NFS，将网站数据迁移至NFS共享服务器

###### 1）部署NFS共享服务器

```shell
[root@nfs ~]# yum install nfs-utils
[root@nfs ~]# mkdir /web_share
[root@nfs ~]# vim /etc/exports/web_share  192.168.2.0/24(rw,no_root_squash)
[root@nfs ~]# systemctl restart rpcbind
[root@nfs ~]# systemctl enable rpcbind
```

no_root_squash参数可以在网络上搜索扩展下自己的知识。

NFS使用的是随机端口，每次启动NFS都需要将自己的随机端口注册到rpcbind服务，这样客户端访问NFS时先到rpcbind查询端口信息，得到端口信息后再访问NFS服务。

```shell
[root@nfs ~]# systemctl restart nfs
[root@nfs ~]# systemctl enable nfs
[root@nfs ~]# firewall-cmd --set-default-zone=trusted
[root@nfs ~]# setenforce  0
[root@nfs ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
```

###### 2）迁移旧的网站数据到NFS共享服务器

将web1（192.168.2.11）上的wordpress代码拷贝到NFS共享。

```shell
[root@web1 ~]# cd /usr/local/nginx/
[root@web1 nginx]# tar -czpf html.tar.gz html/
#-p代表打包时保留文件的权限
[root@web1 nginx]# scp html.tar.gz 192.168.2.31:/web_share/
```

登陆nfs服务器，将压缩包解压

```shell
[root@nfs ~]# cd /web_share/
[root@nfs web_share]# tar -xf html.tar.gz
```

###### 3)所有web服务器访问挂载NFS共享数据。

```shell
[root@web1 ~]# rm -rf /usr/local/nginx/html/*
[root@web1 ~]# yum -y install nfs-utils
[root@web1 ~]# echo "192.168.2.31:/web_share/html /usr/local/nginx/html/ nfs defaults 0 0" >> /etc/fstab
[root@web1 ~]# mount -a
[root@web2 ~]# yum -y install nfs-utils
[root@web2 ~]# echo "192.168.2.31:/web_share/html /usr/local/nginx/html/ nfs defaults 0 0" >> /etc/fstab
[root@web2 ~]# mount -a
[root@web3 ~]# yum -y install nfs-utils
[root@web3 ~]# echo "192.168.2.31:/web_share/html /usr/local/nginx/html/ nfs defaults 0 0" >> /etc/fstab
[root@web3 ~]# mount -a
```

##### 步骤三：部署HAProxy代理服务器

###### 1）部署HAProxy

安装软件，手动修改配置文件，添加如下内容。

```shell
[root@proxy ~]# yum -y install haproxy 
[root@proxy ~]# vim /etc/haproxy/haproxy.cfglisten wordpress *:80        
#监听80端口  
balance roundrobin         
#轮询算法  
server web1 192.168.2.11:80 check inter 2000 rise 2 fall 3  
server web2 192.168.2.12:80 check inter 2000 rise 2 fall 3  
server web3 192.168.2.13:80 check inter 2000 rise 2 fall 3
[root@proxy ~]# systemctl start haproxy
[root@proxy ~]# systemctl enable haproxy
[root@proxy ~]# firewall-cmd --set-default-zone=trusted
[root@proxy ~]# setenforce  0
[root@proxy ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
```

##### 步骤三：部署DNS域名服务器

###### 1）安装DNS相关软件（192.168.4.5操作）。

```shell
 [root@proxy ~]# yum -y  install bind bind-chroot
```

###### 2）修改主配置文件，添加zone。

```shell
[root@proxy ~]# vim /etc/named.confoptions {        
	listen-on port 53 { any; };           #服务监听的地址与端口        
	directory       "/var/named";         #数据文件路径        
	allow-query     { any; };             #允许任何主机访问DNS服务
... ...};
zone "lab.com" IN {                        #定义正向区域        
	type master;        
	file "lab.com.zone";
};
#include "/etc/named.rfc1912.zones";        #注释掉改行
#include "/etc/named.root.key";              #注释掉改行
[root@proxy ~]# named-checkconf /etc/named.conf            #检查语法
```

###### 3）修改正向解析记录文件。

注意：保留文件权限（相关配置文件知识参考第一阶段课程）。

```shell
[root@proxy named]# cp -p /var/named/named.localhost /var/named/lab.com.zone
[root@proxy named]# vim /var/named/lab.com.zone
$TTL 1D@       IN SOA  @ rname.invalid. (                                        
		0       ; serial                                        
		1D      ; refresh                                        
		1H      ; retry                                        
		1W      ; expire                                        
		3H )    ; minimum
@        NS     dns.lab.com.
dns     A       192.168.4.5
www     A       192.168.4.5
```

###### 4）启动服务

```shell
[root@proxy named]# systemctl start named
[root@proxy named]# systemctl enable named
[root@proxy ~]# firewall-cmd --set-default-zone=trusted
[root@proxy ~]# setenforce  0
[root@proxy ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
```

###### 5）客户端修改DNS

如果客户端是Linux主机，则客户端修改DNS解析文件

提示：做完实验修改回原始内容。

```shell
[root@room9pc01 data]# cat /etc/resolv.conf
# Generated by NetworkManager
search tedu.cn
nameserver 192.168.4.5
nameserver 172.40.1.10
nameserver 192.168.0.220
```

如何客户端是Windows则需要在图形中配置网卡的DNS服务器。如图-11所示。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage012)

图-11

备注：

如果不做DNS，也可以直接修改hosts解析文件。

如果是Linux客户端，则修改/etc/hosts文件。

如果是Windows客户端，则需要以管理员身份启动记事本修改C:\Windows\System32\drivers\etc\hosts文件。

##### 步骤四：修改wordpress配置文件

###### 1）修改wp-config.php

在define('DB_NAME', 'wordpress')这行前面添加如下两行内容：

```shell
[root@web3 html]# vim /usr/local/nginx/html/wp-config.php
define('WP_SITEURL', 'http://www.lab.com');
define('WP_HOME', 'http://www.lab.com');
```

如果不添加这两行配置，浏览器访问网站某个子页面后，URL会固定到某一台后端服务器不轮询。

警告：添加的这两行必须与前面的域名解析一致！！！！

### 附加知识（常见面试题）

#### 1) 什么是灰度发布：

答：

```
灰度发布（又名金丝雀发布）是指在黑与白之间，能够平滑过渡的一种发布方式。

让一部分用户继续用产品特性A，一部分用户开始用产品特性B，如果用户对B没有什么反对意见，那么逐步扩大范围，把所有用户都迁移到B上面来。灰度发布可以保证整体系统的稳定，在初始灰度的时候就可以发现、调整问题，以保证其影响度。灰度期：灰度发布开始到结束期间的这一段时间，称为灰度期。
```

#### 2）DNS服务器有哪些种，其使用的端口为多少？

答：

有 根DNS、一级DNS、二级DNS、三级DNS、缓存DNS

主DNS服务器、从DNS服务器

端口：53

#### 3）从日志/opt/bjca3/logs/ca_access.log中截取14点到16点的日志，将截取的日志导入到/tmp/ca_access.txt中，日志格式如下：

```
[Fri Mar 17 13:59:00 2017] [debug] mod_cmp.c(1600):[client 192.168.97.8] [CMP] CMP_set_status: starting …
[Fri Mar 17 13:59:00 2017] [debug] mod_cmp.c(938):[client 192.168.97.8] [CMP] CMP_cu_integer_set: starting …
[Fri Mar 17 13:59:00 2017] [debug] mod_cmp.c(957):[client 192.168.97.8] [CMP] CMP_cu_integer_set: ending ok …………
[Fri Mar 17 16:36:00 2017] [debug] mod_cmp.c(1014):[client 192.168.97.8] [CMP] cu_octet_str_set: starting …
[Fri Mar 17 16:36:00 2017] [debug] mod_cmp.c(1037):[client 192.168.97.8] [CMP] cu_octet_str_set: ending ok …
```

答：

```
awk '$4>="14:00:00"&&$4<="16:59:00"' ca_access.log
```



#### 4）监控检查，使用ping命令编写脚本来查询一组IP地址同时检测他们是否处于活跃状态。要求（range：192.168.1.200-192.168.1.220，一个IP发送4个ping包，ping的过程不能输出信息到终端）？

答：

```
#!/bin/bashfor i in {200..220}doping -c 4  -i 0.2  -W 1  192.168.1.$i &>/dev/nullif  [  $? -ne 0 ];then    echo  "192.168.1.$i is down" >> log.txtfidone
```

#### 5）假设nginx的访问日志格式如下，统计访问页面前10位的IP数？

```
202.101.129.218 - - [26/Mar/2017:23:59:55 +0800] "GET /online/stat_inst.php?pid=d065HTTP/1.1" 302 20 -"-" "-" "Mozilla/4.0(compatible;MSIE 6.0;Windows NT 5.1)"
```

答：

```
awk '{IP[$1]++} END{for(i in IP){print i,IP[i]}}' access.log \

| sort -n | tail -10
```



#### 6) 请列举出10个以上的你所知晓的SQL语句？

参考答案：

```
insert  select   delete  update  create  show   drop   grant    revoke   load data   create view
```

#### 7）如何切换到某个数据库，并在上面工作？

答：

```
use 库名;
```



#### 8）列出数据库内的所有表？

答：

```
show tables;
```



#### 9）如何删除表、删除数据库？

答：

```
drop table 表名;drop database 库名;
```



#### 10）如何列出表"xrt"内name域值为"tecmint"，web_address域值为"tecmint.com"的所有数据？

答：

```
select  *  from  xrt  where  name="tecmint" and  web_address="tecmint.com";
```



## 03：Keepalived高可用、部署Ceph分布式存储



### 1 案例1：Keepalived高可用

#### 1.1 问题

部署两台代理服务器，实现如下效果：

- 利用keepalived实现两台代理服务器的高可用
- 配置VIP为192.168.4.80
- 修改对应的域名解析记录

#### 1.2 方案

实验拓扑如图-1所示，做具体实验前请先配置好环境。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage0011)

图-1

备注：实际操作中DNS服务代理服务器部署在同一台主机上（节约虚拟机资源）。

主机配置如表-1所示。

表-1

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable001.png)

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：配置第二台代理服务器

###### 1）部署HAProxy

安装软件，手动修改配置文件，添加如下内容。

```shell
[root@proxy2 ~]# yum -y install haproxy 
[root@proxy2 ~]# vim /etc/haproxy/haproxy.cfg
listen wordpress *:80        #监听80端口  
	balance roundrobin        #轮询算法  
	server web1 192.168.2.11:80 check inter 2000 rise 2 fall 3  
	server web2 192.168.2.12:80 check inter 2000 rise 2 fall 3  
	server web3 192.168.2.13:80 check inter 2000 rise 2 fall 3
[root@proxy2 ~]# systemctl start haproxy
[root@proxy2 ~]# systemctl enable haproxy
[root@proxy2 ~]# firewall-cmd --set-default-zone=trusted
[root@proxy2 ~]# setenforce  0
[root@proxy2 ~]# sed -i  '/SELINUX/s/enforcing/permissive/'  /etc/selinux/config
```

##### 步骤二：为两台代理服务器配置keepalived

###### 1）配置第一台代理服务器proxy（192.168.4.5）。

```shell
[root@proxy ~]# yum install -y keepalived
[root@proxy ~]# vim /etc/keepalived/keepalived.conf
global_defs {  
	router_id  proxy1                #设置路由ID号  
	vrrp_iptables                    #设置防火墙规则（手动添加该行）
}
vrrp_instance VI_1 {  
	state MASTER                         #主服务器为MASTER（备服务器需要修改为BACKUP）  
	interface eth0                    #网卡名称（不能照抄网卡名）  
	virtual_router_id 51                  
	priority 100                     #服务器优先级,优先级高优先获取VIP（实验需要修改）  
	advert_int 1  
	authentication {    
		auth_type pass    
		auth_pass 1111                #主备服务器密码必须一致  
	}  
	virtual_ipaddress {                #谁是主服务器谁获得该VIP（实验需要修改）
		192.168.4.80 
	}    
}
[root@proxy ~]# systemctl start keepalived
[root@proxy ~]# systemctl enable keepalived
```

###### 2）配置第二台代理服务器proxy（192.168.4.6）。

```shell
[root@proxy2 ~]# yum install -y keepalived
[root@proxy2 ~]# vim /etc/keepalived/keepalived.conf
global_defs {  
		router_id  proxy2                        #设置路由ID号
		vrrp_iptables                               #设置防火墙规则（手动添加该行）
}
vrrp_instance VI_1 {  
	state BACKUP                         #主服务器为MASTER（备服务器需要修改为BACKUP）  
	interface eth0                    #网卡名称（不能照抄网卡名）  
	virtual_router_id 51                  
	priority 50                         #服务器优先级,优先级高优先获取
	VIP  advert_int 1  
	authentication {    
		auth_type pass    
		auth_pass 1111                       #主备服务器密码必须一致  
	}  
	virtual_ipaddress {                   #谁是主服务器谁获得该VIP
		192.168.4.80 
	}    
}
[root@proxy2 ~]# systemctl start keepalived
[root@proxy2 ~]# systemctl enable keepalived
```

##### 步骤三：修改DNS服务器

###### 1）修改网站域名对应的解析记录，解析到新的VIP地址。

192.168.4.5为DNS服务器，DNS配置文件相关知识请参考第一阶段课程。

```shell
[root@proxy ~]# vim /var/named/lab.com.zone
$TTL 1D@       IN SOA  @ rname.invalid. (                                        
										0       ; serial                                        
										1D      ; refresh                                        
										1H      ; retry                                        
										1W      ; expire                                        
										3H )    ; minimum
@       	    NS      dns.
lab.com.dns		A       192.168.4.5
www     	    A       192.168.4.80
```

###### 2）重启DNS服务

```shell
[root@proxy ~]# systemctl restart named
```



### 2 案例2：部署Ceph分布式存储

#### 2.1 问题

部署Ceph分布式存储，实现如下效果：

- 使用三台服务器部署Ceph分布式存储
- 实现Ceph文件系统共享
- 将网站数据从NFS迁移到Ceph存储

#### 2.2 方案

实验拓扑如图-2所示，做具体实验前请先配置好环境。

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage002.png)

图-2

备注：实际操作中DNS服务代理服务器部署在同一台主机上（节约虚拟机资源）。

主机配置如表-2所示。

表-2

![img](C:%5CUsers%5CBJTT%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Ctable002.png)

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：准备实验环境

###### 1）把3台虚拟机全部关机,添加光盘和磁盘:

每台虚拟机都添加一个光驱；

做如下相同操作:

右击虚拟机,选【设置】---【添加】---【CD|DVD驱动器】--【完成】；

点击刚刚新建的光盘[CD|DVD],勾选使用ISO映像文件--[浏览]；

找到自己真机的ceph10.iso加载即可。

添加磁盘：所有3台ceph服务器都添加2块20G磁盘。

启动所有虚拟机后，查看磁盘情况:

```shell
[root@node1 ~]# lsblk    
[root@node2 ~]# lsblk    
[root@node3 ~]# lsblk
```

所有主机设置防火墙和SELinux

```shell
[root@node1 ~]# firewall-cmd --set-default-zone=trusted
[root@node1 ~]# sed -i '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@node1 ~]# setenforce 0
[root@node2 ~]# firewall-cmd --set-default-zone=trusted
[root@node2 ~]# sed -i '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@node2 ~]# setenforce 0
[root@node3 ~]# firewall-cmd --set-default-zone=trusted
[root@node3 ~]# sed -i '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@node3 ~]# setenforce 0
```

###### 2）所有主机挂载ceph光盘和系统光盘（根据实际情况挂载，不能照抄）

```shell
[root@node1 ~]# umount /dev/sr0
[root@node1 ~]# umount /dev/sr1
[root@node1 ~]# mkdir /ceph
[root@node1 ~]# vim /etc/fstab    
/dev/sr0    /ceph     iso9660   defaults   0  0    
/dev/sr1    /media    iso9660   defaults   0  0
[root@node1 ~]# mount -a
[root@node2 ~]# umount /dev/sr0
[root@node2 ~]# umount /dev/sr1
[root@node2 ~]# mkdir /ceph
[root@node2 ~]# vim /etc/fstab    
/dev/sr0    /ceph     iso9660   defaults   0  0    
/dev/sr1    /media    iso9660   defaults   0  0
[root@node2 ~]# mount -a
[root@node3 ~]# umount /dev/sr0
[root@node3 ~]# umount /dev/sr1
[root@node3 ~]# mkdir /ceph
[root@node3 ~]# vim /etc/fstab    
/dev/sr0    /ceph     iso9660   defaults   0  0    
/dev/sr1    /media    iso9660   defaults   0  0
[root@node3 ~]# mount -a
```

###### 3）在node1配置SSH密钥，让node1可用无密码连接node1,node2,node3

```shell
[root@node1 ~]# ssh-keygen  -f /root/.ssh/id_rsa  -N  ''
#-f后面跟密钥文件的名称（创建密钥到哪个文件）
#-N  ''设置密钥的密码为空（不要给密钥配置密码）
[root@node1 ~]# for i in   41  42  43
do
ssh-copy-id  192.168.2.$i
done
#通过ssh-copy-id将密钥传递给node1，node2，node3
```

###### 4)修改/etc/hosts域名解析记录（不要删除原文件的数据），同步给所有ceph节点。

```shell
[root@node1 ~]# vim /etc/hosts      #修改文件，手动添加如下内容（不要删除原文件的数据）
192.168.2.41    node1
192.168.2.42     node2
192.168.2.43    node3
[root@node1 ~]# for i in 41 42 43
do     
	scp /etc/hosts 192.168.2.$i:/etc
done
```

###### 5）为所有ceph节点配置yum源，并将配置同步给所有节点

提示：前面已经将ceph的光盘挂载到/ceph目录。

```shell
[root@node1 ~]# cat /etc/yum.repos.d/ceph.repo
[mon]
name=mon
baseurl=file:///ceph/MON
gpgcheck=0
[osd]
name=osd
baseurl=file:///ceph/OSD
gpgcheck=0
[tools]
name=tools
baseurl=file:///ceph/Tools
gpgcheck=0
[root@node1 ~]# yum repolist                #验证YUM源软件数量源标识            
源名称                    状态
Dvd                redhat                    
9,911
Mon                mon                        41
Osd                osd                        28
Tools            tools                    33
repolist: 10,013
[root@node1 ~]# for i in 41 42 43
do     
scp /etc/yum.repos.d/ceph.repo 192.168.2.$i:/etc/yum.repos.d/
done
```

###### 6）配置NTP服务器同步时间。

node1做服务器。

```shell
[root@node1 ~]# vim /etc/chrony.conf
allow 192.168.2.0/24        #修改26行
local stratum 10            #修改29行(去注释即可)
[root@node1 ~]# systemctl restart chronyd
```

node2和node3做客户端

```shell
[root@node2 ~]# vim /etc/chrony.conf
server 192.168.2.41   iburst              #配置文件第二行，手动加入该行内容
[root@node2 ~]# systemctl restart chronyd
[root@node2 ~]# chronyc sources -v
[root@node3 ~]# vim /etc/chrony.conf
server 192.168.2.41   iburst              #配置文件第二行，手动加入该行内容
[root@node3 ~]# systemctl restart chronyd
[root@node3 ~]# chronyc sources -v
```

##### 步骤二：部署ceph集群

###### 1）给node1主机安装ceph-deploy，创建工作目录，初始化配置文件。

```shell
[root@node1 ~]# yum -y install ceph-deploy
[root@node1 ~]# mkdir ceph-cluster
[root@node1 ~]# cd ceph-cluster
```

###### 2）给所有ceph节点安装ceph相关软件包

```shell
[root@node1 ceph-cluster]# for i in node1 node2 node3
do     
ssh $i "yum -y install ceph-mon ceph-osd ceph-mds"
done
```

###### 3）初始化mon服务

```shell
[root@node1 ceph-cluster]# ceph-deploy new node1 node2 node3#生成ceph配置文件
[root@node1 ceph-cluster]# ceph-deploy mon create-initial #拷贝ceph配置文件给node1,node2,node3，启动所有主机的mon服务
[root@node1 ceph-cluster]# ceph -s                    #查看状态（此时失败是正常的）    
cluster 9f3e04b8-7dbb-43da-abe6-b9e3f5e46d2e     
health HEALTH_ERR     
monmap e2: 3 mons at {node1=192.168.2.41:6789/0,node2=192.168.2.42:6789/0,node3=192.168.2.43:6789/0}     
osdmap e45: 0 osds: 0 up, 0 in
```

###### 4）使用ceph-deploy工具初始化数据磁盘（仅node1操作），硬盘名称根据实际情况填写，不能照抄。

```shell
[root@node1 ceph-cluster]# ceph-deploy disk  zap  node1:sdb  node1:sdc    
[root@node1 ceph-cluster]# ceph-deploy disk  zap  node2:sdb  node2:sdc
[root@node1 ceph-cluster]# ceph-deploy disk  zap  node3:sdb  node3:sdc
```

###### 5）初始化OSD集群，磁盘名称根据实际情况填写。

```shell
[root@node1 ceph-cluster]# ceph-deploy osd create  node1:sdb  node1:sdc  
#每个磁盘都会被自动分成两个分区；一个固定5G大小；一个为剩余所有容量#5G分区为Journal缓存；剩余所有空间为数据盘。
[root@node1 ceph-cluster]# ceph-deploy osd create  node2:sdb  node2:sdc
[root@node1 ceph-cluster]# ceph-deploy osd create  node3:sdb  node3:sdc 
[root@node1 ceph-cluster]# ceph -s                 #查看集群状态，状态为OK
```

##### 步骤三：部署ceph文件系统

###### 1）启动mds服务（可以在node1或node2或node3启动，也可以在多台主机启动mds）

```shell
[root@node1 ceph-cluster]# ceph-deploy mds create node3
```

###### 2）创建存储池（文件系统由inode和block组成）

```shell
[root@node1 ceph-cluster]# ceph osd pool create cephfs_data 64
[root@node1 ceph-cluster]# ceph osd pool create cephfs_metadata 64
[root@node1 ceph-cluster]# ceph osd lspools      #查看共享池
0 rbd,1 cephfs_data,2 cephfs_metadata
```

###### 3）创建文件系统

```shell
[root@node1 ceph-cluster]# ceph fs new myfs1 cephfs_metadata cephfs_data
[root@node1 ceph-cluster]# ceph fs lsname: myfs1, metadata pool: cephfs_metadata, data pools: [cephfs_data ]
```

##### 步骤四：迁移网站数据到ceph集群

###### 1）卸载web1，web2，web3的NFS共享。

暂停服务防止有人实时读写文件。

```shell
[root@web1 ~]# /usr/local/nginx/sbin/nginx -s stop
[root@web2 ~]# /usr/local/nginx/sbin/nginx -s stop
[root@web3 ~]# /usr/local/nginx/sbin/nginx -s stop
[root@web1 ~]# umount /usr/local/nginx/html
[root@web2 ~]# umount /usr/local/nginx/html
[root@web3 ~]# umount /usr/local/nginx/html
[root@web1 ~]# vim /etc/fstab
#192.168.2.31:/web_share/html /usr/local/nginx/html/ nfs defaults 0 0
[root@web2 ~]# vim /etc/fstab
#192.168.2.31:/web_share/html /usr/local/nginx/html/ nfs defaults 0 0
[root@web3 ~]# vim /etc/fstab
#192.168.2.31:/web_share/html /usr/local/nginx/html/ nfs defaults 0 0
```

###### 2）web服务器永久挂载Ceph文件系统（web1、web2、web3都需要操作）。

在任意ceph节点，如node1查看ceph账户与密码。

```shell
[root@node1 ~]# cat /etc/ceph/ceph.client.admin.keyring 
[client.admin]    
key = AQA0KtlcRGz5JxAA/K0AD/uNuLI1RqPsNGC7zg==
```

/etc/rc.local是开机启动脚本，任何命令放在该文件中都是开机自启。

ceph-common是ceph的客户端软件。

```shell
[root@web1 ~]# yum -y install ceph-common
[root@web2 ~]# yum -y install ceph-common
[root@web3 ~]# yum -y install ceph-common
[root@web1 ~]#  mount -t ceph 192.168.2.41:6789:/ /usr/local/nginx/html/ \
-o name=admin,secret=AQA0KtlcRGz5JxAA/K0AD/uNuLI1RqPsNGC7zg==
[root@web1 ~]# echo 'mount -t ceph 192.168.2.41:6789:/ /usr/local/nginx/html/ \
-o name=admin,secret=AQA0KtlcRGz5JxAA/K0AD/uNuLI1RqPsNGC7zg==' >> /etc/rc.local 
[root@web1 ~]# chmod +x /etc/rc.local
[root@web2 ~]#  mount -t ceph 192.168.2.41:6789:/ /usr/local/nginx/html/ \
-o name=admin,secret=AQA0KtlcRGz5JxAA/K0AD/uNuLI1RqPsNGC7zg==
[root@web2 ~]# echo 'mount -t ceph 192.168.2.41:6789:/ /usr/local/nginx/html/ \
-o name=admin,secret=AQA0KtlcRGz5JxAA/K0AD/uNuLI1RqPsNGC7zg==' >> /etc/rc.local 
[root@web2 ~]# chmod +x /etc/rc.local
[root@web3 ~]#  mount -t ceph 192.168.2.41:6789:/ /usr/local/nginx/html/ \
-o name=admin,secret=AQA0KtlcRGz5JxAA/K0AD/uNuLI1RqPsNGC7zg==
[root@web3 ~]# echo 'mount -t ceph 192.168.2.41:6789:/ /usr/local/nginx/html/ \
-o name=admin,secret=AQA0KtlcRGz5JxAA/K0AD/uNuLI1RqPsNGC7zg==' >> /etc/rc.local 
[root@web3 ~]# chmod +x /etc/rc.local
```

另一种解决方案，还可以通过fstab实现永久挂载。

提示：如果希望使用fstab实现永久挂载，客户端需要额外安装libcephfs1软件包。

```shell
[root@web1 ~]# yum -y install libcephfs1
[root@web1 ~]# vim /etc/fstab
… …
192.168.2.41:6789:/ /usr/local/nginx/html/  ceph defaults,_netdev,name=admin,secret=AQCVcu9cWXkgKhAAWSa7qCFnFVbNCTB2DwGIOA== 0 0
```

第三种挂载方案：对于高可用的问题，可以在mount时同时写入多个IP。

```shell
临时命令：
[root@web1 ~]# mount -t ceph  \192.168.2.41:6789,192.168.2.42:6789,192.168.2.43:6789:/ /usr/local/nginx/html  \-o name=admin,secret=
密钥永久修改：
[root@web1 ~]# vim /etc/fstab
192.168.2.41:6789,192.168.2.42:6789,192.168.2.43:6789:/ /usr/local/nginx/html/ \
ceph defaults,_netdev,name=admin,secret=密钥 0 0
```

###### 3)迁移NFS服务器中的数据到Ceph存储

登陆NFS服务器备份数据，将备份数据拷贝给web1或web2或web3，tar备份数据时注意使用-p选项保留文件权限。

```shell
[root@nfs ~]# cd /web_share/html/
[root@nfs html]# tar -czpf /root/html.tar.gz ./*
[root@nfs html]# scp /root/html.tar.gz 192.168.2.11:/usr/local/nginx/html/
```

登陆web1将数据恢复到Ceph共享目录

```shell
[root@web1 html]# tar -xf html.tar.gz
[root@web1 html]# rm -rf html.tar.gz
```

###### 4）恢复web服务

```shell
[root@web1 ~]# /usr/local/nginx/sbin/nginx
[root@web2 ~]# /usr/local/nginx/sbin/nginx
[root@web3 ~]# /usr/local/nginx/sbin/nginx
```

### 附加知识（常见面试题）

#### 1) 如何使用awk查看TCP连接状态？

```shell
答：ss -ant |awk '{print $1}'

netstat -ant |awk '{print $6}'
```

#### 2) 有个txt文件内容如下

http://a.domain.com/l.html

http://b.domain.com/l.html

http://c.domain.com/l.html

http://a.domain.com/2.html

http://b.domain.com/2.html

http://a.domain.com/3.html

要求：编写脚本获取主机名、域名，并统计每个域名出现的次数，并排序。

答：

```shell
#！/bin/bash
awk -F"[/.]" '{print $3}' txt    #单独获取主机名
awk -F"[/]" '{print $3}'  txt    #获取完整域名
awk -F"[/]" '{IP[$3]++} END{for(i in IP){print IP[i],i}}' txt | sort -n
```

#### 3) 至少说出一种linux下实现高可用的方案名称？

```
答：keepalived，HeartBeat
```

#### 4）简述下负载均衡与高可用的概念？

答：

```shell
LB（Load_balancing）: 多台服务器平均响应客户端的多次连接请求。

HA（High Availability）: 主备模式，主服务器宕机后，备用服务器才接替工作。
```



#### 5）列举几种你知道的LVS调度算法？

```shell
答：

轮询（Round Robin）

加权轮询（Weighted Round Robin）

最少连接（Least Connections）

加权最少连接（ Weighted Least Connections ）

源地址哈希值（source hash）
```



#### 6）如果你们公司的网站访问很慢，你会如何排查？

```shell
答：

查看流量(Zabbix,ifconfig,sar,ping延迟… …)

系统负载(Zabbix,uptime,sar,top,ps,free查看CPU和内存)

日志（数据库日志-慢查询日志、web服务器日志、ELK）

DNS解析；ss端口状态、并发量；本机时间（时间错误会导致服务器故障）

浏览器F12（开发者工具）
```



#### 7）你会用什么方法来查看某个应用服务的流量使用情况?

```shell
答：

ifconfig eth0（查看网卡整体流量）

iftop（需要安装iftop软件包，实时查看具体IP、端口的流量，iftop -P）

iptraf-ng (需要安装iptraf-ng软件包，实时查看IP、端口的流量)

sar -n DEV（需要安装sysstat软件包，查看历史网卡流量，或者实时查看流量）

nethogs eth0（需要安装nethogs软件包，实时查看进程流量）

查看网站的访问日志（利用awk统计资源的大小并求和）

通过zabbix查看软件流量
```

## 04：部署Git版本控制系统、优化web服务器

### 1 案例1：部署Git版本控制系统

#### 1.1 问题

部署Git版本控制系统，管理网站代码，实现如下效果：

- 基于SSH协议的服务器
- 基于Git协议的服务器
- 基于HTTP协议的服务器
- 上传代码到版本仓库

#### 1.2 方案

生产环境应该有一台独立的Git服务器，这里为了节约主机资源，我们使用数据库主机同时做完Git服务器，如图-1所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00126)

图-1

主机配置如表-1所示。

表-1

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Ctable00125)

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：部署SSH协议的版本控制服务器

###### 1）安装软件包，创建空仓库。

```shell
[root@database ~]# yum -y install git
[root@database ~]# mkdir /var/lib/git/
[root@database ~]# git init --bare /var/lib/git/wordpress.git        #创建空仓库
```

###### 2）登陆web1服务器克隆git仓库，上传网站代码到git服务器。

```shell
[root@web1 var]# git config --global push.default simple
[root@web1 var]# git config --global user.email you@example.com
[root@web1 var]# git config --global user.name "Your Name"
[root@web1 var]# cd /var/
[root@web1 var]# git clone root@192.168.2.21:/var/lib/git/wordpress.git
[root@web1 var]# cd /var/wordpress
[root@web1 wordpress]# cp -a /usr/local/nginx/html/*  ./
[root@web1 wordpress]# git add .
[root@web1 wordpress]# git commit -m "wordpress code"
[root@web1 wordpress]# git pushroot@192.168.2.21's password:<输入192.168.2.21主机root的密码>
```

##### 步骤二：部署Git协议的版本控制服务器

###### 1）安装软件包（192.168.2.21操作）

```shell
[root@database ~]# yum -y install git-daemon
```

###### 2）修改配置文件，启动Git服务

```shell
[root@database ~]# cat /usr/lib/systemd/system/git@.service#仅查看即可
[root@database ~]# systemctl start git.socket
[root@database ~]# systemctl status git.socket
```

###### 3)客户端测试（使用web2做完客户端主机，192.168.2.12）

在web2执行clone等同于是把代码又备份了一份。

```shell
[root@web2 ~]# cd /var/
[root@web2 var]# git clone git://192.168.2.21/wordpress.git
```

##### 步骤三：部署HTTP协议的版本控制服务器

###### 1）安装软件包（192.168.2.21操作）

```shell
[root@database ~]# yum -y install httpd gitweb
```

###### 2）修改配置文件

```shell
[root@database ~]# vim /etc/gitweb.conf
$projectroot = "/var/lib/git";                        #添加一行
```

###### 3）启动服务

```shell
[root@database ~]# systemctl start httpd
```

###### 4）客户端验证

```
火狐浏览器访问 firefox http://192.168.2.21/git
```

访问网页可以查看到wordpress仓库，点击tree菜单后可以看到如图-2所示的代码。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00124)

图-2



### 2 案例2：优化Web服务器

#### 2.1 问题

优化Web服务器，实现如下效果：

- 自定义网站404错误页面
- 升级nginx至1.15.8版本，开启status模块
- 编写日志切割脚本，实现每周五备份日志
- 开启gzip压缩功能，提高数据传输效率
- 开启文件缓存功能

#### 2.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：自定义404错误页面

###### 1）优化前测试（客户端访问一个不存在的页面）。

```
客户端浏览器访问： firefox http://www.lab.com/git
```

###### 2) 修改Nginx配置文件，自定义错误页面

```shell
[root@web1 ~]# vim /usr/local/nginx/conf/nginx.conf         
error_page   404  /404.html;    //自定义错误页面
[root@web2 ~]# vim /usr/local/nginx/conf/nginx.conf         
error_page   404  /404.html;    //自定义错误页面
[root@web3 ~]# vim /usr/local/nginx/conf/nginx.conf         
error_page   404  /404.html;    //自定义错误页面
```

###### 3） 重启nginx

```shell
[root@web1 ~]# /usr/local/nginx/sbin/nginx -s reload
[root@web2 ~]# /usr/local/nginx/sbin/nginx -s reload
[root@web3 ~]# /usr/local/nginx/sbin/nginx -s reload
```

##### 步骤二：升级nginx版本，开启status模块

###### 1）配置、编译新的nginx（web1、web2、web3做相同操作，下面以web1为例）

```shell
[root@web1 ~]# tar  -xf   nginx-1.15.8.tar.gz
[root@web1 ~]# cd  nginx-1.15.8
[root@web1 nginx-1.15.8]# ./configure     \--with-http_ssl_module         \--with-http_stub_status_module
[root@web1 nginx-1.15.8]# make
```

###### 2) 备份老版本nginx，更新新版本nginx

```shell
[root@web1 nginx-1.15.8]# mv /usr/local/nginx/sbin/nginx{,.old}
[root@web1 nginx-1.15.8]# cp objs/nginx  /usr/local/nginx/sbin/
```

###### 3）修改配置文件

```shell
[root@web1 ~]# vim /usr/local/nginx/conf/nginx.conf
... ...
	location /status {                
		stub_status on;                 
		allow 192.168.2.0/24;          #允许哪个网段查看状态页面                 
		deny all;                       #拒绝谁访问查看状态页面        
	}
... ...
```

###### 4) 升级或重启服务

注意：必须在nginx-1.15.8源码包目录下执行make upgrade命令。

```shell
[root@web1 nginx-1.15.8]# make upgrade
```

或者手动执行killall命令杀死进程后重新启动，没有killall命令则需要安装psmisc软件包。

```shell
[root@web1 ~]# killall nginx
[root@web1 ~]# /usr/local/nginx/sbin/nginx
```

##### 步骤三：编写日志切割脚本

###### 1）编写脚本（以web1为例）

```shell
[root@web1 ~]# vim /usr/local/nginx/logbak.sh
#!/bin/bash
date=`date +%Y%m%d`
logpath=/usr/local/nginx/logs
mv $logpath/access.log $logpath/access-$date.log
mv $logpath/error.log $logpath/error-$date.log
kill -USR1 $(cat $logpath/nginx.pid)
```

###### 2）创建计划任务

```shell
[root@web1 ~]# crontab -e
03 03 * * 5  /usr/local/nginx/logbak.sh
```

##### 步骤四：对页面进行压缩处理

###### 1）修改Nginx配置文件

```shell
[root@web1 ~]# cat /usr/local/nginx/conf/nginx.conf
http {
	.. ..
	gzip on;                            //开启压缩
	gzip_min_length 1000;                //小文件不压缩
	gzip_comp_level 4;                //压缩比率
	gzip_types text/plain text/css application/json application/x-javascript text/xml application/xml
	application/xml+rss text/javascript;                                    //对特定文件压缩，类型参考mime.types
	.. ..
}
```

##### 步骤五：服务器内存缓存

###### 1）如果需要处理大量静态文件，可以将文件缓存在内存，下次访问会更快。

```shell
http { 
	open_file_cache          
	max=2000  inactive=20s;        
	open_file_cache_valid    60s;        
	open_file_cache_min_uses 5;        
	open_file_cache_errors   off;
	//设置服务器最大缓存2000个文件句柄，关闭20秒内无请求的文件句柄//文件句柄的有效时间是60秒，60秒后过期
	//只有访问次数超过5次会被缓存
} 
```

### 附加知识（常见面试题）

#### 1）Git的主要功能是什么。它的常用命令有哪些？

答：

```shell
Git是一个分布式的版本控制软件，支持离线操作，主要功能为版本控制，支持日志、数据恢复等功能。

主要命令：

git clone、git add、git commit、git log、git branch、git checkout、git pull、git merge等。
```



#### 2）工作中你都写过什么脚本？

答：

```
监控脚本（监控系统、监控服务、监控硬件信息、监控性能、安全监控等）

系统初始化脚本（创建目录，创建账户，安装软件包，设置权限，修改内核参数等）

一键部署（源码安装脚本）

备份脚本（自动备份数据库，备份网站数据，备份日志，备份配置文件等）

日志分析脚本（分析日志数据，汇总并统计相关信息，如PV、UV等）
```



#### 3）Nginx你用到哪些模块,在proxy模块中你配置哪些参数？

答：

```shell
ngx_http_core_module（核心模块，包含http、server_name、root等配置参数）

ngx_http_access_module（访问控制模块，包含allow和deny配置参数）

ngx_http_auth_basic_module（用户认证模块，包含auth_basic等配置参数）

ngx_http_charset_module（字符集模块，包含charset utf8等配置参数）

ngx_http_fastcgi_module（fastcgi模块，包含fastcgi_pass等配置参数）

ngx_http_gzip_module（压缩模块，包含gzip、gzip_type等配置参数）

ngx_http_limit_conn_module（限制并发量模块，包含limit_conn等参数）

ngx_http_log_module（日志模块，包含access_log等配置参数）

ngx_http_proxy_module（代理模块，包含proxy_pass等配置参数）

ngx_http_rewrite_module（地址重写模块，包含rewrite、break、last等配置参数）

ngx_http_ssl_module（加密模块，包含ssl_certificate、ssl_certificate_key等参数）

ngx_http_stub_status_module（状态模块，包含stub_status配置参数）

ngx_http_upstream_module(调度器模块，包含upstream、hash、ip_hash等配置参数)

ngx_stream_core_module（4层代理模块）

在proxy模块中有proxy_pass、proxy_cache、proxy_cache_path、proxy_connect_timeout、proxy_limit_rate等参数）
```



#### 4）HTTP常见状态码有哪些，分别是什么含义？

答案参考前面的运维课程

#### 5）linux系统中你会用什么命令查看硬件使用的状态信息?

答：

```
uptime、lscpu查看CPU

free查看内存

lsblk、df、iostat查看磁盘

ifconfig、ip a s查看网卡

dmidecode查看主板设备信息
```



#### 6）如果你用 grep -i "error" 过滤只是包含error的行，想同时过滤error上面和下面的行如何实现？

答：

```
grep -i "error" 文件 -A 后面的行数 -B 前面的行数

grep -i "error" 文件 -C 前后的行数
```



# SECURITY

## 01：监控概述、Zabbix基础、Zabbix监控服



### 1 案例1：常用系统监控命令

#### 1.1 问题

本案例要求熟悉查看Linux系统状态的常用命令，为进一步执行具体的监控任务做准备：

- 查看内存信息
- 查看交换分区信息
- 查看磁盘信息
- 查看CPU信息
- 查看网卡信息
- 查看端口信息
- 查看网络连接信息

#### 1.2 方案

一般企业做监控的目的：实时报告系统状态，提前发现系统的问题。

监控的资源可以分为：共有数据（HTTP、FTP等）和私有数据（CPU、内存、进程数等）。

监控软件可以使用：系统自带的命令、Cacti监控系统、Nagios监控系统、Zabbix监控系统。

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：使用命令查看计算机状态数据

###### 1）查看内存与交换分区信息

```shell
[root@proxy ~]# free        #查看内存信息              
total        used        free      shared  buff/cache   availableMem:       
16166888     8017696      720016      106504     7429176     7731740
Swap:       4194300      218268     3976032
[root@proxy ~]# free | awk '/Mem/{print $4}'        #查看剩余内存容量
720928
[root@proxy ~]# swapon -s        #查看交换分区信息
文件名                类型            大小        已用        权限
/dev/sda3             partition        4194300    218268    -1
```

##### 步骤二：查看磁盘与CPU利用率

###### 1）查看磁盘信息

```shell
[root@proxy ~]# df        #查看所有磁盘的使用率
文件系统           1K-块      已用      可用         已用% 挂载点
/dev/sda2        476254208    116879624    335159084    26%        /
/dev/sda1        198174        133897        49737        73%        /boot
[root@proxy ~]# df | awk '/\/$/{print $5}'        #查看根分区的利用率
```

2）查看CPU平均负载

```shell
[root@proxy ~]# uptime        #查看CPU负载（1，5，15分钟） 
23:54:12 up 38 days, 14:54,  9 users,  load average: 0.00, 0.04, 0.05
[root@proxy ~]# uptime |awk '{print $NF}'        #仅查看CPU的15分钟平均负载0.05
```

步骤二：查看网卡信息、端口信息、网络连接信息

1）查看网卡信息（网卡名称仅供参考），如果没有ifconfig命令则需要安装net-tools软件包。

```shell
[root@proxy ~]# ifconfig 
eth0eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500        
	inet 192.168.4.5  netmask 255.255.255.0  broadcast 172.25.0.255        
	inet6 fe80::5054:ff:fe00:b  prefixlen 64  scopeid 0x20<link>        
	ether 52:54:00:00:00:0b  txqueuelen 1000  (Ethernet)        
	RX packets 62429  bytes 10612049 (10.1 MiB)        
	RX errors 0  dropped 0  overruns 0  frame 0        
	TX packets 5674  bytes 4121143 (3.9 MiB)        
	TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
[root@proxy ~]# ifconfig eth0 |awk '/inet /{print $2}'        #查看IP地址信息192.168.4.5
[root@proxy ~]# ifconfig eth0 |awk '/RX p/{print $5}'        #网卡接受数据包流量10625295
[root@proxy ~]# ifconfig eth0 |awk '/TX p/{print $5}'        #网卡发送数据包流量4130821
```

2）查看端口信息

```shell
[root@proxy ~]# ss -ntulp        #查看本机监听的所有端口
#-n以数字显示端口号
#-t显示tcp连接
#-u显示udp连接
#-p显示监听端口对应的程序名称
```

3）查看网络连接信息

```shell
[root@proxy ~]# ss -antup        
#查看所有的网络连接信息
#-a查看所有连接状态信息
```



### 2 案例2：部署Zabbix监控平台

#### 2.1 问题

本案例要求部署一台Zabbix监控服务器，一台被监控主机，为进一步执行具体的监控任务做准备：

1. 安装LNMP环境
2. 源码安装Zabbix
3. 安装监控端主机，修改基本配置
4. 初始化Zabbix监控Web页面
5. 修改PHP配置文件，满足Zabbix需求
6. 安装被监控端主机，修改基本配置

#### 2.2 方案

使用1台Linux虚拟机，安装部署LNMP环境、Zabbix及相关的依赖包，配置数据库并对Zabbix监控平台进行初始化操作。使用2台Linux被监控端，源码安装Zabbix Agent。完成Zabbix实验需要我们搭建一个实验环境，拓扑结构如表-1所示。

表-1 实验拓扑结构（网卡名称仅供参考，不能照抄）

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/SECURITY/DAY01/CASE/01/index.files/table001.png)

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：部署监控服务器

###### 1）安装LNMP环境

Zabbix监控管理控制台需要通过Web页面展示出来，并且还需要使用MySQL来存储数据，因此需要先为Zabbix准备基础LNMP环境。

```shell
[root@zabbixserver ~]# yum -y install gcc pcre-devel  openssl-devel
[root@zabbixserver ~]# tar -xf nginx-1.12.2.tar.gz
[root@zabbixserver ~]# cd nginx-1.12.2
[root@zabbixserver nginx-1.12.2]# ./configure --with-http_ssl_module
[root@zabbixserver nginx-1.12.2]# make && make install
[root@zabbixserver ~]# yum -y  install  php  php-mysql  php-fpm
[root@zabbixserver ~]# yum -y  install  mariadb  mariadb-devel  mariadb-server
```

###### 2）修改Nginx配置文件

配置Nginx支持PHP动态网站，因为有大量PHP脚本需要执行，因此还需要开启Nginx的各种fastcgi缓存，加速PHP脚本的执行速度。

```shell
[root@zabbixserver ~]# vim /usr/local/nginx/conf/nginx.conf
… …
http{
	… …    
	fastcgi_buffers 8 16k;                  #缓存php生成的页面内容，8个16k    
	fastcgi_buffer_size 32k;              #缓存php生产的头部信息，32k    
	fastcgi_connect_timeout 300;         #连接PHP的超时时间，300秒    
	fastcgi_send_timeout 300;             #发送请求的超时时间，300秒    
	fastcgi_read_timeout 300;            #读取请求的超时时间，300秒
	location ~ \.php$ {                
		root           html;                
		fastcgi_pass   127.0.0.1:9000;                
		fastcgi_index  index.php;                
		include        fastcgi.conf;        
	}
	… …
```

###### 3）启动服务

启动Nginx、PHP-FPM、MariaDB服务，关闭SELinux与防火墙。

```shell
[root@zabbixserver ~]# systemctl start  mariadb        #启动服务
[root@zabbixserver ~]# systemctl start  php-fpm        #启动服务
[root@zabbixserver ~]# systemctl enable  mariadb        #设置开机自启
[root@zabbixserver ~]# systemctl enable  php-fpm        #设置开机自启
[root@zabbixserver ~]# /usr/local/nginx/sbin/nginx        #启动服务
[root@zabbixserver ~]# echo /usr/local/nginx/sbin/nginx  >> /etc/rc.local
[root@zabbixserver ~]# chmod +x /etc/rc.local#通过rc.local设置开机自启
[root@zabbixserver ~]# firewall-cmd --set-default-zone=trusted
[root@zabbixserver ~]# setenforce 0
[root@zabbixserver ~]# sed -i '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
```

##### 步骤二：部署监控服务器Zabbix Server

###### 1）源码安装Zabbix Server

多数源码包都是需要依赖包的，zabbix也一样，源码编译前需要先安装相关依赖包。

```shell
[root@zabbixserver lnmp_soft]# yum -y install  net-snmp-devel \curl-devel autoconf libevent-devel#安装相关依赖包[root@zabbixserver lnmp_soft]# tar -xf zabbix-3.4.4.tar.gz
[root@zabbixserver lnmp_soft]# cd zabbix-3.4.4/
[root@zabbixserver zabbix-3.4.4]# ./configure  --enable-server \ --enable-proxy --enable-agent --with-mysql=/usr/bin/mysql_config \ --with-net-snmp --with-libcurl
# --enable-server安装部署zabbix服务器端软件
# --enable-agent安装部署zabbix被监控端软件
# --enable-proxy安装部署zabbix代理相关软件
# --with-mysql指定mysql_config路径
# --with-net-snmp允许zabbix通过snmp协议监控其他设备（如交换机、路由器等）
# --with-libcurl安装相关curl库文件，这样zabbix就可以通过curl连接http等服务，测试被监控主机服务的状态
[root@zabbixserver zabbix-3.4.4]# make && make install
```

###### 2）创建并初始化数据库

```mysql
[root@zabbixserver ~]# mysql
mysql> create database zabbix character set utf8;
#创建数据库，数据库名称为zabbix，character set utf8是支持中文字符集
mysql> grant all on zabbix.* to zabbix@'localhost' identified by 'zabbix';
#创建可以访问数据库的账户与密码，用户名是zabbix，密码是zabbix
[root@zabbixserver ~]# cd lnmp_soft/zabbix-3.4.4/database/mysql/
[root@zabbixserver mysql]# mysql -uzabbix -pzabbix zabbix < schema.sql
[root@zabbixserver mysql]# mysql -uzabbix -pzabbix zabbix < images.sql
[root@zabbixserver mysql]# mysql -uzabbix -pzabbix zabbix < data.sql
#刚刚创建是空数据库，zabbix源码包目录下，有提前准备好的数据#使用mysql导入这些数据即可（注意导入顺序）
#-u指定数据库用户名，-p指定数据库密码如何测试？
[root@zabbixserver ~]# mysql -uzabbix -pzabbix -h localhost zabbix
#-u指定用户名，-p指定密码，-h指定服务器IP，最后的zabbix是数据库名称
#使用zabbix账户（密码为zabbix）连接localhost服务器上面的zabbix数据库
```

###### 3）修改zabbix_server配置并启动监控服务

修改Zabbix_server配置文件，设置数据库相关参数，启动Zabbix_server服务

```shell
[root@zabbixserver ~]# vim /usr/local/etc/zabbix_server.conf
DBHost=localhost # 85行，定义哪台主机为数据库主机，localhost为本机
DBName=zabbix #95行，设置数据库名称
DBUser=zabbix #111行，设置数据库账户
DBPassword=zabbix #119行，设置数据库密码
LogFile=/tmp/zabbix_server.log    #38行，日志的位置，排错使用，该行仅查看即可
[root@zabbixserver ~]# useradd -s /sbin/nologin zabbix 
#服务不允许以root身份启动，不创建用户无法启动服务（用户不需要登录系统）
#创建zabbix用户才可以以zabbix用户的身份启动服务#启动服务后可以通过ps aux查看进程是以什么用户的身份启动的[root@zabbixserver ~]# zabbix_server  
#启动服务（不推荐这么启动服务，推荐使用systemctl启动服务，下面有service文件模板）
[root@zabbixserver ~]# echo  zabbix_server >>  /etc/rc.local        #设置开机自启 
[root@zabbixserver ~]# chmod +x  /etc/rc.local
[root@zabbixserver ~]# ss -ntulp |grep zabbix_server     
#确认连接状态，端口10051tcp LISTEN 0 128 *:10051 *:* users:(("zabbix_server",pid=23275,fd=4),("zabbix_server",pid=23274,fd=4)
```

提示：如果是因为配置文件不对，导致服务无法启动时，不要重复执行zabbix_server，

一定要先使用killall zabbix_server关闭服务后，再重新启动一次。

安装psmisc软件包，才有killall命令。

附加知识（非必须操作）：也可以通过创建service文件管理zabbix服务。

```shell
[root@zabbixserver ~]# cd /usr/lib/systemd/system/
[root@zabbixserver ~]# vim zabbix_server.service 
[Unit]
Description=zabbix server
After=network.target remote-fs.target nss-lookup.target
[Service]
Type=forking
PIDFile=/tmp/zabbix_server.pid
ExecStart=/usr/local/sbin/zabbix_server
ExecStop=/bin/kill $MAINPID
[Install]
WantedBy=multi-user.target
```

###### 4) 修改Zabbix_agent配置文件，启动Zabbix_agent服务

```shell
[root@zabbixserver ~]# vim /usr/local/etc/zabbix_agentd.conf
Server=127.0.0.1,192.168.2.5            #93行，允许哪些主机监控本机
ServerActive=127.0.0.1,192.168.2.5        #134行，允许哪些主机通过主动模式监控本机
Hostname=zabbix_server                #145行，设置本机主机名（名称可以任意）
LogFile=/tmp/zabbix_agentd.log            #设置日志文件（不需要修改）
UnsafeUserParameters=1                #280行，是否允许自定义监控传参
 [root@zabbixserver ~]# zabbix_agentd    #启动监控agent（不推荐这么启动服务，推荐使用systemctl启动服务，下面有service文件模板）
[root@zabbixserver ~]# echo zabbix_agentd  >> /etc/rc.local    #设置开机自启
[root@zabbixserver ~]# ss -ntulp |grep zabbix_agentd   #查看端口信息为10050tcp    LISTEN     0      128       *:10050                 *:*                   users:(("zabbix_agentd",pid=23505,fd=4),("zabbix_agentd",pid=23504,fd=4)
```

提示：如果是因为配置文件不对，导致服务无法启动时，不要重复执行zabbix_agentd，

一定要先使用killall zabbix_agentd关闭服务后，再重新启动一次。

安装psmisc软件包，才有killall命令。

附加知识：编写zabbix_agentd的service文件，通过systemd管理服务。

```shell
# vim /usr/lib/systemd/system/zabbix_agentd.service
[Unit]
Description=zabbix agent
After=network.target remote-fs.target nss-lookup.target
[Service]
Type=forking
PIDFile=/tmp/zabbix_agentd.pid
ExecStart=/usr/local/sbin/zabbix_agentd
ExecStop=/bin/kill $MAINPID
[Install]
WantedBy=multi-user.target
```

###### 5)上线Zabbix的Web页面

```shell
[root@zabbixserver ~]# cd lnmp_soft/zabbix-3.4.4/frontends/php/
[root@zabbixserver php]# cp -r * /usr/local/nginx/html/
[root@zabbixserver php]# chown -R  apache.apache /usr/local/nginx/html/
```

浏览器访问Zabbix_server服务器的Web页面

```
火狐浏览器访问【 firefox http://192.168.2.5/index.php 】#第一次访问，初始化PHP页面会检查计算机环境是否满足要求，如果不满足会给出修改建议#默认会提示PHP的配置不满足环境要求，需要修改PHP配置文件
```

根据错误提示，安装依赖、修改PHP配置文件，满足Zabbix_server的环境要求。

```shell
[root@zabbixserver ~]# yum -y install  php-gd  php-xml
[root@zabbixserver ~]# yum -y install  php-bcmath  php-mbstring 
[root@zabbixserver ~]# vim /etc/php.ini
date.timezone = Asia/Shanghai                #878行，设置时区
max_execution_time = 300                    #384行，最大执行时间，秒
post_max_size = 32M                        #672行，POST数据最大容量
max_input_time = 300                        #394行，服务器接收数据的时间限制
[root@zabbixserver ~]# systemctl restart php-fpm
```

修改完PHP配置文件后，再次使用浏览器访问服务器，则会提示如图-1和图-2所示的提示信息。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00127)

图-1

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00128)

图-2

注意：这里有一个PHP LDAP是warning状态是没有问题的！

在初始化数据库页面，填写数据库相关参数，如图-3所示。

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/SECURITY/DAY01/CASE/01/index.files/image003.png)

图-3

在登陆页面，使用用户(admin)和密码(zabbix)登陆，登陆后设置语言环境为中文，如图-4和图-5所示。

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/SECURITY/DAY01/CASE/01/index.files/image004.png)

图-4

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/SECURITY/DAY01/CASE/01/index.files/image005.png)

图-5

##### 步骤三：部署被监控主机Zabbix Agent

###### 1）源码安装Zabbix agent软件

在2.100和2.200做相同操作（以web1为例）。

```shell
[root@web1 ~]# useradd -s /sbin/nologin  zabbix
[root@web1 ~]# yum -y install gcc pcre-devel autoconf
[root@web1 ~]# tar -xf zabbix-3.4.4.tar.gz 
[root@web1 ~]# cd zabbix-3.4.4/
[root@web1 zabbix-3.4.4]# ./configure --enable-agent
[root@web1 zabbix-3.4.4]# make && make install 
```

###### 2）修改agent配置文件，启动Agent

```shell
[root@web1 ~]# vim /usr/local/etc/zabbix_agentd.conf
Server=127.0.0.1,192.168.2.5                #93行，谁可以监控本机（被动监控模式）
ServerActive=127.0.0.1,192.168.2.5            #134行，谁可以监控本机（主动监控模式）
Hostname=web1                        #145行，被监控端自己的主机名
EnableRemoteCommands=1    #69行，监控异常后，是否允许服务器远程过来执行命令，如重启某个服务
UnsafeUserParameters=1                    #280行，是否允许自定义key传参
[root@web1 ~]# zabbix_agentd                #启动agent服务（不推荐这么启动服务，推荐使用systemctl启动服务，上面有service文件模板）
[root@web1 ~]# echo zabbix_agentd  >> /etc/rc.local
[root@web1 ~]# chmod +x  /etc/rc.local
[root@web1 ~]# firewall-cmd --set-default-zone=trusted
[root@web1 ~]# sed -i  '/SELINUX/s/enforcing/permissive/' /etc/selinux/config
[root@web1 ~]# setenforce 0
```



### 3 案例3：配置及使用Zabbix监控系统

#### 3.1 问题

沿用练习一，使用Zabbix监控平台监控Linux服务器，实现以下目标：

1. 监控CPU
2. 监控内存
3. 监控进程
4. 监控网络流量
5. 监控硬盘

#### 3.2 方案

通过Zabbix监控平台，添加被监控web1主机（192.168.2.100）并链接监控模板即可，Zabbix默认模板就可以监控CPU、内存、进程、网络、磁盘等项目。

#### 3.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：添加监控主机

主机是Zabbix监控的基础，Zabbix所有监控都是基于Host主机。

使用火狐浏览器登录http://192.168.2.5/index.php，通过Configuration（配置）-->Hosts（主机）-->Create Host（创建主机）添加被监控Linux主机，如图-7所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00129)

图-7

添加被监控主机时，需要根据提示输入被监控Linux主机的主机名称（最好与电脑的主机名一致，但也允许不一致）、主机组、IP地址等参数，具体参考图-8所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00130)

图-8

##### 步骤二：为被监控主机添加监控模板

Zabbix通过监控模板来对监控对象实施具体的监控功能，根据模板来定义需要监控哪些数据，对于Linux服务器的监控，Zabbix已经内置了相关的模板（Template OS Linux），选择模板并链接到主机即可，如图-9所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00131)

图-9

##### 步骤三：查看监控数据

查看监控数据，登录Zabbix Web控制台，点击Monitoring(监控中)—> Latest data(最新数据)，正过滤器中填写过滤条件，根据监控组和监控主机选择需要查看哪些监控数据，如图-10所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00132)

图-10

找到需要监控的数据后，可以点击后面的Graph（图形）查看监控图形，如图-11所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0133)

图-11



### 4 案例4：自定义Zabbix监控项目

#### 4.1 问题

沿用练习二，使用Zabbix实现自定义监控，实现以下目标：

1. 监控Linux服务器系统账户的数量

#### 4.2 方案

需要使用Zabbix自定义key的方式实现自定义监控，参考如下操作步骤：

1. 创建自定义key
2. 创建监控项目
3. 创建监控图形
4. 将监控模板关联到主机

#### 4.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：被监控主机创建自定义key（在192.168.2.100操作）

###### 1）创建自定义key

自定义key语法格式为：UserParameter=自定义key名称,命令。

自定义的key文件一般存储在/usr/local/etc/zabbix_agentd.conf.d/目录，这里还需要修改zabbix_agentd.conf文件，允许自定义监控key，来读取该目录下的所有文件 。

```shell
[root@web1 ~]# vim /usr/local/etc/zabbix_agentd.conf
Include=/usr/local/etc/zabbix_agentd.conf.d/             #264行，加载配置文件目录
[root@web1 ~]# cd /usr/local/etc/zabbix_agentd.conf.d/
[root@web1 zabbix_agentd.conf.d]# vim count.line.passwd
UserParameter=count.line.passwd,sed -n '$=' /etc/passwd
#自定义key语法格式:#UserParameter=自定义key名称,命令
```

###### 2）测试自定义key是否正常工作

```shell
[root@web1 ~]# killall  zabbix_agentd
[root@web1 ~]# zabbix_agentd                                #重启agent服务
[root@web1 ~]# zabbix_get -s 127.0.0.1 -k count.line.passwd21
```

注意：如zabbix_get命令执行错误，提示Check access restrictions in Zabbix agent configuration，则需要检查agent配置文件是否正确：

```shell
[root@web1 ~]# vim /usr/local/etc/zabbix_agentd.conf
Server=127.0.0.1,192.168.2.5
ServerActive=127.0.0.1,192.168.2.5
```

##### 步骤二：创建监控模板

模板、应用集与监控项目的关系图，参考图-12所示

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0134)

图-12

###### 1）添加监控模板

登录Zabbix Web监控控制台，通过Configuration(配置)-->Template(模板)-->Create template(创建模板)，填写模板名称，新建模板群组，如图-13所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0135)

图-13

创建模板后，默认模板中没有任何应用集、监控项、触发器、图形等，如图-14所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0136)

图-14

###### 2）创建应用集

创建完成模板后，默认模板中没有任何应用集、监控项、触发器、图形等资源。这里需要点击模板后面的Application（应用集）链接打开创建应用集的页面，如图-15所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0137)

图-15

点击Application（应用集）后，会刷新出图-16所示页面，在该页面中点击Create application（创建应用集）按钮。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0138)

图-16

设置应用集名称，名称可以任意，如图-17所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0139)

图-17

###### 3）创建监控项目item（监控项）

与创建应用集一样，在模板中还需要创建监控项目，如图-18所示，点击items（监控项），并在刷新出的新页面中选择Create items（创建监控项）创建项目，如图-19所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0140)

图-18

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/SECURITY/DAY01/CASE/01/index.files/image018.png)

图-19

接下来，还需要给项目设置名称（名称可以任意）及对应的自定义key（必须与前面自定义的监控key名称一致），如图-20所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0141)

图-20

###### 4）创建图形

为了后期可以通过图形的方式展示监控数据，还需要在模板中创建图形，设置方法与前面的步骤一致，在监控模板后面点击Graph（图形）即可创建图形，设置监控图形基于什么监控数据，如图-21所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00133)

图-21

###### 5）将模板链接到被监控主机

将完整的监控模板制作完成后，就可以将模板链接到主机实现监控功能了。首先找到被监控主机Configuration（配置）-->Hosts（主机），如图-22所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00134)

图-22

点击需要的被监控主机链接，打开监控主机设置页面，在Template（模板）页面中选择需要链接到该主机的模板，在此选择刚刚创建的模板count_line.passwd添加即可，如图-23所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00135)

图-23

###### 6）查看监控数据图形

点击Monitoring（监控中）-->Craphs（图形），根据需要选择条件，查看监控图形，如图-24和图-25所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00136)

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00137)

图-25

附加思维导图，如图-26所示：

​	

图-26

## 02：Zabbix报警机制、Zabbix进阶操作、监控案例

### 1 案例1：实现Zabbix报警功能

#### 1.1 问题

沿用前面的Zabbix练习环境，使用Zabbix实现报警功能，实现以下目标：

1. 监控Linux服务器系统账户数量
2. 创建Media，设置邮件服务器及收件人邮箱
3. 当系统账户数量超过35人时发送报警邮件

#### 1.2 方案

自定义的监控项默认不会自动报警，首页也不会提示错误，需要配置触发器与报警动作才可以自定报警。

**什么是触发器（trigger）？**

表达式，如内存不足300M，用户超过30个等

当触发条件发生后，会导致一个触发事件

触发事件会执行某个动作

**什么是动作（action）？**

动作是触发器的条件被触发后所执行的行为

可以是发送邮件、也可以是重启某个服务等

参考如下操作步骤：

1. 创建触发器并设置标记
2. 设置邮箱（发件人，收件人）
3. 创建Action动作

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：创建触发器规则

###### 1）创建触发器

创建触发器时强烈建议使用英文的语言环境，通过Configuration（配置）--> Templates（模板），找到我们之前创建的count.line.passwd模板，点击模板后面的triggers（触发器），如图-1所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00179)

图-1

###### 2）触发器表达式

创建触发器时需要定义表达式，触发器表达式（Expression）是触发异常的条件，触发器表达式格式如下：

```
{<server>:<key>.<function>(<parameter>)}<operator><constant>
{主机：key.函数(参数)}<表达式>常数
```



在如图-2所示的蓝色方框中编写触发器表达式，可以直接手写，也可以通过add选择表达式模板。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00178)

图-2

下面，我们看几个表达式的案例：

```
{web1:system.cpu.load[all,avg1].last(0)}>5 #0为最新数据

如果web1主机最新的CPU平均负载值大于5，则触发器状态Problem
```

```
{vfs.fs.size[/,free].max(5m)}<10G #5m为最近5分钟

根分区，最近5分钟的最大容量小于10G，则状态进入Problem
```

```
{vfs.file.cksum[/etc/passwd].diff(0)}>0 #0为最新数据

最新一次校验/etc/passwd如果与上一次有变化，则状态进入Problem
```

大多数函数使用秒作为参数，可以使用#来表示其他含义（具体参考表-1）。

avg, count, last, min and max 等函数支持额外的第二个参数`time_shift`（时间偏移量），这个参数允许从过去一段时间内引用数据。

表-1

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Ctable00178)

###### 3）配置触发器

设置触发器名称，如图-3所示，点击add添加表达式，填写表达式：监控项为账户数量，最近账户数量大于35（根据系统账户数量实际填写），效果如图-4所示。





![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00177)

图-3

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00176)

图-4

选择触发器报警级别，如图-5所示，Add创建该触发器，如图-5		所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00175)

图-5

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00174)

图-6

##### 步骤二：设置邮件

###### 1）创建Media

通过Administration（管理）-->Media Type（报警媒体类型）-->选择Email（邮件），如图-7所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00173)

图-7

设置邮件服务器信息，设置邮件服务器及发件人邮件账户信息，如图-8所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage000172)

图-8

###### 2)为用户添加Media（设置收件人信息）

在Administration（管理）-->Users（用户）中找到选择admin账户，如图-9所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00171)

图-9

点击Admin账户后，在弹出的界面中选择Media（报警媒介）菜单-->点击Add(添加)报警媒介，如图-10所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00170)

图-10

点击Add（添加）后，在Meida Type（类型）中填写报警类型，收件人，时间等信息，如图-11所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00169)

图-11

##### 步骤三：创建Action动作

###### 1）Action动作

Action（动作）是定义当触发器被触发时的时候，执行什么行为。

通过Configuration（配置）-->Actions（动作）-->Create action（创建动作），注意事件源选择触发器，如图-12所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00168)

图-12

###### 2）配置Action动作的触发条件

填写Action动作的名称，配置什么触发器被触发时会执行本Action动作（账户数量大于35），如图-13所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00167)

图-13

###### 3）配置Action动作的具体行为

配置动作的具体操作行为（发送信息或执行远程命令），无限次数发送邮件，60秒1次，发送给Admin用户，如图-14和图-15所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00166)

图-14

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00165)

图-15

###### 4）测试效果

在被监控主机创建账户（让账户数量大于35），然后登录监控端Web页面，在仪表盘中查看问题报警（需要等待一段时间），如图-16所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00164)

图-16

查看报警邮件，在监控服务器上使用mail命令查收报警邮件，如图-17所示。

提示：如果没有mail命令，则需要安装mailx软件包。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00163)

图-17



### 2 案例2：Zabbix自动发现

#### 2.1 问题

沿用前面的练习，配置Zabbix的自动发现机制，实现以下目标：

1. 创建自动发现规则
2. 创建自动发现后的动作，添加主机、为主机链接模板

#### 2.2 方案

什么是自动发现（Discovery）？

当Zabbix需要监控的设备越来越多，手动添加监控设备越来越有挑战，此时，可以考虑使用自动发现功能，自动添加被监控主机，实现自动批量添加一组监控主机功能。

自动发现可以实现：

- 自动发现、添加主机，自动添加主机到组；	
- 自动连接模板到主机，自动创建监控项目与图形等。

自动发现（Discovery）流程：

- 创建自动发现规则
- 创建Action动作，说明发现主机后自动执行什么动作
- 通过动作，执行添加主机，链接模板到主机等操作

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：自动发现规则

###### 1）创建自动发现规则

通过Configuration（配置）-->Discovery（自动发现）-->Create discovery rule（创建发现规则），如图-18所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00162)

图-18

###### 2）填写规则

填写自动发现的IP范围（逗号隔开可以写多个），多久做一次自动发现（默认为1小时，仅实验修改为1m），如图-19所示。配置检查的方式：Ping、HTTP、FTP、Agent的自定义key等检查，如图-20所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00161)

图-19



![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00160)

图-20

##### 步骤二：创建动作

###### 1）创建Action动作

通过Configuration（配置）--> Actions（动作）--> Actions Event source(事件源)：自动发现(Discovery)-->Create action（创建动作），如图-21所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00159)

图-21

###### 2）配置Action动作具体行为

配置动作，添加动作名称，添加触发动作的条件，如图-22所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00158)

图-22

点击操作（触发动作后要执行的操作指令），操作细节：添加主机到组，与模板链接（HTTP模板），如图-23所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00157)

图-23

##### 步骤二：添加新的虚拟机

###### 1）创建新的虚拟机

创建一台新的主机，验证zabbix是否可以自动发现该主机，可以重新部署一台新的虚拟机（注意前面的课程，我们已经创建了虚拟机web2，并且已经安装部署了Zabbix agent）。

###### 2）验证结果

登陆Zabbix服务器的Web页面，查看主机列表，确认新添加的主机是否被自动加入监控主机列表。



### 3 案例3：Zabbix主动监控

#### 3.1 问题

沿用前面的练习，配置Zabbix主动监控，实现以下目标：

1. 修改被监控主机agent为主动监控模式
2. 克隆模板，修改模板为主动监控模板
3. 添加监控主机，并链接主动监控模板

#### 3.2 方案

默认zabbix采用的是被动监控，主动和被动都是对被监控端主机而言的！

被动监控：Server向Agent发起连接，索取监控数据。

主动监控：Agent向Server发起连接，Agent周期性地收集数据发送给Server。

区别：Server不用每次需要数据都连接Agent，Agent会自己收集数据并处理数据，Server仅需要保存数据即可。如图-24、图-25所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00156)

图-24

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00155)

图-25

当监控主机达到一定量级后，Zabbix服务器会越来越慢，此时，可以考虑使用主动监控，释放服务器的压力。

另外，Zabbix也支持分布式监控，也是可以考虑的方案。

#### 3.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：添加被监控主机

###### 1）为被监控主机安装部署zabbix agent

注意：前面的实验如果我们已经在web2主机安装部署了zabbix agent，如果已经完成，则如下操作可以忽略。

```shell
[root@web2 ~]# yum -y install gcc pcre-devel autoconf
[root@web2 ~]# tar -xf zabbix-3.4.4.tar.gz 
[root@web2 ~]# cd zabbix-3.4.4/
[root@web2 ~]#./configure --enable-agent
[root@web2 ~]# make && make install
```

###### 2）修改agent配置文件

将agent监控模式修改为主动模式。

```shell
[root@web2 ~]# vim /usr/local/etc/zabbix_agentd.conf 
#Server=127.0.0.1,192.168.2.5
#93行，注释该行，允许谁监控本机
StartAgents=0            
#118行，被动监控时启动几个Agent进程监听10050端口#设置为0，则禁止被动监控，不启动zabbix_agentd服务及端口
ServerActive=192.168.2.5
#134行，允许哪些主机监控本机（主动模式），一定要取消127.0.0.1
Hostname=web2
#145行，告诉监控服务器，是谁发的数据信息
#一定要和zabbix服务器配置的监控主机名称一致（后面设置）
RefreshActiveChecks=120 #183行，默认120秒检测一次
UnsafeUserParameters=1            #280行，允许自定义监控传参
Include=/usr/local/etc/zabbix_agentd.conf.d/ #264行，自定义监控的位置
[root@web2 ~]# killall zabbix_agentd                    #关闭服务
[root@web2 ~]# zabbix_agentd                            #启动服务
[root@web2 ~]# ss -nutlp |grep  zabbix_agentd            #查看不到任何端口信息
```

##### 步骤二：创建主动监控的监控模板

###### 1）克隆Zabbix自动的监控模板

为了方便，克隆系统自带模板（在此基础上修改更方便）。

通过Configuration（配置）-->Templates（模板）-->选择Template OS Linux

-->全克隆，克隆该模板，新建一个新的模板。如图-26所示。

新模板名称为：			。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00154)

图-26

##### 2）修改模板中的监控项目的监控模式

将模板中的所有监控项目全部修改为主动监控模式，通过Configuration（配置）-->Templates（模板）-->选择新克隆的模板，点击后面的Items（监控项）-->点击全选，选择所有监控项目，点击批量更新，将类型修改为：Zabbix Agent（Active主动模式），如图-27所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00153)

图-27

###### 3）禁用部分监控项目

批量修改监控项的监控模式后，并非所有监控项目都支持主动模式，批量修改后，会发现有几个没有修改主动模式成功，说明，这些监控项目不支持主动模式，关闭即可。

可以点击类型排序，方便操作，点击状态即可关闭。如图-28所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00152)

图-28

##### 步骤三：添加监控主机

###### 1）手动添加监控主机（主动模式监控）

在Zabbix监控服务器，添加被监控的主机（主动模式），设置主机名称：web2 （必须与被监控端的配置文件Hostname一致），将主机添加到Linux servers组，IP地址修改为0.0.0.0，端口设置为0，如图-29和图-30所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00151)

图-29

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00150)

图-30

为主机添加监控模板，选择刚刚创建的模板（主动模式），添加链接模板到主机，如图-31所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage0019)

图-31

###### 2）验证监控效果

查看数据图表，通过Monitoring（监控中）-->Graphs（图形）菜单，选择需要查看的主机组、主机以及图形，查看效果，如图-32所示。

![img](http://tts.tmooc.cn/ttsPage/LINUX/NSDTN202001/SECURITY/DAY02/CASE/01/index.files/image032.png)

图-32

附加：

CPU、内存等其他数据可用正常获取，但是，查看分区图表时并无数据，因为分区数据采用的是自动发现监控，与普通监控项一样，修改为主动模式即可，选择Template OS Linux Server Active模板，修改Discovery自动发现为主动模式。如图-33所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00148)

图-33



### 4 案例4：拓扑图与聚合图形

#### 4.1 问题

沿用前面的练习，熟悉zabbix拓扑图与聚合图形，实现以下目标：

1. 创建修改拓扑图
2. 创建聚合图形

#### 4.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：创建拓扑图

###### 1）创建拓扑

绘制拓扑图可以快速了解服务器架构，通过Monitoring（监控中）-->Maps（拓扑图），选择默认的Local network拓扑图，编辑即可（也可以新建一个拓扑图），如图-34所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00147)

图-34

###### 2）拓扑图图表说明

- Icon（图标），添加新的设备后可以点击图标修改属性
- Shape（形状）
- Link（连线），先使用Ctrl选择两个图标，再选择连线
- 完成后，点击Update（更新）

创建完拓扑图，效果如图-35所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00146)

图-35

##### 步骤二：创建聚合图形

###### 1）创建聚合图形

聚合图形可以在一个页面显示多个数据图表，方便了解多组数据。

通过Monitoring（监控中）-->Screens（聚合图形）-->Create screen(创建聚合图形)即可创建聚合图形，如图-36所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00145)

图-36

修改聚合图形参数如下：

- Owner（所有者）：使用默认的Admin用户
- Name（名称）：名称设置为web2_host
- Columns（列）：列数设置为2列
- Rows（行）：行数设置为2行

##### 2）为聚合图形中添加监控图形

选择刚刚创建的聚合图形（web2_host)，点击后面的构造函数（constructor），点击Change(更改)，设置每行每列需要显示的数据图表，如图-37所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00144)

图-37



### 5 案例5：自定义监控案例

#### 5.1 问题

沿用前面的练习，使用自定义key监控常用监控项目，实现以下目标：

1. 监控Nginx状态
2. 监控网络连接状态

#### 5.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：监控Nginx服务状态

###### 1）准备环境，部署nginx软件

安装nginx软件，开启status模块（参考前面的课程知识）

```shell
[root@web1 ~]# tar -xf nginx-1.12.2.tar.gz
[root@web1 ~]# cd nginx-1.12.2
[root@web1 nginx-1.12.2]# yum -y install gcc pcre-devel openssl-devel
[root@web1 nginx-1.12.2]# ./configure \> --with-http_stub_status_module 
[root@web1 nginx-1.12.2]# make && make install
[root@web1 ~]# vim /usr/local/nginx/conf/nginx.conf        #参考前面的课程内容
	location /status {                
		stub_status on;        
	}
[root@web1 ~]# /usr/local/nginx/sbin/nginx    #启动服务        
[root@web1 ~]# curl  http://192.168.2.100/status
Active connections: 1 
server accepts handled requests
10 10 3 
Reading: 0 Writing: 1 Waiting: 0
```

###### 2）自定义监控key

编写自定义监控脚本（仅供参考，未检测完整状态）

```shell
[root@web1 ~]# vim /usr/local/bin/nginx_status.sh
#!/bin/bash
case $1 in
active)    
	curl -s http://192.168.2.100/status |awk '/Active/{print $NF}';;
waiting)    
	curl -s http://192.168.2.100/status |awk '/Waiting/{print $NF}';;
accepts)    
	curl -s http://192.168.2.100/status |awk 'NR==3{print $2}';;
esac
[root@web1 ~]# chmod +x  /usr/local/bin/nginx_status.sh
```

创建自定义key

语法格式：

`UserParameter=key,command`

`UserParameter=key[*],<command> $1`

key里的所有参数，都会传递给后面命令的位置变量

注意：被监控端修改配置文件，注意要允许自定义key并设置Include！

```shell
[root@web1 ~]# vim /usr/local/etc/zabbix_agentd.conf.d/nginx.status
UserParameter=nginx.status[*],/usr/local/bin/nginx_status.sh $1
[root@web1 ~]# killall zabbix_agentd
[root@web1 ~]# zabbix_agentd
```

测试效果：

```shell
[root@web1 ~]# zabbix_get  -s 127.0.0.1 -k 'nginx.status[accepts]'
```

登陆Zabbix监控Web，创建监控项目item，点击Configuration（配置）-->Hosts(主机)，点击主机后面的items（监控项），点击Create item（创建监控项）。修改监控项参数如图-38所示。

备注：Type（类型）后面的Zabbix agent中文是Zabbix 客户端。

Key的中文是键值。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00143)

图-38

##### 步骤二：监控网络连接状态

###### 1）了解TCP协议

熟悉TCP三次握手，参考图-39。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00142)

图-39

熟悉TCP连接的四次断开，参考图-40。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00141)

图-40

###### 2）查看网络连接状态

模拟多人并发连接(如果没有ab命令，则安装httpd-tools软件包)

```shell
[root@web1 ~]# ab -c 1000 -n 100000 http://192.168.2.100/
```

查看网络连接状态，仔细观察、分析第二列的数据

```shell
[root@web1 ~]# ss -antup
#-a显示所有
#-t显示TCP连接状态
#-u显示UDP连接状态
#-n以数字形式显示端口号和IP地址
#-p显示连接对应的进程名称
```

###### 3）创建自定义key

编写自定义监控脚本（仅供参考，未检测完整状态）

```shell
[root@web1 ~]# vim /usr/local/bin/net_status.sh 
#!/bin/bash
case $1 in
estab)    
	ss -antp |awk 'BEGIN{x=0}  /^ESTAB/{x++} END{print x}';;
close_wait)    
	ss -antp |awk 'BEGIN{x=0} /^CLOSE-WAIT/{x++} END{print x}';;
time_wait)    
	ss -antp |awk 'BEGIN{x=0} /^TIME-WAIT/{x++} END{print x}';;
esac 
[root@web1 ~]# chmod +x  /usr/local/bin/net_status.sh
```

注意：被监控端修改配置文件，注意要允许自定义key并设置Include参数。

如果没有killall命令，则需要安装psmisc软件包。

```shell
[root@web1 ~]# vim /usr/local/etc/zabbix_agentd.conf.d/net.status
UserParameter=net.status[*],/usr/local/bin/net_status.sh $1
[root@web1 ~]# killall zabbix_agentd
[root@web1 ~]# zabbix_agentd
```

测试效果：

```shell
[root@web1 ~]# zabbix_get  -s 127.0.0.1 -k 'net.status[time_wait]'
```

###### 4) 监控netstatus

在监控服务器，添加监控项目item，Configuration（配置）-->Hosts（主机）点击主机后面的items（监控项）

点击Create item（创建监控项），如图-41所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00140)

图-41

附加思维导图，如图-42所示：

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00139)

图-42an



## 03：Linux基本防护、用户切换与提权、SSH访问控制、SElinux安全防护

### 1 案例1：Linux基本防护措施

#### 1.1 问题

本案例要求练习Linux系统的基本防护措施，完成以下任务：

1. 修改用户zhangsan的账号属性，设置为2019-12-31日失效（禁止登录）
2. 临时锁定用户lisi的账户，使其无法登录，验证效果后解除锁定
3. 修改tty终端提示，使得登录前看到的第一行文本为“Windows Server 2012 Enterprise R2”，第二行文本为“NT 6.2 Hybrid”
4. 锁定文件/etc/resolv.conf、/etc/hosts，以防止其内容被无意中修改
5. 关闭不需要的服务

#### 1.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：修改用户zhangsan的账户属性，设置为2019-12-31日失效（禁止登录）

###### 1）正常情况下，未过期的账号可以正常登录，使用chage可以修改账户有效期。

```shell
chage命令的语法格式：chage -l    账户名称        #查看账户信息
chage -E 时间 账户名称        #修改账户有效期
```

###### 2）失效的用户将无法登录

使用chage命令将用户zhangsan的账户设为当前已失效（比如已经过去的某个时间）：

```shell
[root@proxy ~]# useradd zhangsan        #创建账户
[root@proxy ~]# passwd zhangsan        #设置密码
[root@proxy ~]# chage -E 2017-12-31 zhangsan    #设置账户过期时间
```

尝试以用户zhangsan重新登录，输入正确的用户名、密码后直接闪退，返回登录页，说明此帐号已失效。

###### 3）重设用户zhangsan的属性，将失效时间设为2019-12-31

```shell
[root@proxy ~]# chage -E 2019-12-31 zhangsan    #修改失效日期
[root@proxy ~]# chage -l zhangsan                #查看账户年龄信息
Last password change    : May 15, 2017
Password expires    : never
Password inactive    : never
Account expires    : Dec 31, 2019
Minimum number of days between password change    : 0
Maximum number of days between password change    : 99999
Number of days of warning before password expires    : 7
```

###### 4）重设用户zhangsan的属性，将失效时间设为永不过期

```
[root@proxy ~]# chage -E -1 zhangsan               #设置账户永不过期
```

###### 5）定义默认有效期（扩展知识）

/etc/login.defs这个配置文件，决定了账户密码的默认有效期。

```shell
[root@proxy ~]# cat /etc/login.defs
PASS_MAX_DAYS    99999        #密码最长有效期
PASS_MIN_DAYS    0        #密码最短有效期
PASS_MIN_LEN    5        #密码最短长度
PASS_WARN_AGE    7        #密码过期前几天提示警告信息
UID_MIN                  1000        #UID最小值
UID_MAX                  60000        #UID最大值
```

##### 步骤二：临时锁定用户zhangsan的账户，使其无法登录，验证效果后解除锁定

###### 1）锁定用户账号

使用passwd或usermod命令将用户zhangsan的账户锁定。

```shell
[root@proxy ~]# passwd -l zhangsan        #锁定用户账号（lock）锁定用户 zhangsan 的密码。passwd: 操作成功
[root@proxy ~]# passwd -S zhangsan        #查看状态（status）
zhangsan LK 2018-02-22 0 99999 7 -1 (密码已被锁定。)
```

###### 2）验证用户zhangsan已无法登录，说明锁定生效

输入正确的用户名、密码，始终提示“Login incorrect”，无法登录。

###### 3）解除对用户zhangsan的锁定

```shell
[root@proxy ~]# passwd -u zhangsan        #解锁用户账号（unlock）解锁用户 zhangsan 的密码 。passwd: 操作成功[root@proxy ~]# passwd -S zhangsan        #查看状态
zhangsan PS 2018-08-14 0 99999 7 -1 (密码已设置，使用 SHA512 加密。)
```

##### 步骤三：修改tty登录的提示信息，隐藏系统版本

###### 1）账户在登录Linux系统时，默认会显示登陆信息（包括操作系统内核信息）

`/etc/issue`这个配置文件里保存的就是这些登陆信息，修改该文件防止内核信息泄露。

```shell
[root@proxy ~]# cat /etc/issue        #确认原始文件
Red Hat Enterprise Linux Server release 7.5Kernel \r on an \m
[root@proxy ~]# cp /etc/issue /etc/issue.origin        #备份文件
[root@proxy ~]# vim /etc/issue        #修改文件内容
Windows Server 2012 Enterprise R2NT 6.2 Hybrid
```

###### 2）测试版本伪装效果

退出已登录的tty终端，或者重启Linux系统，刷新后的终端提示信息会变成自定义的文本内容，如图-1所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00149)

图-1

##### 步骤四：锁定文件`/etc/resolv.conf`、`/etc/hosts`

###### 1）语法格式：

```shell
# chattr +i  文件名            #锁定文件（无法修改、删除、追加等）
# chattr -i  文件名            #解锁文件
# chattr +a  文件名            #锁定后文件仅可追加
# chattr -a  文件名            #解锁文件
# lsattr 文件名                #查看文件特殊属性
```

###### 2) 使用`+i`锁定文件，使用`lsattr`查看属性

```shell
[root@proxy ~]# chattr +i /etc/resolv.conf 
[root@proxy ~]# lsattr /etc/resolv.conf 
----i---------- /etc/resolv.conf
```

###### 3）使用`+a`锁定文件(仅可追加)，使用`lsattr`查看属性

```shell
[root@proxy ~]# chattr +a /etc/hosts
[root@proxy ~]# lsattr /etc/hosts
-----a---------- /etc/hosts
```

###### 4）测试文件锁定效果

```shell
[root@proxy ~]# rm -rf /etc/resolv.conf
rm: 无法删除"/etc/resolv.conf": 不允许的操作
[root@proxy ~]# echo xyz > /etc/resolv.conf
-bash: resolv.conf: 权限不够

[root@proxy ~]# rm -rf  /etc/hosts          #失败
[root@proxy ~]# echo "192.168.4.1  xyz" > /etc/hosts     #失败
[root@proxy ~]# echo "192.168.4.1  xyz" >> /etc/hosts    #成功
```

###### 5）恢复这两个文件原有的属性（避免对后续实验造成影响）

```shell
[root@proxy ~]# chattr -i /etc/resolv.conf 
[root@proxy ~]# chattr -a /etc/hosts
[root@proxy ~]# lsattr /etc/resolv.conf /etc/hosts
--------------- /etc/resolv.conf
--------------- /etc/hosts
```

##### 步骤五：关闭不需要的服务

使用`systemctl`、`chkconfig`工具，禁用非必要的系统服务。

可选服务列表：

`cups.service `打印服务

`postfix.service` 邮件服务

`NetworkManager.service `网络管理服务(network可以替代）

`firewalld` 防火墙（iptables可以替代）

`atd.service` 一次性计划任务（crond可以替代）

`bluetooth.service `蓝牙服务

`autofs.service` 自动挂载

`pcscd.service` 智能卡设备资源管理器



### 2 案例2：使用sudo分配管理权限

#### 2.1 问题

本案例要求利用`sudo`机制分配管理操作权限，主要完成`以下任务：

1. 使用su命令临时切换账户身份，并执行命令
2. 允许`softadm`管理系统服务的权限
3. 允许用户`useradm`通过`sudo`方式添加/删除/修改除`root`以外的用户账号
4. 允许wheel组成员以特权执行所有命令
5. 为sudo机制启用日志记录，以便跟踪sudo执行操作

#### 2.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：使用su命令临时切换账户身份

su(Substitute User)命令可以快速切换账户身份，普通用户切换账户身份时需要输入密码，root使用su命令切换任何身份都不需要密码，如法格式如下：

```
# su -  [账户名称]
# su -  [账户名称]  -c '命令'  
```

###### 1)从普通用户切换为root账户身份(如果没有普通账户则需要先创建，并设置密码)

```shell
[zhangsan@proxy ~]# whoami
zhangsan
[zhangsan@proxy ~]# su -        #切换账户，默认切换为root账户
密码:                               #输入root的密码
[root@proxy ~]# whoami                #确认结果root
```

###### 2)以普通身份创建文件(如果没有普通账户则需要先创建)

```shell
[root@proxy ~]# su - zhangsan  -c "touch /tmp/test.txt"        #管理员切换普通用户
[root@proxy ~]# ls -l  /tmp/test.txt                        #查看文件详细信息
```

###### 3)以root的身份重启服务

```shell
[zhangsan@proxy ~]# su - -c "systemctl restart sshd"        #普通用户切换管理员
密码：
● sshd.service - OpenSSH server daemonLoaded: 
loaded (/usr/lib/systemd/system/sshd.service; enabled; vendor preset: enabled)active: 
active (running) since 五 2018-01-19 08:59:40 CST; 1 months 4 days ago
```

##### 步骤二：允许softadm管理系统服务的权限

###### 1）修改/etc/sudoers配置

修改`/etc/sudoers`可以直接使用`vim`编辑该文件，或使用`visudo命令`修改该文件。

授权的语法格式：用户或组 主机名=（提权账户） 命令

注释：授权什么人，在什么主机上，以什么人的身份，执行什么命令。

为`softadm`授予通过`systemctl`工具来管理系统服务的权限。

如果没有`softadm`账户可以先创建该账户。

```shell
[root@proxy ~]# useradd softadm            #创建账户
[root@proxy ~]# passwd softadm                #设置密码
[root@proxy ~]# vim /etc/sudoers            #修改文件后，需要使用wq!强制保存
.. ..
softadm    ALL=(ALL)   /usr/bin/systemctl         #授权softadm以root身份执行systemctl命令（ALL包括root）
```

###### 2）切换为softadm用户，并验证sudo执行权限

```shell
[root@proxy ~]# su - softadm
[softadm@proxy ~]$ sudo -l
… …
[sudo] password for softadm:                    #输入softadm的口令
.. ..
用户 softadm 可以在该主机上运行以下命令：    
	(ALL) /usr/bin/systemctl
	
[softadm@proxy ~]$ systemctl start crond       #不用sudo时启动服务失败
Authentication is required
.. ..
[softadm@proxy ~]$ sudo systemctl restart crond          #通过sudo启动服务成功
```

##### 步骤三：允许用户useradm通过sudo方式添加/删除/修改除root以外的用户账号

###### 1）修改/etc/sudoers配置

为useradm授予用户管理相关命令的执行权限，例外程序以!符号取反，放在后面。在执行相关程序时，可以利用通配符*。

```shell
[root@proxy ~]# useradd useradm        #创建账户
[root@proxy ~]# passwd  useradm        #设置密码
[root@proxy ~]# vim /etc/sudoers        #修改文件，需要:wq!强制保存退出
.. ..
useradm ALL=(ALL)  /usr/bin/passwd,!/usr/bin/passwd root,/usr/sbin/user*,!/usr/sbin/user* * root
```

###### 2）切换为useradm用户，验证sudo权限

可以通过sudo方式来添加/删除/修改普通用户：

```shell
[useradm@proxy ~]$ sudo -l
.. ..
用户useradm可以在该主机上运行以下命令：    
(root) /usr/bin/passwd, !/usr/bin/passwd root, /usr/sbin/user*,!/usr/sbin/user* * root
[useradm@proxy ~]$ sudo useradd newuser01                  #可以添加用户
[useradm@proxy ~]$ sudo passwd newuser01                  #可以修改普通用户的口令
更改用户 newuser01 的密码 。
新的 密码：
重新输入新的 密码：
passwd： 所有的身份验证令牌已经成功更新。
```

但是不能修改root用户的密码：

```shell
[useradm@proxy ~]$ sudo passwd root
对不起，用户 useradm 无权以 root 的身份在 localhost 上
执行 /usr/bin/passwd root。
```

##### 步骤四：允许wheel组成员以特权执行所有命令

此案例用来展示sudo的便利性及设置不当带来的危险性，生产环境下慎用。

实现时参考下列操作(如果没有普通用户zengye则先创建该账户)：

```shell
[root@proxy ~]# useradd zengye        #创建账户
[root@proxy ~]# passwd  zengye        #设置密码
[root@proxy ~]# cat /etc/sudoers    #查看文件即可
.. ..
%wheel ALL=(ALL)  ALL
[root@proxy ~]# usermod -G wheel zengye    #设置zengye用户的附加组为wheel
[root@proxy ~]# su - zengye
[zengye@proxy ~]$ sudo -l
.. ..
用户 zengye 可以在该主机上运行以下命令：
(root) /bin/*
```

##### 步骤五：为sudo机制启用日志记录，以便跟踪sudo执行操作

###### 1）修改/etc/sudoers配置，添加日志设置（使用visudo也可以修改配置文件）

```shell
[root@proxy ~]# visudo
Defaults  logfile="/var/log/sudo"
.. ..
```

###### 2）执行sudo操作产生日志

使用root可以执行sudo命令，softadm也可以执行sudo命令（前面已经授权）。

```shell
[root@proxy ~]# sudo -l                  #查看授权的sudo操作
[softadm@proxy ~]# sudo systemctl status crond             #执行sudo重启服务
```

###### 3）确认日志记录已生效

```shell
[root@proxy ~]# cat /var/log/sudo         #查看日志文件
.. ..
May 16 22:14:49 : root : TTY=pts/1 ; PWD=/root ; USER=root ; COMMAND=list
Feb 22 22:35:43 : softadm : TTY=pts/11 ; PWD=/home/softadm ; USER=root ;    
	COMMAND=/bin/systemctl status httpd
```



### 3 案例3：提高SSH服务安全

#### 3.1 问题

本案例要求提高Linux主机上SSH服务端的安全性，完成以下任务：

1. 配置基本安全策略（禁止root）
2. 针对SSH访问采用仅允许的策略，未明确列出的用户一概拒绝登录
3. 实现密钥验证登录（私钥口令）、免密码登入
4. 确认密钥验证使用正常后，禁用口令验证

#### 3.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：配置基本安全策略

###### 1）调整sshd服务配置，并重载服务

```shell
[root@proxy ~]# vim /etc/ssh/sshd_config
.. ..
PermitRootLogin no                      #禁止root用户登录
UseDNS  no                          #不解析客户机地址
LoginGraceTime  1m                      #限时登录
MaxAuthTries  3                      #每连接最多认证次数
.. ..
[root@proxy ~]# systemctl restart sshd
```

###### 2）测试基本安全策略

尝试以root用户SSH登录，失败：

```shell
[root@proxy ~]# ssh root@192.168.4.5
root@192.168.4.5's password:
Permission denied, please try again.
```

##### 步骤二：针对SSH访问采用仅允许的策略，未明确列出的用户一概拒绝登录

###### 1）调整sshd服务配置，添加AllowUsers策略，仅允许用户zhangsan、tom、useradm，其中useradm只能从网段192.168.2.0/24远程登录本机。

注意：如果没有这些用户，需要提前创建用户并设置密码。

```shell
[root@proxy ~]# vim /etc/ssh/sshd_config
.. ..
AllowUsers zhangsan tom useradm@192.168.2.0/24    #定义账户白名单（根据实际情况填写，不能盲目照抄）
##DenyUsers  USER1  USER2                    #定义账户黑名单
##DenyGroups  GROUP1 GROUP2                    #定义组黑名单
##AllowGroups  GROUP1 GROUP2                    #定义组白名单
[root@proxy ~]# systemctl restart sshd
```

###### 2）验证SSH访问控制，未授权的用户将拒绝登录。

```shell
[root@proxy ~]# ssh useradm@192.168.2.5              #已授权的用户允许登录
useradm@192.168.2.5's password:
[useradm@proxy ~]$ exit
[root@proxy ~]# ssh root@192.168.2.5                  #未授权的用户被拒绝登录
root@192.168.2.5's password:
Permission denied, please try again.
```

##### 步骤三：实现密钥对验证登录（私钥口令）、免密码登入

###### 1）准备客户机测试环境

为客户机的用户root建立SSH密钥对

使用ssh-keygen创建密钥对，将私钥口令设为空（直接回车）：

```shell
[root@client ~]$ ssh-keygen
Generating public/private rsa key pair.
Enter file in which to save the key (/root/.ssh/id_rsa):
Created directory '/root/.ssh'.Enter passphrase (empty for no passphrase):          #直接回车将口令设为空
Enter same passphrase again:                          #再次回车确认
[root@client ~]$ ls -lh ~/.ssh/id_rsa*              #确认密钥对文件
-rw-------. 1 root root 1.8K 8月  15 10:35 /root/.ssh/id_rsa
-rw-r--r--. 1 root root  403 8月  15 10:35 /root/.ssh/id_rsa.pub
```

###### 2）将客户机上用户root的公钥部署到SSH服务器

以用户root登入客户机，使用ssh-copy-id命令将自己的公钥部署到服务器：

```shell
[root@client ~]$ ssh-copy-id root@192.168.4.5
root@192.168.4.5's password:
Now try logging into the machine, with "ssh 'root@192.168.4.5'", and check in:  
.ssh/authorized_keysto make sure we haven't added extra keys that you weren't expecting.
```

###### 3）在服务器上确认客户机用户root上传的公钥信息

默认部署位置为目标用户的家目录下 ~/.ssh/authorized_keys文件：

```shell
[root@proxy ~]# cat ~/.ssh/authorized_keys
ssh-rsa AAAAB3NzaC1yc2EAAAABIwAAAQEAzz+5AiFMGQ7LfuiV7eBnOcmRO9JRTcqRoynGO2y5
RyFL+LxR1IpEbkNrUyIZDk5uaX1Y8rwsf+pa7UZ2NyqmUEvNSUo0hQyDGsU9SPyAdzRCCvDgwpOFhaHi/OFnT+zqjAqXH2M9fFYEVUU4PIVL8HT19zCQRVZ/q3acQA34UsQUR0PpLJAobsf1BLe2EDM8BsSHckDGsNoDT9vk+u3e83RaehBMuy1cVEN5sLAaIrIeyM8Q0WxQNlqknL908HRkTlTeKrRoHbMnOBFj8StwlnscKHlkrsKkhUf8A9WWz/vL4GDwGND5jdca3I2hdITAySjMdfL1HMHnMYOgMjPM0Q== root@192.168.4.100
```

###### 4）在客户机上测试SSH密钥对验证

在客户机用户root的环境中，以远程用户root登入192.168.4.5主机时，无需验证口令即可登入（因为私钥口令为空）：

```shell
[root@client ~]$ ssh root@192.168.4.5                      #免交互直接登入
Last login: Thu Aug 15 10:48:09 2013 from 192.168.4.100
```

##### 步骤四：确认密钥验证使用正常后，禁用口令验证

###### 1）调整sshd服务配置，将PasswordAuthentication设为no

```shell
[root@proxy ~]# vim /etc/ssh/sshd_config
.. ..
PasswordAuthentication no        #默认配置文件有这一行，将yes改成no即可
[root@proxy ~]# systemctl restart sshd
```



### 4 案例4：SELinux安全防护

#### 4.1 问题

本案例要求熟悉SELinux防护机制的开关及策略配置，完成以下任务：

1. 将Linux服务器的SELinux设为enforcing强制模式
2. 从/root目录下移动一个包文件到FTP下载目录，调整策略使其能够被下载

#### 4.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：将Linux服务器的SELinux设为enforcing强制模式

###### 1）固定配置：修改/etc/selinux/config文件

确认或修改SELINUX为enforcing模式：

```shell
[root@proxy ~]# vim /etc/selinux/config
SELINUX=enforcing                                #设置SELinux为强制模式
SELINUXTYPE=targeted                            #保护策略为保护主要的网络服务安全
```

###### 2）临时配置：使用setenforce命令

查看当前SELinux状态，如果是disabled则需要根据第1）步的配置重启系统；如果是permissive则使用setenforce命令修改为enforcing即可：

```shell
[root@proxy ~]# getenforce                        #查看当前状态为警告模式
Permissive
[root@proxy ~]# setenforce 1                      #设置SELinux为强制模式
[root@proxy ~]# getenforce                        #查看当前模式为强制模式
Enforcing
[root@proxy ~]# setenforce 0                      #设置SELinux为宽松模式
[root@proxy ~]# getenforce                        #查看当前模式为宽松模式Permissive
```

##### 步骤二：在SELinux启用状态下，调整策略打开vsftpd服务的匿名上传访问

###### 1）配置一个允许匿名上传的vsftpd服务作为测试环境

```shell
[root@proxy ~]# setenforce 1
[root@proxy ~]# yum -y install vsftpd
[root@proxy ~]# systemctl start vsftpd                #启动服务#默认Vsftpd共享目录为/var/ftp/
```

##### 步骤三：从/root目录下移动2个包文件到FTP下载目录，调整文件的安全上下文

###### 1）建立两个FTP下载用的测试文件

由root用户创建两个测试压缩包，一个直接建立到/var/ftp/目录下，另一个先在/root/下建立，然后移动至/var/ftp/目录。

```shell
#测试文件1，直接在ftp目录下创建文件
[root@proxy ~]# tar -czf  /var/ftp/log1.tar  /var/log
[root@proxy ~]# ls -lh /var/ftp/
-rw-r--r--. 1 root root 8M 8月  16 10:16 log1.tar
[root@proxy ~]# ls -Z /var/ftp/
-rw-r--r--. root root unconfined_u:object_r:public_content_t:s0 log1.tar
#测试文件2，在/root下建立，然后移动至/var/ftp目录（注意是移动不是复制）
[root@proxy ~]# tar -czf  log2.tar  /var/log
[root@proxy ~]# mv log2.tar /var/ftp/
[root@proxy ~]# ls -lh /var/ftp/
-rw-r--r--. 1 root root 8M 8月  16 10:16 log2.tar
[root@proxy ~]# ls -Z /var/ftp/
-rw-r--r--. 1 root root unconfined_u:object_r:admin_home_t:s0 log2.tar
```

###### 3）通过FTP方式测试下载

使用wget命令分别下载这两个包文件，第二个包将会下载失败（看不到文件）。

```shell
[root@proxy ~]# wget ftp://192.168.4.5/log1.tar            #下载第一个文件，成功
[root@proxy ~]# wget ftp://192.168.4.5/log2.tar            #下载第二个文件，失败
```

###### 4）检查该测试包的安全上下文，正确调整后再次下载第二个包成功。

文件已经存放到共享目录下，但客户端无法访问下载，是因为被SELinux拦截了！

```shell
[root@proxy ~]# ls -Z /var/ftp/
-rw-r--r--. root root unconfined_u:object_r:public_content_t:s0 log1.tar
-rw-r--r--. 1 root root unconfined_u:object_r:admin_home_t:s0   log2.tar
[root@proxy ~]# chcon -t public_content_t /var/ftp/log2.tar
[root@proxy ~]# ls -Z /var/ftp/log2.tar
-rw-r--r--. root root unconfined_u:object_r:public_content_t:s0 log2.tar
[root@proxy ~]# wget ftp://192.168.4.5/log2.tar            #再次下载，成功
```

注意：上例中的chcon操作可替换为（效果相同）：

\# `restorecon /var/ftp/log2.tar`

### 附加思维导图，如图-2所示：

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00181)

图-2



## 04：加密与解密、AIDE入侵检测系统、扫描与抓包



### 1 案例1：加密与解密应用

#### 1.1 问题

本案例要求采用gpg工具实现加/解密及软件签名等功能，分别完成以下任务：

1. 检查文件的MD5校验和
2. 使用GPG实现文件机密性保护，加密和解密操作
3. 使用GPG的签名机制，验证数据的来源正确性

#### 1.2 方案

加密算法主要有以下几种分类：

##### 1.为确保数据机密性算法：

a) 对称加密算法(AES,DES)

b) 非对称加密算法（RSA，DSA）

##### 2.为确保数据完整性算法：

a) 信息摘要（MD5，SHA256，SHA512）

#### 1.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：检查文件的MD5校验和

###### 1） 查看文件改动前的校验和，复制为新文件其校验和不变

```shell
[root@proxy ~]# vim file1.txt		#新建一个文件，内容如下
abcdef
123456779
[root@proxy ~]# cp file1.txt  file2.txt	#拷贝文件
[root@proxy ~]# cp file1.txt  file3.txt
[root@proxy ~]# md5sum file?.txt  			#文件内容一致，则校验和也不变
b92aa0f8aa5d5af5a47c6896283f3536  file1.txt
b92aa0f8aa5d5af5a47c6896283f3536  file2.txt
b92aa0f8aa5d5af5a47c6896283f3536  file3.txt
```

###### 2） 对文件内容稍作改动，再次检查校验和，会发现校验和已大不相同

```shell
[root@proxy ~]# echo "x" >> file1.txt
[root@proxy ~]# md5sum file?.txt
6be3efe71d8b4b1ed34ac45f4edd2ba7  file1.txt
b92aa0f8aa5d5af5a47c6896283f3536  file2.txt
b92aa0f8aa5d5af5a47c6896283f3536  file3.txt
```

##### 步骤二：使用GPG对称加密方式保护文件

GnuPG是非常流行的加密软件，支持所有常见加密算法，并且开源免费使用。

###### 1）确保已经安装了相关软件

```shell
[root@proxy ~]# yum -y install gnupg2      #安装软件
[root@proxy ~]# gpg --version            #查看版本
gpg (GnuPG) 2.0.22
```

###### 2） gpg使用对称加密算法加密数据的操作

执行下列操作：

```shell
[root@proxy ~]# gpg -c file2.txt
.. ..
```

根据提示依次输入两次密码即可。如果是在GNOME桌面环境，设置密码的交互界面会是弹出的窗口程序，如图-1所示：

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00182)

图-1

如果是在tty终端执行的上述加密操作，则提示界面也是文本方式的，如图-2所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00183)

图-2

根据提示输入两次口令，加密后的文件（自动添加后缀 .gpg）就生成了，传递过程中只要发送加密的文件（比如 file2.txt.gpg）就可以了。

```shell
[root@proxy ~]# cat file2.txt.gpg					#查看加密数据为乱码
```

###### 3）使用gpg对加密文件进行解密操作

收到加密的文件后，必须进行解密才能查看其内容。

```shell
[root@proxy ~]# gpg -d file2.txt.gpg > file2.txt  	#解密后保存
gpg: 3DES 加密过的数据
.. ..  											#根据提示输入正确密码

[root@proxy ~]# cat file2.txt  					#查看解密后的文件
abcdef
123456779
```

##### 步骤三：使用GPG非对称加密方式保护文件

非对称加密/解密文件时，UserA（192.168.2.5主机）生成私钥与公钥，并把公钥发送给UserB（192.168.2.100主机），UserB使用公钥加密数据，并把加密后的数据传给UserA，UserA最后使用自己的私钥解密数据。

流程如图-3所示。

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00184)

图-3

实现过程如下所述。

###### 1）接收方UserA创建自己的公钥、私钥对(在192.168.2.5操作)

```shell
[root@proxy ~]# gpg --gen-key			#创建密钥对
… …
请选择您要使用的密钥种类：
   (1) RSA and RSA (default)			#默认算法为RSA
   (2) DSA and Elgamal
   (3) DSA (仅用于签名)
   (4) RSA (仅用于签名)
您的选择？							#直接回车默认(1)
RSA 密钥长度应在 1024 位与 4096 位之间。
您想要用多大的密钥尺寸？(2048)			#接受默认2048位
您所要求的密钥尺寸是 2048 位
请设定这把密钥的有效期限。
         0 = 密钥永不过期
      <n>  = 密钥在 n 天后过期
      <n>w = 密钥在 n 周后过期
      <n>m = 密钥在 n 月后过期
      <n>y = 密钥在 n 年后过期
密钥的有效期限是？(0)					#接受默认永不过期
密钥永远不会过期
以上正确吗？(y/n)y						#输入y确认

真实姓名：UserA
电子邮件地址：UserA@tarena.com
注释：UserA
您选定了这个用户标识： #姓名、邮箱、注释可以任意，推荐与案例保持一致
    “UserA (UserA) <UserA@tarena.com>”

更改姓名(N)、注释(C)、电子邮件地址(E)或确定(O)/退出(Q)？O  		#输入大写O确认
您需要一个密码来保护您的私钥。

我们需要生成大量的随机字节。这个时候您可以多做些琐事(像是敲打键盘、移动
鼠标、读写硬盘之类的)，这会让随机数字发生器有更好的机会获得足够的熵数。
```

注意：生成密钥后当前终端可能会变的无法使用，执行reset命令即可，或者关闭后再开一个终端。

###### 2）UserA导出自己的公钥文件(在192.168.2.5操作)

用户的公钥、私钥信息分别保存在pubring.gpg和secring.gpg文件内：

```shell
[root@proxy ~]# gpg --list-keys        #查看密钥
/root/.gnupg/pubring.gpg
------------------------------
pub   2048R/421C9354 2037-08-16
uid                  UserA (User A) <UserA@tarena.com>
sub   2048R/9FA3AD25 2037-08-16
```

使用gpg命令结合--export选项将其中的公钥文本导出：

```shell
[root@proxy ~]# gpg -a --export UserA > UserA.pub	#导出密钥（文件名任意）
#--export的作用是导出密钥，导出名称为UserA的密钥
#-a的作用是导出的密钥存储为ASCII格式
[root@proxy ~]# scp UserA.pub 192.168.2.100:/tmp/ 
#UserA将密钥传给UserB
```

###### 3）UserB导入接收的公钥信息（在192.168.2.100操作）

使用gpg命令结合--import选项导入公钥信息，以便在加密文件时指定对应的公钥。

```shell
[root@web1 ~]# gpg --import /tmp/UserA.pub		#导入密钥
gpg: 密钥 421C9354：公钥“UserA (UserA) <UserA@tarena.com>”已导入
gpg: 合计被处理的数量：1
gpg:           已导入：1  (RSA: 1) 
```

注意：常见错误。

```shell
#很多同学做到这里，会出现如下错误提示：
gpg: key 39BD9CAE was created 311549447 seconds in the future (time warp or clock problem)
gpg: 密钥 39BD9CAE 是在 311549335 秒后的未来生成的(可能是因为时空扭曲或时钟的问题)
英语词汇：time（时间），warp（扭曲），clock（时钟），problem（问题）
不管是上面的英文报错，还是下面的中文报错，都是因为两台主机的时间不一致导致的，需要修改计算机的时间。
```

###### 4) UserB使用公钥加密数据，把加密后的数据传给UserA（在192.168.2.100操作）

```shell
[root@web1 ~]# echo "I love you ." > love.txt
[root@web1 ~]# gpg -e -r UserA love.txt		#加密数据
无论如何还是使用这把密钥吗？(y/N)y				#确认使用此密钥加密文件
#-e选项是使用密钥加密数据
#-r选项后面跟的是密钥，说明使用哪个密钥对文件加密
[root@web1 ~]# scp love.txt.gpg  192.168.2.5:/root	#加密的数据传给UserA
```

###### 4）UserA以自己的私钥解密文件（在192.168.2.5操作）

```shell
[root@proxy ~]# gpg -d love.txt.gpg > love.txt		#解密数据
您需要输入密码，才能解开这个用户的私钥：“UserA (UserA) <UserA@tarena.com>”
2048 位的 RSA 密钥，钥匙号 9FA3AD25，建立于 2037-08-16 (主钥匙号 421C9354)
gpg: 由 2048 位的 RSA 密钥加密，钥匙号为 9FA3AD25、生成于 2037-08-16
      “UserA (UserA) <UserA@tarena.com>”
[root@proxy ~]# cat love.txt        #获得解密后的文件内容
I love you.
```

##### 步骤四：使用GPG的签名机制，检查数据来源的正确性

使用私钥签名的文件，是可以使用对应的公钥验证签名的，只要验证成功，则说明这个文件一定是出自对应的私钥签名，除非私钥被盗，否则一定能证明这个文件来自于某个人！

###### 1）在proxy(192.168.2.5)上，UserA为软件包创建分离式签名

将软件包、签名文件、公钥文件一起发布给其他用户下载。

```shell
[root@proxy ~]# tar zcf log.tar /var/log      #建立测试软件包
[root@proxy ~]# gpg -b log.tar              #创建分离式数字签名
[root@proxy ~]# ls -lh log.tar*
-rw-rw-r--. 1 root root 170 8月  17 21:18 log.tar
-rw-rw-r--. 1 root root 287 8月  17 21:22 log.tar.sig
[root@proxy ~]# scp log.tar* 192.168.2.100:/root      #将文件与签名传给UserB
```

###### 2）在192.168.2.100上验证签名

```shell
[root@web1 ~]# gpg --verify log.tar.sig log.tar
gpg:于2037年06月07日 星期六 23时23分23秒 CST 创建的签名，使用 RSA，钥匙号 421C9354
gpg: 完好的签名，来自于“UserA (UserA) <UserA@tarena.com>”
```



### 2 案例2：使用AIDE做入侵检测

#### 2.1 问题

本案例要求熟悉Linux主机环境下的常用安全工具，完成以下任务操作：

1. 安装aide软件
2. 执行初始化校验操作，生成校验数据库文件
3. 备份数据库文件到安全的地方
4. 使用数据库执行入侵检测操作

#### 2.2 方案

Aide通过检查数据文件的权限、时间、大小、哈希值等，校验数据的完整性。

使用Aide需要在数据没有被破坏前，对数据完成初始化校验，生成校验数据库文件，在被攻击后，可以使用数据库文件，快速定位被人篡改的文件。

#### 2.3 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：部署AIDE入侵检测系统

###### 1）安装软件包

```shell
[root@proxy ~]# yum -y install aide
```

###### 2) 修改配置文件

确定对哪些数据进行校验，如何校验数据

```shell
[root@proxy ~]# vim /etc/aide.conf
@@define DBDIR /var/lib/aide        #数据库目录
@@define LOGDIR /var/log/aide        #日志目录
database_out=file:@@{DBDIR}/aide.db.new.gz        #数据库文件名
#一下内容为可以检查的项目（权限，用户，组，大小，哈希值等）
#p:      permissions
#i:      inode:
#n:      number of links
#u:      user
#g:      group
#s:      size
#md5:    md5 checksum
#sha1:   sha1 checksum
#sha256:        sha256 checksum
DATAONLY =  p+n+u+g+s+acl+selinux+xattrs+sha256
#以下内容设置需要对哪些数据进行入侵校验检查
#注意：为了校验的效率，这里将所有默认的校验目录与文件都注释
#仅保留/opt目录，其他目录都注释掉
/opt   DATAONLY
#/boot   NORMAL         #对哪些目录进行什么校验
#/bin    NORMAL
#/sbin   NORMAL
#/lib    NORMAL
#/lib64  NORMAL
#/opt    NORMAL
#/usr    NORMAL
#!/usr/src          #使用[!]，设置不校验的目录
#!/usr/tmp
```

##### 步骤二：初始化数据库，入侵后检测

###### 1）入侵前对数据进行校验，生成初始化数据库

```shell
[root@proxy ~]# aide --init
AIDE, version 0.15.1
AIDE database at /var/lib/aide/aide.db.new.gz initialized.
#生成校验数据库，数据保存在/var/lib/aide/aide.db.new.gz
```

###### 2）备份数据库，将数据库文件拷贝到U盘（非必须的操作）

```shell
[root@proxy ~]# cp /var/lib/aide/aide.db.new.gz   /media/
```

###### 3）入侵后检测

```shell
[root@proxy ~]# cd /var/lib/aide/
[root@proxy ~]# mv aide.db.new.gz aide.db.gz
[root@proxy ~]# aide --check							#检查哪些数据发生了变化
```



### 3 案例3：扫描与抓包分析

#### 3.1 问题

本案例要求熟悉Linux主机环境下的常用安全工具，完成以下任务操作：

1. 使用NMAP扫描来获取指定主机/网段的相关信息
2. 使用tcpdump分析FTP访问中的明文交换信息

#### 3.2 步骤

实现此案例需要按照如下步骤进行。

##### 步骤一：使用NMAP扫描来获取指定主机/网段的相关信息

###### 1）安装软件

```shell
[root@proxy ~]# yum -y install nmap
#基本用法：
# nmap  [扫描类型]  [选项]  <扫描目标 ...>
#常用的扫描类型
# -sS，TCP SYN扫描（半开）
# -sT，TCP 连接扫描（全开）
# -sU，UDP扫描
# -sP，ICMP扫描
# -A，目标系统全面分析
```

###### 2）检查192.168.2.100主机是否可以ping通

```shell
[root@proxy ~]# nmap  -sP  192.168.2.100
Starting Nmap 6.40 ( http://nmap.org ) at 2028-06-06 21:59 CST
mass_dns: warning: Unable to determine any DNS servers. Reverse DNS is disabled. Try using --system-dns or specify val
id servers with --dns-servers
Nmap scan report for host3 (192.168.2.100)
Host is up (0.00036s latency).
MAC Address: 52:54:00:71:07:76 (QEMU Virtual NIC)
Nmap done: 1 IP address (1 host up) scanned in 0.02 seconds
```

使用-n选项可以不执行DNS解析

```shell
[root@proxy ~]# nmap -n -sP  192.168.2.100
Starting Nmap 6.40 ( http://nmap.org ) at 2028-06-06 22:00 CST
Nmap scan report for 192.168.2.100
Host is up (0.00046s latency).
MAC Address: 52:54:00:71:07:76 (QEMU Virtual NIC)
Nmap done: 1 IP address (1 host up) scanned in 0.03 seconds
```

###### 3）检查192.168.2.0/24网段内哪些主机可以ping通

```shell
[root@proxy ~]# nmap  -n  -sP  192.168.2.0/24
Starting Nmap 5.51 ( http://nmap.org ) at 2027-05-17 18:01 CST
Nmap scan report for 192.168.2.1
Host is up.
Nmap scan report for 192.168.2.7
Host is up.
Nmap scan report for 192.168.2.120
Host is up (0.00027s latency).
MAC Address: 00:0C:29:74:BE:21 (VMware)
Nmap scan report for 192.168.2.110
Host is up (0.00016s latency).
MAC Address: 00:50:56:C0:00:01 (VMware)
Nmap scan report for 192.168.2.120
Host is up (0.00046s latency).
MAC Address: 00:0C:29:DB:84:46 (VMware)
Nmap done: 256 IP addresses (5 hosts up) scanned in 3.57 seconds
```

###### 4）检查目标主机所开启的TCP服务

```shell
[root@proxy ~]# nmap -sT 192.168.2.100
Starting Nmap 5.51 ( http://nmap.org ) at 2028-05-17 17:55 CST
Nmap scan report for 192.168.2.100
Host is up (0.00028s latency).
Not shown: 990 closed ports
PORT    STATE SERVICE
21/tcp  open  ftp
22/tcp  open  ssh
25/tcp  open  smtp
80/tcp  open  http
110/tcp open  pop3
111/tcp open  rpcbind
143/tcp open  imap
443/tcp open  https
993/tcp open  imaps
995/tcp open  pop3s
MAC Address: 00:0C:29:74:BE:21 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 1.31 seconds
```

###### 5）检查192.168.2.0/24网段内哪些主机开启了FTP、SSH服务

```shell
[root@proxy ~]# nmap -p 21-22 192.168.2.0/24
Starting Nmap 5.51 ( http://nmap.org ) at 2027-05-17 18:00 CST
Nmap scan report for 192.168.2.1
Host is up (0.000025s latency).
PORT   STATE SERVICE
21/tcp open  ftp
22/tcp open  ssh

Nmap scan report for 192.168.2.7
Host is up.
PORT   STATE    SERVICE
21/tcp filtered ftp
22/tcp filtered ssh

Nmap scan report for 192.168.2.120
Host is up (0.00052s latency).
PORT   STATE SERVICE
21/tcp open  ftp
22/tcp open  ssh
MAC Address: 00:0C:29:74:BE:21 (VMware)

Nmap scan report for pc110.tarena.com (192.168.2.110)
Host is up (0.00038s latency).
PORT   STATE  SERVICE
21/tcp closed ftp
22/tcp closed ssh
MAC Address: 00:50:56:C0:00:01 (VMware)

Nmap scan report for 192.168.2.120
Host is up (0.00051s latency).
PORT   STATE  SERVICE
21/tcp closed ftp
22/tcp closed ssh
MAC Address: 00:0C:29:DB:84:46 (VMware)

Nmap done: 256 IP addresses (5 hosts up) scanned in 4.88 seconds
```

###### 6）检查目标主机所开启的UDP服务

```shell
[root@proxy ~]# nmap   -sU  192.168.2.100    			#指定-sU扫描UDP
53/udp   open          domain
111/udp  open          rpcbind
```

###### 7）全面分析目标主机192.168.2.100和192.168.2.5的操作系统信息

```shell
[root@proxy ~]# nmap -A 192.168.2.100,5

Starting Nmap 5.51 ( http://nmap.org ) at 2017-05-17 18:03 CST
Nmap scan report for 192.168.2.100  					#主机mail的扫描报告
Host is up (0.0016s latency).
Not shown: 990 closed ports
PORT    STATE SERVICE  VERSION
21/tcp  open  ftp      vsftpd 2.2.2
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
| -rw-r--r--    1 0        0            1719 Aug 17 13:33 UserB.pub
| -rw-r--r--    1 0        0             122 Aug 13 05:27 dl.txt
| drwxr-xr-x    2 14       0            4096 Aug 13 09:07 pub
| -rw-rw-r--    1 505      505           170 Aug 17 13:18 tools-1.2.3.tar.gz
|_-rw-rw-r--    1 505      505           287 Aug 17 13:22 tools-1.2.3.tar.gz.sig
22/tcp  open  ssh      OpenSSH 5.3 (protocol 2.0)
| ssh-hostkey: 1024 86:be:d6:89:c1:2d:d9:1f:57:2f:66:d1:af:a8:d3:c6 (DSA)
|_2048 16:0a:15:01:fa:bb:91:1d:cc:ab:68:17:58:f9:49:4f (RSA)
25/tcp  open  smtp     Postfix smtpd
80/tcp  open  http     Apache httpd 2.4.10 ((Red Hat))
|_http-methods: No Allow or Public header in OPTIONS response (status code 302)
| http-title: 302 Found
|_Did not follow redirect to https://192.168.2.100//
110/tcp open  pop3     Dovecot pop3d
|_pop3-capabilities: USER CAPA UIDL TOP OK(K) RESP-CODES PIPELINING STLS SASL(PLAIN)
111/tcp open  rpcbind
MAC Address: 00:0C:29:74:BE:21 (VMware)
No exact OS matches for host (If you know what OS is running on it, see http://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=5.51%D=8/19%OT=21%CT=1%CU=34804%PV=Y%DS=1%DC=D%G=Y%M=000C29%TM=52
OS:11ED90%P=x86_64-redhat-linux-gnu)SEQ(SP=106%GCD=1%ISR=10B%TI=Z%CI=Z%II=I
OS:%TS=A)OPS(O1=M5B4ST11NW6%O2=M5B4ST11NW6%O3=M5B4NNT11NW6%O4=M5B4ST11NW6%O
OS:5=M5B4ST11NW6%O6=M5B4ST11)WIN(W1=3890%W2=3890%W3=3890%W4=3890%W5=3890%W6
OS:=3890)ECN(R=Y%DF=Y%T=40%W=3908%O=M5B4NNSNW6%CC=Y%Q=)T1(R=Y%DF=Y%T=40%S=O
OS:%A=S+%F=AS%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=
OS:0%Q=)T5(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=40%W=0%
OS:S=A%A=Z%F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)U1(
OS:R=Y%DF=N%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=Y%DFI=
OS:N%T=40%CD=S)

Network Distance: 1 hop
Service Info: Host:  mail.tarena.com; OS: Unix

TRACEROUTE
HOP RTT     ADDRESS
1   1.55 ms 192.168.2.100
```

##### 步骤二：使用tcpdump分析FTP访问中的明文交换信息

###### 1）准备Vsftpd服务器（192.168.2.5操作）

```shell
[root@proxy ~]# yum -y install vsftpd
[root@proxy ~]# systemctl restart vsftpd
[root@proxy ~]# useradd  tom
[root@proxy ~]# echo 123 | passwd --stdin tom
```

###### 2）启用tcpdump命令行抓包

执行tcpdump命令行，添加适当的过滤条件，只抓取访问主机192.168.2.5的21端口的数据通信 ，并转换为ASCII码格式的易读文本。

这里假设，192.168.2.5主机有vsftpd服务，如果没有需要提前安装并启动服务！！！

警告：案例中所有抓包命令都没有指定网卡，每位同学需要根据实际情况指定抓包网卡的名称。

```shell
[root@proxy ~]# tcpdump -i 网卡名称 -A host 192.168.2.5 and tcp port 21
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on eth0, link-type EN10MB (Ethernet), capture size 65535 bytes
.. ..											#进入等待捕获数据包的状态
#监控选项如下：
# -i，指定监控的网络接口（默认监听第一个网卡）
# -A，转换为 ACSII 码，以方便阅读
# -w，将数据包信息保存到指定文件
# -r，从指定文件读取数据包信息
#tcpdump的过滤条件：
# 类型：host（主机）、net（网段）、port（端口）、portrange（端口范围）
# 方向：src（源地址）、dst（目标地址）
# 协议：tcp、udp、ip、wlan、arp、……
# 多个条件组合：and、or、not
```

###### 3）执行FTP访问，并观察tcpdump抓包结果

从192.168.2.100访问主机192.168.2.5的vsftpd服务。

```shell
[root@web1 ~]# yum -y install ftp
[root@web1 ~]# ftp 192.168.2.5
Connected to 192.168.2.5 (192.168.2.5).
220 (vsFTPd 3.0.2)
Name (192.168.2.5:root): tom       #输入用户名
331 Please specify the password.
Password:                              #输入密码
530 Login incorrect.
Login failed.
ftp>quit                               #退出
```

观察抓包的结果（回到porxy主机观察tcpdump抓包的结果）：

```shell
[root@proxy ~]#
... …
18:47:27.960530 IP 192.168.2.100.novation > 192.168.2.5.ftp: Flags [P.], seq 1:14, ack 21, win 65515, length 13
E..5..@.@......x...d.*..G.\c.1BvP.......USER tom
18:47:29.657364 IP 192.168.2.100.novation > 192.168.2.5.ftp: Flags [P.], seq 14:27, ack 55, win 65481, length 13
E..5..@.@......x...d.*..G.\p.1B.P.......PASS 123
```

###### 4)再次使用tcpdump抓包，使用-w选项可以将抓取的数据包另存为文件，方便后期慢慢分析。

```shell
[root@proxy ~]# tcpdump -i 网卡名称 -A  -w  ftp.cap  \
> host 192.168.2.5  and  tcp  port  21							#抓包并保存
```

tcpdump命令的-r选项，可以去读之前抓取的历史数据文件

```shell
[root@proxy ~]# tcpdump  -A  -r  ftp.cap | egrep  '(USER|PASS)'	#分析数据包
.. ..
E..(..@.@.. ...x...d.*..G.\c.1BbP.............
18:47:25.967592 IP 192.168.2.5.ftp > 192.168.2.100.novation: Flags [P.], seq 1:21, ack 1, win 229, length 20
E..<FJ@.@.jE...d...x...*.1BbG.\cP...V...220 (vsFTPd 2.2.2)
… …
18:47:27.960530 IP 192.168.2.100.novation > 192.168.2.5.ftp: Flags [P.], seq 1:14, ack 21, win 65515, length 13
E..5..@.@......x...d.*..G.\c.1BvP.......USER tom
… …
18:47:27.960783 IP 192.168.2.5.ftp > 192.168.2.100.novation: Flags [P.], seq 21:55, ack 14, win 229, length 34
E..JFL@.@.j5...d...x...*.1BvG.\pP...i~..331 Please specify the password.
… …
18:47:29.657364 IP 192.168.2.5.ftp > 192.168.2.100.novation: Flags [P.], seq 14:27, ack 55, win 65481, length 13
E..5..@.@......x...d.*..G.\p.1B.P.......PASS 123
… …
18:47:29.702671 IP 192.168.2.100.novation > 192.168.2.5.ftp: Flags [P.], seq 55:78, ack 27, win 229, length 23
E..?FN@.@.j>...d...x...*.1B.G.\}P.......230 Login successful.
```

##### 步骤三：扩展知识，使用tcpdump分析Nginx的明文账户认证信息信息

###### 1）在proxy主机(192.168.2.5)准备一台需要用户认证的Nginx服务器

```shell
[root@proxy ~]# cd /usr/local/nginx/conf/
[root@proxy ~]# cp nginx.conf.default  nginx.conf      #还原配置文件
[root@proxy ~]# vim /usr/local/nginx/conf/nginx.conf
server {
  listen 80;
  server_name localhost;
auth_basic "xx";
auth_basic_user_file "/usr/local/nginx/pass";
… …
[root@proxy ~]# yum -y install httpd-tools
[root@proxy ~]# htpasswd -c /usr/local/nginx/pass tom   #创建账户文件
New password:123                   #输入密码
Re-type new password:123          #确认密码
[root@proxy ~]# /usr/local/nginx/sbin/nginx -s reload
```

###### 2）在proxy主机使用tcpdump命令抓包

```shell
[root@proxy ~]# tcpdump  -i 网卡名称 -A  host 192.168.2.5  and  tcp  port  80
```

###### 3)在真实机使用浏览器访问192.168.2.5

```
客户端使用浏览器访问 firefox  http://192.168.2.5         #根据提示输入用户名与密码
```

###### 4）回到proxy查看抓包的数据结果(找关键词Authorization: Basic)

```shell
[root@proxy ~]# tcpdump -i 网卡名称 -A host 192.168.2.5 and tcp port 80
tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on eth0, link-type EN10MB (Ethernet), capture size 262144 bytes
… …
Authorization: Basic dG9tOjEyMzQ1Ng==
… …
```

###### 5) 查看base64编码内容

```shell
[root@proxy ~]# echo "dG9tOjEyMzQ1Ng==" | base64 -d      #解码数据
tom:123456
[root@proxy ~]# echo "tom:123456" | base64 
dG9tOjEyMzQ1Ngo=
```

### 附加思维导图，如图-4所示：

![img](E:%5CHJCloudComputingNotes%5Clinux-cloud-computing%5Ctypora-user-images%5Cimage00185)

图-4







