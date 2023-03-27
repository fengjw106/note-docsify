# Python概念

## Python介绍

Python由荷兰数学和计算机科学研究学会的吉多·范罗苏姆于1990年代初设计，作为一门叫做ABC语言的替代品。Python提供了高效的高级数据结构，还能简单有效地面向对象编程。Python语法和动态类型，以及解释型语言的本质，使它成为多数平台上写脚本和快速开发应用的编程语言，随着版本的不断更新和语言新功能的添加，逐渐被用于独立的、大型项目的开发。

Python解释器易于扩展，可以使用C语言或C++（或者其他可以通过C调用的语言）扩展新的功能和数据类型。Python也可用于可定制化软件中的扩展程序语言。Python丰富的标准库，提供了适用于各个主要系统平台的源码或机器码。

**优点**

1. 简单：Python是一种代表简单主义思想的语言。阅读一个良好的Python程序就感觉像是在读英语一样。它使你能够专注于解决问题而不是去搞明白语言本身。
2. 易学：Python极其容易上手，因为Python有极其简单的说明文档。
3. 易读、易维护：风格清晰划一、强制缩进
4. 速度较快：Python的底层是用C语言写的，很多标准库和第三方库也都是用C写的，运行速度非常快。
5. 免费、开源：Python是FLOSS（自由/开放源码软件）之一。使用者可以自由地发布这个软件的拷贝、阅读它的源代码、对它做改动、把它的一部分用于新的自由软件中。FLOSS是基于一个团体分享知识的概念。
6. 高层语言：用Python语言编写程序的时候无需考虑诸如如何管理你的程序使用的内存一类的底层细节。
7. 可移植性：由于它的开源本质，Python已经被移植在许多平台上（经过改动使它能够工作在不同平台上）。这些平台包括Linux、Windows、FreeBSD、Macintosh、Solaris、OS/2、Amiga、AROS、AS/400、BeOS、OS/390、z/OS、Palm OS、QNX、VMS、Psion、Acom RISC OS、VxWorks、PlayStation、Sharp Zaurus、Windows CE、PocketPC、Symbian以及Google基于linux开发的android平台。
8. 解释性：一个用编译性语言比如C或C++写的程序可以从源文件（即C或C++语言）转换到一个你的计算机使用的语言（二进制代码，即0和1）。这个过程通过编译器和不同的标记、选项完成。运行程序的时候，连接/转载器软件把你的程序从硬盘复制到内存中并且运行。而Python语言写的程序不需要编译成二进制代码。你可以直接从源代码运行程序。在计算机内部，Python解释器把源代码转换成称为字节码的中间形式，然后再把它翻译成计算机使用的机器语言并运行。这使得使用Python更加简单。也使得Python程序更加易于移植。
9. 面向对象：Python既支持面向过程的编程也支持面向对象的编程。在“面向过程”的语言中，程序是由过程或仅仅是可重用代码的函数构建起来的。在“面向对象”的语言中，程序是由数据和功能组合而成的对象构建起来的。Python是完全面向对象的语言。函数、模块、数字、字符串都是对象。并且完全支持继承、重载、派生、多继承，有益于增强源代码的复用性。Python支持重载运算符和动态类型。相对于Lisp这种传统的函数式编程语言，Python对函数式设计只提供了有限的支持。有两个标准库（functools，itertools）提供了Haskell和Standard ML中久经考验的函数式程序设计工具。
10. 可扩展性、可扩充性：如果需要一段关键代码运行得更快或者希望某些算法不公开，可以部分程序用C或C++编写，然后在Python程序中使用它们。
11. Python本身被设计为可扩充的。并非所有的特性和功能都集成到语言核心。Python提供了丰富的API和工具，以便程序员能够轻松地使用C语言、C++、Cython来编写扩充模块。Python编译器本身也可以被集成到其它需要脚本语言的程序内。因此，很多人还把Python作为一种“胶水语言”（glue language）使用。使用Python将其他语言编写的程序进行集成和封装。在Google内部的很多项目，例如Google Engine使用C++编写性能要求极高的部分，然后用Python或Java/Go调用相应的模块。《Python技术手册》的作者马特利（Alex Martelli）说：“这很难讲，不过，2004年，Python已在Google内部使用，Google 召募许多 Python 高手，但在这之前就已决定使用Python，他们的目的是 Python where we can，C++ where we must，在操控硬件的场合使用C++，在快速开发时候使用Python。”
12. 可嵌入性：可以把Python嵌入C/C++程序，从而向程序用户提供脚本功能。
13. 丰富的库：Python标准库确实很庞大。它可以帮助处理各种工作，包括正则表达式、文档生成、单元测试、线程、数据库、网页浏览器、CGI、FTP、电子邮件、XML、XML-RPC、HTML、WAV文件、密码系统、GUI（图形用户界面）、Tk和其他与系统有关的操作。这被称作Python的“功能齐全”理念。除了标准库以外，还有许多其他高质量的库，如wxPython、Twisted和Python图像库等等。
14. 规范的代码：Python采用强制缩进的方式使得代码具有较好可读性。而Python语言写的程序不需要编译成二进制代码。Python的作者设计限制性很强的语法，使得不好的编程习惯（例如if语句的下一行不向右缩进）都不能通过编译。其中很重要的一项就是Python的缩进规则。一个和其他大多数语言（如C）的区别就是，一个模块的界限，完全是由每行的首字符在这一行的位置来决定（而C语言是用一对大括号“{}”（不含引号）来明确的定出模块的边界，与字符的位置毫无关系）。通过强制程序员们缩进（包括if，for和函数定义等所有需要使用模块的地方），Python确实使得程序更加清晰和美观。
15. 高级动态编程：虽然Python可能被粗略地分类为“脚本语言”（script language），但实际上一些大规模软件开发计划例如Zope、Mnet及BitTorrent，Google也广泛地使用它。Python的支持者较喜欢称它为一种高级动态编程语言，原因是“脚本语言”泛指仅作简单程序设计任务的语言，如shellscript、VBScript等只能处理简单任务的编程语言，并不能与Python相提并论。

## 基本语法

### 关键字

执行代码

~~~py
# python关键字
import keyword
print(keyword.kwlist)
~~~

结果

~~~shell
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
~~~

### 缩进

python的缩进规则：对于类定义、函数定义、流程控制语句、异常处理语句等，行尾的冒号和下一行的缩进，表示下一个代码块的开始，而缩进的结束则表示此代码块的结束。通常情况下都是采用4个空格长度作为一个缩进量（一个Tab键就表示4个空格）。

但是Python并不会对缩进不是4个空格的语句进行直接报错，而且同一个级别代码块的缩进量必须一样，否则解释器会报 SyntaxError 异常错误

### 多行语句

~~~py
# 单行语句
a = 1
b = 2
c = 3
d = a + b + c
# 多行语句
d = a + \
    b + \
    c
# 对于集合
a = [1,2,
3,4]
b = (1,2,
3,4)
~~~

### 引号

~~~py
a = 'hello你好'
a = "hello你好"
# 对于字符串换行时会将原字符串分为两个字符串
c = "hello"\
    "你好"
d = "hello\n你好"
# 对于多行需要使用 \n 换行，使用三个引号（单双引都行）就能解决
e = """
hello
你好
hello
你好
"""
~~~

### 注释

~~~py
# 单行注释
'''
多行注释
'''
"""
多行注释
"""
~~~

### 输入和输出

~~~py
a = input("请输入您的密码：")
print(a)
"""
结果:
请输入您的密码：123456
123456
"""
~~~

### 转义符

**转义字符的定义：**由反斜杠加上一个字符或数字组成，它把反斜杠后面的字符或数字转换成特定的意义。

~~~py
# 引号的转义
print("hello,\"您好\"")
~~~

1. 换行 `\n`

   ```py
   print("hello\n你好")
   ```

2. 制表符 `\t`

   ~~~py
   # \t tab制表符
   print("hello\tooo")
   # 输出 hello   ooo 三个空格
   print("hell\toooo")
   # 输出 hell    oooo 四个空格
   # \t 每四个一划分，作用是补齐，不是直接添加
   ~~~

3. 覆盖 `\r`

   ~~~py
   print("hello\rpython")
   # 输出 python
   ~~~

4. 删除 `\b`

   ~~~py
   print("hello\bpython")
   # 输出 hellpython
   # 类似于键盘的 backspace
   ~~~

5. 两个反斜杠 `\\`

   ~~~py
   print("\\")
   ~~~

6. 原字符 `R`或者 `r`

   ~~~py
   print('hello\nworld')
   print(r'hello\nworld')
   """
   输出
   hello
   world
   hello\nworld
   """
   ~~~

## 变量

变量命名规则： 变量只能是字母，数字和下划线的组合；数字不能作为开头；变量名区分大小写；特殊关键字不能作为变量；大写作为常量

## 数据类型

### Number（数字）

**在Python3中的规则**

整型（int）- 通常被称为整数或者整型，是正数和负数，不带小数点

浮点型（float）- 由整数和小数组成

布尔型（bool）- True/False （T和F必须大写）

复数（complex）- 由实数和虚数组成，可以用 a + bj 或者 complex(a,b) 标识，复数的实数和虚数都是浮点型

数值运算

`+ - * / %`

`4 // 3` 表示向下取整

`2 ** 3` 表示幂运算

比较运算符

`< > <= >= != ==`

逻辑运算符

`and 与 or 或 not 非`

Python的空值

`None` 什么都没有

内置函数的返回值 - 函数运行之后是有返回值的

~~~py
r = print("aaa") # aaa
print(r) # None
~~~

### String（字符串）

字符串下标从0开始，从后开始从-1开始。

**切片**

~~~py
# [开始:结尾] 取左不取右
name = 'helloworldhellopython'
print(name[0:5]) # hello
print(name[5:10]) #world
# [:] 默认取全部
# 负数
print(name[-1:-6]) # （空）
# 应该是小数在前，大数在后
print(name[-6:-1]) # pytho
# 但是没有获取到最后一个字符
print(name[-6:]) # python
# 但是写0是不允许的
print(name[-6:0]) # （空）

# [开始:结尾:步长]
print(name[0:10:4]) # hol
print(name[::-1]) # 字符串反转 nohtypollehdlrowolleh
~~~

**字符串拼接** `+`

~~~python
# join
a = 'hello'
b = 'world'
c = 'python'
d = ','.join((a,b,a,c))
print(d)
# hello,world,hello,python
~~~

**字符串的格式化** `format()`

~~~python
# {}相当于占位，跟下标有关
s1 = "我的名字叫{}，今年{}，性别{}".format("张三","18","男")
s2 = "我的名字叫{1}，今年{0}，性别{2}".format("张三","18","男")
print(s1)
print(s2)
# 我的名字叫张三，今年18，性别男
# 我的名字叫18，今年张三，性别男
# 格式化小数长度和百分号
a = 3.53432
print(('橘子{:.2f}一斤').format(a)) # 橘子3.53一斤
print(('占比{:.2%}').format(a)) # 占比353.43%
b = 6.65342
print(('橘子{:.2f}一斤').format(a,b)) # 橘子3.53一斤
print(('橘子{1:.2f}一斤').format(a,b)) # 橘子6.65一斤
~~~

**字符串的方法**

~~~python
# find(查找的字符，范围开始，范围结束) 查找第一个字符的下标，找不到返回-1
# count(查找的字符，范围开始，范围结束) 查找字符串中字符的数量，找不到返回0
# replace(要替换的字符串，替换的字符串，替换的次数) 替换从前往后，默认是替换全部
# upper() 将小写转换成大写
# lower() 将大写准换成小写
# split(分割点,分割次数)
# strip() 去除字符串首尾的空格，不包含中间的空格，也可以去除字符
a = '  pyt  hon  '
print(a.strip()) # pyt  hon
b = '666python66666'
print(b.strip('6')) # python
# len() 字符串的长度
~~~

**传统的格式化输出**

~~~python
# 传统的格式化输出 %
# %s 为字符串占位，任意类型都可以
# %d 为数值格式占位
# %f 为浮点数占位
a = '我的名字是：%s'%("张三")
print(a) # 我的名字是：张三

# f表达式 （F，f都一样）
s1 = "我的名字叫{}，今年{}，性别{}".format("张三","18","男")
print(s1) # 我的名字叫张三，今年18，性别男
a = '张三'
b = '18'
c= '男'
s2 = f"我的名字叫{a}，今年{b}，性别{c}"
print(s2) # 我的名字叫张三，今年18，性别男
~~~

### List（列表）

列表是一个**有序且可更改**的集合。在 Python 中，列表用方括号编写。

~~~python
# 列表的长度
list  = [1,2,3]
print(len(list)) # 3
list[1] = 99
print(list) # [1, 99, 3]
# 列表的加法和乘法
list1 = [3,7,90]
list2 = ["a","m","f"]
print(list1 + list2) # [3, 7, 90, 'a', 'm', 'f']
print(list1 * 3) # [3, 7, 90, 3, 7, 90, 3, 7, 90]
# 列表的切片取值（字符串一致）
list = [10,20,30,40,50,60,70]
print(list[1:5]) # [20, 30, 40, 50]
print(list[1:5:2]) # [20, 40]
print(list[-6::2]) # [20, 40, 60]
print(list[::-1]) # [70, 60, 50, 40, 30, 20, 10]
print(list[1:5:-2]) # []
print(list[-6::-2]) # [20]
print(list[:-6:-2]) # [70, 50, 30]
# 对于步长step参数，其规律为：step 为正表示从左到右切片，step 为负表示从右到左切片，切时都是在元素前面切一刀，即从左到右时在元素左侧切，从右到左时在元素右边切。由此不难得出，对于切片[参数1：参数2：step]来说，如果想得到有意义的值，在step>0时，参数1一定小于参数2（左边的下标一定小于右边）；而在step<0时，参数1一定大于参数2（右边的下标一定大于左边），否则就会得到空列表。

# 列表的操作方法
# del关键字
list = [1,2,3,4,5]
# del list
# print(list) # <class 'list'>
del list[2]
print(list) # [1, 2, 4, 5]

# append方法 向list表末尾添加
list.append(6)
print(list) # [1, 2, 4, 5, 6]

# insert 第一个参数是插入的位置，第二个参数是插入的值
list.insert(2,3)
print(list) # [1, 2, 3, 4, 5, 6]

# clear
list.clear()
print(list) # []

list = ["hello","python","hello","world"]
# remove 从列表中移除函数，如果有重复只会移除遇到的第一个
list.remove("hello")
print(list) # ['python', 'hello', 'world']

# pop 移除列表中指定位置的元素，并返回要移除的元素，默认情况下，移除列表中最后的一个元素
print(list.pop()) # world
print(list.pop(0)) # python

list = ["hello","python","hello","world"]
# index 返回所匹配元素的索引 第一个参数为查找的对象，第二个参数为查找的起始范围，第三参数为查找的结束范围
print(list.index("hello")) # 0
print(list.index("hello",1,3)) # 2 在整个列表中索引为2

# reverse
list.reverse()
print(list) # ['world', 'hello', 'python', 'hello']

# extend 用于在列表的末尾添加另一个列表，与append函数相比，extend函数可以一次性添加多个元素，注意（使用extend函数和列表加法结果一样，但extend是会将另一个列表并入当前列表，而列表加法返回新的列表，为节约内存空间，推荐使用extend）
list1 = [1,2,3]
list2 = ["a","b","c"]
# list1.extend(list2)
# print(list1) # [1, 2, 3, 'a', 'b', 'c']
list1.append(list2)
print(list1) # [1, 2, 3, ['a', 'b', 'c']]

# copy 深拷贝
list = ["hello","python","hello","world"]
list2 = list.copy()
del list[0]
print(list) # ['python', 'hello', 'world']
print(list2) # ['hello', 'python', 'hello', 'world']

# list = ["hello","python","hello","world"]
# list2 = list
# del list[0]
# print(list) # ['python', 'hello', 'world']
# print(list2) # ['python', 'hello', 'world']

# sort 排序，根据ASCII码值
list = ["1","a","A","world"]
list.sort()
print(list) # ['1', 'A', 'a', 'world']

# count 统计某个元素的个数
list = ["hello","python","hello","world"]
print(list.count("hello")) # 2
a = "sdadaddddddd"
print(a.count("d")) # 9
~~~

### Tuple（元组）

元组是**有序且不可更改**的集合。在 Python 中，元组是用圆括号编写的。

~~~python
# 修改元组
a = (1,2,3,4)
a[1] = 99
print(a)
"""
Traceback (most recent call last):
  File "F:\vscodeProjects\python\python01.py", line 182, in <module>
    a[1] = 99
TypeError: 'tuple' object does not support item assignment
"""
# 元组的元素不能修改，但是元组里的列表中元素可以修改
a = ([1,2],[3,4,5],[6])
a[1][2] = 99
print(a) # ([1, 2], [3, 4, 99], [6])

# 元组的合并
a = (1,2,3,4)
b = ("a","b","c")
print(a + b) # (1, 2, 3, 4, 'a', 'b', 'c')

# 定义元组的时候可以不加括号，但对于单个元素不要在元素后加上逗号
a = 1,2,3,4
print(a) # (1, 2, 3, 4)
b = (10)
print(b) # 10
c = (10,)
print(c) # (10,)
d = 10,
print(d) # (10,)
~~~

### Sets（集合）

集合是无序和无索引的集合。在 Python 中，集合用花括号编写。无法通过引用索引来访问 set 中的项目，因为 set 是无序的，没有索引。

~~~python
# 创建集合 
# 1. 变量名 = set(元素) 字符串/列表/元组/字典
# 2. 变量名 = {} 字符串/元组/数字
a = set("123444")
print(a) # {'2', '1', '3', '4'} 还会自动去重
b = set([1,2,3,4,5])
print(b) # {1, 2, 3, 4, 5}
c = set(("a","b","c"))
print(c) # {'b', 'c', 'a'}
d = set({
    '年龄': 18,
    '名字':'张三'
})
print(d) # {'年龄', '名字'}
e = {"a","b","c","d"}
print(e) # {'c', 'b', 'd', 'a'}
f = {[1,2,3,4]}
print(f)
"""
f = {[1,2,3,4]}
TypeError: unhashable type: 'list'
"""

# 空集合
a = set()
print(a) # set()

# add 集合的添加
a = {1,2,3,4}
a.add(6)
print(a)

# update 将集合合并
b = {"a","b","c"}
a.update(b)
print(a) # {1, 2, 3, 4, 'c', 6, 'a', 'b'}

# 集合的删除
# remove 如果有就删除，没有就报错
a = {1,2,3,4,5,6}
a.remove(5)
print(a) # {1, 2, 3, 4, 6}
# a.remove(99)
# print(a)
"""
a.remove(99)
KeyError: 99
"""
# pop 集合随便删除，没有元素就报错
a = {1,2,3,4,5,6}
a.pop()
print(a) # {2, 3, 4, 5, 6}
# discard 如果有就删除，没有不做任何操作
a = {1,2,3,4,5,6}
a.discard(5)
print(a) # {1, 2, 3, 4, 6}
a.discard(99)
print(a) # {1, 2, 3, 4, 6}

# 集合的交集和并集
a = {1,2,3}
b = {3,2,6}
c = a & b
print(c) # {2, 3}
d = a | b
print(d) # {1, 2, 3, 6}
~~~

### Dictionary（字典）

字典是一个无序、可变和有索引的集合。在 Python 中，字典用花括号编写，拥有键和值。字典的键是不可变，不可重复的。字典的键使用是不可变数据类型（字符串，元组，数组）

~~~python
a = {
    "姓名": "张三",
    1: 18,
    (1,2,3): "123"
}
print(a) # {'姓名': '张三', 1: 18, (1, 2, 3): '123'}
# dict创建
b = dict((["姓名","张三"],["年龄",18]))
print(b) # {'姓名': '张三', '年龄': 18}
# 空字典
c = {}

