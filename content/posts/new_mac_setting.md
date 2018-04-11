---
title: "New Mac Settings for OBSESSIONS"
date: 2018-04-11T05:06:31-04:00
draft: false
tags: ["Mac"]
---
# 强迫症的新Macbook设置指南
新mac到了，想要保持以前的使用习惯还是要配置一番，边配置边写咯

### 触摸板三指拖移
三指拖移在设置>辅助功能>鼠标与触摸板>触摸板选项，启动拖移中选择三指拖移。

### 显示电量百分比
确认节能器的显示电源状态已经打勾（默认），在屏幕顶上菜单条中点击电池，选择显示电池百分比。

### `brew`安装
首先下载brew的安装脚本[brew安装脚本](https://github.com/KKSun/backup-for-mac-settings/blob/master/brew_install.rb)
`ruby brew_install.rb`

### 链接`brewcask`
`brew tap caskroom/cask`

### 用brew安装一切
`python3`
`brew cask install java`
……
所有的软件源管理都在`brew`中，`yarn`、`pip`、`npm`都通过`brew`安装。

### `brew cask`安装小插件
包括`quicksilver`，`go2shell`

### 轻度修改`.vimrc`
只添加三行，显示一下高亮代码即可
```
syntax enable
syntax on
colorscheme desert
```

### 配置shell
在shell的设置中将默认shell改为zsh，我没有使用iTerm2，用的就是Mac自带的终端，改成自己喜欢的颜色和字体就好
```
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

### 配置quick look
使用“一指禅”来查看各种文件，包括代码高亮和视频等。
脚本链接[quick look安装脚本](https://github.com/KKSun/backup-for-mac-settings/blob/master/quicklookinstall.sh)

### 用virtual box安装ubuntu
有的时候不的不用linux（T—T！）
vmware碰到了显示不全的问题，安装进行不下去；如果使用快速安装则不能装增强应用。感觉很坑，遂弃之。
parallel desktop碰到的问题是安装后重启不能进入系统，也弃了。
回到virtual box，勉强用一用也可以，增强应用如果装不上先`sudo apt-get upgrade`，升级了依赖就能装上了。
安装增强之后我做到了双向共享剪贴板（文字），但不能系统间文件拖拽。
共享文件夹在安装增强应用后会自动挂在在`/media`文件夹下，如果不能访问共享文件夹，把本机用户添加到vboxsf用户组就好了。
这个虚拟机先凑合使着

### 安装win双系统


### 剩下的随用随装
包括intellij idea，pycharm，anaconda等等



