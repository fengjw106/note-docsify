# key通用指令
**key 特征**
key是一个字符串，通过key获取redis中保存的数据

**key应该设计哪些操作？**

 - 对于key自身状态的相关操作，例如：删除，判定存在，获取类型等
 - 对于key有效性控制相关操作，例如：有效期设定，判定是否有效，有效状态的切换等
 - 对于key快速查询操作，例如：按指定策略查询key

## key 基本操作
**删除指定key**

```
del key
```
**获取key是否存在**

```
exists key
```
**获取key的类型**

```
type key
```
### key 扩展操作（时效性控制）
**为指定key设置有效期**

```
expire key seconds
pexpire key milliseconds
expireat key timestamp
pexpireat key milliseconds-timestamp
```
**获取key的有效时间**
当没有该key或者时效性已经过了返回-2，有该key但是不具有时效性返回-1
```
ttl key 
pttl key
```
**切换key从时效性转换为永久性**

```
persist key
```
### key 扩展操作（查询模式）
**查询key**

```
keys pattern
```
**查询模式规则**
![key查询规则](https://img-blog.csdnimg.cn/20200713152337332.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
# 数据库通用指令
**key 的重复问题**

 - key是由程序员定义的
 - redis在使用过程中，伴随着操作数据量的增加，会出现大量的数据以及对应的key
 - 数据不区分种类、类别混杂在一起，极易出现重复或冲突

**解决方案**

 - redis为每个服务提供有16个数据库，编号从0到15
 - 每个数据库之间的数据相互独立

![key的重复](https://img-blog.csdnimg.cn/2020071315254147.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjMxNzI2OA==,size_16,color_FFFFFF,t_70)
## db 基本操作
**切换数据库**
我们默认操作的是数据库0
```
select index
```
**其他操作**

```
quit
ping
echo message
```
## db 相关操作
**数据移动**
原数据库没有或者目的数据库已有都会移动失败
```
move key db
```
数据清除

```
dbsize   //查看数据总量
flushdb
flushall
```