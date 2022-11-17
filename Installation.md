1. 制作安装盘
   1. [Ventoy](https://www.ventoy.net/cn/download.html "下载ventoy工具")
   2. [制作启动盘](https://www.ventoy.net/cn/doc_start.html)
   3. 上[官网](https://www.opensuse.org/)，下载OpenSuse镜像到ventoy盘
2. 安装OpenSuse
    1. 重启电脑，按F12,引导至ventoy启动
   1. 英文安装
   2. 暂时不配置网络
   3. 硬盘分区方案的简单介绍
      1. 如果待安装系统的电脑已经有EFI分区，就不要格式它，而是直接挂载；

         如果喜欢安装在移动硬盘上，也可以移动硬盘上划一个EFI分区（vfat格式）
      2. 再划一个50GB左右的btrfs分区，挂载/；然后再划一个70GB左右的xfs分区，挂载/home
   4. 安装必要软件
       1. 安装KDE桌面环境（按照个人喜爱吧，目前我用KDE比较顺心）
       2. 在最后的Summary检查安装配置，发现Software选项还可以~~折腾~~配置一下。发现game,office不需要，取消勾选。点击details,又发现可以安装特定软件。搜索pppoe