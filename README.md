# 折腾OpenSUSE的笔记
## 写作意图：
1. 写给自己，同时学习使用git、github和markdown
2. 如果你完全没用过linux,这个项目可能帮助你把linux桌面环境用于部分的日常用途(**不能取代windows**)
## 选择OpenSUSE的原因：
1. OpenSUSE的社区力量强大
2. Yast非常好用
3. 傻瓜式的btrfs系统快照
## 正文

1. 安装前的准备工作：用Ventoy制作安装盘
   1. 下载工具[Ventoy](https://www.ventoy.net/cn/download.html "下载ventoy工具")
   2. [制作启动盘](https://www.ventoy.net/cn/doc_start.html)
   3. 上[官网](https://www.opensuse.org/)，下载OpenSUSE镜像到ventoy盘
2. 安装OpenSUSE
    1. 重启电脑，按F12,引导至ventoy启动
    2. 最好选择英文安装，否则某些软件里的的中文会让你感到困惑。不用太纠结，因为系统安装好以后也可以改成其他语言
    3. 暂时不配置网络
    4. 硬盘分区方案的简单介绍
        1. 如果待安装系统的电脑已经有EFI分区，就不要格式它，而是直接挂载；

           如果喜欢安装在移动硬盘上，也可以移动硬盘上划一个EFI分区（vfat格式）
        2. 再划一个50GB左右的btrfs分区，挂载/；然后再划一个70GB左右的xfs分区，挂载/home
    5. 安装必要软件
        1. 安装KDE桌面环境（按照个人喜爱吧，目前我用KDE比较顺心）
        2. 在最后的Summary检查安装配置，发现Software选项还可以~~折腾~~配置一下。发现Game,Office两个pattern不需要，取消勾选。点击details,又发现可以安装特定软件。搜索pppoe，安装相关软件，方便启动系统后直接拨号上网。
    6. 确认安装，等待安装完成后会自动重启至OpenSUSE
3. [配置](https://github.com/mtul0729/config-opensuse/blob/main/Post-installion.md)

# 欢迎补充！！