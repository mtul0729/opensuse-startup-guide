# 安装好OpenSUSE之后你应该做的事
## 联网
  + networkmanager连接wifi
  + 如果是拨号上网，确保已经安装PPPoE支持。networkmanager里添加一个dsl
## 配置国内仓库镜像 (以Tumbleweed为例)
  这里我选择的是清华的[tuna源](https://mirrors.tuna.tsinghua.edu.cn/help/opensuse/)
  ```
  sudo zypper mr -da
  sudo zypper ar -cfg 'https://mirrors.tuna.tsinghua.edu.cn/opensuse/tumbleweed/repo/oss/' tuna-oss
  sudo zypper ar -cfg 'https://mirrors.tuna.tsinghua.edu.cn/opensuse/tumbleweed/repo/non-oss/' tuna-non-oss
  ```
  1. 添加[清华packman镜像](https://mirrors.tuna.tsinghua.edu.cn/help/opensuse/)（安装codecs必需）
      1. 打开YaST
     2. 进入YaST软件源（仓库管理）
     3. 点击添加
     4. 选择指定URL
     5. 输入名称与对应的URL
     tuna-packman  
     https://mirrors.tuna.tsinghua.edu.cn/packman/suse/openSUSE_Tumbleweed/
     6. 点击下一步，等待源刷新
     7. 完成
## [安装codecs](https://en.opensuse.org/SDB:Installing_codecs_from_Packman_repositories#Option_3:_YaST)
## 安装各类软件
### 通过Yast安装一些软件
  打开Yast,按需搜索安装以下软件（每个安装包都有description，查看以了解该软件）
  + zsh —— 搭配下面提到的ohmyzsh使你更轻松地敲命令
  + gh —— github的命令行官方客户端，方便把git仓库托管到github。
  + mozillathunderbird —— email客户端
  + fcitx5-chinese-addons —— linux上非常先进的fcitx5平台的中文输入法（安装之后再打开input method > Add Input Method > 搜索“Pinyin” > Add > OK,这才能启用）
  + yt-dlp —— 可以把各类视频网站的的视频下载下来（未必能下载b站1080P视频）
  + exfat-utils —— 用以支持exfat文件系统（现在U盘很多出厂默认使用exfat,所以建议安装）
  + ntfsprogs —— 支持ntfs文件系统（。。。懒得解释）
  + torbrowser-launcher —— 用来安装、启动torbrowser（翻墙才能安装）
  + telegram-desktop —— 不用解释
### 安装仓库里找不到的软件 
  1. 安装 ohmyzsh
  ```bash
  wget https://ghproxy.com/https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
  sh install.sh
  ```
  2. 安装Clion  
     通过[Toolbox App](https://www.jetbrains.com/toolbox-app/)安装、管理Clion更方便
3. 安装[WPS](https://www.wps.cn/product/wpslinux#) 
   1. `sudo zypper install 安装包`
   2. 如果发现是英文，不喜欢，至少有以下方法解决
      1. 把系统改成中文
      2. 每次都敲命令`LANG=zh_CN.utf8 wps`
      3. 基于上一个方法写个shell script
4. 安装翻墙软件
### 安装笔记软件
不需要啦～,在clion里用markdown写文档，搭配git就很方便，还可以同步到github
### 安装微信、QQ
量力而为吧，反正我是放弃了。勇士可以自己到[OBS](https://build.opensuse.org/)里找个包安装。
***
至此，你应该可以开启~~抓狂~~愉快的OpenSUSE之旅啦！

  
 
