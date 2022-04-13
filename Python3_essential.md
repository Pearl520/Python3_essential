# **Python3**

参考：https://www.runoob.com/python3/python3-tutorial.html

## Python介绍

**Python 是交互式语言：** 在一个 Python 提示符 **>>>** 后可以直接执行代码。

运行Python的3种方式：

> - 交互解释器
>
> - 命令行脚本
>
> - 集成开发环境（IDE：Intergrated Development Environment）Pycharm
>
>   注：执行脚本时，请检查脚本是否有可执行权限。

默认情况下，Python 3 源码文件以 **UTF-8** 编码，所有字符串都是 unicode 字符串。

Python 3 中，可以用中文作为变量名，非 ASCII 标识符也是允许的。

标识符第一个字符必须是字母表中字母或下划线**` _ `**。标识符区分大小写。

```python
# 打开Python
~ $ python
Python 3.8.11 (default, Jul 29 2021, 14:57:32) 
[Clang 12.0.0 ] :: Anaconda, Inc. on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> quit() # 退出python
# 或者
>>> exit() # 或control+z，回车
```

## 基础语法

**保留词**

```python
>>> import keyword # 保留词
>>> keyword.kwlist
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

------

**注释**

python中的注释也以`#`开头（回忆一下所学过的语言中，它们的注释符号：

> Perl：`# 注释内容`
>
> R：`# 注释内容`
>
> CSS：`/*注释内容*/`

```python
print("Hello, world!")
# 注释
# 多行注释
'''
注释：白日依山尽
注释：黄河入海流
'''
"""
注释：床前明月光
住释：疑是地上霜
"""
```

------

**缩进**

python最具特色的就是使用缩进来表示代码块，不需要使用大括号**`{}`** （比如Perl）。

⚠️：缩进的空格数可变，但是**同一个代码块**的语句必须包含**相同的缩进空格数**。

⚠️：缩进不一致，会导致运行错误。

```python
if True:
    print ("True")
else:
    print ("False") # 正确
  print （"False"）# 错误
```

------

**多行语句**

python可以用反斜杠 **`\`** 来实现多行语句(但一般是一行写完一条语句)。

```python
# example
total = item_1 + \
        item_2 + \
        item_3
# 在 [], {}, 或 () 中的多行语句，不需要使用反斜杠
total = ['item_1', 'item_2', 'item_3']
```

------

**Number**

python中的数字类型：

> - **int** ：如 1, python3只有一种整数类型 int，表示为长整型。
> - **bool** ：只有True和False。
> - **float** ：如 1.23、3E-2
> - **complex** ：如 1 + 2j、 1.1 + 2.2j

------

**String**

Python中关于字符串的一些规则：

> 1. 单引号 = 双引号 （Perl中单引号与双引号使用有区别）
>
> 2. 三引号( ''' 或者 """ )可以指定一个多行字符串
>
> 3. 转义：**`\`**
>
> 4. 使用**` r `**可以让反斜杠**`\`**不发生转义（r是raw string的意思）
>
>    > ```python
>    > #!/user/bin/python3
>    > print("This is a line.\n")
>    > print(r"This is a line.\n")
>    > $ python test_r_string.py
>    > This is a line.
>    > 
>    > This is a line.\n
>    > ```
>
> 5. Python可以根据字面意义级联字符串
>
> 6. String1`+`String2
>
> 7. index：`0→_`或者`_←-1`
>
> 8. 一个字符就是长度为 1 的字符串
>
> 9. > ```python
>    > word_string = 'apple'
>    > sentence_string = "This is an apple."
>    > paragraph_string = """ This is an apple,
>    > I like apples!"""
>    > ```

**例**

```python
#!/user/bin/python3
test_str = "日照香炉生紫烟遥看瀑布挂前川"
print(test_str)             # output test_str
print(test_str[0:-1])       
print(test_str[2:6])
print(test_str[3:])
print(test_str[1:7:2])
print(test_str * 3)
print(test_str + '飞流直下三千尺疑是银河落九天')
print('---------------------------------')
print('唐\n李白')
$ python py_string.py
日照香炉生紫烟遥看瀑布挂前川
日照香炉生紫烟遥看瀑布挂前   # -1
香炉生紫
炉生紫烟遥看瀑布挂前川
照炉紫
日照香炉生紫烟遥看瀑布挂前川日照香炉生紫烟遥看瀑布挂前川日照香炉生紫烟遥看瀑布挂前川
日照香炉生紫烟遥看瀑布挂前川飞流直下三千尺疑是银河落九天
---------------------------------
唐
李白
```

------

**空行**

函数之间或类的方法之间用**空行分隔**，<u>表示一段新的代码的开始</u>。空行与代码缩进不同，空行并不是 Python 语法的一部分。

⚠️：空行的作用在于分隔两段不同功能或含义的代码，便于日后代码的维护或重构。（提高可读性）

------

**等待用户输入**

```python
#!/user/bin/python3
print("Hello world!")
input("\n\nPress 'Enter' to exit the program.")
$ python input_test.py    
Hello world!


