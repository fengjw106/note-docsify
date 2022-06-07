@[TOC](集群)

## 集群简介

现状问题：业务发展过程中遇到的峰值瓶颈

 - redis提供的服务OPS可以达到10万/秒，当前业务OPS已经达到10万/秒 
 - 内存单机容量达到256G，当前业务需求内存容量1T
 - 使用集群的方式可以快速解决上述问题

**集群架构**

集群就是使用网络将若干台计算机联通起来，并提供统一的管理方式，使其对外呈现单机的服务效果

**集群作用**

 - 分散单台服务器的访问压力，实现负载均衡
 - 分散单台服务器的存储压力，实现可扩展性 
 - 降低单台服务器宕机带来的业务灾难

## Redis集群结构设计
**数据存储设计**

 - 通过算法设计，计算出key应该保存的位置 
 - 将所有的存储空间计划切割成16384份，每台主机保存一部分，每份代表的是一个存储空间，不是一个key的保存空间
 - 将key按照计算出的结果放到对应的存储空间
 - 增强可扩展性

**集群内部通讯设计**

 - 各个数据库相互通信，保存各个库中槽的编号数据 
 - 一次命中，直接返回 
 - 一次未命中，告知具体位置

## cluster集群结构搭建

### 搭建方式

 - 原生安装（单条命令）
   - 配置服务器（3主3从）
   - 建立通信（Meet）
   - 分槽（Slot）
   - 搭建主从（master-slave）
 - 工具安装（批处理）

①将服务器启动起来

②在搭建开始之前要有ruby和gem的支持，如果为联网状态就执行
```java
sudo yum install ruby
```
然后查看是否已经下载完成
![查看是否已经下载完成](https://img-blog.csdnimg.cn/20200816141429641.png#pic_center)
③集群添加结点 
./ 的意义是该指令只在当前目录下有效
replicas 1 的意义是每个master跟一个slave

```java
./redis-trib.rb create --replicas 1 127.0.0.1:6379 127.0.0.1:6380 127.0.0.1:6381 127.0.0.1:6382 127.0.0.1:6383 127.0.0.1:6384
```
然后出现问题 ，Ruby的redis接口没有安装，需要安装Redis接口
```java
/usr/share/rubygems/rubygems/core_ext/kernel_require.rb:55:in `require': cannot load such file -- redis (LoadError)
	from /usr/share/rubygems/rubygems/core_ext/kernel_require.rb:55:in `require'
	from ./redis-trib.rb:25:in `<main>'
```
输入命令，进行安装
```java
gem install redis
```
但是又发现版本太低
![ruby版本太低](https://img-blog.csdnimg.cn/20200816143210252.png#pic_center)
需要更新版本，在此之前要下载RVM。RVM是一个命令行工具，可以提供一个便捷的多版本Ruby环境的管理和切换。RVM需要通过CRUL来进行下载，那要先下载CUEL，CURL是Linux下的文件传输工具，利用URL的规则在命令行下工作，输入命令 
```java
yum install curl
```

进行安装，使用curl安装rvm，使用key进行RVM的安装

```java
curl -L get.rvm.io | bash -s stable
```
![使用curl安装rvm](https://img-blog.csdnimg.cn/2020081614464987.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
![输入key](https://img-blog.csdnimg.cn/20200816144848292.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
使用source让当前shell读入路径为" /usr/local/rvm/scripts/rvm "（路径可以自定义）的shell文件并依次执行文件中的所有语句，并重新执行刚修改的初始化文件，使之立即生效，而不必注销并重新登录，
输入命令 "  source /usr/local/rvm/scripts/rvm " ，查看rvm中管理的所有ruby版本，
输入命令 " rvm list known " 进行查询
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200816145246141.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
安装需要的ruby版本

```java
rvm install 2.4.6
```
检查版本，移除旧版本，check新版本
```java
rvm use 2.4.6 //启用新版本

rvm remove 2.0.0 //移除旧版本

ruby -v //检查当前使用的版本号
```
![检查版本移除旧版本](https://img-blog.csdnimg.cn/20200816150922810.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
然后继续redis接口安装（gem install redis），然后可以执行redis集群启动命令
![执行redis集群启动命令](https://img-blog.csdnimg.cn/20200816151447371.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
结点加入成功，可以看到槽的分配
![结点加入成功](https://img-blog.csdnimg.cn/20200816151904489.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
④查看数据的变化
**nodes-6379.conf**，可以清晰的看到各个master对应的slave，还有各个分配的槽
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200816152534364.png#pic_center)
**服务器日志**
在集群连接之前为等待连接
![服务器日志](https://img-blog.csdnimg.cn/20200816152853704.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
进程上也有变化
![进程上变化](https://img-blog.csdnimg.cn/2020081615312049.png#pic_center)
### Cluster配置

在启动服务器之前

添加节点

```java
cluster-enabled yes|no
```
cluster配置文件名，该文件属于自动生成，仅用于快速查找文件并查询文件内容

```java
cluster-config-file <filename>
```
节点服务响应超时时间，用于判定该节点是否下线或切换为从节点

```java
cluster-node-timeout <milliseconds>
```
master连接的slave最小数量

```java
cluster-migration-barrier <count>
```
![Cluster配置](https://img-blog.csdnimg.cn/20200816123217624.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)

### Cluster节点操作命令

查看集群节点信息
```java
cluster nodes
```
进入一个从节点 redis，切换其主节点

```java
cluster replicate <master-id>
```
发现一个新节点，新增主节点

```java
cluster meet ip:port
```
忽略一个没有solt的节点
```java
cluster forget <id>
```
手动故障转移

```java
cluster failover
```
### redis-trib命令
添加节点

```java
redis-trib.rb add-node
```
删除节点

```java
redis-trib.rb del-node
```
重新分片

```java
redis-trib.rb reshard
```

### 读取数据

添加数据，如图
![添加数据](https://img-blog.csdnimg.cn/20200816153526310.png#pic_center)
可以看到redis-cli不在适用，要使用redis-cli -c 重定向到5798这个槽
取数据的时候服务器也会发生变换
![取数据](https://img-blog.csdnimg.cn/20200816153844329.png#pic_center)

### 主从下线和主从切换

**将slave下线**

如将6382下线，查看它的master和和其他服务器的日志显示

6379会显示：
![下线6379会显示](https://img-blog.csdnimg.cn/20200816155047784.png#pic_center)
其他显示：
![下线其他显示](https://img-blog.csdnimg.cn/2020081615514398.png#pic_center)
**将6382上线** 

查看它的master和和其他服务器的日志显示

6379显示：
![上线6379显示](https://img-blog.csdnimg.cn/20200816155357758.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
其他会显示：
![上线其他会显示](https://img-blog.csdnimg.cn/20200816155451865.png#pic_center)
**将master下线**

如将6379下线，查看它的slave和和其他服务器的日志显示
6382显示：会显示与master断开，然后尝试连接，一秒一次，次数为配置文件中设置为依据，10秒为10次
![6379下线1](https://img-blog.csdnimg.cn/20200816160200738.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
超过连接时间后slave就会成为新的master继续工作，集群修改成功
![6379下线2](https://img-blog.csdnimg.cn/20200816160455564.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
**将master上线**

再将6379上线，显示成为6382的slave
![6379上线](https://img-blog.csdnimg.cn/20200816160923194.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
从6382的日志显示：清除标记，完成主从同步
![6382的日志显示](https://img-blog.csdnimg.cn/20200816161043979.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
从结点的记录信息也可观察到，使用命令 cluster nodes，前后6379和6382的变化
![6379上线记录信息](https://img-blog.csdnimg.cn/20200816161714607.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)