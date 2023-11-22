复习记录：
1.关于各个数据类型函数的复习，高级特性，

keyword.kwlist：

什么是sys.argv,sys.path?

“Windows 命令行窗口”下清屏，可用下面两种方法。

第一种方法，在命令行窗口输入：
>>> import os
>>> i=os.system("cls")
>>> 第二种方法，在命令行窗口输入：
>>> import subprocess
>>> i=subprocess.call("cls", shell=True)
>>> 格式化输出：
>>> %s： 作为字符串
>>>  %d： 作为有符号十进制整数
>>>  %u： 作为无符号十进制整数
>>>  %o： 作为无符号八进制整数
>>>  %x： 作为无符号十六进制整数，a～f采用小写形式
>>>  %X： 作为无符号十六进制整数，A～F采用大写形式
>>>  %f： 作为浮点数
>>>  %e，%E： 作为浮点数，使用科学计数法
>>>  %g，%G： 作为浮点数，使用最低有效数位
>>>  标准数据类型

###  **1.number int,float,bool,complex**

 内置的 type() 函数可以用来查询变量所指的对象类型。
 此外还可以用 isinstance 来判断：
 a = 111
>>> isinstance(a, int)
>>> True

isinstance 和 type 的区别在于：

type()不会认为子类是一种父类类型。
isinstance()会认为子类是一种父类类型。
>>> class A:
>>> ...     pass
>>> ... 
>>> class B(A):
>>> ...     pass
>>> ... 
>>> isinstance(A(), A)
>>> True
>>> type(A()) == A 
>>> True
>>> isinstance(B(), A)
>>> True
>>> type(B()) == A
>>> False

注意：Python3 中，bool 是 int 的子类，True 和 False 可以和数字相加， True==1、False==0 会返回 True，但可以通过 is 来判断类型。

>>> issubclass(bool, int) 
>>> True
>>> True==1(从而“==”并不意味着全等)
>>> True
>>> False==0
>>> True
>>> True+1
>>> 2
>>> False+1
>>> 1
>>> 1 is True
>>> False
>>> 0 is False
>>> False

您也可以使用del语句删除一些对象引用。
del语句的语法是：
del var1[,var2[,var3[....,varN]]]
您可以通过使用del语句删除单个或多个对象。例如：
del var
del var_a, var_b    

数值运算

>>> 5 + 4  # 加法
>>> 9
>>> 4.3 - 2 # 减法
>>> 2.3
>>> 3 * 7  # 乘法
>>> 21
>>> 2 / 4  # 除法，得到一个浮点数
>>> 0.5
>>> 2 // 4 # 除法，得到一个整数
>>> 0
>>> 17 % 3 # 取余
>>> 2
>>> 2 ** 5 # 乘方
>>> 32

2、一个变量可以通过赋值指向不同类型的对象。
4、在混合计算时，Python会把整型转换成为浮点数。
Python 还支持复数，复数由实数部分和虚数部分构成，可以用 a + bj，或者 complex(a,b) 表示， 复数的实部 a 和虚部 b 都是浮点型。



### **2.string**

```
#!/usr/bin/python3

str = 'Runoob'

print (str)          # 输出字符串
print (str[0:-1])    # 输出第一个到倒数第二个的所有字符
print (str[0])       # 输出字符串第一个字符
print (str[2:5])     # 输出从第三个开始到第五个的字符
print (str[2:])      # 输出从第三个开始的后的所有字符
print (str * 2)      # 输出字符串两次，也可以写成 print (2 * str) 
print (str + "TEST") # 连接字符串
```



```python
Runoob
Runoo
R
noo
noob
RunoobRunoob
RunoobTEST
```

### 3.bool

- 布尔类型只有两个值：True 和 False。
- 布尔类型可以和其他数据类型进行比较，比如数字、字符串等。在比较时，Python 会将 True 视为 1，False 视为 0。
- 布尔类型可以和逻辑运算符一起使用，包括 and、or 和 not。这些运算符可以用来组合多个布尔表达式，生成一个新的布尔值。
- 布尔类型也可以被转换成其他数据类型，比如整数、浮点数和字符串。在转换时，True 会被转换成 1，False 会被转换成 0。

**注意:** 在 Python 中，所有非零的数字和非空的字符串、列表、元组等数据类型都被视为 True，只有 **0、空字符串、空列表、空元组**等被视为 False。因此，在进行布尔类型转换时，需要注意数据类型的真假性。



### **4.list**

```
list = [ 'abcd', 786 , 2.23, 'runoob', 70.2 ]
tinylist = [123, 'runoob']

**print** (list)       # 输出完整列表
**print** (list[0])     # 输出列表第一个元素
**print** (list[1:3])    # 从第二个开始输出到第三个元素
**print** (list[2:])     # 输出从第三个元素开始的所有元素
**print** (tinylist * 2)   # 输出两次列表
**print** (list + tinylist) # 连接列表
```



```
['abcd', 786, 2.23, 'runoob', 70.2]
abcd
[786, 2.23]
[2.23, 'runoob', 70.2]
[123, 'runoob', 123, 'runoob']
['abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob']
```

>>> a = [1, 2, 3, 4, 5, 6]
>>> a[0] = 9
>>> a[2:5] = [13, 14, 15]
>>> a
>>> [9, 2, 13, 14, 15, 6]
>>> a[2:5] = []   # 将对应的元素值设置为 [] (另一种删除list对应元素的方法，但是只能连续删除，不能有步长)
>>> a
>>> [9, 2, 6]

***string、list 和 tuple 都属于 sequence（序列）。***

#### prominent functinos for list:

join



split



### 5.set



**注意：**创建一个空集合必须用 **set()** 而不是 **{ }**，因为 **{ }** 是用来创建一个空字典。

创建格式：





### 6.Dictionary（字典）

***键(key)必须使用不可变类型。***



构造函数 dict() 可以直接从键值对序列中构建字典如下：



>>> dict([('Runoob', 1), ('Google', 2), ('Taobao', 3)])
>>> {'Runoob': 1, 'Google': 2, 'Taobao': 3}
>>> {x: x**2 for x in (2, 4, 6)}  #字典推导式
>>>
>>> [python推导式]: https://www.runoob.com/python3/python-comprehensions.html
>>>
>>> {2: 4, 4: 16, 6: 36}
>>> dict(Runoob=1, Google=2, Taobao=3)
>>> {'Runoob': 1, 'Google': 2, 'Taobao': 3}

另外，字典类型也有一些内置的函数，例如 clear()、keys()、values() 等。



**注意：**

- 1、字典是一种映射类型，它的元素是键值对。
- 2、字典的关键字必须为不可变类型，且不能重复。
- 3、创建空字典使用 **{ }**。



### 7.bytes 类型

bytes 类型通常用于处理二进制数据，比如图像文件、音频文件、视频文件等等。在网络编程中，也经常使用 bytes 类型来传输二进制数据。



创建 bytes 对象的方式有多种，最常见的方式是使用 b 前缀：

此外，也可以使用 bytes() 函数将其他类型的对象转换为 bytes 类型。bytes() 函数的第一个参数是要转换的对象，第二个参数是编码方式，如果省略第二个参数，则默认使用 UTF-8 编码：

```
x = bytes("hello", encoding="utf-8")
```

需要注意的是，bytes 类型中的元素是整数值，因此在进行比较操作时需要使用相应的整数值。例如：

```
x = b"hello"
if x[0] == ord("h"):
    print("The first element is 'h'")
```



关于各个类型的数据转换，参见：

[python数据转换]: https://www.runoob.com/python3/python3-type-conversion.html	"数据转换"

























