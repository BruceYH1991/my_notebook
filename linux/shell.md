### 删除指定程序的进程号:

```
ps -ef | grep mysql-workbench-bin | grep -v grep | awk '{print $2}' | xargs kill -9

ps -ef | grep server.py | grep -v gre | awk '{print $2}' | xargs kill -9
```
### 临时加入环境变量

```
export PYTHONPATH=/data/python/risk-etl-service/:$PYTHONPATH
```
### 启动aria2

```
sudo aria2c --conf-path=/etc/aria2/aria2.conf

```

### ssh链接服务器

```
ssh -i Test.pem centos@13.251.77.216
ssh -i Test.pem centos@13.251.63.156        # 废弃

ssh root@111.231.209.157
cash@123456
```

### ssh 长连接

###### 方法1: 修改server端的etc/ssh/sshd_config

```
ClientAliveInterval 60 ＃server每隔60秒发送一次请求给client，然后client响应，从而保持连接
ClientAliveCountMax 3 ＃server发出请求后，客户端没有响应得次数达到3，就自动断开连接，正常情况下，client不会不响应

systemctl reload sshd

# Manjaro 执行:
sudo systemctl start sshd
```
###### 方法2: 修改client端的etc/ssh/ssh_config添加以下：（在没有权限改server配置的情形下）

```
ServerAliveInterval 60 ＃client每隔60秒发送一次请求给server，然后server响应，从而保持连接
ServerAliveCountMax 3  ＃client发出请求后，服务器端没有响应得次数达到3，就自动断开连接，正常情况下，server不会不响应

```
###### 方法3: 在命令参数里ssh -o ServerAliveInterval=60 这样子只会在需要的连接中保持持久连接， 毕竟不是所有连接都要保持持久的

```
ssh -o ServerAliveInterval=60 
```





### tail 指令

```
tail -f 实时输出
tail -n 100 输出最后100行
```

### 查看当前路径

```
pwd
```

### 后台执行程序

```
$ nohup python -u test.py > out.log 2>&1 &
# 2>&1 :  错误输出到 标准输出
$ nohup python3 -u server.py > server.out &
```


---
### 解决ssh登录后闲置时间过长而断开连接
##### 方法一
###### 修改/etc/ssh/sshd_config配置文件，找到ClientAliveCountMax（单位为分钟）修改你想要的值。 
执行：

```
service sshd reload 
```
##### 方法二【推荐】
###### 找到所在用户的.ssh目录，如root用户该目录在：/root/.ssh/，在该目录创建config文件,并加入下面一句:

```
$ vi /root/.ssh/config

ServerAliveInterval 60
```

### 配置触摸板

```
$ vim /etc/X11/xorg.conf.d/30-touchpad.conf


---
 Section "InputClass"
        Identifier "tap-by-default"
        MatchIsTouchpad "on"
        MatchDriver "libinput"
        Option "Tapping" "on"
        Option "ClickMethod" "clickfinger"
        Option "NaturalScrolling" "true"
 EndSection
~

```

### 配置多屏显示器

```
$ xrandr        # 显示屏幕接口信息

# 配置输出, eDP1: 主显示器接口
$ xrandr --output eDP1 --mode 1920x1080 --right-of DP1
```