Press 'Enter' to exit the program.
$ # 按"Enter"就会退出程序
# 类似于Perl中的钻石操作符：$input=<STDIN>（等待用户键盘输入）
```

------

**显示多条语句**

在同一行中使用多条语句，语句之间使用分号 **`;`** 分割

```
>>> import sys; x = 'test'; sys.stdout.write(x + '\n')
test
5  # 表示字符数，test占4个字符，\n占一个字符
```

------

**代码组**

==缩进相同==的一组语句构成一个代码块，我们称之**代码组**。首行及后面的代码组称为一个**==子句(clause)==**。

------

**Print**

**print** 默认输出是换行的，如果要实现不换行需要在变量末尾加上 **`end=""`**。

```python
#!/user/bin/python3
x="a"
y="b"
# test1:换行output
print(x)
print(y)
# test2:不换行output
print(x, end=" ") # 双引号之间是空格
print(y, end=" ")
print()
$ python print_test.py
a
b  # 默认输出换行
a b # 不换行
```

------

**import**

python 用 **`import`** 或者 **`from...import`** 来导入相应的模块；

> 导入整个模块：`import somemodule`
>
> 导入某个模块中的某个函数：`from somemodule import somefunction`
>
> 导入某个模块中的多个函数：`from somemodule import func1, func2, func3`
>
> 导入某个模块中的全部函数：`from somemodule import *`

------

**命令行参数**

```python
$ python -h # 查看各参数帮助信息
```

> 获取帮助：
>
> 在R中：`?`、`??`、`help`、`apropos`
>
> 在Perl中：`perldoc`

------



## 基本数据类型

在Python中的变量不需要声明，变量使用前需要赋值。赋值后，变量才会被成功创建。

Python中的变量没有类型。

### 变量赋值

```python
# 例：给变量赋值
#!/user/bin/python
a = 10000
b = 10000.0
c = "abcde"
print (a) # print后面可以直接连()，也可以空一格
print (b)
print (c)
# 多个变量同时赋值
x = y = z = 1000
# 多个变量赋多值
a, b, c = 1, 2, 3
```

**`del`**可以删除一些对象引用（单个、多个）：

```python
>>> var1 = 1
>>> var2 = 2
>>> var3 = 3
>>> print (var1)
1
>>> del var1, var2, var3 #
>>> print(var2)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'var2' is not defined
```

### 数据类型

> - **不可变数据：**
>   - ==Number==：`int`、`float`、`bool`、`complex`
>   - ==String==:
>   - ==Tuple==（元组）
> - **可变数据**
>   - ==List== （列表）
>   - ==Dictionary== （字典）
>   - ==Set==（集合）

`type`函数可以用来查询变量的类型；或者使用`isinstance`

```python
# type：指明
>>> a, b, c, d = 5, 5.5, False, 1+3j
>>> print(type(a), type(b), type(c), type(d))
<class 'int'> <class 'float'> <class 'bool'> <class 'complex'>
# isinstance：判断
>>> x = 123
>>> isinstance(x, float)
False
# 两者区别：type不会认为子类是一种父类；isinstance会认为子类是一种父类
```

⚠️：Python3中，bool是int的子类；`True`和`False`可以和number相加。

```python
>>> True==1
True
>>> False==0
True
# python2没有bool
```

### 数值运算

与==**R**==大同小异:

```python
>>> 1+1
2
>>> 2-1
1
>>> 2*3
6
>>> 3/6   # 浮点数除法
0.5
>>> 3//6  # 整数除法，R中是%/%
0
>>> 16%5  # 求余，R中是%%
1
>>> 4**3
64
```

⚠️：**混合计算时，Python会把整型转换成为浮点数。**

**Python中的复数**

Python支持复数，复数由<u>==实数==</u>部分和<u>==虚数==</u>部分构成，可以用`a + bj`或者`complex(a,b)`表示， 复数的实部a和虚部b都是浮点型。

### 字符串（String）

字符串用单引号 **`'`** 或双引号 **`"`** 括起来，同时使用反斜杠 **`\`** 转义。

**字符串索引方式**

