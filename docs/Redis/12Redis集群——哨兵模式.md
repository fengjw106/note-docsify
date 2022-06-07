@[TOC](哨兵模式)

## 哨兵简介

**主机“宕机”**

 - 关闭master和所有slave 
 - 找一个slave作为master 
 - 修改其他slave的配置，连接新的主
 - 启动新的master与slave 
 - 全量复制*N+部分复制*N

**问题**
 - 关闭期间的数据服务谁来承接？ 
 - 找一个主？怎么找法？ 
 - 修改配置后，原始的主恢复了怎么办？

**哨兵**
哨兵(sentinel) 是一个分布式系统，用于对主从结构中的每台服务器进行监控，当出现故障时通过投票机制选择新的master并将所有slave连接到新的master。

**哨兵的作用**

 - 监控 
   - 不断的检查master和slave是否正常运行。 
   - master存活检测、master与slave运行情况检测 
 - 通知（提醒）
   - 当被监控的服务器出现问题时，向其他（哨兵间，客户端）发送通知。 
 - 自动故障转移
   - 断开master与slave连接，选取一个slave作为master，将其他slave连接到新的master，并告知客户端新的服务器地址

注意：
 哨兵也是一台redis服务器，只是不提供数据服务 
通常哨兵配置数量为单数

## 启用哨兵模式
**配置哨兵**

 - 配置一拖二的主从结构 
 - 配置三个哨兵（配置相同，端口不同） 参看sentinel.conf 
 - 启动哨兵

```java
redis-sentinel sentinel-端口号.conf
```
![配置哨兵](https://img-blog.csdnimg.cn/20200816102507607.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
**操作**

修改配置文件
![修改配置文件](https://img-blog.csdnimg.cn/20200816103318302.png#pic_center)
添加好配置文件，三个哨兵，一个master两个slave
![添加配置文件](https://img-blog.csdnimg.cn/20200816104358644.png#pic_center)
启动哨兵和服务器，查看info
![查看info](https://img-blog.csdnimg.cn/2020081611002336.png#pic_center)
哨兵之间会自动识别，可以从日志和配置文件中查看
![日志](https://img-blog.csdnimg.cn/20200816110344153.png#pic_center)
![配置文件·](https://img-blog.csdnimg.cn/202008161105473.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
现在将6379端口的master关闭，模拟master宕机，查看哨兵日志，看哨兵怎么工作
![哨兵工作](https://img-blog.csdnimg.cn/2020081611142132.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)
6379master宕机后，哨兵就把6379down掉，然后投票选出新的master，新的master为6380,6379和6381为slave

再将6379上线，6379就会以slave的身份加入集群
![上线](https://img-blog.csdnimg.cn/20200816114134668.png#pic_center)


## 哨兵工作原理
**主从切换**
哨兵在进行主从切换过程中经历三个阶段

 - 监控 
 - 通知 
 - 故障转移

### 阶段一：监控阶段

 - 用于同步各个节点的状态信息 
   - 获取各个sentinel的状态（是否在线） 
   - 获取master的状态 
     - master属性 
       - runid
       - role：master 
     - 各个slave的详细信息 
    - 获取所有slave的状态（根据master中的slave信息） 
      - slave属性
        - runid 
        - role：slave 
        - master_host、master_port 
        - offset 
         - ……

![监控阶段](https://img-blog.csdnimg.cn/20200816114514359.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)

### 阶段二：通知阶段
![通知阶段](https://img-blog.csdnimg.cn/20200816114607729.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)

### 阶段三：故障转移阶段
![故障转移阶段1](https://img-blog.csdnimg.cn/20200816114700880.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)

![故障转移阶段2](https://img-blog.csdnimg.cn/20200816114748192.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70#pic_center)

 - 服务器列表中挑选备选master 
    - 在线的 
    - 响应慢的 
   - 与原master断开时间久的 
   - 优先原则 
     - 优先级 
     - offset 
     - runid
 - 发送指令（ sentinel ）
   - 向新的master发送slaveof no one 
   - 向其他slave发送slaveof 新masterIP端口

**主从切换总结**

 - 监控 
   - 同步信息 
 - 通知 
   - 保持联通 
 - 故障转移 
   - 发现问题 
   - 竞选负责人 
   - 优选新master
   - 新master上任，其他slave切换master，原master作为slave故障回复后连接