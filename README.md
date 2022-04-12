# hyper-v-vm-
hyper-v与vm共存

弃用Hyper-V
  这里用的Win10 Hyper-V，这是虚拟机，和VBox、VMware同类产品。用Hyper-V的好处是，他有个WSL(win10 内核版本18xxx以上才支持WSL2)，可以在应用商店下载Ubuntu等linux应用。
  win10安装的Linux和Windows公用一个环境，很神奇，你们可以尝试用一下。后来我要用VMware（因为没找到什么方式可以连接linux内部应用端口），结果和Hyper冲突了，于是做了以下操作：

1.关掉Hyper-V，在运行-> appwiz.cpl界面，启动关闭功能中，关掉

2.在开始里面的管理员 power-shell中执行:

bcdedit /set hypervisorlaunchtype off

3.重启计算机就可以用VMware了

再用Hyper-V

要想再用Hyper-V就需要打开Hyper-V功能在运行-> appwiz.cpl界面，启动关闭功能中，Hyper-V全部勾选

再运行Hyper-V就出现Hyper-V虚拟机监控程序未运行问题。

解决方法

在开始里面的管理员 power-shell中执行:

bcdedit /set hypervisorlaunchtype auto

然后重启，问题就不大了

结论

有的时候没有说明具体原因，百度到的都不是这些问题。看到有些情况是，BIOS的硬件虚拟没启用，这类的情况可以参考其他文章。我这里介绍我遇到的情况。


版权声明：本文为CSDN博主「明天,今天,此时」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/LearnToPain/article/details/117336093
