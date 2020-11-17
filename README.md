# tmux_for_windows
tmux是一个开源工具，用于在一个终端窗口中运行多个终端会话。本工具从msys2里提取，可以在Git for Windows的Git Bash (MingW64)下正常使用。

蘭雅sRGB 龙芯小本服务器 | [https://262235.xyz](https://262235.xyz)

### tmux在windows系统下安装使用
https://youtu.be/zSUwczhdtKI

![](https://raw.githubusercontent.com/hongwenjun/tmux_for_windows/master/tmux_for_windows.gif)

### 首先你要保证已经安装有 Git for Windows
下载地址 https://git-scm.com/download/win

### tmux for Git Bash (MingW64) 安装包使用
- 下载  [tmux_for_git-bash.zip](https://github.com/hongwenjun/tmux_for_windows/raw/master/tmux_for_git-bash.zip)
- 释放文件到 D:\Git
- 实际可执行文件在 D:\Git\usr\bin\tmux.exe

### tmux 使用
- Windows 开始菜单 运行 D:\Git\git-bash.exe
- 命令行输入 tmux

### git-bash环境下命令行安装

```bash
git clone https://github.com/hongwenjun/tmux_for_windows.git
cd tmux_for_windows/
unzip -x tmux_for_git-bash.zip  -d /
```

### 原始的 tmux for msys2 的安装包，不需要下载
```
# tmux-2.7-1 旧版本   tmux_for_windows/tmux_271
a31b2636ff7540ec11a38ac4d9c95dc9  libevent-2.1.8-1-x86_64.pkg.tar.xz
a7ac01f4ccef1ecedf9ef346fb2c818e  tmux-2.7-1-x86_64.pkg.tar.xz
ba061b3687f77dde53658a95793e952e  tmux_for_git-bash.zip   # 旧版本

# tmux-3.1-c1 新版本   tmux_for_windows/tmux_311
9abfa52145cf5a7e591847f58a5253e3  libevent-2.1.12-2-x86_64.pkg.tar.zst
b433f58e1267f5582de43d2e9d78d82d  tmux-3.1.c-1-x86_64.pkg.tar.zst
  
```

![](https://raw.githubusercontent.com/hongwenjun/tmux_for_windows/master/tmux_for_windows.png)


# tmux 启用鼠标操作
###  .tmux.conf 设定
```
# https://www.youtube.com/watch?v=xTplsyQaGFs

# tmux 启用鼠标操作
setw -g mouse
set-option -g history-limit 20000
set-option -g mouse on
bind -n WheelUpPane select-pane -t= \; copy-mode -e \; send-keys -M
bind -n WheelDownPane select-pane -t= \; send-keys -M
```
![](https://raw.githubusercontent.com/hongwenjun/tmux_for_windows/master/tmux_mouse.gif)

------


![](http://fishshell.com/assets/img/Terminal_Logo2_CRT_Flat.png)
## fish_for_git-bash

Fish 是"the friendly interactive shell"的简称，最大特点就是方便易用。很多其他 Shell 需要配置才有的功能，Fish 默认提供，不需要任何配置。

### fish for Git Bash (MingW64) 安装包使用
- 下载  [fish_for_git-bash.7z](https://github.com/hongwenjun/tmux_for_windows/raw/master/fish_for_git-bash.7z)
- 释放文件到 D:\Git
- 实际可执行文件在 D:\Git\usr\bin\fish.exe


### fish 使用教程
- http://fishshell.com/docs/current/tutorial.html

### 原始的 fish for msys2 的安装包，不需要下载
```
Path:  tmux_for_windows/fish_312
9cb0219a335d2b54c388cbf25c2ea456  bc-1.07.1-2-x86_64.pkg.tar.xz
4fd6c824c616709966167fdc5f1a5195  fish-3.1.2-1-x86_64.pkg.tar.zst
b882faf644ccd4770f7c3002e1dc6d71  groff-1.22.4-1-x86_64.pkg.tar.xz
0d78c572a6cd9f0bf88e2b0ceedf62e6  libpcre2_16-10.35-1-x86_64.pkg.tar.zst
f3d45b93b85a9d57c978224bd8111c09  libpipeline-1.5.2-1-x86_64.pkg.tar.xz
4dd5d447bb0e160502afe95a1bafe044  man-db-2.9.3-1-x86_64.pkg.tar.zst

```

## 把fish设为交互式shell
如果不将fish设为默认shell，就能照常运行Bash的初始化脚本。这能够保证用户当前的环境变量不受影响并且在fish中也能使用，因为fish是作为Bash的子进程运行的。下面是几种只把fish设为交互式shell的方法。

### 通过.bashrc启动fish
保持默认shell为Bash不变，然后添加一行**exec fish**到合适的Bash配置文件中，比如.bashrc。在这种方法中，Bash会正常执行/etc/profile和/etc/profile.d中的所有配置文件。相对于之后几种方法，这种是最通用的，因为这种方法在本机计算机和SSH远程计算机上都能使用。


### 使用终端复用器的选项
要将fish设为tmux启动的默认shell，在~/.tmux.conf中加入这行：

  set-option -g default-shell "/usr/bin/fish"

### 关闭问候语
默认情况下，每次启动fish，fish都会打印问候语。要关闭问候语，可以在fish中运行：

  set -U fish_greeting
  
### 网页界面
通过下面命令即可用浏览器打开fish的配置页面。

  fish_config