> 从左到右：0 1 2 3 4 5
>
> 字符串例：a b c d e f
>
> 从右到左：-6 -5 -4 -3 -2 -1          

### 列表（List）

==列表==是 Python 中使用最频繁的数据类型。列表中元素的类型可以==不相同==：数字，字符串甚至可以包含列表（嵌套）。

列表的表示方法：写在方括号 **==[]==** 之间、用逗号`,`分隔开列表中的元素。（类似于==R==）

```python
#!/user/bin/python3
# 先构建一个list
list = [ '12345', 567, 'happy', 20+3j,'small']
another_list = [123, '000', 'DAY']

# 对上面的两个list进行索引等操作
print(list)
print(list[0]) # 索引列表list的第一元素
print(list[2:4]) # 索引列表第三个到第五个元素
print(list[3:]) # 索引列表list从第四个元素开始的所有元素
print('----------------')
print(another_list * 2)
print('----------------')
print(list + another_list) # 链接两个列表
# output
$ python list_index_test.py
['12345', 567, 'happy', (20+3j), 'small']
12345
['happy', (20+3j)]
[(20+3j), 'small']
----------------
[123, '000', 'DAY', 123, '000', 'DAY']
----------------
['12345', 567, 'happy', (20+3j), 'small', 123, '000', 'DAY']
```

⚠️：字符串不可改变，但列表中的元素可以改变。

```python
# 改变字符串中的元素
>>> a = [ 'I', 'want', 3 , 'apples', 'and', 5 , 'peaches']
>>> print(a)
['I', 'want', 3, 'apples', 'and', 5, 'peaches']
>>> # change
>>> a[0] = 'She'
>>> a[2:3] = [4, 'lemons']
>>> a[4:] = [] # 空
>>> a
['She', 'want', 4, 'lemons']
```

在列表中索引也可以像R一样限定步长，表现在第3个参数：

```python
>>> a_word = ['f', 'a', 'n', 't', 'a', 's', 't', 'i', 'c']
>>> a_word
['f', 'a', 'n', 't', 'a', 's', 't', 'i', 'c']
>>> a_word[1:6:2]  # 步长为2
['a', 't', 's']
```

⚠️：**如果第三个参数为负数表示逆向读取。**

### 元组（Tuple）

==Tuple==与==List==类似，但Tuple的元素不能修改。Tuple写在小括号 **`() `**里，元素之间用逗号**`,`**隔开。

```python
#!/user/bin/python3
# 创建一个tuple
tuple = ('123', 456, 5.5, 'sad', 10+4j)
another_tuple = ('A', 'sky', 777)

# 对tuple进行操作
print(tuple)
# 索引方式与list相同
print(another_tuple * 2) 
print(tuple + another_tuple) # tuple也能连接
$ python tuple_test.py
('123', 456, 5.5, 'sad', (10+4j))
('A', 'sky', 777, 'A', 'sky', 777)
('123', 456, 5.5, 'sad', (10+4j), 'A', 'sky', 777)
```

⚠️：字符串看作一种特殊的元组。

⚠️：元组的元素不可改变，但可以包含可变的对象，比如列表。

⚠️：构造包含 0 个或 1 个元素的元组比较特殊。

```python
tuple_0 = ()    # 空元组,0个元素
tuple_1= (20,)  # 1个元素，需添加逗号
```

### 集合（Set）

集合由<u>一个或数个形态各异的大小整体</u>组成的，构成集合的事物或对象称作==元素==或是==成员==。

==集合的功能：==进行成员关系测试和删除重复元素。

==集合的表示方法：==大括号 **`{ }`** 或者 **`set()`** 函数。

⚠️：创建一个空集合必须用 **`set()`** 而不能用 **`{ }`**，因为 **`{ }`** 是用来创建一个空==字典==。

```python
#!/user/bin/python3
animals_set = {'cat', 'dog', 'pig', 'duck', 'parrot','cat'}
print(animals_set) # Delete duplicate elements.

# Member test
if 'parrot' in animals_set :
    print("'parrot' is in this set.")
else :
    print("'parrot' is not in this set.")

print('----------------------------------------')
# Set operation
A_set = set('absdhcgsfedca')
B_set = set('ashdjhad')
print(A_set)
print(A_set - B_set)
print(A_set | B_set) # Union of A and B
print(A_set & B_set) # Intersection of A and B
print(A_set ^ B_set) # Unique of A and B
$ python set_test.py
{'cat', 'dog', 'pig', 'duck', 'parrot'}
'parrot' is in this set.
----------------------------------------
{'s', 'e', 'b', 'f', 'a', 'g', 'c', 'h', 'd'}
{'e', 'b', 'f', 'g', 'c'}
{'s', 'e', 'b', 'f', 'a', 'g', 'c', 'h', 'j', 'd'}
{'a', 'h', 's', 'd'}
{'g', 'e', 'c', 'b', 'j', 'f'}
```

