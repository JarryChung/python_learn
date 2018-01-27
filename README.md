# python_learn
Record learning python.

### 代码文件说明
+ python_1: 输入与输出,格式化
+ python_2: list,tuple,dict,set
+ python_3: 条件判断与循环
+ python_4: 函数(重点难点)
+ python_5: 
+ python_6: 
+ python_7: 
+ python_8: 
+ python_9: 
+ python_10: 

### 语法
+ python不需要分号，采用换行以及缩进的形式。
+ 当语句以冒号:结尾时，下一行开始的缩进的语句视为代码块。
+ 字符串是以单引号'或双引号"括起来的任意文本，如果'本身也是一个字符，那就可以用""括起来。
+ 转义字符\可以转义很多字符，比如\n表示换行，\t表示制表符，字符\本身也要转义，所以\\\表示的字符就是\。
+ 如果字符串里面有很多字符都需要转义，就需要加很多\，为了简化，Python还允许用r''表示''内部的字符串默认不转义。
+ 空值是Python里一个特殊的值，用None表示。
+ 常量就是不能变的变量，比如常用的数学常数π就是一个常量。在Python中，通常用全部大写的变量名表示常量。
+ python有两种除法：“/”结果为浮点数，“//”结果为整除。
+ int()函数发现一个字符串不是合法的数字时就会报错并退出。

### 各节需注意
#### python_1
+ python3.5中，print是一个函数，需要括号（）。
+ print()函数也可以接受多个字符串，用逗号“,”隔开，遇到逗号“,”会输出一个空格。
+ print()也可以打印整数，或者计算结果。
+ 输入使用input()方法，input()返回的数据类型是str。
+ python的格式化方式与c语言的一致。
+ 如果你不太确定应该用什么，**%s**永远起作用，它会把任何数据类型转换为字符串。

#### python_2
+ list
    + list是一种有序的集合，可以随时添加和删除其中的元素。
    + len()可以获得list中元素的个数。
    + 使用下标访问元素。
    + 添加元素用insert()方法，删除元素用pop()方法。
    + list里面的元素的数据类型可以不同,其元素可以是另一个list。
    + 如果要取最后一个元素，除了计算索引位置外，还可以用-1做索引，直接获取最后一个元素。
+ tuple
    + tuple和list非常类似，但是tuple一旦初始化就不能修改。
    + 只有1个元素的tuple定义时必须加一个逗号“,”，防止被当作小括号运算。
+ dict
    + Python内置了字典：dict的支持，dict全称dictionary，在其他语言中也称为map，使用键-值（key-value）存储，具有极快的查找速度。
    + dict内部存放的顺序和key放入的顺序是没有关系的。
    + 要删除一个key，用pop(key)方法，对应的value也会从dict中删除
    + **dict的key必须是不可变对象**
+ set
    + set和dict类似，也是一组key的集合，但不存储value。由于key不能重复，所以，在set中，没有重复的key。
    + 通过add(key)方法可以添加元素到set中，可以重复添加，但不会有效果。
    + 通过remove(key)方法可以删除元素。
    + set显示的顺序也不表示set是有序的。
    + **set的key必须是不可变对象**
#### python_3
+ 条件判断
    + 注意不要少写了冒号“:”。
+ 循环
    + for x in ...循环就是把每个元素代入变量x，然后执行缩进块的语句。
    + range()函数可以生成一个整数序列，再通过list()函数可以转换为list。
    + while循环，只要条件满足，就不断循环，条件不满足时退出循环。
    + 在循环中，break语句可以提前退出循环。
    + 在循环过程中，也可以通过continue语句，跳过当前的这次循环，直接开始下一次循环。
    + 利用ctrl+c退出死循环。
#### python_4
+ 函数名其实就是指向一个函数对象的引用，完全可以把函数名赋给一个变量，相当于给这个函数起了一个“别名”。
+ 在Python中，定义一个函数要使用def语句，依次写出函数名、括号、括号中的参数和冒号:，然后，在缩进块中编写函数体，函数的返回值用return语句返回。
+ pass为占位符，为了方便以后添加执行语句。
+ python函数可以返回多个值，其实就是一个tuple。
+ 在语法上，返回一个tuple可以省略括号，而多个变量可以同时接收一个tuple，按位置赋给对应的值，所以，Python的函数返回多值其实就是返回一个tuple，但写起来更方便。
+ 函数在定义时可以设置默认参数，需从右到左含有。
+ **定义默认参数要牢记一点：默认参数必须指向不变对象！**
+ 当不按顺序提供部分默认参数时，需要把参数名写上。比如调用enroll('Adam', 'M', city='Tianjin')n。
+ 定义可变参数和定义一个list或tuple参数相比，仅仅在参数前面加了一个*号。
+ *nums表示把nums这个list的所有元素作为可变参数传进去。
+ 注意定义可变参数和关键字参数的语法：
    + *args是可变参数，args接收的是一个tuple
    + **kw是关键字参数，kw接收的是一个dict。
+ 定义命名的关键字参数在没有可变参数的情况下不要忘了写分隔符*，否则定义的将是位置参数。
+ 如果要限制关键字参数的名字，就可以用命名关键字参数，例如，只接收city和job作为关键字参数。
+ 命名关键字参数必须传入参数名，这和位置参数不同。如果没有传入参数名，调用将报错。
+ **难以理解的是，有关键字参数以及命名关键字参数的函数被调用后会输出None。**
+ 递归函数：如果一个函数在内部调用自身本身，这个函数就是递归函数。
    + 尾递归是指，在函数返回的时候，调用自身本身，并且，return语句不能包含表达式。这样，编译器或者解释器就可以把尾递归做优化，使递归本身无论调用多少次，都只占用一个栈帧，不会出现栈溢出的情况。
#### python_5
+ 



### 篇章标题
+ 注意小点
> 单行代码

### page2

**impotant**  
dafewfew
fesfewf  
fd

```python
print("代码")
```

***