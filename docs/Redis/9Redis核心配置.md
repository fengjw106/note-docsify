@[TOC](Redis 核心配置)

## 服务器基础配置
**服务器端设定**
设置服务器以守护进程的方式运行

```java
daemonize yes|no
```
绑定主机地址

```java
bind 127.0.0.1
```
设置服务器端口号

```java
port 6379
```
设置数据库数量

```java
databases 16
```
![服务器端设定](https://img-blog.csdnimg.cn/20200814095300237.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)

**日志配置**
设置服务器以指定日志记录级别

```java
loglevel debug|verbose|notice|warning
```
日志记录文件名

```java
logfile 端口号.log
```
**注意：** 日志级别开发期设置为verbose即可，生产环境中配置为notice，简化日志输出量，降低写日志IO的频度

**客户端配置**
设置同一时间最大客户端连接数，默认无限制。当客户端连接到达上限，Redis会关闭新的连接

```java
maxclients 0
```
客户端闲置等待最大时长，达到最大值后关闭连接。如需关闭该功能，设置为 0

```java
timeout 300
```

**多服务器快捷配置**
导入并加载指定配置文件信息，用于快速创建redis公共配置较多的redis实例配置文件，便于维护

```java
include /path/server-端口号.conf
```