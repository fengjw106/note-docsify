# Redis简单入门
## Redis介绍

**问题**：12306网站，淘宝，京东网站服务器崩溃

 - 访问量巨大
 - 高并发

**原因**：关系型数据库

 - 性能瓶颈：磁盘IO性能低下 
 - 扩展瓶颈：数据关系复杂，扩展性差，不便于大规模集群

**解决**：

 - 降低磁盘IO次数，越低越好  ——内存存储
 - 除去数据间的关系  ——仅存数据，不搞关系

nosql：泛指非关系性数据库，作为关系数据库的**补充**

特征：

 - 可扩容，可伸缩 
 - 大数据下要高性能
 -  灵活的数据模型 
 - 高可用

常见的Nosql数据库

 - Redis
 - memcache
 -  HBase
 -  MongoDB

![Redis实例方案](https://img-blog.csdnimg.cn/20200622115638197.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)

**Redis**：C语言开发的开源的高性能的键值对数据库

特征：

 - 数据间没有必然的关系
 -  内部采用单线程机制工作
 -  高性能 
 - 多数据类型支持
 -  持久化支持，进行数据灾难恢复

应用：
为热点数据加速查询
任务队列，比如秒杀，访问统计
及时信息查询
时效性信息控制
分布式数据共享
消息队列
分布式锁

## Redis下载和安装
下载地址：https://github.com/MSOpenTech/redis/tags
网络不好可以用网盘：
链接：https://pan.baidu.com/s/1ccLuQzcaL4tKuKqWgWjZSg 
提取码：qgnx
![Redis的下载](https://img-blog.csdnimg.cn/2020062212091686.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
目录

![Redis目录](https://img-blog.csdnimg.cn/20200622130721676.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
启动Redis
![启动Redis](https://img-blog.csdnimg.cn/2020062213081772.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
客户端
![Redis客户端](https://img-blog.csdnimg.cn/20200622130856349.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)

## Redis的基本操作

### 命令
添加指令

```
set key value
```
查询指令

```
get key
```
注意：如果不存在，返回空（uil）

清屏指令

```
clear
```
帮助指令

```
help XXX
help @XXX
```
退出

```
quit
exit
<ESC>
```