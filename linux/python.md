### centos 安装 Python
###### 下载

```
wget https://www.python.org/ftp/python/3.7.0/Python-3.7.0.tgz
```
###### 安装,编译

```
tar -zxvf Python-3.7.0.tgz
cd Python-3.7.0
./configure
make&&make install

ps: 编译时报错 -->ModuleNotFound：No module named '_ctypes
需要安装工具: yum install libffi-devel -y
```
###### 安装pip

```
1.首先找到pip3的位置(在python3.6的安装包内)
        cd /usr/local/bin
        ls      (这里可以看见pip3.6的文件了)
 
        ln -s /usr/local/bin/pip3.6 /bin/pip3       #创建pip3命令的连接符
        pip3 -v

```
###### 配置环境变量（python和pip的）

```
mv /usr/bin/python /usr/bin/python.bak
ln -s /usr/local/bin/python3 /usr/bin/python
mv /usr/bin/pip /usr/bin/pip.bak
ln -s /usr/local/bin/pip3 /usr/bin/pip

```
###### 删除Python

```
rpm -qa|grep python3|xargs rpm -ev --allmatches --nodeps       卸载pyhton3
whereis python3 |xargs rm -frv           删除所有残余文件
   
whereis   python       查看现有安装的python

```

