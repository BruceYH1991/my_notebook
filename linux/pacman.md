### sudo pacman -S

```
$ sudo pacman -Ss <packagename>         #搜索包名,支持正则表达式,用于查询想要安装的软件

$ sudo pacman -Sc       # 清除缓存的软件
```
### sudo pacman -R

```
$ sudo pacman -Rs <packagename>     # 删除软件和相关的依赖

$ sudo pacman -Rns <packagename>        # 删除软件以及相关依赖和 全局 的配置文件
```

### sudo -pacman -Q

```
$ sudo pacman -Q | wc -l        # 查看安装软件的数量

$ sudo pacman -Qe       # 显示自己安装的软件

$ sudo pacman -Qq       # 不显示版本信息

$ sudo pacman -Qs   <name>      # 查看本地包含 name 的软件

$ sudo pacman -Qdt      # 显示不在需要的软件,没有安装且没有被其他软件所依赖

$ sudo pacman -R $(pacman -Qdtq)       #快速删除本地孤包,即不需要的软件
```

### 常用软件

```
# i3下更换主题软件
$ sudo pacman -S lxappearance

# i3下更换桌面
$ sudo pacman -S feh
$ sudo pacman -S variety    # 基于feh的软件

# i3下渲染器
$ sudo pacman -S compton
```

###  i3下的网络连接
```
# 查看网络设备
$ sudo nmcli dev

# 开启WiFi
$ sudo nmcli r wifi on

# 扫描WiFi
$ sudo nmcli dev wifi

# 连接WiFi
$ sudo nmcli dev wifi connect "wifi名" password "密码"
```

###  i3下音量调节

```
$ alsamixer     #音量调节工具
```
###  i3下图形化文件管理器

```
$ nautilus
```


