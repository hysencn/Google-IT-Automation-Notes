# Python 的数据类型

## 概念: 什么是代码？

代码是现实世界事物在计算机世界中的映射

- 什么是写代码？写代码是将现dd'd实世界中的事物用计算机语言来描述

  

## number: 数字

> **Python**
> 整数, int
> 浮点数: float (python 的浮点数是其他语言的双精度)

> **其他语言**
> 其他语言：单精度(float ) ,双精度( double)
> 其他语言： short, int, long

```python
## 数据类型举例:

type(1)
<class 'int'>    ## 整数类型
type(-1)
<class 'int'>   
type(-1.1)
<class 'float'>    ## 浮点数类型
type(-1.1111111)
<class 'float'>
1+0.1
1.1

type(1+0.1)
<class 'float'>
type(1+1)
<class 'int'>
type(1 + 1.0)
<class 'float'>
 
```

> Windows 下 idel 没有好的清屏方法, 关闭再开最好. mac 的 terminal 中可以 ctrl + l 解决

```python
## Python 中除法如何取到整数类型

type(2/2)
<class 'float'>
## 因为: >>> 2/2 的输出结果是数值 1.0

type(2//2)
<class 'int'>d

```

### 3-3 10, 2 , 8, 16 进制

```
type(2/2)
<class 'float'>
>>> type(2//2)
<class 'int'>
>>> type(1//2)  ## 整除, 获得的是 int. 只保留整数部分
<class 'int'>
>>> 1//2    
0
>>> 
```

>  进制是人类计数的一种方式.

10 进制 满 10 进 1.
1, 2, 3,.....9, 10

以此类推:

二进制: 0.1,10

八进制: 0.1,2....7,10,

十六进制: 0, 1, 2, ......9, a, b, c, d, e, f, 10

在 ptyhon 里如何表示各种进制.

时间是 60 秒 = 1 分

### 3-4 各进制的表示与转换

如何在不同的进制里进行区分, 如何转换

```
## 0b 开头表示是二进制
>>> 0b10
2
>>> 0b11
3
>>> 

```

  8 进制

```
## 0o 开头表示八进制
>>> 0o10
8
>>> 0o11
9
```

16进制

```
## 0x 开头表示十六进制
>>> 0x10
16
>>> 0x11
17
0x1F
31  ## 为什么?
```

## 如何在进制之间转换

### bin() 向二进制转换 

```python

### 10进制, 8 进制,16 进制 0, 1 转换结果
#### 转换 0 
>>> bin(0)
'0b0'
>>> bin(0o0)
'0b0'
>>> bin(0x0)
'0b0'

#### 转换 1
>>> bin(1)
'0b0'
>>> bin(0o1)
'0b1'
>>> bin(0x1)
'0b1010'


### 10 进制, 8 进制, 16 进制的数值`10`的二进制表示方法:
>>> bin(10)
'0b1010'
>>> bin(0o12)
'0b1010'
>>> bin(0xa)
'0b1010'
```



### ## oct() 向八进制转换 

```python
### 各进制数值"10"的八进制转换

>>> oct(10)  
'0o12'
>>> oct(0b1010)
'0o12'
>>> oct(0xa)
'0o12'
```

### hex() 向十六进制转换

```python
## 各进制数值"10"的十六进制转换

>>> hex(10)
'0xa'
>>> hex(0b1010)
'0xa'
>>> hex(0o12)
'0xa'

```

### int() 向十进制转换

```python
## 各进制数值"10"的十进制转换

>>> int(0b1010)
10
>>> int(0o12)
10
>>> int(0xa)
10
```

###  

> 总结:
>
> int() 向十进制转换
> bin() 向二进制转换
> oct() 向八进制转换
> hex() 向十六进制转换

## bool 布尔类型

### 为何布尔类型归为数字类型

```python
## 布尔的类型举例

>>> True
True
>>> False
False

>>> type(True)
<class 'bool'>
>>> type(False)
<class 'bool'>

## 通过数字类型说明布尔归类于 number 类型的原因

>>> int(True)   ## 十进制转换 True
1
>>> int(Flase)
0

>>> bool(1)
True
>>> bool(0)
False
>>> 
```



> - 是不是只有数字 1 表示 True, 数字 0 表示 False?
>
>   ```python
>   >>> bool(2)
>   True
>   >>> bool(2.2)
>   True
>   >>> bool(-1.1)
>   True
>   >>> bool(0)
>   False
>   ```
>
>   **结论: 只有 0 表示 False, 其他非 0 的数值都表示布尔 True**

```python
## 其他数据类型的布尔示例:

>>> bool (1) 
True
>>> bool (0)
False

>>> bool ('abc')       ## 非空字符串的布尔值为 True
True
>>> bool ('')          ## 空字符串的布尔值为 False
False

>>> bool ([1, 2, 3])    ## 非空 list 的布尔值为 True
True
>>> bool ([])           ## 空 list 的布尔值为 False
False

>>> bool ({1, 1, 1})   ## 非空 array 的布尔值为 True
True
>>> bool ({})          ## 空 array 的布尔值为 False
False

>>> bool (None)        ## None 是比较特殊的值, 后面会讲到
False

```

**总结: 
在 python 中, 简单可以认为, 0 以及空值都被认为是 False, 非空值是 True.** 
**None 的类型比较特殊, 它也是 False**



## 单引号和双引号

复数: 例如`36j`