### 字典（Dictionary）

字典是Python中另一个非常有用的==内置数据类型==；字典是一种==映射类型==，字典用**`{ }`**标识.

字典它是一个无序的**`键(key) : 值(value)`**的==集合==。

⚠️：==列表==是==有序==的对象集合，==字典==是==无序==的对象集合。

⚠️：字典当中的元素是通过==键==来存取的，而不是通过==偏移==存取。

⚠️：键(key)必须使用==不可变==类型。在同一个字典中，键(key)必须是唯一的。

```python
#!/user/bin/python3

dict = {}
dict['one'] = "1 - 字典测试"
dict[2]     = "2 - 你好"

a_dict = {'SPECIES':'cat', 'CHARACTER':'cute', 'BODY':'tiny'}  # 'key':'value'

print(dict['one'])        # 输出key为'one'的值
print(dict[2])            # 输出key为2的值
print(a_dict)             # 输出完整的字典
print(a_dict.keys())      # 输出所有的key
print(a_dict.values())    # 输出所有的value
$ python dic_test.py
1 - 字典测试
2 - 你好
{'SPECIES': 'cat', 'CHARACTER': 'cute', 'BODY': 'tiny'}
dict_keys(['SPECIES', 'CHARACTER', 'BODY'])
dict_values(['cat', 'cute', 'tiny'])
```

构造函数**`dict()`**可以直接从**`key：value`**对序列中构建字典：

```python
>>> dict([('rank1', 'Amy'), ('rank2', 'Bob'), ('rank3', 'Tom')])
{'rank1': 'Amy', 'rank2': 'Bob', 'rank3': 'Tom'}
>>> {x: x**2 for x in (1, 2, 3, 4, 5)}  # 字典推导式
{1: 1, 2: 4, 3: 9, 4: 16, 5: 25}
>>> dict(AAA=1, AAB=2, AAC=3, ABB=4, ABC=5)
{'AAA': 1, 'AAB': 2, 'AAC': 3, 'ABB': 4, 'ABC': 5}
```

字典有一些内置的函数：` clear()`、`keys()`、`values() `等。

一些注意事项：

> ⚠️ 字典是一种映射类型，它的元素是key-value对。
>
> ⚠️ 字典的关键字必须为==不可变==类型，且不能重复。
>
> ⚠️ 创建空字典使用 **`{}`**。

 

## 数据类型转换

数据类型转换，一般只需要将数据类型作为函数名即可。

Python 数据类型转换可以分为两种：

> - 隐式类型转换 - 自动完成
>
> - 显式类型转换 - 需要使用类型函数来转换

### 隐式类型转换

在隐式类型转换中，Python 会自动将一种数据类型转换为另一种数据类型。

```python
>>> num_int = 333
>>> num_flo = 333.333
>>> num_new = num_int + num_flo
>>> print("datatype of num_int:", type(num_int))
datatype of num_int: <class 'int'>
>>> print("datatype of num_int:", type(num_flo))
datatype of num_int: <class 'float'>
>>> print("value of num_new:", num_new)
value of num_new: 666.3330000000001
>>> print("datatype of num_new:", type(num_new))
datatype of num_new: <class 'float'>   # 这里整数和浮点数相加，新的数变成了浮点数，以免数据丢失
```

⚠️：==int==是较低数据类型；==float==为较高数据类型

```python
# 另一个例子
>>> a_int = 12345
>>> a_str = "6789"
>>> print("Data type of a_str:", type(a_str))
Data type of a_str: <class 'str'>
>>> print(a_str + a_int)
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: can only concatenate str (not "int") to str
  # 产生报错，这里Python无法使用隐式转换
```

如何解决这一问题？——Python的显式转换。

### 显式类型转换

显式类型转换，将对象的数据类型转换为所需的数据类型。 使用` int()`、`float()`、`str() `等预定义函数来执行显式类型转换。

```python
>>> a = int(1)
>>> b = int(1.1)
>>> c = int("1")
>>> print(a, b, c)
1 1 1
>>> a = float(3)
>>> b = float(3.3)
>>> c = float("3.3")
>>> d = float("3")
>>> print(a, b, c, d)
3.0 3.3 3.3 3.0
# 同理str()
```

整型和字符串类型进行运算，就可以用强制类型转换后来完成。

更多转换函数可用通过`help()`或者Google、百度查询。