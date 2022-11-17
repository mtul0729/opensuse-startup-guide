# config-opensuse
## 配置国内仓库镜像 
  ```
  sudo zypper mr -da
  sudo zypper ar -cfg 'https://mirrors.tuna.tsinghua.edu.cn/opensuse/tumbleweed/repo/oss/' tuna-oss
  sudo zypper ar -cfg 'https://mirrors.tuna.tsinghua.edu.cn/opensuse/tumbleweed/repo/non-oss/' tuna-non-oss
  ```
添加[清华packman镜像](https://mirrors.tuna.tsinghua.edu.cn/help/opensuse/)
  1. 打开YaST
  2. 进入YaST软件源
  3. 点击添加
  4. 选择指定URL
  5. 输入名称与对应的URL
  tuna-packman  
  https://mirrors.tuna.tsinghua.edu.cn/packman/suse/openSUSE_Tumbleweed/
  6. 点击下一步，等待源刷新
  7. 完成
## [安装codecs](https://en.opensuse.org/SDB:Installing_codecs_from_Packman_repositories#Option_3:_YaST)
## 安装软件
`zypper in aria2 yt-dlp thunderbird zsh opi torbrowser`
### 安装 ohmyzsh
```bash
wget https://ghproxy.com/https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
sh install.sh
```
## 安装clion
通过[Toolbox App](https://www.jetbrains.com/toolbox-app/)安装、管理Clion更方便，
## 卸载kmail
## 安装exfat，ntfs支持
 
