# 折腾OpenSUSE的笔记
## 写作意图：
1. 写给自己，同时学习使用git、github和markdown
2. 如果你完全没用过linux,这个项目可能帮助你把linux桌面环境用于部分的日常用途(**不能取代windows**)
## 选择OpenSUSE的原因：
1. OpenSUSE的社区力量强大
2. Yast非常好用
3. 傻瓜式的btrfs系统快照
## 正文

### 安装OpenSUSE
参看[Category:SDB:Installation ](https://en.opensuse.org/Category:SDB:Installation)。  
或者使用Ventoy  
1. 下载工具[Ventoy](https://www.ventoy.net/cn/download.html "下载ventoy工具")
2. [制作启动盘](https://www.ventoy.net/cn/doc_start.html)
3. 上[官网](https://www.opensuse.org/)，下载OpenSUSE镜像到ventoy盘
4. 重启电脑，按F12,引导至ventoy启动
5. 最好选择英文安装，否则某些软件里的的中文会让你感到困惑。不用太纠结，因为系统安装好以后也可以改成其他语言
6. 暂时不配置网络
7. 硬盘分区方案的简单介绍
   1. 如果待安装系统的电脑已经有EFI分区，就不要格式它，而是直接挂载；

    如果要安装在移动硬盘上，也可以移动硬盘上划一个EFI分区（vfat格式）
   2. 再划一个50GB左右的btrfs分区，挂载/；然后再划一个70GB左右的xfs分区，挂载/home
8. 安装必要软件
   1. 安装KDE桌面环境（按照个人喜爱吧，目前我用KDE比较顺心）
   2. 在最后的Summary检查安装配置，发现Software选项还可以~~折腾~~配置一下。发现Game,Office两个pattern不需要，取消勾选。点击details,又发现可以安装特定软件。搜索pppoe，安装相关软件，方便启动系统后直接拨号上网。
9. 确认安装，等待安装完成后会自动重启至OpenSUSE
### 简单配置一下系统
1. 联网
         + networkmanager连接wifi
         + 如果是拨号上网，确保已经安装PPPoE支持。在networkmanager里添加一个dsl的连接
2. 配置国内仓库镜像 (以Tumbleweed为例)
   1. 已有的仓库不必换成国内仓库镜像
   3. [安装codecs](https://en.opensuse.org/SDB:Installing_codecs_from_Packman_repositories#Option_3:_YaST)  
   安装前确保添加一个稳定快速的packman仓库镜像，[官网](http://packman.links2linux.org/mirrors)有镜像网站列表。没有codecs就可能无法正常使用某些视频网站。
   4. 安装各类软件
   - 通过Yast安装一些软件  
     打开Yast,按需搜索安装以下软件
       + `git`
       + `clang`
       + `gdb`
       + `opi` —— 更方便地安装OBS里的包
       + `gh` —— github的命令行官方客户端，方便把git仓库托管到github。
       + `MozillaThunderbird` —— 一个email客户端
       + `fcitx5-chinese-addons` —— linux上非常先进的fcitx5平台的中文输入法（安装之后再打开input method > Add Input Method > 搜索“Pinyin” > Add > OK,这才能启用）
       + `yt-dlp` —— 可以把各类视频网站的的视频下载下来（ 未必能下载b站1080P视频）
       + `exfat-utils` —— 用以支持exfat文件系统（现在U盘很多出厂默认使用exfat,所以建议安装）
       + `ntfsprogs` —— 支持ntfs文件系统（。。。懒得解释）
       + `torbrowser-launcher` —— 用来安装、启动torbrowser（翻墙才能安装）
       + `telegram-desktop` —— 不用解释  
       + `fish`  —— 也许比zsh和bash都更人性化
       + `texlive`
     
     **或者**这样
     ```bash
     sudo zypper install git clang gdb zsh opi gh MozillaThunderbird fcitx5-chinese-addons yt-dlp exfat-utils ntfsprogs torbrowser-launcher telegram-desktop fish
     ```
   - 安装仓库里找不到的软件
       + 安装Clion  
         通过[Toolbox App](https://www.jetbrains.com/toolbox-app/)安装、管理Clion更方便
       + `opi vscode`
       + 安装[WPS](https://www.wps.cn/product/wpslinux#)  
         下载rpm安装包，然后`sudo zypper install /安装包/的/路径`
       + 安装Resilio Sync   
         以下节选自[Installing Sync package on Linux](https://help.resilio.com/hc/en-us/articles/206178924)
         >    **Running Sync under the current user**
         >
         >    If you want to run Sync under your current user - edit file /usr/lib/systemd/user/resilio-sync.service and change "WantedBy=multi-user.target" to "WantedBy=default.target". Save this file and then enable the service with `--user` parameter:
         >
         >    `systemctl --user enable resilio-sync`
         >
         >    Systemctl can be also run with the following arguments: `start, stop, enable, disable, status`
         >
         >    For example, to start Sync under current user:
         >
         >    `systemctl --user start resilio-sync`
         >
         >    To force the user session to be active on headless linux, you can use command:
         >
         >    `sudo loginctl enable-linger username`
   - 安装翻墙软件,比如clash for windows
   - 安装腾讯会议  
     先上[官网](https://source.meeting.qq.com/download-center.html)确认最新版本号，然后上[OBS](https://build.opensuse.org/)找，或者`opi wemeet`
   - 安装[Veracrypt](https://veracrypt.fr/en/Downloads.html)
5. Extra
   - 安装笔记软件  
     vscode、clion、idea等软件可以同时支持markdown和git，也许可以用来记笔记。更好的选择是[logseq](logseq.com)
   - 安装微信、QQ  
     微信目前应该没有好用又稳定的方案，而[QQ](https://im.qq.com/linuxqq/index.shtml)比较好用。
***
# 至此，你应该可以开启~~糟心~~愉快的OpenSUSE之旅啦！
# 欢迎补充！！