# 增删改查
a = {'姓名': '张三', '年龄': 18}
a["成绩"] = 99
print(a) # {'姓名': '张三', '年龄': 18, '成绩': 99}
del a["成绩"]
print(a) # {'姓名': '张三', '年龄': 18}
a["姓名"] = "小明"
print(a) # {'姓名': '小明', '年龄': 18}
# get 如果字典里没有该键的话，会返回None，但是可以赋默认值，返还的就是默认值，但是不影响原字典
print(a.get("姓名")) # 小明
#keys 对于嵌套字典数据，只会返回最外层的主键
print(a.keys()) # dict_keys(['姓名', '年龄'])
# items 以列表的形式返回字典中的所有键值对
print(a.items()) # dict_items([('姓名', '小明'), ('年龄', 18)])
# values 以列表的形式返回字典中的所有值
print(a.values()) # dict_values(['小明', 18])
# clear
# copy
# fromkeys 用于创建一个新的字典，第一个参数是一个序列（列表/元组/集合），用于作为字典的键。第二个参数可以是任何数据类型，作为每个键的值
b = {}
b1 = b.fromkeys(('姓名', '年龄'))
print(b1) # {'姓名': None, '年龄': None}
b2 = b.fromkeys(('姓名', '年龄'),6)
print(b2) # {'姓名': 6, '年龄': 6}
b3 = b.fromkeys(('姓名', '年龄'),(1,2))
print(b3) # {'姓名': (1, 2), '年龄': (1, 2)}

# pop 用于从字典中移除指定键，并返回键所对的值
a = {'姓名': '张三', '年龄': 18}
print(a.pop('姓名')) # 张三
print(a) # {'年龄': 18}

# popitem 用于从字典中删除最后一项，并以元组的形式返回该项对应的键和值
a = {'姓名': '张三', '年龄': 18}
print(a.popitem()) # ('年龄', 18)

# setdefault 用于设置键的默认值。若在字典中该键已经存在，则忽略设置，若不存在，则添加键和值
a = {'姓名': '张三', '年龄': 18}
print(a.setdefault("技能","python")) # python
print(a) # {'姓名': '张三', '年龄': 18, '技能': 'python'}

# update 用于将字典2的值更新到字典1，若字典2的键在字典1中已经存在，则修改字典1，若不存在，对字典1添加
a = {'姓名': '张三', '年龄': 18}
b = {'姓名':'小明'}
c = {'技能':'Python'}
a.update(b)
a.update(c)
print(a) # {'姓名': '小明', '年龄': 18, '技能': 'Python'}
~~~

## 语法

### in 和 not in

使用`in`和`not in`运算符来判断某个对象是否为序列的成员。

`in` 判断对象是否在序列（列表、字符串、元组、字典）中，如果是则返回 True。

`not in` 判断对象是否不在序列中，如果是则返回 True。

~~~python
print('2' in '1234') # True
~~~

### `is` 和 `is not`

判断两个对象是否相等。

数字、字符串、元组都是不可变数据类型，表面一样，就是完全一样。

列表、字典、集合都是可变数据类型，表面一样，其实不一样，不是同一个。

### 条件语句

`if...elif...else...` 分支语句，注意缩进，每个分支必须有缩进

例子：

~~~python
password_list = ['*#*#','12345'] 
def account_login(): 
    password = input('Password:') 
    password_correct = password == password_list[-1] 
    password_reset = password == password_list[0] 
    if password_correct: 
            print('Login success!') 
    elif password_reset: 
        new_password = input('Enter a new password:') 
        password_list.append(new_password) 
        print('Your password has changed successfully!') 
        account_login() 
    else: 
        print('Wrong password or invalid input!') 
        account_login() 
account_login()
~~~

第一行：创建一个列表，用于存储用户的密码，初始密码和其他数据（对实际数据库的简化模拟）；

第二行：定义函数；

第三行：使用input获取用户输入的字符串并存储在变量password中；

第四行：当用户输入的密码等于密码列表最后一个元素的时候（即用户最新设定的密码），登录成功；

第五~九行：当用户输入的密码等于密码列表的第一个元素的时候（即重置密码的“口令”）触发密码修改，并将变更后的密码储存至列表的最后一个，成为最新的用户密码；

第十行：反正，一切不等于预设密码的输入结果，全部会执行打印错误提示，并且再次调用函数，让用户再次输入密码；

第十一行：调用函数。

在上面的代码中其实可以清晰的看见代码（code Block）。代码块的产生是由于缩进，也是说，具有相同缩进量的代码实际上是共同完成相同层面的事情，这有点像是编辑文档时不同层级的任务列表。

### 循环

for循环作为编程语言中最强力的特性之一，能够帮助我们做很多重复的事情，比如批量命名，批量操作等等。把for循环所做的事情概括成一句话就是：于...其中的每一个元素，做...事情。

for循环

~~~Python
for i in range(1,10):
	for j in range(1,10):
	print('{} X {} = {}'.format(i,j,i*j))
~~~

while循环

和for相同点在于能循环的做一件事重复的事情，不同点在于for循环会在可迭代的序列被穷尽的时候停止，while则是在条件不成立的时候停止，当然如果条件恒成立，程序就会一直执行，就会进入死循环。这种情况，可以在循环中设置可以使循环结束的条件，然后使用break跳出循环。因此while的作用概括一句话是：只要...条件成立，就一直做...。

~~~Python
password_list = ['*#*#','12345']
def account_login():
    tries = 3
    while tries > 0: 
        password = input('Password:')
        password_correct = password == password_list[-1]
        password_reset = password == password_list[0]
        if password_correct:
            print('Login success!')
        elif password_reset:
            new_password = input('Enter a new password :')
            password_list.append(new_password)
            print('Password has changed successfully!')
            account_login()
        else:
            print('Wrong password or invalid input!')
            tries = tries - 1 
            print( tries, 'times left')
    else:
        print('Your account has been suspended') 
account_login()
~~~

这段代码只有三处与前面的不一样：

第四~五行：增加了while循环，如果tries>0这个条件成立，那么便可输入密码，从而执行辨别密码是否正确的逻辑判断。

第二十~二十一行：当密码输入错误时可尝试的次数tries减少1；

第二十三~二十四行：while循环的条件不成立时，就意味着尝试的次数用光，通告用户账户被锁。

在这里while可以理解为if循环版，可以使用while-else结构，而在while代码块中又存在着第二层的逻辑判断，这其实构成了嵌套逻辑。

### 数据结构的一些技巧

**多重循环**

对于列表，如果需要排序可以使用 sorted() 函数，它不会改变原列表，会先复制原列表，然后再整理排序，使用参数 reverse=Ture 可以逆序，但是如果是两个列表需要处理，可以使用zip

~~~python
num = [1,2,3,4]
str = [6,7,8,9]
for a,b in zip(num,str):
    print(a,b)
"""
1 6
2 7
3 8
4 9
"""
~~~

**推导式**

将十个元素装入列表中，是这样写的：

~~~python
a = []
for i in range(1,11):
	a.append(i)
~~~

可以换成列表解析的方式。

~~~python
b = [i for i in range(1,11)]
~~~

列表解析式不仅非常方便，而且在执行的效率上远远胜于前者。

公式：

`list = [item for item in iterable]`

~~~python
a = [i**2 for i in range(1,10)]
c = [j+1 for j in range(1,10)]
k = [n for n in range(1,10) if n % 2 ==0]
z = [letter.lower() for letter in 'ABCDEFGHIGKLMN']
~~~

字典推导式的方式略有不同，主要是因为创建字典必须满足键-值的两个条件

~~~python
d = {i:i+1 for i in range(4)}
g = {i:j for i,j in zip(range(1,6),'abcde')}
g = {i:j.upper() for i,j in zip(range(1,6),'abcde')}
~~~

**循环列表的时候获取列表索引**

可以使用 enumerate 函数

~~~python
letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
for num,letter in enumerate(letters):
print(letter,'is',num + 1)
~~~

## 函数

例如 print() , len() , input() , int()

以3.50版本为例，一共存在68个这样的函数，它们被统称为内建函数。之所以被称为内建函数，并不是因为还有“外建函数”这个概念，内建的意思是这些函数在3.50版本安装之后就能使用，是“自带”的而已。

Python官网中各个函数介绍的链接 https://docs.python.org/3/library/functions.html

- def（即define，定义）的含义是创建函数，也就是定义一个函数。
- arg（即argument，参数）有时还会见到这种写法：parameter
- return 即返回结果

~~~Python
# 摄氏度转换
def fahrenheit_converter(C):
	fahrenheit = C * 9/5 + 32
	return str(fahrenheit) + '˚F'
~~~

注意函数的返回值，有的函数没有返回值，如果将函数调用放入print()中时，打印的结果是None。

**传递参数和参数类型**

传递参数有两种方式 **位置参数（positional argument）** **关键词参数（keyword argument）**

例如：求梯形面积

~~~Python
def trapezoid_area(base_up, base_down, height):
	return 1/2 * (base_up + base_down) * height
~~~

位置参数方式。不难看出，填入的参数1，2，3分别对应着参数base_up，base_down和heigth。

~~~python
trapezoid_area(1,2,3)
~~~

关键词参数方式。更直观地，在调用函数的时候，我们将每个参数名称后面赋予一个我们想要传入的值，这种以名称作为一一对应的参数传入的方式为关键词参数

~~~python
trapezoid_area(base_up=1,base_down=2,height=3)
~~~

位置参数和关键词参数混用的时候，位置参数要在关键词参数的前面

~~~python
trapezoid_area(height=3, base_down=2, base_up=1) # RIGHT!
trapezoid_area(height=3, base_down=2, 1) # WRONG! Positional argument cannot appear after keyword arguments
trapezoid_area(1, 2, height=3)  # RIGHT!
~~~

~~~python
base_up = 1
base_down = 2
height = 3
trapezoid_area(height, base_down, base_up) # 2.5
~~~

对于这个结果为啥是2.5，而不是4.5 如果你有这样的困惑证明你对于参数的命名和变量的命名出现混淆。对于函数定义中的入参只是形式上的占位符，表达的意思是函数所需要的参数应该是和其有关的变量或者对象，进入函数中进行计算，不要因为命名的原因和关键词参数混淆。

参数默认值

~~~python
trapezoid_area(1, 2)
~~~

如果这样传参的话，会因为少传入一个参数而报错。可以在函数定义的时候给heigth一个默认值。给一个参数默认值的方式很简单，**只需要在定义参数的时候给参数赋值即可**。

~~~python
def trapezoid_area(base_up, base_down, height=3):
	return 1/2 * (base_up + base_down) * height
~~~

如果不想使用默认值，直接赋值即可

~~~python
trapezoid_area(1, 2, height=15)
~~~

**练习：统计文件中不同单词出现的次数（词频统计）**

~~~python
path = '/Users/Hou/Desktop/Walden.txt'
with open(path,'r') as text:
	words = text.read().split()
	print(words)
	for word in words: 
        print('{}-{} times'.format(word,words.count(word)))
~~~

不足点：

1. 有一些带标点符号的单词被单独统计了次数
2. 有些单词不止一次的展示了出现的次数
3. 由于Python对大小写敏感，开头大写的单词被单独统计了

修改之后：

~~~Python
import string
path = '/Users/Hou/Desktop/Walden.txt'
with open(path,'r') as text:
    words = [raw_word.strip(string.punctuation).lower() for raw_word in text.read().split()]
    words_index = set(words)
    counts_dict = {index:words.count(index) for index in words_index}
for word in sorted(counts_dict,key=lambda x: counts_dict[x],reverse=True):
    print('{} -- {} times'.format(word,counts_dict[word]))
~~~

第一行：引入了一个新的模块 String。其实这个模块的用法很简单，可以把 String.punctuation 打印出来，其实这里面也仅仅是包含了所有的标点符号。

第四行：在文字的首位去掉了连在一起的标点符号，并把首字母大写的单词转化为小写。

第五行：将列表用set函数转换成集合，自动去除掉了其中所有重复的元素。

第六行：创建了一个已单词为键（key）出现频率为值（value）的字典。

第七八行：打印整理后的函数，其中 key=lambda x: counts_dict[x] 叫做lambda表达式，可以暂时理解为以字典中的值为排序的参数。

## 类

正如“类”的名称一样，他描述的概念和我们显示生活中的类的概念相似。生物有不同的种类，食物有不同的物种，人类社会的种种商品也有不同的种类。但凡可以被称为一类的物体，他们都有着相似的特征和行为方式。也就是说，类是有一些系列有共同特征和行为事物的抽象概念的总和。

对于可乐来讲，只要是同一个品牌的可乐，他们就有着同样的成分，这被称为配方（formula），就像是工厂进行批量生产时所遵循的统一标准，正是因为有着相同的配方，所以可口可乐才能打到一样的口味，在Python中类可以表达这一件事：

~~~python
class CocaCola:
	formula = ['caffeine','sugar','water','soda']
~~~

我们使用class来定义一个类，就如同创建函数是使用的def定义一个函数一样简单，接着你可以看到缩进的地方有着装载着列表的变量formula，在类里面赋值的变量就是类的变量，而类的变量有一个专业的术语，叫做类的属性。

### 类的实例化

~~~python
coke_for_me = CocaCola()
coke_for_you = CocaCola()

print(CocaCola.formula)
print(coke_for_me.formula)
print(coke_for_you.formula)

#结果
"""
['caffeine', 'sugar', 'water', 'soda']
['caffeine', 'sugar', 'water', 'soda']
['caffeine', 'sugar', 'water', 'soda']
"""

~~~

在左边我们创建一个变量，右边写上类的名称，这样看起来很像赋值的行为，我们称之为类的实例化。而被实例化后的对象，我们称为实例（instance），或者说是类的实例。对应可乐来说，按照配方把可乐生产出来的过程就是实例化的过程。

### 类属性引用

在类的名字后面输入`.`，加上类的属性，这就是类属性的引用（attribute references）。

类的属性会被所有类的实例共享，所以当你在类的实例后面再点上`.`，索引用的属性值是完全一样的。就如上面打印的结果一致。

### 实例属性

对于进口的可口可乐，需要进行本地化的包装，创建的实例属性并不会被别的实例所使用。

~~~python
coke_for_china = CocaCola()
coke_for_china.local_logo = "可口可乐"  # 创建实例属性
print(coke_for_china.local_logo) # 打印实例属性引用结果
# print(coke_for_me.local_logo) # AttributeError: 'CocaCola' object has no attribute 'local_logo'
# print(CocaCola.local_logo) # # AttributeError: 'CocaCola' object has no attribute 'local_logo'
~~~

通过上面的代码，在中国生产的可口可乐贴上了中国字样的“可口可乐”标签，在创建了类之后，通过`object.new_attr`的形式进行一个赋值，于是就得到了一个新的实例的变量，实例的变量叫实例变量，而实例变量有个专业的术语，称之为实例属性（Instance Atrribute）。

可口可乐的配方（formula）属于可口可乐（class），而“可口可乐”的中文标签（local_logo）属于中国区的可乐（instance），给中国区的可口可乐贴上中文标签，并不会影响别的国家或地区销售的可乐标签，从引用方式上来说，引用实例属性和引用类属性完全一样，但是两者却又本质上的差异。

### 实例方法

类的实例可以引用属性，类的实例也可以使用方法。方法就是函数，但是我们把这个函数称之为方法。方法是供实例使用的，因此可以称之为实例方法（instance method）。

~~~python
class CocaCola:
    formula = ['caffeine','sugar','water','soda']
    def drink(self):
        print("Energy!")
        
coke = CocaCola()
coke.drink() # Energy!
~~~

**`self`的作用**

看一个相似的代码：

~~~python
class CocaCola:
    formula = ['caffeine','sugar','water','soda']
    def drink(coke):
        print("Energy!")
        
coke = CocaCola()
coke.drink()
~~~

这个参数其实就是被创建出来的实例本身，再进一步说，一旦一个类被实例化，那么我们其实可以使用和我们使用函数相似的方式：

~~~python
coke = CocaCola
coke.drink() == CocaCola.drink(coke) #两边写法完全一致
~~~

被实例化的对象会被编译器默默的传入后面方法的括号中，作为第一个参数。上面这两种方法是一样的，但是我们更多地会写成前面那种形式，其实`self`这个参数名字输可以随意修改名称的，但是按照Python的规矩，还是统一使用`self`。

更多的参数

~~~Python
class CocaCola:
    formula = ['caffeine','sugar','water','soda']
    def drink(coke,how_much):
        if how_much == "a sip":
            print("cool~~")
        elif how_much == "whole bottle":
            print("Headache!")
        
coke = CocaCola()
coke.drink("a sip") #cool~~
~~~

**魔术方法**

`__init__()`

~~~Python
class CocaCola:
    formula = ['caffeine','sugar','water','soda']
    def __init__(self):
        self.local_logo = "可口可乐"
    def drink(self):
        print("Energy")
coke = CocaCola()
print(coke.local_logo) # 可口可乐
~~~

它的神奇之处就在于，如果你在类里定义了它，在创建实例的时候它就会能帮你自动的处理很多事情，比如新增实例属性。在上面的代码中，我们创建了一个实例属性，但是在定义完类之后再做，这次我们一步到位。其实`__init__()`是initialize（初始化）的缩写，这也就意味着即使我们在创建实例的时候不去引用init（）方法，其中的命令也会先被自动执行。

`__init__()`给了类的使用提供极大的灵活性。

~~~Python
class CocaCola:
    formula = ['caffeine','sugar','water','soda']
    def __init__(self):
        for element in self.formula:
            print('Coke has {}!'.format(element))
    def drink(self):
        print("Energy")
coke = CocaCola()
"""
Coke has caffeine!
Coke has sugar!
Coke has water!
Coke has soda!
"""
~~~

除了必写的self参数以外，init方法同样可以有自己的参数，同时也不需要这样`obj.__init__()`的方式来调用（因为会自动执行）而是在实例化的时候往类的括号中放进参数，相应的随意参数都会传递到这个特殊的`__init__()`方法中，和函数的参数的用法完全相同。

~~~python
class CocaCola:
    formula = ['caffeine','sugar','water','soda']
    def __init__(self,logo_name):
        self.local_logo = logo_name
    def drink(self):
        print("Energy")
coke = CocaCola("可口可乐")
print(coke.local_logo) # 可口可乐
~~~

如果你对上面代码中的`self.local_logo = logo_name`感到不理解，在这里可以解释一下，左边是变量作为类的属性，右边是传入的这个参数作为变量，也就是说这个变量的赋值所存储的结果将取决于初始化的时候所传进来的参数`logo_name`，传进来什么那么它就将是什么。

### 类的继承

随着时代的变迁，消费品种类也在不断增多，比如可乐的种类，使用可口可乐的配料重新创建一个类。

~~~python
class CocaCola:
    calories = 140
    sodium = 45
    total_carb = 39
    caffeine = 34
    ingredients = ['High Fructose Corn Syrup','Carbonated Water','Phosphoric Acid','Natural Flavors','Caramel Color','Caffeine']
    def __init__(self,logo_name):
        self.local_logo = logo_name
    def drink(self):
        print('You got {} cal energy!'.format(self.calories))

~~~

所以的子牌子都会继承可口可乐的牌子，Python中类也有对应的概念，称为类的继承（Inheritance），拿无咖可乐举例：

~~~python
class CaffeineFree(CocaCola):
    caffeine = 0
    ingredients = ['High Fructose Corn Syrup','Carbonated Water','Phosphoric Acid','Natural Flavors','Caramel Color']

cake_a = CaffeineFree("Caffeine-Free")
cake_a.drink()
~~~

