# config-opensuse
1. [清华packman](https://mirrors.tuna.tsinghua.edu.cn/help/opensuse/) 
  ```
  sudo zypper mr -da
  sudo zypper ar -cfg 'https://mirrors.tuna.tsinghua.edu.cn/opensuse/tumbleweed/repo/oss/' tuna-oss
  sudo zypper ar -cfg 'https://mirrors.tuna.tsinghua.edu.cn/opensuse/tumbleweed/repo/non-oss/' tuna-non-oss
  ```
  1.打开YaST
  2.进入YaST软件源
  3.点击添加
  4.选择指定URL
  5.输入名称与对应的URL
  tuna-packman  
  https://mirrors.tuna.tsinghua.edu.cn/packman/suse/openSUSE_Tumbleweed/
  6.点击下一步，等待源刷新
  7.完成
2. [安装codecs]（https://en.opensuse.org/SDB:Installing_codecs_from_Packman_repositories#Option_3:_YaST）
3. `zypper in yt-dlp thunderbird zsh`
4. 安装zsh ohmyzsh
```bash
wget https://ghproxy.com/https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh
sh install.sh
```
3. 安装clion
5. 卸载kmail
6. 安装exfat，ntfs支持
7. 
