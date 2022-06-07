

 - 下载安装包 wget http://download.redis.io/releases/redis-?.?.?.tar.gz
 - 解压 tar -xvf 文件名.tar.gz
 - 安装 make install [destdir=/目录]
![解压Redis](https://img-blog.csdnimg.cn/20200810104644114.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
![安装Redis](https://img-blog.csdnimg.cn/20200810104754247.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
正常启动
![启动](https://img-blog.csdnimg.cn/20200810104910663.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
**使用配置文件启动**
创建一个文件夹放日志信息
![日志文件夹](https://img-blog.csdnimg.cn/20200810111145968.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
![创建配置文件](https://img-blog.csdnimg.cn/20200810111438216.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)

![修改配置文件](https://img-blog.csdnimg.cn/20200810111242360.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
![启动](https://img-blog.csdnimg.cn/20200810112317468.png)
启动多个redis服务器
复制配置文件
![复制配置文件](https://img-blog.csdnimg.cn/20200810113013582.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
修改配置文件里的端口
![修改配置](https://img-blog.csdnimg.cn/20200810112900182.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
启动redis，查看进程
![启动](https://img-blog.csdnimg.cn/20200810113249523.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)

**总结**
**Redis服务启动**

 - 默认配置启动

        redis-server 
        redis-server –-port 6379 
        redis-server –-port 6380 ……

 - 指定配置文件启动

        redis-server 
        redis.conf 
        redis-server redis-6379.conf 
        redis-server redis-6380.conf …… 
        redis-server conf/redis-6379.conf 
        redis-server config/redis-6380.conf ……

**Redis客户端连接**

 - 默认连接

        redis-cli

 - 连接指定服务器

        redis-cli -h 127.0.0.1 
        redis-cli –port 6379 
        redis-cli -h 127.0.0.1 –port 6379

**Redis服务端配置**
基本配置 

daemonize yes 
以守护进程方式启动，使用本启动方式，redis将以服务的形式存在，日志将不再打印到命令窗口中 

port 6*** 
设定当前服务启动端口号 

dir “/自定义目录/redis/data“ 
设定当前服务文件保存位置，包含日志文件、持久化文件（后面详细讲解）等 

logfile "6***.log“ 
设定日志文件名，便于查阅