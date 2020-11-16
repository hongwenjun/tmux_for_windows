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

# fish_for_git-bash
![](http://fishshell.com/assets/img/Terminal_Logo2_CRT_Flat.png)

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