在新的类CaffeineFree后面的括号中放入CocaCola，这就表示这个类是继承于CocaCola这个父类的，而CaffeineFree则成为了CocaCola子类。类中的变量和方法可以完全被子类继承，但如需有特殊的改动也可以进行覆盖（Override）。可以看到CaffeineFree存在着咖啡因含量，成分这两处不同的地方，并且在新的类中也仅仅是重写了这两个地方，并且这新的类中也仅仅是重写了这两个地方其他的没有重写的地方，方法和属性都能照常使用。

### 类属性和实例属性的困惑

> 类属性的修改会不会影响类属性的引用

~~~python
class TestA:
    attr = 1
obj_a = TestA()
TestA.attr = 42
print(obj_a.attr) # 42
~~~

>实例属性的修改会不会影响类属性的引用

~~~Python
class TestA:
    attr = 1
obj_a = TestA()
obj_b = TestA()
obj_a.attr = 42
print(obj_b.attr) # 1
print(TestA.attr) # 1
~~~

> 类属性和实例属性名一样，那么`.`后面的引用将是什么

~~~Python
class TestA:
    attr = 1
    def __init__(self):
        self.attr = 42
obj_a = TestA()
print(obj_a.attr) # 42
~~~

注意：

对于`obj_a.attr = 42`和`TestA.attr = 42`的区别，他们`.`前面不同代表的意思完全不同，修改的也完全不是一个东西，类属性只能通过类去修改，通过实例无法修改类的属性，在使用`object.new_attr`时，虽然new_attr和类属性名恰好相同，但是这条语句的意思一直都是添加名为new_attr的实例属性，而不是修改名为new_attr的类属性，对其重新赋值，不要混淆。即**可以通过类直接访问类的属性，也可以通过对象实例访问类的属性，但是不能通过对象实例修改的属性**。

在Python里也是一切皆对象，每一个对象都会有一个`__dict__`属性，它是一个字典，对象的属性都会存储在这里。即使你不去定义它，它也存在每一个类中，是默认隐藏的。类TestA和类的实例obj_a各自都有独立的dict，所以必然没法互相修改，通过打印就可以看到。

~~~Python
class TestA:
    attr = 1
    def __init__(self):
        self.attr = 42
obj_a = TestA()
print(obj_a.attr)
print(TestA.__dict__) #{'__module__': '__main__', 'attr': 1, '__init__': <function TestA.__init__ at 0x0000028B8A34E830>, '__dict__': <attribute '__dict__' of 'TestA' objects>, '__weakref__': <attribute '__weakref__' of 'TestA' objects>, '__doc__': None}
print(obj_a.__dict__) #{'attr': 42}
~~~

首先可以发现，dict不仅有属性，还有方法，**实例属性属于实例，类属性属于类，方法属于类**

至于为什么是42不是1，是和Python的引用机制有关，是自外而内的，当创建一个实例后，准备开始引用属性，这时候编译器会先搜索该实例是否有该属性，如果有则引用；如果没有，将搜索这个实例所属的类是否有这个属性，如果有，则引用，没有那就只能报错了。

### 类的实践

其实类背后所承载的理念是OOP的编程理念。在大型项目中为了易于管理和和维护代码质量，会采取面向对象的方式，这也是软件工程的智慧所在。接下来，我们将使用类的概念来编写一个日常的工具库导入到Python的库中，这样一来我们也可以使用import方式导入自己的库了。

在使用Python处理数据或者开发网站时，有时候会使用一些无意义的假数据，比如用户详情信息，我们来制作这样一个填充假数据的小工具。思路如下：

>父类：FakeUser
>
>功能：
>
>1. 随机姓名
>   1. 单字名
>   2. 双子名
>   3. 无所谓
>2. 随机性别
>
>子类：SnsUser
>
>功能：
>
>1. 随机数量的追随者
>   1. few
>   2. a lot

**先处理一下词库**

~~~Python
xing_path = "C://Users/Administrator/Desktop/xing.txt"
ming_paht = "C://Users/Administrator/Desktop/ming.txt"
xing_list = []
single_ming_list = []
double_ming_list = []
with open(xing_path,"r",encoding="UTF-8") as f:
    for line in f.readlines():
        xing_list.append(line.split("\n")[0])
with open(ming_paht,"r",encoding="UTF-8") as f:
    for line in f.readlines():
        ming = line.split("\n")[0]
        if len(ming) == 1:
            single_ming_list.append(ming)
        else:
            double_ming_list.append(ming)
print(xing_list)
print(single_ming_list)
print(double_ming_list)
~~~

将list转为元组，元组比列表更省内存，将打印出来的结果复制粘贴到元组中，显然在制作完成后我们不能每做一次就重新读取一遍，要把这些变成常量。

~~~Python
xing_tuple = tuple(xing_list)
single_ming_tuple = tuple(single_ming_list)
double_ming_tuple = tuple(double_ming_list)
~~~

**定义父类**

~~~Python
import random
class FakeUser:
    def fake_name(self, one_word = False, two_word = False):
        if one_word:
            name = random.choice(xing_tuple) + random.choice(single_ming_tuple)
        elif two_word:
            name = random.choice(xing_tuple) + random.choice(double_ming_tuple)
        else:
            name = random.choice(xing_tuple) + random.choice(single_ming_tuple + double_ming_tuple)
        print(name)
    def fake_gender(self):
        gender = random.choice(("男","女","未知"))
        print(gender)
fakeUser = FakeUser()
fakeUser.fake_name()
fakeUser.fake_gender()
~~~

**定义子类**

~~~python
class SnsUser(FakeUser):
    def get_followers(self,few=True,a_lot=False):
        if few:
            followers = random.randrange(1,50)
        elif a_lot:
            followers = random.random(100,500)
        print(followers)

user_a = SnsUser()
user_a.get_followers(few=True)
~~~

似乎这并没有解决什么问题，我们已经创建的类可以正常使用了，我们的目的是批量制作假的填充数据，但是这样是比起手工添加，效果并不好到哪里去，因此在原有的代码上需要做一些小的调整，把所有的print替换为yield并在其上方添加一层循环，然后就能想rang函数一样使用方法了。

~~~Python
import random
class FakeUser:
    def fake_name(self,amount=1,one_word=False,two_word=False):
        n = 0
        while n < amount:
            if one_word:
                name = random.choice(xing_tuple) + random.choice(single_ming_tuple)
            elif two_word:
                name = random.choice(xing_tuple) + random.choice(double_ming_tuple)
            else:
                name = random.choice(xing_tuple) + random.choice(single_ming_tuple + double_ming_tuple)
            yield name
            n+=1
    def fake_gender(self,amount=1):
        n = 0
        while n < amount:
            gender = random.choice(("男","女","未知"))
            yield gender
            n+=1
class SnsUser(FakeUser):
    def get_followers(self,amount=1,few=True,a_lot=False):
        n = 0
        while n < amount:
            if few:
                followers = random.randrange(1,50)
            elif a_lot:
                followers = random.random(100,500)
            yield followers
            n+=1

user_a = FakeUser()
user_b = SnsUser()
for name in user_a.fake_name(30):
    print(name)
for gender in user_a.fake_gender(30):
    print(gender)
~~~

带有yield的函数在Python中被称之为generator(生成器)，也就是说，当你调用这个函数的时候，函数内部的代码并不立即执行 ，这个函数只是返回一个生成器(Generator Iterator)。

~~~Python
def generator():
	for i in range(10) :
		yield i*i
gen = generator()
print(gen) # <generator object generator at 0x000001E6AE899D20>
print(next(gen)) # 0
print(next(gen)) # 1
print(next(gen)) # 4
~~~

在函数第一次调用next(gen)函数时，generator函数从开始执行到yield，并返回yield之后的值。

在函数第二次调用next(gen)函数时，generator函数从上一次yield结束的地方继续运行，直至下一次执行到yield的地方，并返回yield之后的值。依次类推。

**安装自己的库**

我们一般使用pip来进行第三方库的安装，那么自己的库怎么安装呢？当然可以把自己的库提交到pip上，但是还要添加一定量的代码和必要的文件才行。这里可以使用更简单的方法：

1. 找到你的Python安装目录，找到下面的lib文件夹。
2. 记住你的文件名，因为它将作为引用时的名称，然后将你写的py文件放进去。

这个文件应该有你所装的所有第三方库。

如果你并不清楚你的安装路径，你可以尝试以下方式：

~~~Python
import sys
print(sys.path)
~~~

对于不知道放到哪里也可以使用这个方法，看看别的库在哪个位置

~~~python
import random
print(random) # <module 'random' from 'C:\\Users\\Administrator\\AppData\\Local\\Programs\\Python\\Python310\\lib\\random.py'>
~~~

加入之后就可以使用了

~~~python
import getName
user_a = getName.FakeUser()
name_list = []
gender_list = []
for name in user_a.fake_name(30):
    name_list.append(name)
for gender in user_a.fake_gender(30):
    gender_list.append(gender)
print(name_list)
print(gender_list)
"""
['施夕君', '王崇才', '韩文兰', '陈益增', '陶海英', '陈兴凤', '郑茂利', '曹德尚', '韩国全', '严冰', '范勋强', '宇文庆岩', '仲孙玉香', '诸葛玉香', '卫桂娟', '施淑钰', '轩辕若付', '魏德
祥', '东方金永', '华传瑞', '上官玉香', '范彦梅', '陶从海', '魏万荣', '冯莹', '上官忠阳', '姜平', '蒋传孝', '孙景亮', '奚俊爱']
['女', '未知', '未知', '未知', '女', '未知', '男', '男', '女', '未知', '未知', '女', '女', '男', '女', '男', '未知', '男', '男', '未知', '女', '女', '男', '男', '男', '未知', '未知', '女', '男', '未知']
"""
~~~

## 第三方库

**pip安装**

安装好的Python是直接支持pip，可以在终端中输入`pip --version`查看版本

如果显示版本就是安装成功了。安装好pip之后，以后安装库，只需要在命令行输入（如果想安装到Python2中，可以将pip3换为pip）：

~~~shell
pip3 install PackageName
~~~

如果安装了Python2和3两个版本可能会遇到安装目录的问题可以换成（如果想安装到Python2中，可以将pip3换为pip）：

~~~shell
python3 -m pip install PackageName
~~~

pip常用命令

~~~shell
pip install --upgrade pip #升级pip
pip uninstall flask #卸载库
pip list #ັ查看已安装库
~~~

**手动安装**

进入`pypi.python.org`，搜索你要安装的库的名字，这时候有3种可能：

- 第一种是exe文件，这种是最方便的，下载满足你电脑系统和Python环境的对应的exe，再一路点击next就可以安装。
- 第二种是.whl类文件，好处是在于可以自动安装依赖的包
- 第三种是源码，大概是zip、tar.zip、tar.bz2格式的压缩包，这个方法要求用户已经安装了这个包所依赖的其他包。例如pandas依赖于numpy，如果不安装numpy，这个方法是无法安装成功pandas的。如果没有前两种文件，就只能用这个了。

# Python通用应用

## 正则表达式

### 正则表达式介绍

正则表达式为高级的的文本模式匹配、抽取、与/或文本形式的搜索和替换功能提供了基础。简单的说。正则表达式（简称为regex）是一些由字符和特殊符号组成的字符串，它们描述了模式的重复或者表述多个字符，于是正则表达式能按照某种模式匹配一系列有相似特征的字符串。

最基本的正则表达式，仅仅需要一个简单的字符串构造成匹配字符串的模式。

| 正则表达式模式 | 匹配的字符串 |
| :------------- | :----------- |
| foo            | foo          |
| abc            | abc          |

上面的第一个正则表达式模式是“foo”。该模式没有使用任何特殊符号去匹配其他符号，而只匹配所描述的内容，所以能够匹配到这个模式的只有包含“foo”的字符串。正则表达式的强大之处在于引入特殊字符来定义字符集。匹配子组和重复模式。正是由于这些特殊符号，使得正则表达式可以匹配字符串集合，而不仅仅只是某个单独的字符串。

**元字符**

