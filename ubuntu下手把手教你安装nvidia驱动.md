## 【超详细】【ubunbu 22.04】 手把手教你安装nvidia驱动，
![](https://csdnimg.cn/release/blogv2/dist/pc/img/original.png)

## 

**目录**

[前言](#main-toc)

[一、英伟达官网下载驱动](#%E4%B8%80%E3%80%81%E8%8B%B1%E4%BC%9F%E8%BE%BE%E5%AE%98%E7%BD%91%E4%B8%8B%E8%BD%BD%E9%A9%B1%E5%8A%A8)

[二、更新软件列表和安装必要软件、依赖](#%E4%BA%8C%E3%80%81%E4%BD%BF%E7%94%A8%E6%AD%A5%E9%AA%A4)

[三、禁用默认驱动](#%E4%B8%89%E3%80%81%E7%A6%81%E7%94%A8%E9%BB%98%E8%AE%A4%E9%A9%B1%E5%8A%A8)

[四、进入tty模式](#2.%E8%AF%BB%E5%85%A5%E6%95%B0%E6%8D%AE)

[1、关闭图形界面进入tty模式](#1%E3%80%81%E5%85%B3%E9%97%AD%E5%9B%BE%E5%BD%A2%E7%95%8C%E9%9D%A2%E8%BF%9B%E5%85%A5tty%E6%A8%A1%E5%BC%8F)

[2、进入tty以后需要输入用户名和密码登录。](#2%E3%80%81%E8%BF%9B%E5%85%A5tty%E4%BB%A5%E5%90%8E%E9%9C%80%E8%A6%81%E8%BE%93%E5%85%A5%E7%94%A8%E6%88%B7%E5%90%8D%E5%92%8C%E5%AF%86%E7%A0%81%E7%99%BB%E5%BD%95%E3%80%82)

[3、禁用X-window服务](#3%E3%80%81%E7%A6%81%E7%94%A8X-window%E6%9C%8D%E5%8A%A1)

[五、安装驱动](#%E5%9B%9B%E3%80%81%E5%AE%89%E8%A3%85%E9%A9%B1%E5%8A%A8)

[六、返回图形界面](#%E4%BA%94%E3%80%81%E8%BF%94%E5%9B%9E%E5%9B%BE%E5%BD%A2%E7%95%8C%E9%9D%A2)

[七、可能遇到的问题](#%E6%80%BB%E7%BB%93)

[1、进入tty模式如果不是英语系统可能会出现乱码](#%E8%BF%9B%E5%85%A5tty%E6%A8%A1%E5%BC%8F%E5%A6%82%E6%9E%9C%E4%B8%8D%E6%98%AF%E8%8B%B1%E8%AF%AD%E7%B3%BB%E7%BB%9F%E5%8F%AF%E8%83%BD%E4%BC%9A%E5%87%BA%E7%8E%B0%E4%B9%B1%E7%A0%81)

[2、返回图形界面黑屏](#%E8%BF%94%E5%9B%9E%E5%9B%BE%E5%BD%A2%E7%95%8C%E9%9D%A2%E9%BB%91%E5%B1%8F)

* * *

## 前言

前几天组了台新电脑装ubuntu系统跑深度学习，nvidia的驱动是出了名的麻烦。忙活了一天还重装了几次系统终于搞定了。下面是我总结出来的安装方法给大家参考参考。

## 一、英伟达官网下载驱动

英文地址：[Official Advanced Driver Search | NVIDIA](https://www.nvidia.com/Download/Find.aspx?lang=en-us# "Official Advanced Driver Search | NVIDIA")

中文地址：[官方驱动 | NVIDIA](https://www.nvidia.cn/Download/index.aspx?lang=cn# "官方驱动 | NVIDIA")

![](https://img-blog.csdnimg.cn/c9a47c6f76c146b3aa0370d8ca3fcca9.png)

 根据自己的显卡选择驱动。**注意：下载的驱动文件要放在英语路径中！！！**

## 二、更新软件列表和安装必要软件、依赖

终端输入以下命令：

```bash
    sudo apt-get update
     
    sudo apt-get install g++
     
    sudo apt-get install gcc
     
    sudo apt-get install make
```

## 三、禁用默认驱动

在安装NVIDIA驱动以前需要禁止系统自带显卡驱动nouveau。

在终端输入命令打开blacklist.conf文件。

```bash
sudo gedit /etc/modprobe.d/blacklist.conf
```

或者新建一个单独的blacklist-nouveau.conf文件。

```bash
sudo gedit /etc/modprobe.d/blacklist-nouveau.conf
```

在打开的文件末尾输入并保存：

```bash
blacklist nouveau
options nouveau modeset=0
```

最后更新一下系统的*initramfs*镜像文件，在终端中输入：

```bash
sudo update-initramfs -u
```

完成以上步骤后，重启电脑。然后在终端中输入：

```bash
lsmod | grep nouveau
```

如果没有输出的话就说明禁用了nouveau。

## 四、进入tty模式

到这一步需要关闭图形界面，推荐使用其他设备阅读。

### 1、关闭图形界面进入tty模式

终端输入：

```cs
sudo telinit 3
```

输入如下命令可以重新打开图形界面。

```cs
sudo telinit 5
```

### 2、进入tty以后需要输入用户名和密码登录。

![](https://img-blog.csdnimg.cn/4330a4bd9f314466a6b6037fc1efc5e4.png)

**注意：这里输入的用户名是和创建账户时第三行的名字，例如下图 "Pick a username"。**

![](https://img-blog.csdnimg.cn/2ad233b2fa2f476aa947da2e5ee49b1d.png)

**如果不记得的话可以在/home打开属性查看 "Name"。**![](https://img-blog.csdnimg.cn/d3132c74dd084937abb8082e96cfd37a.png)

输入用户名和密码后，出现这个画面就是登录成功了。

![](https://img-blog.csdnimg.cn/2c3f33c3a9f94a50801b3484f668d42e.png)

### 3、禁用X-window服务

输入以下命令：

```cs
sudo service gdm3 stop
```

## 五、安装驱动

cd进入存放驱动文件的目录中，ls查看目录中的文件 。

 ![](https://img-blog.csdnimg.cn/5276e452a1494b63910406279b3cec3a.png)

输入以下命令安装。

```cs
    sudo chmod 777 NVIDIA-Linux-x86_64-525.53.run   #给下载的驱动赋予可执行权限
     
    sudo ./NVIDIA-Linux-x86_64-525.53.run –no-opengl-files -no-x-check   #安装
```

\-no-opengl-files：只安装驱动文件，不安装OpenGL文件。

\-no-x-check：安装驱动时关闭X服务，不设置可能导致安装失败。

**会出现的选项：**

+   Install Nvidia's 32-bit compatibility libraries?  
    **选择 "No"**
+   Would you like to run the nvidia-xconfig utility to automatically update your X configuration file so that the NVIDIA X driver dill be used dhen you restart X? Any pre-existing X configuration file will be backed up.  
    **选择 "Yes"**

## 六、返回图形界面

再次启动X-window服务。

```cs
sudo service gdm3 start
```

返回图形界面后打开终端输入：

```cs
nvidia-smi
```

出现以下画面说明安装完成。

![](https://img-blog.csdnimg.cn/801996228420430ba5cbca620c4210e0.png)

## 七、可能遇到的问题

### 1、进入tty模式如果不是英语系统可能会出现乱码

输入以下命令：

```cs
export LANG="UTF-8"
export LANGUAGE="UTF-8"
```

### 2、返回图形界面黑屏

检查hdmi线是不是接在主板的hdmi接口上了，接到显卡上就可以了（我被这个问题折磨了一下午才发现这么简单）。

## 卸载驱动

```javascript
sudo /usr/bin/nvidia-uninstall
sudo apt-get --purge remove nvidia-*
sudo apt-get purge nvidia*
sudo apt-get purge libnvidia*
```

+   直到命令不输出任何内容

```javascript
sudo dpkg --list | grep nvidia-*
```

+   重新安装