> 学习方法:
> 初学者: 抓大放小, 语言的知识点是非常多的, 不可能全部学习完成. 对于生僻的知识点, 
> 以后碰到需要使用的时候, 再去查找观看.

### str 字符串

如何表示字符串: 单引号, 双引号, 三引号

引号需要成对出现:

```python
## 一种需要用到单双引号的情况: 字符串内有英文祈使句

"let's go"
'let\'s go'  ### 第二种方法使用
```

每行字符建议 79 个字符. 输入超过 79 字符使用三引号换行

```python
## 三引号换行举例:

>>> '''
... hello world
... hello world
... '''
'\nhello world\nhello world\n'
>>> """
... hello world
... hello world
... """
'\nhello world\nhello world\n'
```

回车或者 tab 键都是一个字符, 会有相应的字符显示在 python 里.
enter 键的转义字符是 \n

```python
## 如何使用 enter 键的转义符 \n

>>> """hello world\nhello world\nhello world""" ## 直接输入 `/n` 只会得到相应的字符串
'hello world\nhello world\nhello world'         ## 输出

>>> print("""hello world\nhello world\nhello world""") ## 使用 print(), 即可得到相应的输出结果
hello world
hello world
hello world

>>> print("hello world\nhello world\nhello world")     ## 同样字符串内容使用双引号举例, 结果一致
hello world
hello world
hello world

>>> print('hello world\nhello world\nhello world')     ## 同样字符串内容使用单引号举例, 结果一致
hello world
hello world
hello world
```

常见使用上的理解误区:

三引号习惯上, 作为单独一行

```python

"""hello world      ## 这个很不优雅, 但不会报错
... hello world"""

    # output: 'hello world\nhello world'
```

单引号也可以用作换行输出

```python
## 使用转义符反斜杠换行

>>> 'hello\
...  world'    ## note:空格在第二行

'hello world'  ## 输入了完整的一行. 

```

总结: 换行的几种方式



### 3-8 转义字符

特殊的字符:

1. 无法看见的字符:
2. 与语言本身语法有冲突的字符 \n \' \t

```
\n 换行
\' 单引号
\t 横向制表符
```



区别: /r 和 /n...自己查查资料

```python
## 作业, 输出 "'hello \n world'"

>>> print('hello \\n world')
hello \n world
>>> print("'hello \\n world'")
'hello \n world'
>>> print('''"'hello \\n world'"''') ## 三引号输出: 双引号 + 单引号
"'hello \n world'"
```

### 3-9 原始字符串

转义符的实际应用

```python
## 输出一个目录:c:\northwind\\northwest
>>> print('c:\\northwind\\northwest')
c:\northwind\northwest

## 目录很长时的解决方法
>>> print(r' c:\northwind\northwest')
 c:\northwind\northwest  ## 前面有一个空格输出
>>> print(r'c:\northwind\northwest')
c:\northwind\northwest   ## 无空格输出

```

`r`表示后面跟着的**不是一个普通字符串, 而是一个原始字符串**

```python
## r 的错误用法示例
无论是 >>> print(r'le's go')
还是 >>> print(r'"le's go'")

## 都会报错, 因为出现了多引号
    
```

### 3-10 字符串运算

#### 合并字符串

```python
## 几个实际例子:

## "hello" 和 "world" 表示为 "hello world"
>>> "hello" + "world"
'helloworld'

## "hello"*3 的输出结果会是什么?

>>> "hello"*3
'hellohellohello'
```



#### 提取指定序号的字符串:

```python
>>> "hello world"[0]
'h'
>>> "hello world"[3]
'l'
>>> "hello world"[4]
'o'
>>> "hello world"[-1]
'd'
```

> [-n] 从末尾开始计数, 起始序数是 -1
> [n]  从字符串开始计数, 起始序数是 0

```python
## 提取一段字符

>>> "hello world"[0:5]
'hello'
>>> "hello world"[0:4]
'hell'
>>> "hello world"[0:-1]
'hello worl'
>>> "hello world"[0:-4]
'hello w'

```

#### 作业

```python
## 从 "hello world"中输出 world

>>> "hello world"[6:10]  ## 少一位
'worl'
>>> "hello world"[6:11]  
'world'
>>> "hello world"[6:20]  ## 尝试超出范围的数值
'world'
```

### 提取一段字符串之截头去尾

````python

## 示例
 
"hello python java c# javascript php ruby"    ## 原始字符串

## 要求输出:'python java c# javascript php ruby'
>>> "hello python java c# javascript php ruby"[6:]
'python java c# javascript php ruby'

## 要求输出:'ruby'的方法

>>> "hello python java c# javascript php ruby"[-4:]
'ruby'           ## 复数在冒号前面的意义, 从指定的序列位置开始, 一直取到字符串的末尾. 

## 常见的错误, 可以看出[0:-4] 等效于 [:-4]
>>> "hello python java c# javascript php ruby"[:-4]
'hello python java c# javascript php '
>>> "hello python java c# javascript php ruby"[0:-4]
'hello python java c# javascript php '
 
 
````

##### 原始字符的 `r` 或 `R`

```python
## 原始字符串, r 大小写等效

>>> r'C:\Windows'
'C:\\Windows'
>>> R'C:\Windows'
'C:\\Windows'    ## 上下等效

## 三种等效输出
>>> print('C:\\Windows')
C:\Windows
>>> print(r'C:\Windows')
C:\Windows
>>> print(R'C:\Windows')
C:\Windows    ## 三者等效

print()
```











## 概念

无法看见的字符:换行, tab, enter键

Double flash "//" called floor division. 取商