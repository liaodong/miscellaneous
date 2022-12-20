1.首先启动系统，在这个开机界面按e，进入编辑模式

2.进入编辑界面，上下光标键移动，找到linux16这一行，在将 ro 改成 rw init=/sysroot/bin/bash,然后按Ctrl+x键进入单用户模式。

3.进入系统，输入 chroot /sysroot/

4.接着输入命令 passwd 修改root密码。
注意，修改密码时，输入的密码不会显示，我们输入即可。

5.现在密码已经修改完成，

6.输入 touch /.autorelabel 否则重启后不生效

7.exit 后  reboot命令进入系统。

————————————————
版权声明：本文为CSDN博主「小胡yhu」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/weixin_44304678/article/details/123184848
