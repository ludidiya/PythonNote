# Python基础{#PythonBase}

## Anaconda与Jupyter

### Anaconda
`Anaconda`指的是一个开源的Python发行版本，其中包含里conda、Python等180多个科学包及其依赖项。

### Jupyter
`Jupyter Notebook`的本质是一个web应用程序，便于创建和共享文档，支持实时代码、数学方程、可视化和markdown。用途包括：数据清理和转化、数值模拟、统计建模、机器学习等等。

### 安装Jupyter Notebook拓展

第一：在终端输入以下代码

```bash
# 终端输入
pip install jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
pip install jupyter_nbextensions_configurator
```

第二：重启jupyter

关于插件的介绍[点击](https://jupyter-contrib-nbextensions.readthedocs.io/en/latest/nbextensions/code_prettify/README_code_prettify.html)

例如：Hinterland拓展会在用户使用jupyter写python代码时提供代码提示

如果安装不成功，卸载拓展包，重新安装。卸载代码如下：

```bash
pip uninstall jupyter_contrib_nbextensions
pip uninstall jupyter_nbextensions_configurator
```

### Jupyter中常用操作

1）jupyter notebook启动

2）jupyter创建文件和文件夹

3）修改文件名

4）运行单元格

5）单元格的添加和删除单元格

### 注意事项

1）不需要{}作为作用域，以缩进确定层级关系；

2）代码的执行顺序：从上到下，从右到左。但是要注意优先级；

3）代码中使用符号的时候，要用英文状态下的标点符号。 

## 语句与注释

**语句**：程序进行编写，执行的每一行代码叫做语句。

**注释**：对代码的解释和说明。可以提供代码的可读性。

注释分为多行注释和单行注释

&emsp; 1）单行注释是以`#`开始

&emsp; 2）多行注释可以使用三对双引号`""" """`或者三对单引号`''' '''`

```python
# 我是单行注释
print(123)
'''
    我是多行注释
    我是多行注释
    我是多行注释
'''
print(123)
"""
    我也是多行注释
    我也是多行注释
    我也是多行注释
"""
print(123)
```

## 变量与赋值

### 变量的定义

**变量**：通俗理解就是存储程序数据的容器。

**变量定义的格式**：`变量名 = 数据` （变量名尽量有含义，方便理解）

**变量类型**：int, str, float, bool

### 变量的命名规则

**变量名**：是由字母、数字、下划线组成,注意是只有这三种，但是不能以数字开头

```python
name = 'Theshy'
name1 = 'Ning'
name_ = 'UZi'
name_2 = 'Ming'
_name = 'doinb'

# 虽然中文作为变量名仍然能运行，但是不建议这样使用
名字 = "Xiaoming"
print(名字)
```

**命名方法**：下划线、小驼峰、大驼峰

```python
hero_name = '鲁班' # 下划线命名法
heroName = '刘备' # 小驼峰 第一个单词首字母要小写，其它单词首字母都大写
HeroName = '元芳' # 大驼峰 每个单词首字母都大写
```

### 关键字

在python里面具有特殊功能的标识符（理解成变量名、函数名）， 关键字不能作为变量名使用，如：

```python
['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```
 
查看python中有哪些关键字：

```python
import keyword
print(keyword.kwlist)
```

### 常用的数据类型转换{#PythonDataType}

```python
name = "马超"  # 字符串
print(name)

skill = 450    # int
print(skill)

money = 1.98   # float
print(money)

is_ok = True   # bool类型  True / False
print(is_ok)
```


```{r, eval=TRUE, echo=FALSE}
knitr::kable(
 data.frame(函数=c("int(x[,base])",
                 "float(x)",
                 "complex(real[,imag])",
                 "str(x)",
                 "repr(x)",
                 "eval(str)",
                 "tuple(s)",
                 "list(s)",
                 "chr(x)",
                 "ord(x)",
                 "hex(x)",
                 "oct(x)",
                 "bin(x)"), 
            说明=c("将x转换为一个整数",
                 "将x转换为一个浮点数",
                 "创建一个复数，real为实部，imag为虚部",
                 "将对象x转换为字符串",
                 "将对象x转换为表达式字符串",
                 "用来计算在字符串中的有效Python表达式，并返回一个对象",
                 "将序列s转换为一个元组",
                 "将序列s转换为一个列表",
                 "讲一个整数转换为一个Unicode字符",
                 "将一个字符转换为它的ASCII整数值",
                 "将一个整数转换为一个十六进制字符串",
                 "将一个整数转换为一个八进制字符串",
                 "将一个整数转换为一个二进制字符串")),
 booktabs = TRUE,
 caption = '数据类型之间强制转换常用的函数'
)
```

## 输入和输出

### Python中的输出
指在控制台中输出，或者是将准备要输出的内容输出到相应的设备上，如手机上看到的文字、图片、视频等数据。其实本质上也是程序员敲代码输出到手机上的。

认识`print()`函数中两个重要的参数：

1）end = '\n' (默认有换行符)

2）sep = ' ' (默认字符串间分隔符是空格)

3）jupyter快捷键：光标放在函数处，键盘`shift + Tab`查看函数文档

```python
print('Hello world!')

print(100 + 200)

str1 = 'Hello'
str2 = 'World'

# 认识print函数里两个重要的参数
# 1）end = '\n' 默认有个换行符
print(str1)  # 默认有个换行符
print(str2)
## Hello
## World

print(str1,end='---')
print(str2)
## Hello---World

# 2) sep = ' ', 字符串间的分隔符，默认是个空格
print(str1,str2)
## Hello World
print(str1,str2,sep='**')
## Hello**World
```

### 格式化输出{#FormattingOutPut}

```{r, eval=TRUE, echo=FALSE}
knitr::kable(
 data.frame(格式化符号=c("%s",
                    "%d",
                    "%f",
                    "%x"),
            说明=c("输出字符串",
                 "输出int类型数字",
                 "输出浮点数",
                 "输出16进制数据")),
 booktabs = TRUE,
 caption = '格式化输出符号'
)
```

比如：其中字符串内的%叫做占位符

```python
PI = 3.1415926
print("PI的值是%.2f" %PI) # 保留两位小数
## PI的值是3.14

job = "数据分析师"
money = 25000
print("%s的月薪是：%d" %(job,money))
## 数据分析师的月薪是：25000

# 或者使用format()，其中{}内可以设置数字
print("{}的月薪是：{}".format(job,money))
## 数据分析师的月薪是：25000
print("{1}的月薪是：{0}".format(job,money))
## 25000的月薪是：数据分析师
```

### Python中的输入

利用`input()`函数可以实现用户交互，并接收用户输入传递给变量，以供后续使用。

```python
fileName = input('请输入文件名字：')
print(fileName)
```

## 运算符{#PythonMathOperator}

```{r, eval=TRUE, echo=FALSE}
knitr::kable(
 data.frame(运算符=c("+",
                    "-",
                    "*",
                    "/",
                  "//",
                  "%",
                  "**"),
            说明=c("加",
                 "减",
                 "乘",
                 "除",
                 "取整数",
                 "取余",
                 "指数"),
            例子=c("x+y = 30",
                 "x-y = -10",
                 "x*y = 200",
                 "y/x = 2",
                 "z//x = 2",
                 "z%y = 5",
                 "x**5 = 100000")),
 booktabs = TRUE,
 caption = '算数运算符（x=10, y=20, z=25）'
)
```

混合运算时，优先级顺序为：`**`、`*` `/` `%` `//`、`+` `-`，为了避免歧义，建议使用()来处理运算符优先级。并且，不同类型的数字在进行混合运算时，整数将会转换为浮点数进行运算。

### 算数运算符（拓展）

```{r, eval=TRUE, echo=FALSE}
knitr::kable(
 data.frame(运算符=c("int(num1)",
                    "round(num1)",
                    "round(num1,3)"),
            说明=c("float转int类型，取整，不四舍五入",
                 "取整，四舍五入",
                 "保留三位小数，四舍五入"),
            结果=c("3",
                 "4",
                 "3.642")),
 booktabs = TRUE,
 caption = '算数运算符（num1 = 3.6415）'
)
```

要求：num1=3.6415，保留三位小数，不四舍五入

显然上面的函数都不能满足要求，我们可以通过运算符号来实现目的，代码如下：

```python
num1 = 3.6415
print(num1*1000//1/1000)
### 3.641
```

## if...elif...else

```python
age = 18

if age >= 18:
    print('Your age is', age)
    print('Adult')
else:
    print('Your age is', age)
    print('Juvenile')
```

可以用`elif`做更精细的判断：

```python
age = 6
if age >=18:
    print('成年')
elif age >=7:
    print('青少年')
else:
    print('儿童')
```

## 循环语句

程序的三大执行流程：

（1）顺序执行

（2）选择执行

（3）循环执行

### while循环

**死循环**：无限次执行
```python
num = 1

while num <= 5:
    print(num)
```

使用`while`时，需要指定循环终止条件

```python
num = 1
while num <= 5:
    print(num)
    num = num + 1
```

### for循环

```python
for i in range(1,5):
    print(i)
```

```python
names = ['Mike','Hua','Jan']
for name in names:
    print(name)
```

### break

输出1-10之间的数，

```python
num = 1
while num <= 10:
    if num > 8:
        break 
        # break语句会结束当前循环
        # 如果此条件满足，下面最外层循环里的语句都不再执行
    print(num)
    num = num + 1
print('END')
```

输出：

```
1
2
3
4
5
6
7
8
END
```

### continue

**死循环**：num永远卡在num=8的时候，最后一个END也不会被输出

```python
num = 1
while num <= 10:
    if num == 8
        continue
    # num = 8 后下面的代码都不再运行
    print(num)
    num = num + 1
print('END')
```

怎么改代码呢？把累加放在continue前面:

```python
num = 1
while num < 10:
    num = num + 1
    if num == 8:
        continue
    print(num)
print('END')
```

## 练习

### 打印10以内的奇数

```python
num = 0
while num < 10:
    num = num + 1
    if (num%2==0):
        continue
    print(num)
print('END')
```

### 程序输出随机数

产生一个随机4位数：

```python
import random
argot = ''
for index in range(4):
    argot = argot + str(random.randint(0,9))
print(argot)
```

要求： 程序随机生成一个个位整数，用户有3次猜的机会，如果3次都没有猜对程序退出，并告知答案，猜对了直接退出。

```python
# 程序随机生成一个两位数
numtemp = ''
for index in range(2):
    numtemp = numtemp + str(random.randint(0,9))
num = int(numtemp)

# count 控制答题次数，只有5次机会
count = 0
while count < 5:
    answer = int(input('请输入100以内任意一个两位数：'))
    if answer > num:
        print('大了')
    elif answer < num:
        print('小了')
    elif answer == num:
        print('恭喜你猜对了')
        # 猜对了，程序直接退出
        break
    count = count + 1
# 3次都没猜对，程序给出正确答案
else:
    print('很遗憾5次都没猜对，正确答案是：',str(num))
```