| 字符              | 描述                                                         |
| ----------------- | ------------------------------------------------------------ |
| literal           | 匹配文本字符串的字面值 literal                               |
| \                 | 将下一个字符标记为一个特殊字符、或一个原义字符、或一个 向后引用、或一个八进制转义符。例如，'n' 匹配字符 "n"。'\n' 匹配一个换行符。序列 '\\' 匹配 "\" 而 "\(" 则匹配 "("。 |
| ^                 | 匹配输入字符串的开始位置。如果设置了 RegExp 对象的 Multiline 属性，^ 也匹配 '\n' 或 '\r' 之后的位置。 |
| $                 | 匹配输入字符串的结束位置。如果设置了RegExp 对象的 Multiline 属性，$ 也匹配 '\n' 或 '\r' 之前的位置。 |
| *                 | 匹配前面的子表达式零次或多次。例如，zo* 能匹配 "z" 以及 "zoo"。* 等价于{0,}。 |
| +                 | 匹配前面的子表达式一次或多次。例如，'zo+' 能匹配 "zo" 以及 "zoo"，但不能匹配 "z"。+ 等价于 {1,}。 |
| ?                 | 匹配前面的子表达式零次或一次。例如，"do(es)?" 可以匹配 "do" 或 "does" 。? 等价于 {0,1}。当该字符紧跟在任何一个其他限制符 (*, +, ?, {n}, {n,}, {n,m}) 后面时，匹配模式是非贪婪的。非贪婪模式尽可能少的匹配所搜索的字符串，而默认的贪婪模式则尽可能多的匹配所搜索的字符串。例如，对于字符串 "oooo"，'o+?' 将匹配单个 "o"，而 'o+' 将匹配所有 'o'。 |
| {n}               | n 是一个非负整数。匹配确定的 n 次。例如，'o{2}' 不能匹配 "Bob" 中的 'o'，但是能匹配 "food" 中的两个 o。 |
| {n,}              | n是一个非负整数。至少匹配n次。例如，“o{2,}”不能匹配“Bob”中的“o”，但能匹配“foooood”中的所有o。“o{1,}”等价于“o+”。“o{0,}”则等价于“o*”。 |
| {n,m}             | m 和 n 均为非负整数，其中n <= m。最少匹配 n 次且最多匹配 m 次。例如，"o{1,3}" 将匹配 "fooooood" 中的前三个 o。'o{0,1}' 等价于 'o?'。请注意在逗号和两个数之间不能有空格。 |
| .                 | 匹配除换行符（\n、\r）之外的任何单个字符。要匹配包括 '\n' 在内的任何字符，请使用像"**(.\|\n)**"的模式。 |
| (pattern)         | 匹配 pattern 并获取这一匹配。所获取的匹配可以从产生的 Matches 集合得到，在VBScript 中使用 SubMatches 集合，在JScript 中则使用 $0…$9 属性。要匹配圆括号字符，请使用 '\(' 或 '\)'。 |
| (?iLmsux)         | 在正则表达式中嵌入一个或者多个特殊“标记”参数（或者通过函数/方法） |
| (?:pattern)       | 匹配 pattern 但不获取匹配结果，也就是说这是一个非获取匹配，不进行存储供以后使用。 |
| (?P<name>pattern) | 向一个由name标识而不是数字ID标识的正则表达式                 |
| (?P=name)         | 在同一个字符串中匹配由(?P<name>)分组的之前文本               |
| (?#pattern)       | 表示注射                                                     |
| (?=pattern)       | 正向肯定预查（look ahead positive assert），在任何匹配pattern的字符串开始处匹配查找字符串。这是一个非获取匹配，也就是说，该匹配不需要获取供以后使用。例如，"Windows(?=95\|98\|NT\|2000)"能匹配"Windows2000"中的"Windows"，但不能匹配"Windows3.1"中的"Windows"。预查不消耗字符，也就是说，在一个匹配发生后，在最后一次匹配之后立即开始下一次匹配的搜索，而不是从包含预查的字符之后开始。 |
| (?!pattern)       | 正向否定预查(negative assert)，在任何不匹配pattern的字符串开始处匹配查找字符串。这是一个非获取匹配，也就是说，该匹配不需要获取供以后使用。例如"Windows(?!95\|98\|NT\|2000)"能匹配"Windows3.1"中的"Windows"，但不能匹配"Windows2000"中的"Windows"。预查不消耗字符，也就是说，在一个匹配发生后，在最后一次匹配之后立即开始下一次匹配的搜索，而不是从包含预查的字符之后开始。 |
| (?<=pattern)      | 反向(look behind)肯定预查，与正向肯定预查类似，只是方向相反。例如，"`(?<=95|98|NT|2000)Windows`"能匹配"`2000Windows`"中的"`Windows`"，但不能匹配"`3.1Windows`"中的"`Windows`"。 |
| (?<!pattern)      | 反向否定预查，与正向否定预查类似，只是方向相反。例如"`(?<!95|98|NT|2000)Windows`"能匹配"`3.1Windows`"中的"`Windows`"，但不能匹配"`2000Windows`"中的"`Windows`"。 |
| (?(id/name)Y\|N)  | 如果分组所提供的id或者name（名称）存在，就返回正则表达式的条件匹配Y，如果不存在，就返回N；\|N是可选项 |
| x\|y              | 匹配 x 或 y。例如，'z\|food' 能匹配 "z" 或 "food"。'(z\|f)ood' 则匹配 "zood" 或 "food"。 |
| [xyz]             | 字符集合。匹配所包含的任意一个字符。例如， '[abc]' 可以匹配 "plain" 中的 'a'。 |
| [^xyz]            | 负值字符集合。匹配未包含的任意字符。例如， '`[^abc]`' 可以匹配 "plain" 中的'p'、'l'、'i'、'n'。 |
| [a-z]             | 字符范围。匹配指定范围内的任意字符。例如，'[a-z]' 可以匹配 'a' 到 'z' 范围内的任意小写字母字符。 |
| [^a-z]            | 负值字符范围。匹配任何不在指定范围内的任意字符。例如，'`[^a-z]`' 可以匹配任何不在 'a' 到 'z' 范围内的任意字符。 |
| \b                | 匹配一个单词边界，也就是指单词和空格间的位置。例如， 'er\b' 可以匹配"never" 中的 'er'，但不能匹配 "verb" 中的 'er'。 |
| \B                | 匹配非单词边界。'er\B' 能匹配 "verb" 中的 'er'，但不能匹配 "never" 中的 'er'。 |
| \cx               | 匹配由 x 指明的控制字符。例如， \cM 匹配一个 Control-M 或回车符。x 的值必须为 A-Z 或 a-z 之一。否则，将 c 视为一个原义的 'c' 字符。 |
| \d                | 匹配一个数字字符。等价于 [0-9]。                             |
| \D                | 匹配一个非数字字符。等价于 '`[^0-9]`'。                      |
| \f                | 匹配一个换页符。等价于 \x0c 和 \cL。                         |
| \n                | 匹配一个换行符。等价于 \x0a 和 \cJ。                         |
| \r                | 匹配一个回车符。等价于 \x0d 和 \cM。                         |
| \s                | 匹配任何空白字符，包括空格、制表符、换页符等等。等价于 [ \f\n\r\t\v]。 |
| \S                | 匹配任何非空白字符。等价于 '`[^\f\n\r\t\v]`'。               |
| \t                | 匹配一个制表符。等价于 \x09 和 \cI。                         |
| \v                | 匹配一个垂直制表符。等价于 \x0b 和 \cK。                     |
| \w                | 匹配包括下划线的任何单词字符。等价于 '`[A-Za-z0-9_]`'。      |
| \W                | 匹配任何非单词字符。等价于 '`[^A-Za-z0-9_]`'。               |
| \xn               | 匹配 n，其中 n 为十六进制转义值。十六进制转义值必须为确定的两个数字长。例如，'\x41' 匹配 "A"。'\x041' 则等价于 '\x04' & "1"。正则表达式中可以使用 ASCII 编码。 |
| \num              | 匹配 num，其中 num 是一个正整数。对所获取的匹配的引用。例如，'(.)\1' 匹配两个连续的相同字符。 |
| \n                | 标识一个八进制转义值或一个向后引用。如果 \n 之前至少 n 个获取的子表达式，则 n 为向后引用。否则，如果 n 为八进制数字 (0-7)，则 n 为一个八进制转义值。 |
| \nm               | 标识一个八进制转义值或一个向后引用。如果 \nm 之前至少有 nm 个获得子表达式，则 nm 为向后引用。如果 \nm 之前至少有 n 个获取，则 n 为一个后跟文字 m 的向后引用。如果前面的条件都不满足，若 n 和 m 均为八进制数字 (0-7)，则 \nm 将匹配八进制转义值 nm。 |
| \nml              | 如果 n 为八进制数字 (0-3)，且 m 和 l 均为八进制数字 (0-7)，则匹配八进制转义值 nml。 |
| \un               | 匹配 n，其中 n 是一个用四个十六进制数字表示的 Unicode 字符。例如， \u00A9 匹配版权符号 (?)。 |

### Python语言中的正则表达式

在Python中通过re模块来支持正则表达式，表中列出了来自re模块的常见函数和方法，它们中的大多数函数也与已经编译的正则表达式对象（regex object）和正则匹配对象（regex match object）的方法同名并且具有相同的功能。

**函数参数说明**

| 参数    | 描述                                 |
| ------- | ------------------------------------ |
| pattern | 匹配的正则表达式                     |
| string  | 要匹配的字符串                       |
| flags   | 标志位，用于控制正则表达式的表示方式 |

**仅仅是re模块函数**

| 函数/方法                | 描述                                                         |
| ------------------------ | ------------------------------------------------------------ |
| compile(pattern,flags=0) | 使用任何可选的标记来编译正则表达式的模式。然后返回一个正则表达式对象 |

**re模块函数和正则表达式对象的方法**

| 函数/方法                         | 描述                                                         |
| --------------------------------- | ------------------------------------------------------------ |
| match(pattern,string,flags=0)     | 尝试使用带有可选的标记的正则表达式的模式来匹配字符串。如果匹配成功，返回匹配对象，如果失败，就返回None |
| search(pattern,string,flags=0)    | 使用可选标记搜索字符串中第一次出现的正则表达式模式。如果匹配成功，返回匹配对象；如果失败，则返回None |
| findall(pattern,string,[,flags])  | 查找字符串中所有（非重复）出现的正则表达式模式，并且返回一个匹配列表 |
| finditer(pattern,string,[,flags]) | 与findall()函数相同，但返回的不是一个列表，而是一个迭代器。对于每一次匹配，迭代器都返回一个匹配对象 |
| split(pattern,string,max=0)       | 根据正则表达式的模式分隔符，split函数将字符串分割为列表，然后返回成功匹配的列表，分割最多操作max次（默认分割所有匹配成功的位置） |
| sub(pattern,repl,string,count=0)  | 使用repl替换所有正则表达式的模式在字符串中出现的位置，除非定义count，否则就将替换所以出现的位置（另见subn()函数，该函数返回替换操作的数目） |
| purge()                           | 清除隐式编译的正则表达式                                     |

**常用的匹配对象方法**

| 函数/方法               | 描述                                                         |
| ----------------------- | ------------------------------------------------------------ |
| group(num=0)            | 返回整个匹配对象，或者编号为num的特定子组                    |
| group(default=None)     | 返回一个包含所有匹配子组的元组（如果没有成功匹配，则返回一个空元组） |
| groupdict(default=None) | 返回一个包含所有匹配的命名子组的字典，所有的子组名称作为字典的键（如果没有匹配成功，则返回一个空字典） |

**常见的模块属性（用于大多数正则表达式函数的标记）**

| 函数/方法          | 描述                                                         |
| ------------------ | ------------------------------------------------------------ |
| re.I,re.IGNORECASE | 不区分大小写的匹配                                           |
| re.L,re.LOCALE     | 根据所使用的的本地语言环境通过\w、\W、\b、\B、\s、\S实现匹配 |
| re.S,re.DOTALL     | "."（点号）通常匹配除了\n（换行符）之外的所有单个字符串；该标记表示"."（点号）能够匹配全部字符 |
| re.X,re.VERBOSE    | 通过反斜线转义，否则所有空格加上#（以及在该行中所有后续文字）都被忽略，除非在一个字符串中或者允许注释并且提高可读性 |

> `match`和`search`的区别

`match`从字符串的其实开始匹配，`search`不但会搜索模式在字符串中第一次出现的位置，而且是严格地对字符串从左到右搜索。

~~~Python
import re
m = re.match("foo","foo") # 匹配成功
if m is not None:
    print(m.group()) # foo

m = re.match("foo","bfoo") # 匹配失败
if m is not None:
    print(m.group())

m = re.match("foo","bfoo") # 匹配成功
if m is not None:
    print(m.group())
~~~

> `gruop`分组的使用

当处理正则表达式时，除了正则表达式对象之外，还有另一个对象类型：匹配对象。这些是成功调用match()或者search()返回的对象。匹配对象有两个主要的方法：group()和groups()。

group()要么返回整个匹配对象，要么根据要求返回特定子组。groups()则仅返回一个包含唯一或者全部子组的元组。如果没有子组的要求，那么当group()仍然返回整个匹配时，groups()返回一个空元组。

在正则表达式中可以使用圆括号来匹配和保存子组，以便于后续处理，而不是确定一个正则表达式匹配之后，在一个单独的子程序里面收到编码来解析字符串。

~~~Python
m = re.match('(\w\w\w)-(\d\d\d)','abc-123')
print(m.group()) # abc-123
print(m.group(1)) # abc
print(m.group(2)) # 123
print(m.groups()) # ('abc', '123')

m = re.match('ab','ab')
print(m.group()) # ab
print(m.groups()) # ()

m = re.match('(ab)','ab')
print(m.group()) # ab
print(m.group(1)) # ab
print(m.groups()) # ('ab',)

m = re.match('(a(b))','ab')
print(m.group()) # ab
print(m.group(1)) # ab
print(m.group(2)) # b
print(m.groups()) # ('ab', 'b')

m = re.match('(a)(b)','ab')
print(m.group()) # ab
print(m.group(1)) # a
print(m.group(2)) # b
print(m.groups()) # ('a', 'b')
~~~

> `findall`和`finditer`的使用

`findall`在字符串中找到正则表达式所匹配的所有子串，并返回一个列表，如果有多个匹配模式，则返回元组列表，如果没有找到匹配的，则返回空列表。

`match` `search`是匹配一次，而`findall`是匹配所有

~~~Python
m = re.findall("car","car")
print(m) # ['car']

m = re.findall("car","scary")
print(m) # ['car']

m = re.findall(r"car\w","carry the barcardi to the car")
print(m) # ['carr', 'card']
~~~

子组在一个更复杂的返回列表中搜索结果，而且这样做是有意义的，因为子组是允许从单个正则表达式中抽取特定模式的一种机制，例如匹配一个完整电话号码中的一部分（例如区号），或者完整电子邮件地址的一部分（例如登录名称）

对于成功的匹配，每个子组匹配是由`findall`返回的结果列表中的单一元素；对于多个成功的匹配，每个子组匹配时返回的一个元组中的单一元素，而且每个元组（每个元组都对应一个成功的匹配）是结果列表的元素。

`finditer`和`findall`类似，但是是更加节省内存的变体。两者之间以及和其他变体函数之间的差异（很明显不同于返回的是一个迭代器还是列表）在于和返回的匹配字符串相比，`finditer`在匹配对象中迭代。

~~~Python
m = re.findall(r"(th\w+) and (th\w+)", "this and that", re.I)
print(m) # [('this', 'that')]

result = re.findall(r'(\w+)=(\d+)', 'set width=20 and height=10')
print(result) # [('width', '20'), ('height', '10')]

m = re.finditer(r"(th\w+) and (th\w+)", "this and that", re.I)
for item in m :
    print(item.groups()) # ('this', 'that')
    
result = re.finditer(r'(\w+)=(\d+)', 'set width=20 and height=10')
for item in result: 
    print(item.groups()) # ('width', '20') ('height', '10')
~~~

注意，使用`finditer`函数完成的所有额外工作都是旨在获取它的输出来匹配`findall`的输出

`match` `search` `finditer` `findall`方法的都支持可选的pos和endpos参数，这两个参数用于控制目标字符串的搜索边界。

> `sub`和`subn`搜索和替换

`subn`除了返回被替换的字符串，还会返回一个表示替换的总数，替换后的字符串和表示替换总数的数字一起作为一个拥有两个元素的元组返回。

~~~Python
m = re.sub('X','Mr.Smith','attn: X Dear X ')
print(m) # attn: Mr.Smith Dear Mr.Smith

m = re.subn('X','Mr.Smith','attn: X Dear X ')
print(m) # ('attn: Mr.Smith Dear Mr.Smith ', 2)
~~~

> `split`分割

re模块和正则表达式的对象方法split对于相对应字符串的工作方式是类似的，但是与分割一个固体字符串相比，它们基于正则表达式的模式分割字符串，为字符串分割功能添加一些额外的威力。如果不想为每次模式的出现都分割字符串，就可以通过max参数设定一个值（非零）来指定最大分割数。

如果给定分割符不是使用特殊符号来匹配多重模式的正则表达式，那么两个split的工作方式相同。

~~~Python
DATA = ('Mountain View, CA 94040',
'Sunnyvale, CA',
'Los Altos, 94023',
'Cupertino 95014',
'Palo Alto CA'
)
for datum in DATA: 
    print(re.split(', |(?= (?:\d{5}|[A-Z]{2})) ',datum))
"""
['Mountain View', 'CA', '94040']
['Sunnyvale', 'CA']
['Los Altos', '94023']
['Cupertino', '95014']
['Palo Alto', 'CA']
"""
~~~

> 扩展符号

通过使用`(?iLmusux)`系列选项，用户可以直接在正则表达式里指定一个或者多个标记，而不是通过compile()或者其他re模块函数。

`re.I/IGNORECASE` 使匹配对大小写不敏感。

~~~Python
print(re.findall(r'(?i)yes','yes? Yes. YES!!')) # ['yes', 'Yes', 'YES']
~~~

`re.M/MULTILINE` 多行匹配，影响 ^ 和 $。

~~~Python
m = re.findall(r'(?im)(^th[\w ]+)', """
this line is the first,
another line,
that line, it's the best
""")
print(m) # ['this line is the first', 'that line']
~~~

`re.S/DOTALL` 使 . 匹配包括换行在内的所有字符。

~~~Python
print(re.findall(r'th.+',"""
The first line
the second line
the third line
""")) # ['the second line', 'the third line']
print(re.findall(r'(?s)th.+',"""
The first line
the second line
the third line
""")) # ['the second line\nthe third line\n']
~~~

`re.X/VERBOSE` 该标记允许用户通过抑制在正则表达式中使用空白符（除了在字符类中或者再反斜线转义中）来创建更易读的正则表达式。此外，散列、注释和井号也可以用于一个注释的起始，只要它们不在一个用反斜线转义的字符类中。

~~~Python
m = re.search(r"""(?x)
\((\d{3})\) # 区号
[ ] # 空白符
(\d{3}) # 前缀
- # 横线
(\d{4}) # 终点数组
""",'(800) 555-1212').groups()
print(m) # ('800', '555', '1212')
~~~

>`(?:...) `非捕获分组，和捕获分组唯一的区别在于，非捕获分组匹配的值不会保存起来

`(?:...)`符号将更流行；通过使用该符号，乐于对部分正则表达式进行分组，但是并不会保存改分组用于后续的检索或者应用。当不想保存今后永远不会使用的多余匹配时，这个符号就非常有用。

~~~Python
m = re.findall(r'http://(?:\w+\.)*(\w+\.com)','http://google.com http://www.google.com http://code.google.com')
print(m) # ['google.com', 'google.com', 'google.com']

m = re.search(r'\((?P<areacode>\d{3})\) (?P<prefix>\d{3})-(?:\d{4})','(800) 555-1212')
print(m.groupdict()) # {'areacode': '800', 'prefix': '555'}
~~~

> `(?P<name>)`,`(?P=name)`,`\g<name>` 
>
> `(?P<name>)`相当于是给此group命名了，所以，后续（同一正则表达式内和搜索后得到的Match对象中），都可以通过此group的名字而去引用此group。
>
> `(?P=name)`,`\g<name>` 对于分组的引用，前者用于同一个表达是中，后着用于不同表达式，一般用于sub中

可以同时使用`(?P<name>)`（为分组再指定一个组合名，每个组合名只能用一个正则表达式定义，只能定义一次）和`(?P=name)`（反向引用一个命名组合，匹配前面那个名字叫name的命名组中匹配到的字符串）符号。前者通过使用一个名称标识而不是使用从1开始增加到N的增量数字来保存匹配，如果使用数字来保存匹配结果，就可以通过使用\1,\2...\N来检索。

~~~Python
m = re.sub(r'\((?P<areacode>\d{3})\) (?P<prefix>\d{3})-(?:\d{4})','(\g<areacode>) \g<prefix>-xxxx','(800) 555-1212')
print(m) # (800) 555-xxxx

m = re.sub(r'\((?P<areacode>\d{3})\) (?P<prefix>\d{3})-(?:\d{4})','(\g<2>) \g<1>-xxxx','(800) 555-1212')
print(m) #(555) 800-xxxx

m = re.sub(r'\((?P<areacode>\d{3})\1\) (?P<prefix>\d{3})\2-(?:\d{4})','(\1) \2-xxxx','(800) 555-1212')
print(m) # (800) 555-1212
~~~

使用`(?P=name)`可以在同一个相同的正则表达式中重用模式，而不必稍后再次在（相同）正则表达式中指定相同的模式。

~~~Python
m = re.match(r'\((?P<areacode>\d{3})\) (?P<prefix>\d{3})-(?P<number>\d{4}) (?P=areacode)-(?P=prefix)-(?P=number) 1(?P=areacode)(?P=prefix)(?P=number)','(800) 555-1212 800-555-1212 18005551212')
print(m.groups()) # ('800', '555', '1212')
~~~

> `(?=...)`和`(?!...)` 正向肯定断言和正向否定断言

和普通的正则表达式的区别：

- 一是普通的正则项在结果中有对应的字符串，参与匹配项的提取，即会被**捕获**，断言则不被捕获，即不进入最终匹配结果；
- 二是断言的位置固定，前向断言只用于整个正则式的末尾，后向断言则只用于整个正则式的起始。

~~~Python
m = re.findall(r'\w+(?= van Rossum)',"""
Guido van Rossum
Tim Peters
Alex Martelli
Just van Rossum
Raymond Hettinger
""")
print(m) # ['Guido', 'Just']

m = re.findall(r'(?m)^\s+(?!noreply|postmaster)(\w+)','''
 sales@phptr.com
 postmaster@phptr.com
 eng@phptr.com
 noreply@phptr.com
 admin@phptr.com
''')
print(m) # ['sales', 'eng', 'admin']
~~~

最后一个示例展示了使用条件正则表达式匹配。假定拥有另一个特殊字符，它仅仅包含字母“x”和“y”，因此想要这样限定字符串：两字母的字符串必须由一个字母跟着另一个字母，换句话说，不能同时拥有两个相同的字母。

~~~Python
m = re.search(r'(?:(x)|y)(?(1)y|x)','xy')
print(m.group()) # xy
m = re.search(r'(?:(x)|y)(?(1)y|x)','xx')
print(m) # None
~~~

> ASCII转义字符和正则表达式中特殊字符冲突

作为一个特殊的符号，`\b`表示ASCII字符的退格符，但是`\b`同时也是一个正则表达式的特殊符号，表示匹配一个单词的边界。对于正则表达式编译器而言，若它把两个`\b`视为字符串内容而不是单个退格符，就需要在字符串中再使用一个反斜线转义反斜线，`\\b`。

~~~Python
m = re.search('\bblow','blow')
if m:
    print(m.group()) # 

m = re.search('\\bblow','blow') # 转义\
if m:
    print(m.group()) # blow

m = re.search(r'\bblow','blow') #原始字符串
if m:
    print(m.group()) # blow
~~~

> 贪婪匹配

现在有一个字符串 `The Feb 15 17:46:04 2007:uzifzf@dpyicihw.gov::1171590364-6-8` 现在想找三个由连字符串分割的整数，创建正则表达式来说明这需求：`\d+-\d+-\d+`。该正则表达式的含义是，“任何数字（至少一个）后面跟着一个连字符，然后是多个数字、另一个连字符，最后是一个数字集”。

~~~Python
m = re.search('\d+-\d+-\d+','The Feb 15 17:46:04 2007:uzifzf@dpyicihw.gov::1171590364-6-8')
if m:
    print(m.group()) # 1171590364-6-8
~~~

没法匹配整个字符串，因为匹配从字符串的起始部分开始，需要被匹配的数值位于字符串的末尾。可以使用贪婪匹配，即使用`.+`来表明一个任意字符串集跟在我们真正感兴趣的部分之后。

~~~Python
m = re.search('.+\d+-\d+-\d+','The Feb 15 17:46:04 2007:uzifzf@dpyicihw.gov::1171590364-6-8')
if m:
    print(m.group()) # The Feb 15 17:46:04 2007:uzifzf@dpyicihw.gov::1171590364-6-8
~~~

但是如果只想要末尾的数字字段，而不是整个字符串，可以使用园括号对想要的内容进行分组。

~~~Python
m = re.search('.+(\d+-\d+-\d+)','The Feb 15 17:46:04 2007:uzifzf@dpyicihw.gov::1171590364-6-8')
if m:
    print(m.group(1)) # 4-6-8
~~~

出现了问题，我们想提取1171590364-6-8，然而却是4-6-8，第一个整数的其余部分没有了。问题出在于正则表达式本质上实现贪婪匹配。这就意味着对于通配符模式，将对正则表达式从左到右按顺序求值，而且试图获取匹配该模式的尽可能多的字符。在之前的示例中，使用`.+`获取从字符串起始位置开始的全部单个字符，包括所期望的一个整数字段。\d+仅仅需要一个数字，因此将得到4，其中`.+`匹配了从字符串起始部分到所期望的第一个数字的全部内容。

~~~Python
m = re.search('(.+)(\d+-\d+-\d+)','The Feb 15 17:46:04 2007:uzifzf@dpyicihw.gov::1171590364-6-8')
if m:
    print(m.group(1)) # The Feb 15 17:46:04 2007:uzifzf@dpyicihw.gov::117159036
~~~

其中的一个方案可以是使用“非贪婪”操作符“？”。可以在“*”、“+”或者“？”之后使用该操作符。该操作符将要求正则表达式引擎尽可能少的匹配字符。

~~~Python
m = re.search('.+?(\d+-\d+-\d+)','The Feb 15 17:46:04 2007:uzifzf@dpyicihw.gov::1171590364-6-8')
if m:
    print(m.group(1)) # 1171590364-6-8
~~~

最后一个示例，如果想取出三个整数字段中间的那个整数，可以使用`-(\d+)-`

~~~Python
m = re.search('-(\d+)-','The Feb 15 17:46:04 2007:uzifzf@dpyicihw.gov::1171590364-6-8')
if m:
    print(m.group(1)) # 6
~~~

## 网络编程

### socket套接字

套接字是计算机网络数据结构，它体现了“通信端点”的概念。在任何类型的通信开始之前，网络应用程序必须创建套接字。

套接字起源于 20 世纪 70 年代加利福尼亚大学伯克利分校版本的 Unix,即人们所说的 BSD Unix。 因此,有时人们也把套接字称为“伯克利套接字”或“BSD 套接字”。一开始,套接字被设计用在同 一台主机上多个应用程序之间的通讯。这也被称进程间通讯,或 IPC。套接字有两种（或者称为有两个种族）,分别是基于文件型的和基于网络型的。

基于文件类型的套接字家族：AF_UNIX

unix一切皆文件，基于文件的套接字调用的就是底层的文件系统来取数据，两个套接字进程运行在同一机器，可以通过访问同一个文件系统间接完成通信。

基于网络类型的套接字家族：AF_INET

还有AF_INET6被用于ipv6，还有一些其他的地址家族，不过，他们要么是只用于某个平台，要么就是已经被废弃，或者是很少被使用，或者是根本没有实现，所有地址家族中，AF_INET是使用最广泛的一个，python支持很多种地址家族，但是由于我们只关心网络编程，所以大部分时候我么只使用AF_INET。

Python目前只支持AF_UNIX、AF_NETLINK、AF_TIPC、AF_INET。

每个家族的套接字都分为两种。一种是面向连接的套接字，一种是无连接的套接字。

面向连接的套接字的主要协议是传输控制协议，就是TCP协议，为了创建TCP套接字，必须使用SOCK_STREAM作为套接字类型。TCP套接字的名称SOCK_STREAM基于流套接字到额其中一种表示。因为这些套接字（AF_INET）的网络版本使用因特网协议（IP）来搜寻网络总的主机，所以整个系统通过结合这两种协议（TCP/IP）进行。

无连接的套接字主要协议是用户数据报协议，就是UDP协议。为了创建UDP套接字，必须使用SOCK_DGRAM作为套接字类型，因为这些套接字也使用因特网协议（IP）来搜寻网络总的主机，所以整个系统通过结合这两种协议（UDP/IP）进行。

### Python中的网络编程

本节使用得我主要模块是socket模块，在这个模块里可以找到socket函数，该函数可以创建套接字对象。套接字也有自己的方法集，这些方法可以实现基于套接字的网络通信。

> socket()模块函数

要创建套接字，必须使用socket.socket()函数，

`socket(socket_family,socket_type,protocol=0)`

其中，socket_family是AF_INET或者AF_UNIX，socket_type是SOCK_STREAM或者SOCK_DGRAM。protocol通常省略，默认为0。所以创建TCP/IP套接字，可以这样写

`tcpSock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)`

同理，创建UDP/IP套接字

`udpSock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)`

> 套接字对象（内置）方法

**服务器套接字方法**

| 名称       | 描述                                              |
| ---------- | ------------------------------------------------- |
| s.bind()   | 将地址（主机名、端口号）绑定到套接字上            |
| s.listen() | 设置并启动TCP监听器                               |
| s.accept() | 被动接受TCP客户端连接，一直等待到连接到达（阻塞） |

**客户端套接字方法**

| 名称           | 描述                                                         |
| -------------- | ------------------------------------------------------------ |
| s.connect()    | 主动初始化TCP服务器连接，。一般address的格式为元组（hostname,port），如果连接出错，返回socket.error错误。 |
| s.connect_ex() | connect()函数的扩展版本,出错时返回出错码,而不是抛出异常      |

**普遍套接字方法**

| 名称                                 | 描述                                                         |
| ------------------------------------ | ------------------------------------------------------------ |
| s.recv()                             | 接收TCP数据，数据以字符串形式返回，bufsize指定要接收的最大数据量。flag提供有关消息的其他信息，通常可以忽略。 |
| s.recv_into()                        | 接收TCP消息到指定的缓冲区                                    |
| s.send()                             | 发送TCP数据，将string中的数据发送到连接的套接字。返回值是要发送的字节数量，该数量可能小于string的字节大小。 |
| s.sendall()                          | 完整发送TCP数据。将string中的数据发送到连接的套接字，但在返回之前会尝试发送所有数据。成功返回None，失败则抛出异常。 |
| s.recvfrom()                         | 接收UDP数据，与recv()类似，但返回值是（data,address）。其中data是包含接收数据的字符串，address是发送数据的套接字地址。 |
| s.recvfrom_into()                    | 接收UDP消息到指定的缓冲区                                    |
| s.sendto()                           | 发送UDP数据，将数据发送到套接字，address是形式为（ipaddr，port）的元组，指定远程地址。返回值是发送的字节数。 |
| s.getsockname()                      | 返回套接字自己的地址。通常是一个元组(ipaddr,port)            |
| s.getpeername()                      | 返回连接套接字的远程地址。返回值通常是元组（ipaddr,port）。  |
| s.setsockopt(level,optname,value)    | 设置给定套接字选项的值。                                     |
| s.getsockopt(level,optname[.buflen]) | 返回套接字选项的值。                                         |
| s.shutdown()                         | 关闭连接                                                     |
| s.close()                            | 关闭套接字                                                   |
| s.detach()                           | 在未关闭文件描述符的情况下关闭套接字，返回文件描述符         |
| s.ioctl()                            | 控制套接字的模式（仅支持Windows）                            |

**面向阻塞的套接字方法**

| 名称            | 描述                           |
| --------------- | ------------------------------ |
| s.setblocking() | 设置套接字的阻塞或者非阻塞模式 |
| s.settimeout()  | 设置阻塞套接字操作的超时时间   |
| s.gettimeout()  | 获取阻塞套接字操作的超时时间   |

**面向文件的套接字方法**

| 名称         | 描述                       |
| ------------ | -------------------------- |
| s.fileno()   | 套接字的文件描述符         |
| s.makefile() | 创建与套接字关联的文件对象 |

**数据属性**

| 名称     | 描述       |
| -------- | ---------- |
| s.family | 套接字家族 |
| s.type   | 套接字类型 |
| s.proto  | 套接字协议 |

> 创建TCP服务器

首先将展示创建通用TCP服务器的一般伪代码，然后对这些代码的含义进行一般性的描述。

~~~python
ss = socket() # 创建服务器套接字
ss.bind() # 套接字于地址绑定
ss.listen() # 监听连接
inf_loop: # 服务器无限循环
    cs = ss.accept() # 接受客户端连接
    comm_loop: # 通信循环
        cs.recv()/cs.send() # 对话（接收/发送）
    cs.close() # 关闭客户端套接字
ss.close() # 关闭服务端套接字
~~~

所以套接字都是通过使用socket.socket()函数创建出来的，因为服务器需要占用一个端口并等待客户端的请求，所以它们必须绑定到一个本地地址，因为TCP是一种面向连接的通信系统，所以在TCP服务器开始操作之前，必须安装一些基础设施。特别地，TCP服务器必须监听（传入）的连接。一旦这个安装过程完成后，服务端就可以开始它的无限循环。

调用accept()函数之后，就开启了一个简单的（单线程）服务器，它会等待客户端的连接。默认情况下，accept()是阻塞的，这意味着执行将被暂停，直到一个连接到达。另外，套接字确实也支持非阻塞模式。

一旦服务器接受了一个连接，就会返回（利用accept()）一个独立的客户端套接字，用来与即将到来的消息进行交换。使用新的客户端套接字类似于将客户的电话切换给客服代表，当一个客户电话最后接进来时，主要的总机接线员会接收到这个电话，并使用另一条线路将这个电话转接给合适的人来处理客户的需求。

这将能够空出主线（原始服务器套接字），以便接线员可以继续等待新的电话（客户请求），而此时客户机其连接的客服代表能够进行他们自己的谈话，同样的，当一个传入的请求到达时，服务器会创建一个新的通信端口来直接与客户端进行通信，再次空出主要的端口，以便其能接受新的客户端连接。

一旦创建了临时套接字，通信就可以开始，通过使用这个新的套接字，客户端与服务器就可以开始参与发送和接收的对话中，直到连接终止。当一方关闭连接或者向对方发送空字符串时，通常就会关闭连接。

在代码中，一个客户端连接关闭之后，服务器就会等待另一个客户端连接。最后一行代码是可选的，在这里关闭了服务器套接字。其实，这种情况永远也不会碰到，因为服务器应该在一个无限循环中运行，在实例中这行代码用来提醒读者，当为服务器实现一个智能的退出方案时，建议使用close()方法。例如，当一个处理程序监测到一些外部条件时，服务器就应该关闭。在这些情况下，应该调用一个close()方法。

~~~Python
from socket import *
from time import ctime

host = 'localhost'
port = 21567
bufSiz = 1024
addr = (host,port)


tcpSerSocket = socket(AF_INET,SOCK_STREAM)
tcpSerSocket.bind(addr)
tcpSerSocket.listen(5)

while True: 
    print('waiting for connection...')
    tcpCliSocket, addr= tcpSerSocket.accept()
    print('...connection from:', addr)
    while True: 
        data = tcpCliSocket.recv(bufSiz)
        if not data:
            break
        data = '[%s] %s' %(ctime(), data.decode('utf-8'))
        tcpCliSocket.send(data.encode('utf-8'))
    tcpCliSocket.close()
tcpSerSocket.close()
~~~

> 创建TCP客户端

创建客户端要比服务端简单

~~~Python
cs = socket() # 创建客户端套接字
cs.connect() # 尝试连接服务器
inf_loop: # 通信循环
    cs.recv()/cs.send() # 对话（接收/发送）
cs.close() # 关闭客户端套接字
~~~

正如之前提到的，所有套接字都是利用socket.socket()创建的。然而，一旦客户端拥有了一个套接字，它就可以利用套接字的connect()方法直接创建一个到服务器的连接。当连接建立之后，它就可以参与到与服务器的一个对话中。最后，一旦客户端完成了它的事务，它就可以关闭套接字，终止此次连接。

~~~Python
from socket import *

host = 'localhost'
port = 21567
bufSiz = 1024
addr = (host,port)

tcpCliSocket = socket(AF_INET, SOCK_STREAM)
tcpCliSocket.connect(addr)
while True: 
    data = input('请输入信息：')
    if not data: 
        break
    tcpCliSocket.send(bytes(data, 'utf-8'))
    data = tcpCliSocket.recv(bufSiz)
    if not data: 
        break
    print(data.decode('utf-8'))
tcpCliSocket.close()
~~~

> 创建UDP服务端

UDP服务器不需要TCP服务器那么多的设置，因为它们不是面向连接的。除了连接外，几乎不需要做其他工作

~~~Python
ss = socket() # 创建服务器套接字 
ss.bind() # 绑定服务器套接字
inf_loop: # 服务器无限循环
    cs = ss.recvfrom()/ss.sendto() # 接收/发送
ss.close() # 关闭服务器套接字
~~~

以上伪代码中可以看出，除了普通的创建套接字并将其绑定到本地地址（主机名/端口号）外，并没有额外的工作。无限循环包换接收客户端消息，打上时间戳返回消息，然后回到等待另一条消息的状态。再一次，close()调用是可以选择的，由于无限循环的缘故，关闭方法并不会被调用，但是提醒我们，它应该是优雅或者智能退出方案的一部分。

UDP和TCP服务器之前的另一个显著差异是，因为数据报套接字是无连接的，所以就没有成功通信而使一个客户端连接到一个独立的套接字“转换“的操作。这些服务器仅仅接受消息并有可能回复数据。

~~~Python
from socket import *
from time import ctime

host = 'localhost'
port = 21567
bufSiz = 1024
addr = (host,port)

udpSerSocket = socket(AF_INET,SOCK_DGRAM)
udpSerSocket.bind(addr)

while True: 
    print('waiting for message...')
    data, addr = udpSerSocket.recvfrom(bufSiz)
    data = '[%s] %s' %(ctime(), data.decode('utf-8'))
    udpSerSocket.sendto(data.encode('utf-8'),addr)
    print('...receiced from and returned to:', addr)
udpSerSocket.close()
~~~

> 创建UDP客户端

~~~Python
cs = socket() # 创建客户端套接字
comm_loop: # 通信循环
    cs.sendto()/cs.recvfrom() # 对话（发送/接收）
cs.close() # 关闭客户端套接字
~~~

一旦创建了套接字对象，就会进入对话循环中，在这里与服务器交换信息，通信结束时，就会关闭套接字。

~~~Python
from socket import *
from time import ctime

host = 'localhost'
port = 21567
bufSiz = 1024
addr = (host,port)

udpCliSocket = socket(AF_INET,SOCK_DGRAM)

while True: 
    data = input('输入消息：')
    if not data: 
        break
    udpCliSocket.sendto(data.encode('utf-8'),addr)
    data,addr = udpCliSocket.recvfrom(bufSiz)
    if not data: 
        break
    print(data.decode('utf-8'))
udpCliSocket.close()
~~~

## 因特网客户端编程

因特网可以理解为用来传输数据的地方，数据在服务提供这和服务使用者之间传递。在某些情况下称为“生产者-消费者”。服务器就是生产者，提供服务，而客户端就是消费者，使用服务。对于特定的服务，一般只有一个服务器，但是会有多个消费者。虽然现在不在使用底层的套接字创建因特网客户端，但是模型是完全相同的。

### 文件传输因特网协议

因特网中最常见的就是文件传输。最流行的包括文件传输协议（FTP），UNIX到UNIX复制协议（UUCP），用于web的超文本传输协议（HTTP），还有（UNIX下的）远程文件复制命令rcp。

> 文件传输协议

FTP主要用于匿名下载公共文件，也可以运用于在两台计算机之间传输文件。FTP需要输入用户名和密码才能访问远程FTP服务器，但是也允许没有账号的用户匿名登录。不过管理员要先设置FTP服务器以允许匿名用户登录，这时匿名用户的用户名是“anonymous”，密码一般是用户的电子邮箱地址。与想特定的登录用户传输文件不同，这相当于公开某些目录让大家访问。但是与登录用户相比，匿名用户只能使用有限的几个FTP命令。

工作流程：

1. 客户端连接远程主机上的FTP服务器。
2. 客户端输入用户名和密码。
3. 客户端进行各种文件传输和信息查询操作。
4. 客户端从远程FTP服务器退出，结算传输。

在使用Python的FTP支持时，所需要做的只是导入ftplib模块，并实例化一个ftplib.FTP类对象，所有的FTP操作都是使用这个对象完成的。

伪代码

~~~Python
from ftplib import FTP
f = FTP('some.ftp.server')
f.login('anonymous','')
...
f.quit()
~~~

> ftplib常用方法

| 方法                              | 描述                                                         |
| --------------------------------- | ------------------------------------------------------------ |
| login(user='',passwd='',acct='')  | 登录FTP服务器，所有参数都是可选的                            |
| pwd()                             | 获得当前工作目录                                             |
| cwd(path)                         | 把当前工作目录设置为path所示路径                             |
| dir([path[,...[,cb]])             | 显示path目录的内容，可选的参数cb是一个回调函数，会传递给retrlines()方法 |
| nlst([path[,...])                 | 与dir()类似，但返回一个文件名列表，而不是显示这些文件名      |
| retrlines(cmd[,cb])               | 给定FTP命令（如“RETR filename”），用于下载文本文件。可选的回调函数cb用于处理文件每一行 |
| retrbinary(cmd,cb[,bs=8192[,ra]]) | 和retrlines()类似，只是这个指令处理二进制文件。回调函数cb用于处理每一块（块大小默认为8KB下载的数据 |
| storlines(cmd,f)                  | 给定FTP命令（如“STOR filename”），用于上传文本文件。要给定一个文件对象f |
| storbinary(cmd,f[,bs=8192])       | 与storlines()类似，只是这个指令处理二进制文件。要给定一个文件对象f，上传块大小bs默认为8KB |
| rename(old,new)                   | 把远程文件old重命名为new                                     |
| deletc(path)                      | 删除位于path的远程文件                                       |
| mkd(dirctory)                     | 创建远程目录                                                 |
| rmd(dirctory)                     | 删除远程目录                                                 |
| quit()                            | 关闭连接并退出                                               |

~~~Python
from ftplib import FTP
f = FTP()
f.connect('XXX.XXX.XXX.XXX') # 连接
f.login('anonymous','') # 登录
f.cwd('/log') # 进入具体的路径
print(f.pwd()) # 显示路径
f.dir() # 显示文件
for i in f.nlst(): # 展示目录下文件名，文件夹和文件都会展示
    print(i)
fd = open('C:/Users/Administrator/Desktop/test.txt','rb') # 以只读的方式打开要上传的文件
f.storbinary('STOR test.txt',fd) # 上传文件
fd = open('C:/Users/Administrator/Desktop/LogFile_20230117.txt','wb') # 以只写的方式打开要下载文件及目录
f.retrbinary('RETR LogFile_20230117.txt', fd.write, 2048) # 下载文件
f.quit()
~~~

## 多线程编程

### 进程与线程

> 进程

计算机程序只是存储在磁盘上的可执行二进制文件，只有把他们加载到内存中并被操作系统调用，才能拥有其生命期。进程是一个执行中的程序。每个进程都拥有自己的地址空间、内存、数据栈以及其用于跟踪执行的辅助数据。操作系统管理其上所有进程的执行，并为这些进程合理的分配时间。进程也可以通过派生新的进程来执行其他任务，不过因为每个新进程也都拥有自己的内存和数据栈等，所以只能有进程间通信（IPC）的方式共享信息。

> 线程

线程与进程类似，不过它们是在同一个进程下执行的，并共享相同的上下文。可以将它们认为是在一个主进程或者“主线程”中并行运行的一些”迷你进程“。

线程包括开始、执行顺序和结束三个部分。它们有一个指令指针，用于记录当前运行的上下文。当其他线程运行时，它可以被抢占（中断）和临时挂起（睡眠），这种做法叫做让步。

一个进程中的各个线程与主线程共享同一片数据空间，因此相比于独立的进程而言，线程间的信息共享和通信更加容易。线程一般是以并发方式执行的，正是由于这种并行和数据的共享机制，是的多任务间的协作成为可能。当然，在单核CPU系统中，因为真正的并发是不可能的，所以线程的执行实际上是每个线程运行一会然后让步给其他线程（再次排队等待获取CPU执行时间）。在整个进程的执行过程中，每一个线程执行它自己特定的任务，在必要时和其他线程进行结果通信。

当然，这种共享并不是没有风险的。如果两个或者多个线程访问同一片数据，由于数据访问顺序不同，可能会导致结果不一致。这种情况被称为竞态条件，幸运的是大多数线程库都有一些同步原语，以允许线程管理器控制执行和访问。

另一个需要主要的问题是，线程无法给予公平的执行时间。这是因为一些函数会在完成前保持阻塞状态，如果没有专门为多线程情况进行修改，会导致CPU的时间分配向这些贪婪的函数倾斜。

### 线程和Python

> 全局解释器锁

Python代码的执行是由Python虚拟机（解释器主循环）进行控制的。Python在设计时是这样考虑的，在主循环中同时只能有一个控制线程在执行，就像单核CPU系统中的多进程一样。内存中可以有许多程序，但是在任意给定时刻只能有一个线程在运行。同理，尽管Python解释器中可以运行多个线程，但是在任意给定时刻只有一个线程会被解释器执行。

对Python虚拟机的访问时由全局解释器锁（GIL）控制的。这个锁就是用来保证同时只能有一个线程运行的。在多线程环境下，Python虚拟机将按照下面所述的方式执行。

1. 设置GIL。
2. 切换进一个线程去运行。
3. 执行下面操作之一。
   1. 指定数量的字节码指令。
   2. 线程主动让出控制权（可以调用time.sleep(0)来完成）。
4. 吧线程设置回睡眠状态（切换出线程）。
5. 解锁GIL。
6. 重复上述步骤。

当调用外部代码（即，任意C/C++扩展的内置函数）时，GIL会保持锁定，直到函数执行结束（因为在这期间没有Python字节码计数）。编写扩展函数的程序员有能力解锁GIL，然而，作为Python开发者，并不需要担心Python代码会在这种情况下被锁住。

例如，对于任意面向I/O的Python例程（调用了内置的操作系统C代码的那种），GIL会在I/O调用前被释放，以允许其他线程在I/O执行的时候运行。而对于那些没有太多I/O财政的代码而言，更倾向于在该线程整个时间片始终占有处理器（和GIL）。换句话说就是，I/O密集型的Python程序要比计算密集型的代码能够更好地利用多线程环境。

> 退出线程

当一个线程完成函数的执行时，它就会退出，另外，还可以通过调用诸如thread.exit()之类的退出函数，或者sys.exit()之类的退出Python进程的标准方法，亦或者抛出SystemExit异常，来使线程退出。不过，你不能直接“终止”一个进程。

> 不使用线程的情况

~~~Python
from time import sleep, ctime

def loop0():
    print('start loop 0 at:', ctime())
    sleep(4)
    print('loop 0 done at:', ctime())

def loop1():
    print('start loop 1 at:', ctime())
    sleep(2)
    print('loop 1 done at:', ctime())

def main():
    print('start at:', ctime())
    loop0()
    loop1()
    print('all DONE at:', ctime())
main()
~~~

如果在一个进程中执行睡眠loop0()和loop1()，整个执行结果至少达到6秒。

> Python中的threading模块

Python提供类多个模块来支持多线程编程，包括thread、threading和Queue模块等。程序是可以使用thread和threading模块来创建与管理线程。thread模块提供了基本的线程和锁定支持；而threading模块提供了更高级、功能更全面的线程管理。使用Queue模块，用户可以创建一个队列数据结构，用于在多线程之间进行共享。

推荐使用更高级的threading模块，而不是使用thread。threading模块更加先进，有更好的线程支持，并且thread模块中的一些属性会和threading模块有冲突。另一个原因是低级别的thread模块拥有的同步原语很少（实际上只有一个），而threading模块则有很多。

避免使用thread模块的另一个原因是它对于进程何时退出没有控制。当主线程结束时，所有其他线程也都强制结束。不会发出警告或者进行适当的清理。如前所述，至少threading模块能确保重要的子线程在进程退出前结束。

只是建议哪些想访问线程的更底层级别的专家使用thread模块。为了强调这一点，在Python3中该模块呗重命名为_thread。你创建的任何多线程应用都应该使用threading模块或者其他更高级别的模块。

> thread模块

除了派生线程外，thread模块还提供基本的同步数据结构，称为锁对象（lock object，也叫原语锁，简单锁，互斥锁，互斥和二进制信号量）。如前所述，这个同步原语和线程管理是密切相关的。

**thread模块的函数**

| 方法                                        | 描述                                                         |
| ------------------------------------------- | ------------------------------------------------------------ |
| start_new_thread(function,args,kwargs=None) | 派生一个新的线程，使用给定的args和可选的kwargs来执行function |
| allocate_lock()                             | 分配LockType锁对象                                           |
| exit()                                      | 给线程退出指令                                               |

**lockType锁对象的方法**

| 方法               | 描述                                    |
| ------------------ | --------------------------------------- |
| acquire(wait=None) | 尝试获取锁对象                          |
| locked()           | 如果获取了锁对象返回True，否则返回False |
| release()          | 释放锁                                  |

thread模块的核心函数是start_new_thread()。它的参数包含函数（对象），函数的参数以及可选的关键字参数。将专门派生新的线程来调用这个函数。

~~~Python
from time import sleep, ctime
import _thread

def loop0():
    print('start loop 0 at:', ctime())
    sleep(4)
    print('loop 0 done at:', ctime())

def loop1():
    print('start loop 1 at:', ctime())
    sleep(2)
    print('loop 1 done at:', ctime())

def main():
    print('start at:', ctime())
    _thread.start_new_thread(loop0,())
    _thread.start_new_thread(loop1,())
    sleep(6)
    print('all DONE at:', ctime())
main()
~~~

相比之前的代码，现在执行完两个方法只需要4秒时间，也就是最长的循环加上其他所以开销的时间之和。

睡眠4秒和睡眠2秒是并发执行的，这样有助于减少整体的运行时间，甚至可以看到loop1在loop2之前结束。

这个程序中剩下的一个主要的区别是增加了一个sleep(6)调用。这是因为如果没有阻止主线程继续执行，它将会继续执行下一条语句，显示“all done”然后退出，而loop0()和loop1()这两个线程将直接终止。

但是又有一个新的问题，由于这个延时，整个程序的运行并没有比单线程更快，像这样使用sleep()来进行线程同步是不可靠的。如果循环有独立且不同的执行时间要怎么办，我们可能会过早或者过晚的退出主线程，这就是引出锁的原因。

~~~Python
from time import sleep, ctime
import _thread

loops = [2,4]

def loop(nloop, nsec, lock):
    print('start loop', nloop, 'at:', ctime())
    sleep(nsec)
    print('loop', nloop, 'done at:', ctime())
    lock.release()

def main():
    print('starting at:', ctime())
    locks = []
    nloops = range(len(loops))
    for i in nloops:
        lock = _thread.allocate_lock()
        lock.acquire()
        locks.append(lock)
    for i in nloops:
        _thread.start_new_thread(loop, (i, loops[i], locks[i]))
    for i in nloops:
        while locks[i].locked(): pass
    print('all DONE at:', ctime())

main()
~~~

代码解析：

1. 在UNIX启动行后，导入了time模块的几个熟悉属性以及thread模块。我们不再把4秒和2秒硬编码到不同的函数中，而是使用了唯一的loop()函数，并把这些常量放进列表loops中。
2. loop()函数代替了之前例子中的loop*()函数，因此，必须在loop()函数中做一些修改，以便它能使用锁来完成自己的任务。其中最明显的变化是我们需要知道现在处于哪个循环中，以及需要睡眠多久。最后一个新的内容就是锁本身。每个线程将被分配一个已获得的锁。当sleep()的时间到了的时候，释放对应的锁，向主线程表明该线程已完成。
3. 大部分工作是在main()中完成的，这里使用了3个独立的for循环。首先创建一个锁列表，通过使用`thread.allocate_lock()`函数获得锁对象，然后通过acquire()方法取得每个锁，取得锁效果相当于“把锁锁上”。一旦锁被锁上后，就可以将它添加到锁列表locks中。下一个循环用于派生线程，每个线程都会调用loop()函数，并传递循环号，睡眠时间以及用于该线程的锁这几个参数。那么为什么我们不在上锁的循环中启动线程呢？有两个原因：其一。想要同步线程，以便同时开始，其二，获取所需要花费一点时间。如果线程执行的太快，有可能出现获取锁之前线程就只想结束的情况。在每个线程执行完成时，它会释放自己的锁对象。最后一个循环只是坐在那里等待(暂停主线程)，直到所有锁都被释放之后才会继续执行。因为我们按照顺序检查每个锁，所有可能会被排在循环列表前面但是执行较慢的循环所拖累。这种情况下，大部分时间是在等待最前面的循环。当这种线程的锁被释放时，剩下的锁可能早已被释放，结果就是主线程会飞快地、没有停顿地完成对剩下锁的检查，然后就是结束程序。

> threading模块

**threading模块的对象**

| 对象             | 描述                                                         |
| ---------------- | ------------------------------------------------------------ |
| Thread           | 表示一个执行线程的对象                                       |
| Lock             | 锁原语对象（和thread模块中的锁一样）                         |
| RLock            | 可重入锁对象，使单一线程可以（再次）获得已持有的锁（递归锁） |
| Condition        | 条件变量对象，使得一个线程等待另一个线程满足特定的“条件”，比如改变状态或者某个数值 |
| Event            | 条件变量的通用版本，任意数量的线程等待某个事件的发生，在该事件发生后所有线程将被激活 |
| Semaphore        | 为线程间共享的有限资源提供了一个“计数器”，如果没有可用资源时会被堵塞 |
| BoundedSemaphore | 与Semaphore相似，不过它不允许超过初始值                      |
| Timer            | 与Thread相似，不过它要在运行前等待一段时间                   |
| Barrier          | 创建一个“障碍”，必须达到指定数量的线程后才可以继续           |

避免使用thread模块的另一个原因是该模块不支持守护线程这个概念。当主线程退出时，所以子线程都将终止，不管他们是否仍在工作。threading支持守护线程，其工作的方式是：守护线程一般是一个等待客户端请求的服务器。如果没有客户端请求，守护线程就是空闲的。如果吧一个线程设置为守护线程，就表示这个线程是不重要的，进程退出时不需要等待这个线程执行完成。如果主线程准备退出时，不需要等待某些子线程完成，就可以为这些子线程设置守护线程标记。该标记值为真时，表示该线程是不重要的，或者说该线程只是用来等待客户端请求而不做任何其他事情。

要将一个线程设置为守护线程，需要在启动线程之前执行赋值语句`thread.daemon=True`。同样，要检查线程的守护状态，也只需要检查这个值即可。一个新的子线程会继承线程的守护标记。整个Python程序（主线程）将在所有非守护线程退出之后才退出。换句话说，就是没有剩下存活的非守护线程时。

> thread类

thread是threading模块中主要的执行对象，它有thread模块中许多没有的函数。

**thread对象数据属性**

| 属性   | 描述                             |
| ------ | -------------------------------- |
| name   | 线程名                           |
| ident  | 线程的标识符                     |
| daemon | 布尔标志，表示线程是否为守护线程 |

**thread对象方法**

| 属性                                                         | 描述                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| \__init__(self, group=None, target=None, name=None,args=(), kwargs=None, *, daemon=None) | 应始终使用关键字参数调用此构造函数。参数包括：组应为None；保留用于将来在ThreadGroup类。target是run()调用的可调用对象方法默认为None，表示不调用任何内容。name是线程名称。默认情况下，唯一名称由形式为“Thread-N”，其中N是小小数。args是目标调用的参数元组。默认值为()。kwargs是目标的关键字参数字典调用。默认值为｛｝。在对线程执行任何其他操作之前，请使用基类构造函数（Thread.\__init__()）。 |
| start()                                                      | 每个线程对象最多只能调用一次。它安排在单独的控制线程中调用对象的run()方法。如果在同一线程对象上多次调用此方法，则该方法将引发RuntimeError。 |
| run()                                                        | 表示线程活动的方法。可以在子类中重写此方法。标准run()方法调用传递给对象构造函数的可调用对象作为目标参数（如果有），并分别从args和kwargs参数中获取顺序参数和关键字参数。 |
| join(self, timeout=None)                                     | 等待线程终止。这将阻止调用线程，直到其join()方法被调用的线程终止——正常情况下或通过未处理的异常，或直到出现可选超时。当超时参数存在而不是None时，它应该是一个浮点数字，以秒（或其小数）为单位指定操作超时。由于join()总是返回None，因此必须在join()之后调用is_alive()来决定是否发生超时——如果线程仍然处于活动状态，则join()调用超时。当超时参数不存在或None时，操作将阻塞，直到线程终止。线程可以多次join()。如果试图加入当前线程，join()会引发RuntimeError，因为这会导致死锁。在线程启动之前join()也是一个错误，尝试这样做会引发相同的异常。 |
| name(self, name)                                             | 设置线程名                                                   |
| name(self)                                                   | 返回线程名                                                   |
| is_alive(self)                                               | 返回线程是否活动。此方法在run()方法开始之前返回True，直到run()结束。另请参见模块函数enumerate()。 |
| daemon(self)                                                 | 一个布尔值，指示此线程是否为守护程序线程。必须在调用start（）之前设置此值，否则会引发RuntimeError。它的初始值继承自创建线程；主线程不是守护进程线程，因此在主线程中创建的所有线程默认为daemon=False。当只剩下守护程序线程时，整个Python程序将退出。 |
| isDaemon(self)                                               | 返回此线程是否为守护进程。此方法已弃用，请改用守护程序属性。`thread.daemon` |

使用Thread类，可以有许多方法创建线程，介绍其中的三种：

1. 创建Thread的实例，传给它一个函数。
2. 创建Thread的实例，传给它一个可调用的类实例。
3. 派生Thread的子类，并创建子类的实例。

你会发现你讲选择第一个或者第三个方案。当你需要一个更加符合面向对象的接口时，会选择后者；否者会选择前者。第二种方案显得有些尴尬并且稍微难以理解。

**创建Thread的实例，传给它一个函数**

~~~Python
from time import sleep, ctime
import threading

loops = [2,4]

def loop(nloop, nsec):
    print('start loop', nloop, 'at:', ctime())
    sleep(nsec)
    print('loop', nloop, 'done at:', ctime())

def main():
    print('starting at:', ctime())
    threads = []
    nloops = range(len(loops))
    for i in nloops:
        t = threading.Thread(target=loop,args=(i,loops[i]))
        threads.append(t)
    for i in nloops:
        threads[i].start()
    for i in nloops:
        threads[i].join()
    print('all DONE at:', ctime())

main()
~~~

和之前相比，使用Thread模块时实现的锁没有了，取而代之的是一组Thread对象。当实例化每个Thread对象时，把函数（target）和参数（args）传进去，然后得到返回的Thread实例。实例化Thread（调用Thread()）和调用Thread.start_new_thread()的最大区别是新线程不会立即执行。

当所有线程都分配完以后，通过调用每个线程的start()方法让它们开始执行，而不是在这之前就会执行。相比于管理一组锁（分配、获取、释放、检查锁状态）而言，这里只需要为每个线程调用join()方法即可。join()方法将等待线程结束，或者在提供了超时时间的情况下，达到超时时间。使用join()方法要比等待释放锁的无限循环更加清晰（这也是这种锁又称为自旋锁的原因）。

对于join()方法而言，其另一个重要方面是其实它根本不需要调用，一旦线程启动，它们就会一直执行，直到给定的函数完成后退出。如果主线程还有其他事情要去做，而不是等待这些线程完成，就可以不调用join()。join()只有在你需要等待线程完成的时候才是有用的。

> 创建Thread的实例，传给它一个可调用的类实例

在创建线程时，与传入函数相似的一个方法是传入一个可调用的类的实例，用于线程执行————这种方法更加接近于面向对象的多线程，这种可调用的类包含一个执行环境，比起一个函数或者从一组函数中选择而言，有更好的灵活性。现在有了一个类对象，而不是仅仅是单个函数或者一个函数列表/元组。

~~~Python
from time import sleep, ctime
import threading

loops = [2,4]

class ThreadFunc(object):
    def __init__(self, func, args, name=''):
        self.name = name
        self.func = func
        self.args = args

    def __call__(self):
        self.func(*self.args) # 不定长参数：* 表示接受元组参数，** 接收字典类参数

def loop(nloop, nsec):
    print('start loop', nloop, 'at:', ctime())
    sleep(nsec)
    print('loop', nloop, 'done at:', ctime())

def main():
    print('starting at:', ctime())
    threads = []
    nloops = range(len(loops))
    for i in nloops:
        # t = threading.Thread(target=loop,args=(i,loops[i]))
        t = threading.Thread(target=ThreadFunc(loop, (i,loops[i]), loop.__name__))
        threads.append(t)
    for i in nloops:
        threads[i].start()
    for i in nloops:
        threads[i].join()
    print('all DONE at:', ctime())

main()
~~~

在此次修改中主要是添加了ThreadFunc类，并在实例化Thread对象时做了一点小改动，同时实例化了可调用类ThreadFunc。实际上，这里完成了两个实例化。这样改是希望这个类能够更加的通用，而不是局限于loop()函数，让这个类保存了函数的参数、函数自身以及函数名的字符串。而构造函数\_\_init\_\_()用于设定上述这些值。当创建线程时，Thread类的代码将调用ThreadFunc对象，此时会调用\_\_call\_\_()这个特殊方法。由于已经有了要用到的参数，这里就不需要再将其参数传递给Thread()的构造函数了，直接调用即可。

> 派生Thread的子类，并创建子类的实例

~~~Python
from time import sleep, ctime
import threading

loops = [2,4]

class MyThread(threading.Thread):
    def __init__(self, func, args, name=''):
        threading.Thread.__init__(self)
        self.name = name
        self.func = func
        self.args = args

    def run(self):
        self.func(*self.args) # *self.args表示接受元组参数，**kwargs接收字典类参数

def loop(nloop, nsec):
    print('start loop', nloop, 'at:', ctime())
    sleep(nsec)
    print('loop', nloop, 'done at:', ctime())

def main():
    print('starting at:', ctime())
    threads = []
    nloops = range(len(loops))
    for i in nloops:
        # t = threading.Thread(target=loop,args=(i,loops[i]))
        # t = threading.Thread(target=ThreadFunc(loop, (i,loops[i]), loop.__name__))
        t = MyThread(loop, (i,loops[i]), loop.__name__)
        threads.append(t)
    for i in nloops:
        threads[i].start()
    for i in nloops:
        threads[i].join()
    print('all DONE at:', ctime())

main()
~~~

注意：

1. MyThread子类的构造函数必须先调用其基类的构造方法。
2. 之前的特殊方法\_\_call\_\_()在这个子类中必须要写成run()。

现在将Mythread完善，成为一个独立的模块。

~~~Python
class MyThread(threading.Thread):
    def __init__(self, func, args, name=''):
        threading.Thread.__init__(self)
        self.name = name
        self.func = func
        self.args = args

    def getResult(self):
        return self.res

    def run(self):
        print('starting', self.name, 'at:', ctime())
        self.res = self.func(*self.args)
        print(self.res)
        print('finished at:', ctime())
~~~

### 多线程实践

> 同步原语

在多线程中会有一个重要的方面就是同步，一般在多线程的代码中，总会有一些特定的函数或者代码不希望被多个线程同时执行，通常包括修改数据库，更新文件或者其他会产生竞态条件的类似情况。当任意数量的线程可以通过时，就是使用同步的时候了。选择合适的原语，或者线程控制机制来执行同步。这里就使用两种类型的同步原语演示几个示例程序：锁/互斥，以及信号量。锁是所有机制中最简单的，最低级的机制。而信号量用于多线程竞争有限资源的情况。

> 锁

锁有两种状态：锁定和未锁定。而且它也支持两个函数：获得锁和释放锁。当多线程争夺锁时，允许第一个锁的线程进入临界区，并执行代码。所有之后到达的线程将被阻塞，直到第一个线程执行结束，退出临界区，释放锁。此时，其他等待的线程可以获得锁并进入临界区。不过那些别阻塞的线程是没有顺序的，胜出线程的选择是不确定的，而且还会根据Python实现的不同而有所区别。

~~~Python
from atexit import register
from random import randrange
from threading import Thread, current_thread
from time import sleep, ctime

# randrange(start, end)产生一个start~end范围内的随机整数，(randrange(2,5) for x in range(randrange(3,7))返回一个包含3~6个随机数的生成器对象，且随机数的范围为2~4
loops = (randrange(2,5) for x in range(randrange(3,7)))

# CleanOutputSet继承自set，重写__str__方法以改变print的输出样式
class CleanOutputSet(set):
    def __str__(self):
        # 字符串的join方法接收的参数类型为一个可迭代对象，生成器表达式(x for x in self)返回一个生成器对象，属于可迭代对象
        return ', '.join(x for x in self)

remaining = CleanOutputSet()

def loop(nsec):
    myname = current_thread().name
    remaining.add(myname)
    print('[%s] Started %s' %(ctime(), myname))
    sleep(nsec)
    remaining.remove(myname)
    print('[%s] Completed %s (%d secs)' %(ctime(), myname, nsec))
    print('(remaining: %s)' %(remaining or 'NONE'))

for pause in loops:
    Thread(target=loop, args=(pause,)).start()

# 使用atexit.register()来注册_atexit函数，解释器会在脚本退出前执行该函数，这里使用了装饰器的方式
@register
def _atexit():
    print ('all DONE at:',ctime())
~~~

正常的输出应该是根据程序的执行顺序来打印相关输出语句，但是实际情况是

~~~shell
[Mon Feb 13 15:07:14 2023] Started Thread-1 (loop)
[Mon Feb 13 15:07:14 2023] Started Thread-2 (loop)
[Mon Feb 13 15:07:14 2023] Started Thread-3 (loop)
[Mon Feb 13 15:07:14 2023] Started Thread-4 (loop)
[Mon Feb 13 15:07:16 2023] Completed Thread-2 (loop) (2 secs)
[Mon Feb 13 15:07:16 2023] Completed Thread-1 (loop) (2 secs)
(remaining: Thread-4 (loop), Thread-3 (loop))
(remaining: Thread-4 (loop), Thread-3 (loop))
[Mon Feb 13 15:07:16 2023] Completed Thread-4 (loop) (2 secs)
(remaining: Thread-3 (loop))
[Mon Feb 13 15:07:17 2023] Completed Thread-3 (loop) (3 secs)
(remaining: NONE)
all DONE at: Mon Feb 13 15:07:17 2023
~~~

我们发现输出存在部分混乱的情况（多个线程可能并行执行IO），还有就是两个线程修改同一个变量（剩余线程名集合）。IO和访问相同的数据结构都属于临界区，因此需要引入锁防止多个线程同时进入临界区。

~~~Python
from atexit import register
from random import randrange
from threading import Thread, current_thread, Lock
from time import sleep, ctime

lock = Lock()
loops = (randrange(2,5) for x in range(randrange(3,7)))

class CleanOutputSet(set):
    def __str__(self):
        return ', '.join(x for x in self)

remaining = CleanOutputSet()

def loop(nsec):
    myname = current_thread().name
    lock.acquire()
    remaining.add(myname)
    print('[%s] Started %s' %(ctime(), myname))
    lock.release()
    sleep(nsec)
    lock.acquire()
    remaining.remove(myname)
    print('[%s] Completed %s (%d secs)' %(ctime(), myname, nsec))
    print('(remaining: %s)' %(remaining or 'NONE'))
    lock.release()

for pause in loops:
    Thread(target=loop, args=(pause,)).start()

@register
def _atexit():
    print ('all DONE at:',ctime())
~~~

现在应该使用刚创建的这个锁，代码中突出显示的acquire()和()调用就是应当在loop()函数中添加的语句。再次运行就不会出现混乱的情况了

~~~shell
[Mon Feb 13 15:12:26 2023] Started Thread-1 (loop)
[Mon Feb 13 15:12:26 2023] Started Thread-2 (loop)
[Mon Feb 13 15:12:26 2023] Started Thread-3 (loop)
[Mon Feb 13 15:12:26 2023] Started Thread-4 (loop)
[Mon Feb 13 15:12:26 2023] Started Thread-5 (loop)
[Mon Feb 13 15:12:26 2023] Started Thread-6 (loop)
[Mon Feb 13 15:12:28 2023] Completed Thread-2 (loop) (2 secs)
(remaining: Thread-6 (loop), Thread-4 (loop), Thread-1 (loop), Thread-3 (loop), Thread-5 (loop))
[Mon Feb 13 15:12:29 2023] Completed Thread-3 (loop) (3 secs)
(remaining: Thread-6 (loop), Thread-4 (loop), Thread-1 (loop), Thread-5 (loop))
[Mon Feb 13 15:12:29 2023] Completed Thread-5 (loop) (3 secs)
(remaining: Thread-6 (loop), Thread-4 (loop), Thread-1 (loop))
[Mon Feb 13 15:12:29 2023] Completed Thread-1 (loop) (3 secs)
(remaining: Thread-6 (loop), Thread-4 (loop))
[Mon Feb 13 15:12:29 2023] Completed Thread-6 (loop) (3 secs)
(remaining: Thread-4 (loop))
[Mon Feb 13 15:12:30 2023] Completed Thread-4 (loop) (4 secs)
(remaining: NONE)
all DONE at: Mon Feb 13 15:12:30 2023
~~~

> 信号量

如前所示，锁非常易于理解和实，也很容易决定何时需要他们。然而，如果情况更加复杂，可能需要一个更加强大的同步原语来代替锁。对于拥有有限资源的应用来说，使用信号量可能是也不错的选择。

信号量是最古老的同步原语之一。它是一个计数器，当资源消耗时递减，当资源释放时递减，信号量可以代表它们的资源可用或不可用。消耗资源使计数器递减的操作习惯上称为P()，也称为wait、try、pend或procure。相对地，当一个线程对一个资源完成操作时，该资源需要返回资源池中。这个操作一般称为V()，也称为signal、increment、release、post、vacate。Python建好了所有的命名，使用和锁的函数/方法一样的名字：acquire和release。信号量比锁更加灵活，因为可以有多个线程，每个线程拥有有限资源的一个实例。

下面的例子中，我们将模拟一个简化的糖果机。这个特制的机器只有5个可用的槽来保持库存，如果槽都满了，糖果就不能再加入这个机器中了；相似的，如果每个槽都空了，想购买的消费者就无法买到糖果了。我们可以使用信号量来追踪这些有限的资源。

~~~Python
from atexit import register
from random import randrange
from threading import BoundedSemaphore, Lock, Thread
from time import sleep, ctime

lock = Lock()
MAX = 5
candytray = BoundedSemaphore(MAX)

#向库存中添加糖果。这段代码是一个临界区，输出用户的行动，并在糖果超过最大库存的时候给出警告
def refill():
    lock.acquire()
    print('Refilling candy...')
    try:
        candytray.release()
    except ValueError:
        print('full, skipping')
    else:
        print('OK')
    lock.release()

#购买糖果。也是一个临界区，效果和refill函数相反
def buy():
    lock.acquire()
    print('Buying candy...')
    #检查是否所有的资源都已经消费完。
    #计数器的值不能小于0，所以这个调用一般会在计数器再次增加之前被阻塞。传入非阻塞标志False，让调用不再阻塞，而在应当阻塞的时候返回一个false,表示没有更多资源了。
    if candytray.acquire(False):
        print('OK')
    else:
        print('empty,skipping')
    lock.release()

#模拟糖果机的所有者
def producer(loops):
    for i in range(loops):
        refill()
        sleep(randrange(3))

#模拟消费者
def consumer(loops):
    for i in range(loops):
        buy()
        sleep(randrange(3))

def _main():
    print('starting at:', ctime())
    nloops = randrange(2,6)
    print('THE CANDY MACHINE (full with %d bars)!' %MAX)
    #其中消费者线程中，增加了额外的操作，用于随机给出正偏差，使得消费者真正消费的糖果数可能会比供应者放入机器的更多；否则代码永远不会进入消费者尝试从空机器购买糖果的情况
    Thread(target=consumer,args=(randrange(nloops,nloops+MAX+2),)).start()
    Thread(target=producer,args=(nloops,)).start()

@register
def _atexit():
    print('all DONE at:', ctime())

if __name__ == '__main__':
    _main()
~~~

产生结果：

~~~Shell
starting at: Mon Feb 13 16:04:25 2023
THE CANDY MACHINE (full with 5 bars)!
Buying candy...
OK
Buying candy...
OK
Refilling candy...
OK
Refilling candy...
OK
Buying candy...
OK
Buying candy...
OK
Refilling candy...
OK
Buying candy...
OK
Buying candy...
OK
all DONE at: Mon Feb 13 16:04:29 2023
~~~

### 生产者和消费者问题和Queue/queue模块

最后一个例子演示了生产者-消费者模型的场景。在这个场景下，商品或者服务的生产者生产商品，然后将其放到类似队列的数据结构中。生产商品的时间是不确定的，同样消费者消费生产者生产的商品的时间也不是确定的。

使用Queue（Python2.x版本，在Python3.x版本中重命名为queue）来提供线程间通信的机制，从而让线程之间可以互相分享数据。具体而言，就是创建一个队列，让生产者（线程）在其中放入新的商品，而消费者（线程）消费这些商品。

**Queue/queue模块的类**

| 类                       | 描述                                                         |
| ------------------------ | ------------------------------------------------------------ |
| Queue(maxsize=0)         | 创建一个先入先出队列。如果给定最大值，则在队列没有空间时阻塞；否者，为无限队列 |
| LifoQueue(maxsize=0)     | 创建一个先入先出队列。如果给定最大值，则在队列没有空间时阻塞；否者，为无限队列 |
| PriorityQueue(maxsize=0) | 创建一个先入先出队列。如果给定最大值，则在队列没有空间时阻塞；否者，为无限队列 |

**Queue/queue的异常**

| 异常  | 描述                                   |
| ----- | -------------------------------------- |
| Empty | 当对空队列调用get*()方法时抛出异常     |
| Full  | 当对已满的队列调用put*()方法时抛出异常 |

**Queue/queue对象方法**

| 方法                              | 描述                                                         |
| --------------------------------- | ------------------------------------------------------------ |
| qsize()                           | 返回队列大小（由于返回时队列大小可能被其他线程修改，所以该值为近似值） |
| empty()                           | 当队列为空，则返回True；否者，返回False                      |
| full()                            | 当队列已满，则返回True；否者，返回False                      |
| put(item,block=Ture,timeout=None) | 将item放入队列中。如果block为True且timeout为None，则在有可用空间之前阻塞；如果timeout为正值，则最多阻塞timeout秒，如果block为False，则抛出异常 |
| put_nowait()                      | 和put(item,False)相同                                        |
| get(block=Ture,timeout=None)      | 从队列中取得元素。如果给定了block(非0)，则一直阻塞到有可用的元素为止 |
| get_nowait()                      | 和get(False)相同                                             |
| task_done()                       | 用于表示队列中的某个元素已执行完成，该方法会被下面的join()使用 |
| join()                            | 在队列中所有元素执行完毕并调用上面的task_done()信号之前，保持阻塞 |

实例：

~~~Python
from random import randint
from time import sleep
from queue import Queue
from threading import Thread

def writeQ(queue):
    print('prodecing object for Q...')
    queue.put('XXX',1)
    print('size now', queue.qsize())

def readQ(queue):
    val = queue.get(1)
    print('consumed object from Q... size now', queue.qsize())

def writer(queue,loops):
    for i in range(loops):
        writeQ(queue)
        sleep(randint(1,3))

def reader(queue,loops):
    for i in range(loops):
        readQ(queue)
        sleep(randint(1,9))
        
funcs = [writer, reader]
nfuncs = range(len(funcs))

def main():
    nloops = randint(2,5)
    q = Queue(32)
    threads = []
    for i in nfuncs:
        t = Thread(target=funcs[i],args=(q,nloops))
        threads.append(t)
    for i in nfuncs:
        threads[i].start()
    for i in nfuncs:
        threads[i].join()
    print('all DONE')

if __name__ == '__main__':
    main()
~~~

结果：

~~~Shell
prodecing object for Q...
size now 1
consumed object from Q... size now 0
prodecing object for Q...
size now 1
prodecing object for Q...
size now 2
consumed object from Q... size now 1
prodecing object for Q...
size now 2
consumed object from Q... size now 1
prodecing object for Q...
size now 2
consumed object from Q... size now 1
consumed object from Q... size now 0
all DONE
~~~

writeQ()和readQ()函数分别用于讲一个对象放入队列中和消费队列中的一个对象。writer()将作为单个线程运行，其中的只有一个：向队列中放入一个对象，等待片刻，然后重复上述步骤，直至达到每次脚本执行时随机产生的次数为止。reader()与之类似，只不过变成了消耗对象。writer睡眠的随机秒数通常比reader的要短。这是为了阻碍reader从空队列中获取对象。通过给writer一个更短的等候时间，使得轮到reader时，已存在可消费对象的可能性更大。

## 数据库编程

### DB-API

DB-API是阐明一些列所需对象和数据库访问机制的标准。它可以为不同的数据库适配器和底层数据库系统提供一致性的访问。就像很多基于社区的成果一样。DB-API也是强需求驱动的。

在过去的日子里，曾经有这样一种场景：有很多种数据库，并且很多人实现了他们自己的数据库适配器。就像做无用功一样。这些数据库和适配器是在不同的时间被不同的人实现的，在功能上完全没有一致性可言。但是，这意味着使用这些接口的应用代码需要与他们选择使用的数据库模块进行定制化处理，接口的任何改变都会导致应用代码的变更。

由此，为了解决Python数据库连接问题特殊兴趣小组成立了，并且撰写了1.0版本的DB-API。该API为不同的关系数据库提供了一致性的接口，并且使不同数据库间移植代码变得更加简单，通常只需要修改几行代码即可。

> 模块属性

DB-API标准要求必须提供下文列出的功能和属性。一个兼容DB-API的模块必须定义表中所示的几个全局属性。

| 属性         | 描述                    |
| ------------ | ----------------------- |
| apilevel     | 需要适配器兼容的DB-API  |
| threadsafety | 本模块的线程安全级别    |
| paramstyle   | 本模块的SQL语句参数风格 |
| connect()    | Connect()函数           |
| 多种异常     | 见下表                  |

**数据类型**

`apilevel`

该字符串（注意，不是浮点型）指明了模块需要兼容的DB-API最高版本。

`threadsafety`

这是个整型值，可选值如下：

- 0：不支持线程安全。线程间不能共享模块。
- 1：最小化线程安全支持：线程间可以共享模块，但是不能共享连接。
- 2：适度的线程安全支持：线程间可以共享模块和连接，但是不能共享游标。
- 3：完全的线程安全支持：线程间可以共享模块、信号和游标。

如果有资源需要进行共享，那么就需要诸如自旋锁、信号量之类的同步原语来达到原子锁定的目的。由于此目的，磁盘文件和全局变量都不可靠，甚至还会干扰到标准的互斥操作。

**参数风格**

DB-API支持以不同的方式指明如何将参数与SQL语句进行整合，并最终传递给服务器中执行。该参数是一个字符串，用于指定构建查询行或命令时使用的字符串替代形式。

| 参数风格 | 描述                       | 示例                |
| -------- | -------------------------- | ------------------- |
| numeric  | 数值位置风格               | WHERE name=:1       |
| nameed   | 命名风格                   | WHERE name=:name    |
| pyformat | Python字典printf()格式转换 | WHERE name=%(name)s |
| qmark    | 问号风格                   | WHERE name=?        |
| format   | ANSIC的printf()格式转换    | WHERE name=%s       |

**函数属性**

connect()函数通过Connection对象访问数据库。兼容模块必须实现connect()函数，改函数创建并返回一个Connection对象。可以使用包含多个参数的字符串（DSN）来传递数据库连接信息，也可以按照位置传递每一个参数，或者是使用关键字参数的形式传入。

| 参数     | 描述     |
| -------- | -------- |
| user     | 用户名   |
| password | 密码     |
| host     | 主机名   |
| database | 数据库名 |
| dsn      | 数据源名 |

使用DSN还是独立参数主要基于所连接的系统。比如，如果你使用的是像ODBC或者JDBC的API，则需要使用DSN；如果直接使用数据库，则更倾向已使用独立的登录参数。另一个使用独立参数的原因是很多数据库适配器并没有实现对DSN的支持。需要注意的是，并不是所以的适配器都会严格按照标准实现，比如MySQLdb使用了db而不是database。

**异常**

| 异常              | 描述                       |
| ----------------- | -------------------------- |
| Warning           | 警告异常基类               |
| Error             | 错误异常基类               |
| InterfaceError    | 数据库接口（非数据库）错误 |
| DatabaseError     | 数据库错误                 |
| DataError         | 处理数据时出现问题         |
| OperationlError   | 数据库执行期间出现错误     |
| IntegrityError    | 数据库关系完整性错误       |
| InternalError     | 数据库内部错误             |
| ProgrammingError  | SQL命令执行失败            |
| NotSupportedError | 出现不支持的操作           |

> connection对象

应用于数据库之间进行通信需要建立数据库连接，它是最基本的机制，只有通过数据库连接才能把命令传递到服务器，并得到返回的结果。当一个连接（或者一个连接池）建立后，可以创建一个游标，向数据库发送请求，然后从数据库中接收回应。

**Connection对象方法**

| 方法名                              | 描述                                           |
| ----------------------------------- | ---------------------------------------------- |
| close()                             | 关闭数据库连接                                 |
| commit()                            | 提交当前事务                                   |
| rollback()                          | 取消当前事务                                   |
| cursor()                            | 使用该连接创建（并返回）一个游标或类游标的对象 |
| errorhandler(cxn,cur,errcls,errval) | 作为给定连接的游标的处理程序                   |

当使用close()时，这个连接将不能在使用，否者会进入到异常处理中。

如果数据库不支持事务处理，或启用了自动提交功能，commit()方法都将无法使用。如果你愿意，可以实现单独的方法用来启动或者关闭自动提交功能。因为本方法是DB-API中的一部分，所以对于不支持事务处理的数据库而言，只需要在方法实现“pass”即可。

和commit()相似，rollback()方法也只有在支持事务处理的数据库中才有用。发生异常之后，rollback()会将数据库的状态恢复到事务处理开始时。

如果RDBMS不支持游标，那么cursor()仍然会返回一个尽可能模仿真实游标的对象。这是最基本的要求。每个适配器开发者都可以为他的接口或数据库专门添加特殊属性。

DB-API建议适配器开发者为连接编写所有的数据库模块异常，但并没有做强制要求。如果没有，则认为Connection对象将会抛出对应模块级别的异常，当完成数据库连接并关闭游标时，需要对所有操作执行commit()，并对你的连接执行close()。

> Cursor对象

当建立连接后，就可以和数据库进行通信了，游标可以让用户提交数据库命令，并获得查询的结果行。Python DB-API游标对象总能提供游标的功能，即使是哪些不支持游标的数据库。此时，如果你创建了一个数据库适配器，还必须要实现cursor对象，以扮演类似游标的角色。这样，无论你将数据库系统切换到支持游标的数据库还是不支持游标的数据库，都能保持Python代码的一致性。

当游标创建好后，就可以执行查询或命令，并从结果集中取回一行或多行。游标对象最重要的属性是execute\*()和fetch\*()方法，所有针对数据库的服务请求都是通过它们执行的。arraysize数据属性在为fetchmany()设置默认大小时非常有用。当然，在不需要时关闭游标是个好主意，而如果你对数据库支持存储过程，可能会用到callproc()。

**Cursor对象属性**

| 对象属性                           | 描述                                                         |
| ---------------------------------- | ------------------------------------------------------------ |
| arraysize                          | 使用fetchmany()方法时，一次取出的结果行数，默认为1           |
| connection                         | 创建此游标的连接（可选）                                     |
| description                        | 返回游标活动状态（7项元组）：（name，type_code，display_size，internal_size，precision，scale，null_ok），只有name和type_code是必需的 |
| lastrowid                          | 上次修改行的行ID（可选；如果不支持行ID，则返回None）         |
| rowcount                           | 上次execute方法处理或者影响的行数                            |
| callproc(func[,args])              | 调用存储过程                                                 |
| close()                            | 关闭游标                                                     |
| execute(op[,args])                 | 执行数据库查询或者命令                                       |
| executemany(op,args)               | 类似execute()和map()的结合，为给定的所有参数准备并执行数据库查询或者命令 |
| fetchone()                         | 获取查询结果的下一行                                         |
| fetchmany([size=cursor.arraysize]) | 获取查询结果的下面size行                                     |
| fetchall()                         | 获取查询结果的所有（剩余）行                                 |
| \_\_iter\_\_()                     | 为游标创建迭代器（可选，参考next()）                         |
| messages                           | 游标执行后从数据库中获取的消息列表（元组集合，可选）         |
| next()                             | 被迭代器用于获取查询结果的下一行（可选，类似fetchone()）     |
| nextset()                          | 移动到下一个结果集合（如果支持）                             |
| nextnumber                         | 当前结果集中游标的索引（以行为单位，从0开始，可选）          |
| setinputsizes(sizes)               | 设置允许的最大输入大小（必须有，但是实现是可选的）           |
| setoutputsize(size[,col])          | 设置大列获取的最大缓冲区大小（必须有，但是实现是可选的）     |

> 类型对象和构造函数

通常，两个不同系统间的接口是最脆弱的。比如在Python对象和C类型中进行转换就是这样的。类似地，在Python对象和原生数据库对象间也存在这问题。作为一个使用Python的DB-API的程序员，虽然你传递给数据库的参数是字符串，但是数据库可能需要将其转换为多种不同的类型，从而乐于对任何特定查询都能给出正确的数据类型。例如，一个Python字符串是应该转换成VARCHAR、TEXT、BLOB，还是原生BINARY对象，亦或是DATE或者TIME对象呢？为数据库提供期望格式的输入必须非常小心。因此，DB-API的另一个需求是创建构造函数，从而构建可以简单转换成适当数据库对象的特殊对象。SQL的NULL值对应于Python的NULL对象None。

| 类型对象                       | 描述                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| Date(yr,mo,dy)                 | 日期对象                                                     |
| Time(hr,min,sec)               | 时间对象                                                     |
| Timestamp(yr,mo,dy,hr,min,sec) | 时间戳对象                                                   |
| DateFromTicks(ticks)           | 日期对象，给出从新纪元时间(1970年1月1日00:00:00UTC)以来的秒数 |
| TimeFromTicks(ticks)           | 时间对象，给出从新纪元时间(1970年1月1日00:00:00UTC)以来的秒数 |
| TimestampFromTicks(ticks)      | 时间戳对象，给出从新纪元时间(1970年1月1日00:00:00UTC)以来的秒数 |
| Binary(string)                 | 对应二进制（长）字符串对象                                   |
| STRING                         | 表示基于字符串列的对象，比如VARCHAR                          |
| BINARY                         | 表示（长）二进制的对象，比如RAW、BLOB                        |
| NUMBER                         | 表示数值列的对象                                             |
| DATETIME                       | 表示日期/时间列的对象                                        |
| ROWID                          | 表示“行ID”列的对象                                           |

> 数据库和Python：适配器

对于每种支持的数据库，Python都有一个或者多个适配器用于连接Python中的目标数据库系统。挑选标准可能包括：它的性能如何，它的文档或者网站是否有用，是否有一个活跃的社区，驱动的质量和稳定性如何等。需要记住的是，大多数适配器只提供给你连接数据库的基本需求，所以你还需要寻找一些额外的特性。请记住，你需要负责编写更高级别的代码，比如线程管理和数据库连接池管理等。

现在看几个使用适配器模块与关系数据库进行通信的例子，真正的密码在于建立连接。一旦建立连接，并使用DB-API的对象、属性和对象方法，你的核心代码就会看起来很相似，而无须去管它使用了哪个适配器以及RDBMS。

> 使用数据库适配器示例

本例使用的是mysql数据库，使用的适配器是MySQLdb，在Python3中需要下载PyMySQL

~~~Shell
pip install PyMySQL
~~~

**创建删除数据库**

~~~Python
import pymysql
pymysql.install_as_MySQLdb()
cxn = pymysql.connect(host='127.0.0.1', port=3306, user='root', password='123456')
cxn.query('DROP DATABASE test')
cxn.query('CREATE DATABASE test')
cxn.commit()
cxn.close()
~~~

**创建表**

在上面的代码中，并没有使用游标，一些适配器有Connection对象，这些对象可以使用query()方法执行SQL查询，不过不是所有的适配器都能这样。因此，建议或者不要使用这个方法，或者事先检查适配器中该方法是否可用。

~~~Python
import pymysql
pymysql.install_as_MySQLdb()
cxn = pymysql.connect(host='127.0.0.1', port=3306, user='root', password='123456', db='test')
cur = cxn.cursor() # 使用游标
cur.execute('CREATE TABLE users(login VARCHAR(8),userid INT)')
cur.close()
cxn.commit()
cxn.close()
~~~

**添加查询数据**

~~~Python
import pymysql
pymysql.install_as_MySQLdb()
cxn = pymysql.connect(host='127.0.0.1', port=3306, user='root', password='123456', db='test')
cur = cxn.cursor()
cur.execute("INSERT INTO users VALUES('john',7000)")
cur.execute("INSERT INTO users VALUES('jane',7001)")
cur.execute("INSERT INTO users VALUES('bob',7200)")
cur.execute("SELECT * FROM users WHERE login LIKE 'j%'")
for data in cur.fetchall():
    print('%s\t%s' % data) # john    7000  jane    7001
cur.close()
cxn.commit()
cxn.close()
~~~

**更新删除数据**

~~~Python
import pymysql
pymysql.install_as_MySQLdb()
cxn = pymysql.connect(host='127.0.0.1', port=3306, user='root', password='123456', db='test')
cur = cxn.cursor()
cur.execute("UPDATE users SET userid=7100 WHERE userid=7001")
cur.execute("SELECT * FROM users")
for data in cur.fetchall():
    print('%s\t%s' % data)
cur.execute("DELETE FROM users WHERE login='bob'")
cur.execute('DROP TABLE users')
cur.close()
cxn.commit()
cxn.close()
~~~

### ORM

正如前面章节所看到的，先有很多不同的数据库系统，并且其中的大部分系统都包含Python接口，能够使你更好地利用它们的功能。而这些系统唯一的缺点是需要你了解SQL。如果你是一个更愿意操纵Python对象而不是SQL查询的程序员，并且仍然希望使用关系数据库作为你的数据后端，那么你可能更倾向于使用ORM（对象模型与数据库表的映射）。

这些ORM系统的作者将纯SQL语句进行了抽象化处理，将其实现为Python中的对象，这样你只操纵这些对象就能完成与生成SQL语句相同的任务。一些系统也允许一定的灵活性，可以让你执行几行SQL语句，但是大多数情况下，都应该避免普通的SQL语句。

数据库表被神奇地转化为Python类，其中的数据列作为属性，而数据操作则会为方法，让你调应用支持ORM与标准数据库适配器有些相似。由于ORM需要代替你执行很多工作，因此一些事情变得更加复杂，或者需要比直接使用适配器更多的代码行。

目前最有名的Python ORM是SQLAlchemy和SQlObject。由于版本是Python3，将会以SQLAlchemy为例子。

>SQLAlchemy

**Python3安装SQLAlchemy**

SQLAlchemy是Python编程语言下的一款ORM框架，该框架建立在数据库API之上，使用关系对象映射进行数据库操作，简言之便是：将对象转换成SQL，然后使用数据API执行SQL并获取执行结果。SQLAchemy 本身无法操作数据库，其本质上是依赖pymysql.MySQLdb,mssql等第三方插件。

~~~Python
pip install sqlalchemy
~~~

**连接数据库**

连接数据库使用create_engine():

~~~Shell
MySQL-Python
    mysql+mysqldb://<user>:<password>@<host>[:<port>]/<dbname>
 
pymysql
    mysql+pymysql://<username>:<password>@<host>/<dbname>[?<options>]
 
MySQL-Connector
    mysql+mysqlconnector://<user>:<password>@<host>[:<port>]/<dbname>
 
cx_Oracle
    oracle+cx_oracle://user:pass@host:port/dbname[?key=value&key=value...]
~~~

**用SQLAlchemy执行原生SQL**，该写法只适用于2.0版本以上

~~~Python
from sqlalchemy import create_engine, text
#链接数据库
engine = create_engine('mysql+pymysql://root:123456@127.0.0.1:3306/test')
conn = engine.connect()
#创建表
conn.execute(text('create table test(id int,name varchar(48),salary int not null)'))
#插入表数据
conn.execute(text("insert into test(id,name,salary) values(1,'zs',88888)"))
#查看数据
result = conn.execute(text('select * from test'))
print(result.fetchall())
~~~

**使用原生sql语句的缺点**

1. SQL语句重复利用率不高，越复杂的SQL语句条件越多，代码越长，会出现很多相近的SQL语句。
2. 大型的项目是在业务逻辑中拼接出来的，如果数据库需要更改，就要去修改这些逻辑，这会很容易漏掉对某些SQL语句的修改。
3. 写SQL时容易忽略web安全问题，造成隐患。

**SQLAlchemy的优势**

- 易用性：使用ORM做数据库开发可以有效减少重复SQL语句的概率，写出来的模型也更加直观、清晰
- 性能损耗小：任何操作都要通过ORM转化，确实会损耗性能，但综合考虑开发效率、代码阅读性，带来的好处远大于性能损耗，而且项目越大作用越明显。
- 设计灵活：可以轻松的写出复杂的查询
- 可移植：SQLAlchemy封装了底层的数据库实现，支持多个关系数据库引擎，可以非常轻松的切换数据库

**定义ROM模型映射到数据库中**

**步骤：**

1. 用**declarative_base**根据**engine**创建一个**ORM基类**。
2. 用这个**Base**类作为基类来写自己的ORM类。要定义`__tablename__`类属性，来指定这个模型映射到数据库中的表名。
3. 创建属性来映射到表中的字段，所有需要映射到表中的属性都应该为**Column类型**
4. 使用`Base.metadata.create_all()`来将模型映射到数据库中。

**注意：**

使用create_all函数创建的表映射到数据库之后，即使改变了模型的字段，也不会重新映射了。

解决方法：每次运行时，先把之前的表全部删除之后，在创建新的表。

~~~Python
from sqlalchemy import Column, Integer, String, ForeignKey, UniqueConstraint, Index
from sqlalchemy.orm import sessionmaker, relationship, declarative_base
from sqlalchemy import create_engine
#链接数据库
engine = create_engine('mysql+pymysql://root:123456@127.0.0.1:3306/test')
# 创建对象的基类
Base = declarative_base()
# 创建单表
class Person(Base):
    __tablename__='person'
    id = Column(Integer, primary_key=True) #主键 autoincrement=True 自增
    name =  Column(String(32))
    certno = Column(String(16))
    age = Column(Integer)
    country = Column(String(32))
    # __table_args__ = (
    #     Index('ix_id_name','name','certno','country'), #索引
    # )
#定义初始化数据库函数
def init_db():
    Base.metadata.create_all(engine) 

#顶固删除数据库函数
def drop_db():
    Base.metadata.drop_all(engine)

init_db()
# drop_db()
~~~

**对数据的增删改查操作（crud→增删改查）**

**步骤：**

1. 构建session对象，所有的所有和数据库的ORM操作都必须通过一个叫做`session`的会话对象来实现
2. 对表添加数据**{add(),add_all([])}**
3. 查询表中数据
   1. 全表查询 查找某个模型对应的那个表中所有的数据
      all_person = session.query(Person).all()
   2. 条件查询 filter_by
      all_person = session.query(Person).filter_by(name='momo1').all()
   3. 条件查询 filter
      all_person = session.query(Person).filter(Person.name=='momo1').all()
   4. 条件查询 get方法是根据id来查找的，只会返回一条数据或者None
      person = session.query(Person).get(primary_key)
   5. 条件查询 使用first方法获取结果集中的第一条数据
      person = session.query(Person).first()

1. 修改对象
   首先从数据库中**查找对象**，然后将这条数据**修改**为你想要的数据，最后做**commit**操作就可以修改数据了
2. 删除对象
   将需要删除的数据从数据库中**查找出来**，然后使用**session.delete**方法将这条数据从session中删除，最后做**commit**操作就可以了。

~~~Python
from sqlalchemy import Column, Integer, String, ForeignKey, UniqueConstraint, Index
from sqlalchemy.orm import sessionmaker, relationship, declarative_base
from sqlalchemy import create_engine
#链接数据库
engine = create_engine('mysql+pymysql://root:123456@127.0.0.1:3306/test')
# 创建对象的基类
Base = declarative_base()
# 创建单表
class Person(Base):
    __tablename__='person'
    id = Column(Integer, primary_key=True) #主键 autoincrement=True 自增
    name =  Column(String(32))
    certno = Column(String(20))
    age = Column(Integer)
    country = Column(String(32))
    # __table_args__ = (
    #     Index('ix_id_name','name','certno','country'), #索引
    # )
#定义初始化数据库函数
def init_db():
    Base.metadata.create_all(engine) 

#顶固删除数据库函数
def drop_db():
    Base.metadata.drop_all(engine)

# 新增
def insert():
    # 单条
    p1 = Person(name='zhangsan',certno='493028427438296572', age=17, country='China')
    session.add(p1)
    session.commit()
    # 多条
    p2 = Person(name='jack',certno='104924837205737753', age=20, country='USA')
    p3 = Person(name='Alice',certno='103244582949002342', age=17, country='England')
    session.add_all([p2,p3])
    session.commit()

# 查询
def select():
    # 查询全表
    p1 = session.query(Person).all()
    for p in p1:
        print("查询全表：主键：%s 名称：%s 年龄：%d 国籍：%s" % (p.id, p.name, p.age, p.country))
    # 条件查询 filter_by filter_by只能用=
    p2 = session.query(Person).filter_by(name = 'zhangsan').all()
    for p in p2:
        print("条件查询filter_by: 主键：%s 名称：%s 年龄：%d 国籍：%s" % (p.id, p.name, p.age, p.country))
    # 条件查询 filter
    p3 = session.query(Person).filter(Person.name == 'zhangsan').all()
    for p in p3:
        print("条件查询filter: 主键：%s 名称：%s 年龄：%d 国籍：%s" % (p.id, p.name, p.age, p.country))
    # 条件查询 get 根据主键查询
    p4 = session.get(Person,2)
    print("条件查询get: 主键：%s 名称：%s 年龄：%d 国籍：%s" % (p4.id, p4.name, p4.age, p4.country))
    # 条件查询 first
    p5 = session.query(Person).first()
    print("条件查询first: 主键：%s 名称：%s 年龄：%d 国籍：%s" % (p5.id, p.name, p5.age, p5.country))

# 修改
def update():
    p = session.query(Person).filter(Person.name == 'zhangsan').one()
    print("修改数据为 主键：%s 名称：%s 年龄：%d 国籍：%s" % (p.id, p.name, p.age, p.country))
    p.name = 'hahahaha'
    session.commit()
    p = session.get(Person,p.id)
    print("修改结果为 主键：%s 名称：%s 年龄：%d 国籍：%s" % (p.id, p.name, p.age, p.country))

# 删除
def delect():
    p = session.get(Person,3)
    print("删除数据为 主键：%s 名称：%s 年龄：%d 国籍：%s" % (p.id, p.name, p.age, p.country))
    session.delete(p)
    session.commit()

# init_db()
# drop_db()

# Session = sessionmaker(engine)
# session = Session()
#下一行代码相当于上两行
session = sessionmaker(engine)()
# insert()
# select()
# update()
# delect()
~~~

**sqlalchemy常用数据类型**

1. **Integer**：整型，映射到数据库中是**int**类型。
2. **Float**：浮点类型，映射到数据库中是**float**类型。他占据的32位。
   浮点类型，有可能会造成精度丢失，特别是在money方面，不可原谅。
3. Double（**SQLAlchemy中没有，代替品为DECIMAL**）：双精度浮点类型，映射到数据库中是double类型，占据64位
4. **String**：可变字符类型，映射到数据库中是**varchar**类型.
5. **Boolean**：布尔类型，映射到数据库中的是**tinyint**类型。
6. **DECIMAL**：定点类型。是专门为了**解决浮点类型精度丢失**的问题的。在存储money相关的字段的时候建议大家都使用这个数据类型。并且这个类型使用的时候需要传递两个参数，**第一个参数是用来标记这个字段总能能存储多少个数字**，**第二个参数表示小数点后有多少位**。
7. **Enum**：枚举类型。指定某个字段只能是枚举中指定的几个值，不能为其他值。在ORM模型中，使用**Enum**来作为枚举。
8. **Date**：存储时间，只能**存储年月日**。映射到数据库中是date类型。在Python代码中，可以使用`datetime.date`来指定。
9. **DateTime**：存储时间，可以**存储年月日时分秒毫秒等**。映射到数据库中也是datetime类型。在Python代码中，可以使用`datetime.datetime`来指定。
10. **Time**：存储时间，可以**存储时分秒**。映射到数据库中也是time类型。在Python代码中，可以使用`datetime.time`来指定
    ps：注意区分Date/DateTime/Time的储存信息！！！
11. **Text**：存储长字符串。一般可以存储**6W**多个字符
12. **LONGTEXT**：长文本类型，映射到数据库中是longtext类型（**不过这个只有mysql有，orcale没有**）

**其他查询用法**

~~~Python
# 且的关系
    person = session.query(Person).filter(Person.id > 1, Person.name == 'Alice').all()
    person = session.query(Person).filter(Person.id.between(1,3), Person.name == 'Alice').all()
    person = session.query(Person).filter(Person.id.in_([1,3,4])).all()
    # 非的关系
    person = session.query(Person).filter(~Person.id.in_([1,3,4])).all()
    # 条件嵌套
    person = session.query(Person).filter(Person.id.in_(session.query(Person.id).filter_by(name='jack'))).all()
    # 且和或的关系
    from sqlalchemy import and_, or_
    person = session.query(Person).filter(or_(Person.id > 1, Person.name == 'Alice')).all()
    # 通配符
    person = session.query(Person).filter(Person.name.like('A%')).all()
    person = session.query(Person).filter(~Person.name.like('A%')).all()
    # 限制 limit用法
    person = session.query(Person)[0:3]
    # 排序
    person = session.query(Person).order_by(Person.name.desc()).all()
    person = session.query(Person).order_by(Person.name.desc(), Person.id.asc()).all()
    for p in person:
        print("主键：%s 名称：%s 年龄：%d 国籍：%s" % (p.id, p.name, p.age, p.country))
    # 分组
    person = session.query(Person.age).group_by(Person.age).all()
    from sqlalchemy.sql import func
    person = session.query(func.max(Person.id),func.sum(Person.id),func.min(Person.id)).group_by(Person.name).all()
    person = session.query(func.max(Person.id),func.sum(Person.id),func.min(Person.id)).group_by(Person.name).having(func.min(Person.id) > 2).all()
    print(str(person))
    # 连表
    ret = session.query(Person, User).filter(User.id == Person.id).all()
    ret = session.query(Person).join(User).all() # 默认为 inner join
    ret = session.query(Person).join(User,isouter=True).all() # isouter表示为left join
    # 组合
    q1 = session.query(Person.name).filter(Person.id >2)
    q2 = session.query(User.name).filter(User.uid < 2)
    ret = q1.union(q2).all() # union默认去重
    q1 = session.query(Person.name).filter(Person.id >2)
    q2 = session.query(User.name).filter(User.uid < 2)
    ret = q1.union_all(q2).all() # union_all不去重
~~~

### 非关系型数据库

> Redis

**安装redis-py模块**

~~~Python
pip install redis
~~~

**连接**

普通连接

~~~Python
import redis
conn = redis.Redis(host="XXX.XXX.XXX.XXX", port=6379, password="123456")
conn.set("x1","hello",ex=20) # ex代表seconds，px代表ms
val = conn.get("x1")
print(val)
~~~

连接池

~~~Python
pool = redis.ConnectionPool(host="XXX.XXX.XXX.XXX", port=6379, password="123456", max_connections=1024)
conn = redis.Redis(connection_pool=pool)
print(conn.get("x1"))
~~~

**管道**

`redis-py`默认在执行每次请求都会创建（连接池申请连接）和断开（归还连接池）一次连接操作，如果想要在一次请求中指定多个命令，则可以使用`pipline`实现一次请求指定多个命令，并且默认情况下一次pipline 是原子性操作(MySQL中的事务)。

~~~Python
pool = redis.ConnectionPool(host="XXX.XXX.XXX.XXX",  port=6379, password="123456", max_connections=1024)
conn = redis.Redis(connection_pool=pool)
pipe = conn.pipeline(transaction=True)
conn.set('hello','world')
conn.set('name','zhangsan')
pipe.execute()
~~~

