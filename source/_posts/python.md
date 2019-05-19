---
title: python
date: 2019-04-26 21:50:51
tags:
    - python
categories:
    - python
---
## python零基础到入门
### 人生苦短，我用python。

### 1.安装

- [建议直接使用python3](https://www.python.org)
- 注意:安装时选中 Add python 3.x to Path

### 2.基本类型
```bash
进制：
    二进制:0b10->2
    八进制:0o10->8
    十六进制:0x10->16
进制之间的转换:
	转换输出二进制:  bin(23)
	转换输出十进制： int(0x02)
	转换输出十六进制： hex(80)
	转换输出八进制：  oct(90)

数字类型
    浮点:
    	a = 1.23
    整数:
    	a = 1
    bool：真/假
    	a = false,b= true
    	任意类型都可以用 bool判断
    complex复数:
    	complex(1, 2)
序列类型:
	排序:
	sort是属于list上的方法，sorted可以对所有可迭代的对象进行分排序操作
	sorted(L)返回一个排序后的L，不改变原始的L；
	sorted 的应用，也可以通过 key 的值来进行数组/字典的排序，比如：

    array = [{"age":20,"name":"a"},{"age":25,"name":"b"},{"age":10,"name":"c"}]
    array = sorted(array,key=lambda x:x["age"])
    print(array)
    输出结果：
    [{'age': 10, 'name': 'c'}, {'age': 20, 'name': 'a'}, {'age': 25, 'name': 'b'}]
    
        L.sort()是对原始的L进行操作，调用后原始的L会改变，没有返回值。【所以a = a.sort()是错的啦！a = sorted(a)才对！
	序列解包:
		a,b,c = 1,2,3
		a.replace('C#','Go')
		
	判断是否存在序列中: xx in 序列
	元素个数:len(xx)
	最大:max()
	最小:min()
    字符串str
        单引号:
            'hello world'
        双引号:
            "hello world"
            "let's go"
        三引号:
            '''hello world '''
        字符串操作
            拼接："hello " + "world"
            乘法："hello"*2
            获取某个字符:"hello"[0]->'h' "hello"[-1]->'0'
            截取字符串："hello"[0:4] 不包含末尾-> 'hell'
    组：
        列表：
            a = [1,2,3]
            嵌套列表:[[],[]]
            使用:和字符串一样使用
            合并:和字符串一样
        元祖：
            a = (1,2,3,4)
            唯一不同点，元祖不能改变组中元素的数值
            定义只有一个元素的元祖 (1,)
集合:
	特点:无序的，不重复
	支持:len（）
	支持  in 操作
	集合差集合:{1，2}-{1} = {2}
	交集 {1,2}&{2} = {2}
	并集  {1,2} | {2,3} = {1,2,3}
	定义空的集合:set()
字典（集合一种）key不重复,key不可变的类型:
	key,value
	定义:{key:value,....}
	访问:{}[key]
	字典的嵌套{a:{a:1,b:2},b:3}
	空的字典:{}
```
### 3.变量
```
定义变量 a = 12
```
### 4.运算符
```python
 +  *  /   取余%   取整 //
 身份运算 is： a = 1 b= 1  a is b ->True  a = 1 b = 1.0   a is b->false 比较的是内存地址
 or  and  not 

```
### 5. 条件 循环控制
- if
```python
else if =  elif
	if condition:
    	pass
	else:
   	 	pass
   	或
	if condition:
   		 pass
    else if condition:
        pass 
    else:
        pass
        
account = "qiyue"
passord = "123456"

user_name = input("请输入用户名:")
user_password = input("请输入密码")
if(account == user_name and passord == user_name)
	print("sucess")
else:
	print("fail")

```
- while 循环

  ```python
  递归时候用比较合适
  while expression:
  	pass
  else:
  	pass	#while条件不满足，执行
  
  
  ```
- for循环
```python 

for target_list in expression_list:
	pass
else:
	pass
https://cowtransfer.com/
continue：跳过本次循环
break：跳出循环
for x  in range(0,10) :  0-9
	print(x)
range(起始,结束,步长)
a[0:len(a)等价  for  x in range(0,len(a),2): a[x]
```
### 6.包/模块/类/函数.变量
```python
包:必须包含 __init__.py文件
模块:命名空间  包名.模块
import   moule_name
import   moule_name  as  别名
form moudle_name  import  变量或者函数
*表示导入所有模块   选择__all__=['c','d']#在模块中使用
换行操作：  \或者()

__init__.py:包导入自动执行
避免循环导入
python 只有一个入口文件
```
### 7.函数
```python
局部变量不会更改全局变量的值
可变参数：
*arg  表示列表 
def a(*arg):
    for i in arg:
        print(i)
a(1,2,3,4)
**kargs 表示字典
def a(**arg):
    for k,v in arg.items():
        print(k)
        print(v)
a(a = 1,b = 3,c =4)


a = 1.2.3.4
round(a,2)->a = 1.23
def funcname(self, parameter_list):
	pass

return value/None
return  value2，value2

v1,v2 = func(1,2) #接收返回值

import  sys
sys.setrecursionlimit(100000)  #设置默认最小递归次数
可变参数：
匿名函数:
  def f(x,y):
    return x+y
匿名函数
   f= lambda x,y:x+y
   f(1,2)
x = [1,2,3]
def fun(x)
	return x*x
list_x = [1,2,3]
list_y = [4,5,6]
r = map(fun,list_x)#第二个参数只能是序列类型 ,可变参数  对列表中的每个元素进行平方操作
r = map(lambda x:x*x,list_x)#和匿名函数结合使用
r = map(lambda x，y:x*x+y,list_x,list_y)#和匿名函数结合使用，传入多个列表
print(list(r))#list中元素进行平方操作  
from funtools import reduce
r = reduce(lambda x,y:x+y,list_x，初始值/默认None)#连续计算，所以不需要第二个列表 y是列表里面元素参数，x是初始值，每次循环返回值
print(r)#列表的和  每一次调用匿名函数的结果作为第一个参数的值，第二个参数取下一个数值
filter()过滤不需要的元素
r = filter(lambda x:True if x==1 else False,list_x)#x真，返回True,否则返回Flase  返回True表示保留  False表示从列表中去除
print(list(r))
闭包:
不会受到外部变量影响
def curve_pr():
    a = 3
    def curve(x):
        return a*x*x
    return curve
f =  curve_pr()#返回内部函数
f(2)#调用内部函数
结果:12
显示定义不是局部本地变量 nolocal  
闭包可以记忆上次调用的状态
全局变量使用
def  factory(pos):
	def go(step):
        nolocal pos
        new_pos = pos + step
        pos = new_pos
        return new_pos
    return go

tourist = factory(0)
tourist(2)
tourist(3)
tourist(4)
装饰器：
给已经写好的内容添加额外的作用
import time
def decorator(func)：
	def wrappper():
        print(time.time())
        fun()
    return wrapper
def f1():
    print("This is a funtuion")
f = decorator(f1)
f()
装饰器语法糖@
import time
def decorator(func)：
	def wrappper(*arg):#多参数支持
        print(time.time())
        func(*arg)
    return wrapper
@decorator
def f1(name):
    print("This is a funtuion")
@decorator
def f2(name，name2):
    print("This is a funtuion")
f1('test')
f2("test1","test2")
方式2:
import time
def decorator(func)：
	def wrappper(*arg,*kw):#多参数支持
        print(time.time())
        func(*arg,*kw)
    return wrapper
@decorator
def f0():
    print('This is funtion0')
@decorator
def f1(name):
    print("This is a funtuion1")
@decorator
def f2(name，name2):
    print("This is a funtuion2")
@decorator
def f3(name，name2,*kw):
    print("This is a funtuion3")

f()
f1('test')
f2("test1","test2")
f3("test1","test2"，a =2,b =3)
在类中使用：
def catch_exception(origin_func):
    def wrapper(*args, **kwargs):
        try:
            u = origin_func(*args, **kwargs)
            return u
        except Exception:
            return 'an Exception raised.'
    return wrapper


class Test(object):
    def __init__(self):
        pass

    def revive(self):
        print('revive from exception.')
        # do something to restore

    @catch_exception
    def read_value(self):
        print('here I will do something.')
 		# do something.
  类装饰器:
class Foo():
    def __init__(self,func):
        self.func = func#装饰器函数传递，初始化
    def __call__(self,*args,**kw):#装饰器调用
        print("do something")
        self.func(*args,**kw)
        pass

@Foo
def bar():
    print('bar')


bar()   
        
```
### 8.面向对象
```python
class StudentHomework():
#类变量
	name = ''
	age = 0
    def __init__(self,name,age):
    # 实例变量:
		self.name = name
		self.age = age
	def print_file(self):#实例方法
		print(self.name) #实例变量
		print(Student.name) #类变量 self.__class__.name
stduent = StudentHomework()
studnet.print_file()

类方法:
	@classmethod
	def func(cls):
		cls.name #直接调用类变量
		pass
静态方法:
@staticmethod
def func(): #就是普通函数，不常用 和类 对象没有太大关系时候用
	pass
成员的可见性:
	__:#表示方法或者变量是私有的，类外部不能调用，也不能在类的外面定义,子类不能访问父类的私有方法和属性
        class Person(object):
            self.name = name
            self._age = age
            self.__tast= taste
            
            
mavepavefo@simpleemail.info
Meteor开发框架
mqtt
uni-app
https://www.youtube.com/watch?v=TsI8hsEf7tU&list=PLJjGSrG2EKgm8DpIFi9w-sBv1jyjm3n_6
https://www.drguo.com/index.aspx
https://www.ctolib.com
类的作用在于封装代码

继承：
	class G(F):
		def__init__(self,name,age):
			F.__init__(self，name,age)#显示调用父类构造
			或者
			super(G,self).__init__(name,age)
					pass
多态:
    一个变量，多种状态
    class Cat():
        def say(self):
            print('I am Cat')
	class Dog():
         def say(self):
            print('I am Dog'
    class Duck():
         def say(self):
            print('I am Duck')
animal = Cat()/animal = Dog()/animal = Duck()
animal.say()                 
封装:

```
### 9.正则表达式
```python
正则是一个特殊字符序列，字符串是否与设定的字符序列匹配
import re
正则查找：
    r = re.findall("python",'python c++ c  java javascript') #返回列表
    表示数组0-9:  ‘\d’
    或:[cf] #匹配c或者F        [^cf]匹配非 c或者非f字符  [c-f]陪匹配c到F单个字符
    概括字符集：
                0-9 -> \d
                \n \r \t 空格等制表符 ->  \s
                匹配数量 ->{n}/{min,max}
                *:表示出现n 前面的字符0或者多次匹配  pytho0python1pythonn2->['pytho','python','pythonn'] r = re.findall('python*','pytho0python1pythonn2')
                +:前面的字符出现一次或者多次匹配 ->['python','pythonn']
                ？:前面的字符0或者1次匹配->['pytho','python']
    边界匹配：^$表示完全匹配  完整字符串 ^[a-z] 只能匹配以小写字母为行首的行"a..."[a-z]$ 只能匹配以小写字母为行尾的行: "...a"  
    组:  ()：提取匹配到的字符串里面()匹配的内容  例子下面
    忽略大小写匹配:re.findall('python*','pytho0python1pythonn2',re.I)     re.S表示匹配包括换行符\n  和  .合用 匹配任意字符
正则替换 : 
    re.sub('正则','替换/函数','pytho0python1pythonn2',count)  count=0默认能多次替换 count=1,能被1次替换  
    第二个参数可以是函数： def  convert(value):
                            match = value.group()#获取匹配的字符串
						
r= re.match()首字母开始匹配，不成功返回None，匹配成功，立即返回匹配的单个对象结果  r.group()   下标  r.span()    只匹配一次
r = re.search()全字符串匹配，匹配成功，立即返回匹配的单个对象结果 r.group()
下标  r.span()     只匹配一次

取某个字符串中间的字符串  
a = lift  多放点胡椒粉   python  dfjkasdjf  python

r = findall('lift(.*)python(.*)python')
import re
s = ' so  lift i love python you python  hight' 

r = re.findall("lift(.*)python(.*)python",s)#匹配字符串，并提取匹配字符串以lift开头python结尾的内容
print(r)
结果:[(' i love ', ' you ')]
    
贪婪和非贪婪
import re
a="aa<div>test1</div>bb<div>test2</div>cc "
r1 = re.findall('<div>.*</div>',a)#贪婪模式 默认  尽可能匹配最多的
r2 = re.findall('<div>.*?</div>',a)#非贪婪模式  尽可能匹配最少的，就近匹配原则
print(r1)
print(r2)
结果：
['<div>test1</div>bb<div>test2</div>']
['<div>test1</div>', '<div>test2</div>']


    
```
### 10.JSON
```python
JSON是轻量级数据交换格式
json_str = "{"name":"jone","age":23}"
方法:
 ojb方式
 	反序列化
	dict_s = json.loads(json_str) #字典
array方式
	dict_s = json.loads("[{"name":"jone","age":23},{"name":"jone","age":23},{"name":"jone","age":23}]") #得到列表
序列化：
s = json.dumps(dict_s) 得到json格式

```
### 11.高级语法和用法
```python
枚举类型
from enum import Enum

class Vip(Enum):
	y = 1
	y_b = 1
	g = 2
	b = 3
	r = 4
获取值方法:Vip.y.value
获取名字方法:Vip.y.name
可以遍历 for v in Vip:
			print(v)#不包含别名成员
可以做==和is比较操作
y_b相当于y的别名，不会打印出来
便利成员  for v in Vip.__numbers__:
				print(v)#包含别名成员
https://www.youtube.com/channel/UCKUmZM_yDHMKxl4EWAt6GKw

函数式编程:
函数返回一个函数
http请求
from urllib import request
class Spider():
    url=''
    def __fetch_content(self):
        r = request.urlopen(Spilder.url)#打开网页
        htmls = r.read()#读取网页html
    def go(self):
        self.__fetch_content()
spider = Spider()
spider.go()
	
爬虫实例
from  urllib import request
import re

class Spider():
    url='https://www.huya.com/g/wzry'
    root_pattern='<li class="game-live-item" gid="2336">([\s\S]*?)</li>'#?表示使用非贪婪模式
    def __fetch_content(self):#获取内容
        r = request.urlopen(Spider.url)#打开网页
        htmls = r.read()#读取网页html
        htmls = str(htmls,encoding='utf-8')#bt转换str
        return htmls
    def __analysis(self,htmls):#分析
        root_html = re.findall(Spider.root_pattern,htmls)
        print(root_html[0])
    def go(self):
        htmls = self.__fetch_content()
        self.__analysis(htmls)
spider = Spider()
spider.go()



```

### 12.常用库
```python
爬虫:
	BeautifulSoup爬虫库
	scrap爬虫框架

```
### 13.python实用方法
- 字典代替switch:
```python
字典代替switch:
    day = 1
    def get_s():
        return 's'
        
    def get_m():
        return 'm'

    def get_t():
        return 't'

    def get_default():
        return 'default'
        
    switch = {0:get_s,1:get_m,2:get_t}

    day_name = switch.get(day,get_default)()
    print(day_name)

列表推导式：
序列：
	a = [1,2,3,4,5]
    b = [i*i for i in a]
    print(b)
    结果：[1, 4, 9, 16, 25]
    或
     b = [i*i for i in a if i>2]
    结果;
    	[9, 16, 25]
集合:
     a = {1,2,3,4,5}
     b = {i*i for i in a if i>2}
字典:
    students = {"xiaole":18,"shigandang":19}
    b = [key for key,value in students.items()]
    print(b)

```
- 数据结构

  - 如何在列表，字典，集合中根据条件筛选数据

  ```python
  1.列表数据筛选:  
         filter：函数返回True，数据保留，函数参数x为列表数据
              from random import randint
              data = [randint(-10,10) for _ in range(10)]
              # data = filter(lambda x:Ture if x>=0 else False ,data)
              data = filter(lambda x:x>=0 ,data)
              print(list(data))
        使用列表解析:
              data = [x for x in data if x >=0]#比filter速度快
              print(data)
        字典解析：
              d = {"a":'1',"b":'98'}
              data = {k:v for k,v in d.items() if int(v) >90}
              print(data)
        集合解析：
                d = {1,98}
              data = {k for k in d if v >90}
              print(data)
  2.元组命名：
      	collections.namedtuple 
            命名元组有助于对元组每个位置赋予意义，并且让我们的代码有更好的可读性和自文档性
              from collections import namedtuple
              Point = namedtuple("Piont",['x','y'])
              p = Point(1,2)
              print(p.x)
          
            列表解析:
                y,g,b,r=range(4)
              用枚举
              from enum import Enum
              class Vip(Enum):
                  y = 1
                  y_b = 1
                  g = 2
                  b = 3
                  r = 4
              获取值方法:Vip.y.value
              获取名字方法:Vip.y.name
              可以遍历 for v in Vip:
                      print(v)#不包含别名成员
   3.统计元素出现的频率：
  					from random import randint
                      data = [randint(0,20) for _ in range(30)]#实际项目中可以是任意列表数据
                      d = dict.fromkeys(data,0)#date中的元素作为key,0作为value，创建新字典，
                      for k in data:#数据统计
                          d[k] +=1#思路字典的key,就是列表的元素
                     end = d.items()
                     print(sorted(end,key=lambda x:x[1],reverse=True))#排序
  
   4.让字典排序：
  				先转化成序列
      					字典转换成元组用zip方法
          				a_tuple = zip(d.values(),d.keys())或者d.items()
                          from  random import randint
                          d = {x:randint(60,100) for x in "xyzabc"}
                          # l1 = zip(d.values(),d.keys())
                          # jieguo1 =   sorted(l1)
                          # print(jieguo1)
                          l2 = d.items()
                          jieguo2 = sorted(l2,key=lambda x:x[1])
                          print(jieguo2)
              
   5.序列排序：
          sort是属于list上的方法，sorted可以对所有可迭代的对象进行分排序操作
          sorted(L)返回一个排序后的L，不改变原始的L；
          sorted 的应用，也可以通过 key 的值来进行数组排序，比如：
  
          array = [{"age":20,"name":"a"},{"age":25,"name":"b"},{"age":10,"name":"c"}]
          array = sorted(array,key=lambda x:x["age"])
          print(array)
          输出结果：
          [{'age': 10, 'name': 'c'}, {'age': 20, 'name': 'a'}, {'age': 25, 'name': 'b'}]
  
              L.sort()是对原始的L进行操作，调用后原始的L会改变，没有返回值。【所以a = a.sort()是错的啦！a = sorted(a)才对！
   6.快速找到多个字典中的公共键
  		random.sample()可以从指定的序列中，随机的截取指定长度的片断，不作原地修改
          from random import randint,sample
          list_name = sample("abcdefg",randint(3,6))
          方法1：
          from random import randint,sample
          list_name = sample("abcdefg",randint(3,6))
  
          dict_name1 = {x:randint(1,4) for x in list_name}#集合
          dict_name2 = {x:randint(1,4) for x in list_name}
          dict_name3 = {x:randint(1,4) for x in list_name}
          print(dict_name1.keys()&dict_name2.keys()&dict_name3.keys())#集合交集方法获取公共键
          方法2：多个字典
          from random import randint,sample
          from functools import reduce
          list_name = sample("abcdefg",randint(3,6))
  
          dict_name1 = {x:randint(1,4) for x in list_name}
          dict_name2 = {x:randint(1,4) for x in list_name}
          dict_name3 = {x:randint(1,4) for x in list_name}
          print(dict_name1.keys()&dict_name2.keys()&dict_name3.keys())
          s = map(dict.keys,[dict_name1,dict_name2,dict_name3])#多个字典放在列表中，取key值
          print(reduce(lambda a,b:a&b,s))
    7.如何让字典保持有序：
  					from collections import OrderedDict
                      d = OrderedDict()
                      d["jim"] = (1.2)
                      d['leo'] = [2,3]
                      d['bob'] = [3,4]
                      print(d)
  8.历史记录功能
  	用队列：
      from collections import deque#进行历史记录
      import pickle #可以把对象存入电脑，也可以把对象，加载到程序中，用这个模块进行历史存储
      q = deque([],5)#[]初始队列  5：队列元素数量
      q.append(1)
      q.append(2)
      q.append(3)
      q.append(4)
      q.append(5)
      q.append(6)
  
      pickle.dump(q,open("history",'wb'))#q对象保存到文件
      pickle.dump("test",open("history",'wb'))
      q1 = pickle.load(open("history","rb"))#从文件中提取对象
  
      print(list(q1))
      
  ```

  

- 迭代器和生成器

  ```
  1.如何实现可迭代对象和迭代器对象
  ```

  

- 字符串处理

- 文件IO操作

- 数据编码与处理

- 类和对象

- 多线程和多进程

- 装饰器

### 13.迭代器和生成器

```
迭代器:可以用 for in 遍历的对象就是可迭代对象，并返回值的对象，可以用iter()，把一个可以遍历的可迭代对象，变成迭代器。可以调用next()调用，
iter(list/tuple/dict/str/集合等可迭代对象)

a = iter([1,23])
while True:
    try:
        print(next(a))
    except:
        print("StopIteration")
        break
```




































