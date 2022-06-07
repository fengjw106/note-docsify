# Jedis简介
## 编程语言与redis

 - Java语言连接redis服务
   - Jedis
   - SpringData Redis
   - Lettuce
 - C 、C++ 、C# 、Erlang、Lua 、Objective-C 、Perl 、PHP 、Python 、Ruby 、Scala
 - 可视化连接redis客户端
   - Redis Desktop Manager
   - Redis Client
   - Redis Studio
## 简单程序
环境是idea的maven下
1.导入坐标
一个是jedis坐标，还有一个用于测试用的坐标
```java
	<dependencies>
        <dependency>
            <groupId>redis.clients</groupId>
            <artifactId>jedis</artifactId>
            <version>2.9.0</version>
        </dependency>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.12</version>
        </dependency>
    </dependencies>
```
2.编写一个测试类

```java
import org.junit.Test;
import redis.clients.jedis.Jedis;

public class JedisTest {

    @Test
    public void jedisTest(){
        //建立连接
        Jedis jedis = new Jedis("127.0.0.1", 6379);
        //操作数据库
        String set = jedis.set("name", "zhangsan");
        System.out.println(set);
        String name = jedis.get("name");
        System.out.println(name);
        //关闭连接
        jedis.close();
    }
}

```
3.运行测试类
这里要将Redis启动起来
运行结果
![运行结果](https://img-blog.csdnimg.cn/202007131618175.png)
## Jedis读写redis数据
简单写写几个测试方法

```java
@Test
    public void testList(){
        //1.连接redis
        Jedis jedis = new Jedis("127.0.0.1", 6379);
        //2.操作redis
        jedis.lpush("list1","a","b","c");
        jedis.rpush("list1","x");

        List<String> list1 = jedis.lrange("list1", 0, -1);
        for(String s : list1){
            System.out.println(s);
        }

        System.out.println(jedis.llen("list1"));

        System.out.println();
        //3.关闭连接
        jedis.close();
    }

    @Test
    public void testHash(){
        //1.连接redis
        Jedis jedis = new Jedis("127.0.0.1", 6379);
        //2.操作redis

        jedis.hset("hash1","a1","b1");
        jedis.hset("hash1","a2","a2");
        jedis.hset("hash1","a3","b3");

        Map<String, String> hash1 = jedis.hgetAll("hash1");

        System.out.println(hash1);

        System.out.println(jedis.hlen("hash1"));

        System.out.println();
        //3.关闭连接
        jedis.close();
    }
```

**案例：服务调用次数控制**

人工智能领域的语义识别与自动对话将是未来服务业机器人应答呼叫体系中的重要技术，百度自研用户评价语义识别服务，免费开放给企业试用，同时训练百度自己的模型。现对试用用户的使用行为进行限速，限制每个用户每分钟最多发起10次调用

**案例要求**
①设定A、B、C三个用户
②A用户限制10次/分调用，B用户限制30次/分调用，C用户不限制

**案例：需求分析**
①设定一个服务方法，用于模拟实际业务调用的服务，内部采用打印模拟调用
②在业务调用前服务调用控制单元，内部使用redis进行控制，参照之前的方案
③对调用超限使用异常进行控制，异常处理设定为打印提示信息
④主程序启动3个线程，分别表示3种不同用户的调用

**案例：实现步骤**
1.设定业务方法
2.设定多线类，模拟用户调用
3.设计redis控制方案
4.设计启动主程序

```java
public class Service {
    private String id;
    private int num;

    public Service(String id,int num){
        this.id = id;
        this.num = num;
    }
    //控制单元
    public void service(){
        Jedis jedis = new Jedis("127.0.0.1",6379);
        String value = jedis.get("compid:"+id);
        //判断该值是否存在
        try{
            if(value == null){
                //不存在，创建该值
                jedis.setex("compid:"+id,3,Long.MAX_VALUE-num+"");
            }else{
                //存在，自增，调用业务
                Long val = jedis.incr("compid:"+id);
                business(id,num-(Long.MAX_VALUE-val));
            }
        }catch (JedisDataException e){
            System.err.println(id+"使用已经到达次数上限，请升级会员级别");
            return;
        }finally{
            jedis.close();
        }
    }
    //业务操作
    public void business(String id,Long val){
        System.out.println("用户:"+id+" 业务操作执行第"+val+"次");
    }
}

class MyThread extends Thread{
    Service sc ;
    public MyThread(String id,int num){
        sc = new Service(id,num);
    }
    public void run(){
        while(true){
            sc.service();
            try {
                Thread.sleep(200L);
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

class Main{
    public static void main(String[] args) {
        MyThread mt1 = new MyThread("初级用户",5);
        MyThread mt2 = new MyThread("高级用户",10);
        mt1.start();
        mt2.start();
    }
}
```
结果
![结果](https://img-blog.csdnimg.cn/20200713165722368.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
## Jedis简易工具类开发
**基于连接池获取连接**
JedisPool：Jedis提供的连接池技术 
poolConfig:连接池配置对象 
host:redis服务地址 
port:redis服务端口号

**封装连接参数**
创建一个jedis.properties文件

```
jedis.host=localhost 
jedis.port=6379 
jedis.maxTotal=30 
jedis.maxIdle=10
```
**编写工具类**

```java
public class JedisUtils {
    private static JedisPool jp = null;
    private static String host = null;
    private static int port;
    private static int maxTotal;
    private static int maxIdle;

    static {
        ResourceBundle rb = ResourceBundle.getBundle("redis");
        host = rb.getString("redis.host");
        port = Integer.parseInt(rb.getString("redis.port"));
        maxTotal = Integer.parseInt(rb.getString("redis.maxTotal"));
        maxIdle = Integer.parseInt(rb.getString("redis.maxIdle"));
        JedisPoolConfig jpc = new JedisPoolConfig();
        jpc.setMaxTotal(maxTotal);
        jpc.setMaxIdle(maxIdle);
        jp = new JedisPool(jpc,host,port);
    }

    public static Jedis getJedis(){
        return jp.getResource();
    }
    public static void main(String[] args){
        JedisUtils.getJedis();
    }
}
```