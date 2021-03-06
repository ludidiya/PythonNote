- [Python数据容器{#PythonDataContainers}](#python------pythondatacontainers-)
  * [字符串（str）](#----str-)
    + [下标和切片](#-----)
    + [字符串常见内置函数{#StrBuildInFunctions}](#-----------strbuildinfunctions-)
  * [列表（list）](#---list-)
    + [列表常用操作{#ListBuildInFunctions}](#--------listbuildinfunctions-)
  * [元组（tuple）](#---tuple-)
  * [字典（dict）](#---dict-)
    + [字典常见操作{#DicBuildInFunctions}](#--------dicbuildinfunctions-)
  * [集合（set）](#---set-)
    + [交集/并集](#-----)
  * [拓展：可变类型&不可变类型{#VariableAndInvariable}](#---------------variableandinvariable-)
  * [练习](#--)
    + [字符串遍历](#-----)
    + [获取列表中相同元素对应的索引，并保存到字典中](#----------------------)

<small><i><a href='http://ecotrust-canada.github.io/markdown-toc/'>Table of contents generated with markdown-toc</a></i></small>

# Python数据容器{#PythonDataContainers}

## 字符串（str）

定义： 只要使用引号('xx', "xx", """jjj""", '''xxx''') 引起来的数据就叫做字符串

```python
my_str = 'hello' 
print(type(my_str))
# <class 'str'>
```

**单双引号嵌套**
```python
print("fadf'af'")
print('"文字"')
```

### 下标和切片

**字符串索引**
```python
my_str = 'hello'   
print(my_str[0])
print(my_str[4])
print(my_str[-1]) # 取字符串倒数第一个
print(my_str[-2]) # 取字符串倒数第二个
# h
# o
# o
# l

len(my_str) # 判断字符长度
print(my_str[len(my_str) - 1])
```

**切片**

切片: 根据下标的范围获取一部分数据，比如: 列表，字符串可以使用切片

切片的使用格式：数据[起始下标:结束下标:步长]，e.g. `my_str[0:1]`

提示： 起始下标默认0， 结束下标是不包含（python下标左闭右开）， 步长默认是1。

```python
str = 'Hello'
str[0:2]
# 'He'
str[:2]  # 起始为0可以省略
# 'He'
my_str[-5:-3]
# 'He'
my_str[-1:-6:-1] # 把字符串倒序输出
# 'olleh'
```

### 字符串常见内置函数{#StrBuildInFunctions}

* **增/字符串连结**
  * str.join(mystr)
  * '%s%s%s'%('hello',' ','world')
  * '{}{}{}'.format('hello',' ','world')
  * f"{'hello'}{' '}{'world'}"
  * 'hello' + ' ' + 'world'

* **删**
  * mystr.strip() 默认删除两边空格
  * mystr.lstrip()
  * mystr.rstrip()

* **改**
  * mystr.replace(str1, str2, mystr.count(str1))
  * mystr.split(str = ' ', 2)
  * mystr.splitlines()
  * mystr.capitalize()
  * mystr.title()
  * mystr.lower()
  * mystr.upper()
  * mystr.ljust()
  * mystr.rjust()
  * mystr.center(width)
  * mystr.partition(str)
  * mystr.rpartition(str)

* **查**
  * mystr.find(str, start, end)
  * mystr.rfind(str, start, end)
  * mystr.index(str, start, end)
  * mystr.rindex(str, start, end)
  * mystr.count(str)
  * mystr.startswith(str)
  * mystr.endswith(str)
  
  
```{r, eval=TRUE, echo=FALSE}
knitr::kable(
 data.frame(函数=c("str.index('l')",
                 "str.rindex('l')",
                 "str.find('h')",
                 "len(str)",
                 "str.count('l')",
                 "str.replace('l', 'x')",
                 "str.split('e')",
                 "str.capitalize()",
                 "str.title()",
                 "str.upper()",
                 "str.lower()",
                 "str.startswith('h')",
                 "str.endswith('h')",
                 "str.strip('h')",
                 "str.lstrip()",
                 "str.rstrip()",
                 "'abc'.isalpha()",
                 "'123'.isdigit()",
                 "'abc'.isalnum()",
                 "'12'.join('abc')"), 
            说明=c("从左查找字符串中第一次出现的某个字符的下标，结果是2",
                 "从右查找字符串中第一次出现的某个字符的下标，结果是3",
                 "根据指定字符查找对应的下标，结果是2。find 和 index的区别, find如果没有找到数据那么返回的结果是-1",
                 "统计字符串长度",
                 "统计某个字符在字符串中出现次数，结果是2",
                 "替换字符串中指定数据（原字符串不变)，新的结果可赋值给新的变量",
                 "分隔符，默认为所有的空字符，包括空格、换行`\\n`、制表符`\\t` 等",
                 "如果str = 'hello world', 结果为'Hello world'，只有首个单词首字母大写",
                 "如果str = 'hello world', 结果为'Hello World'，每个单词首字母都大写",
                 "把所有字符中的小写字母转换成大写字母",
                 "把所有字符中的大写字母转换成小写字母",
                 "判断是否以指定数据开头",
                 "判断是否以指定数据结尾",
                 "去除两边指定数据，不填默认去除两边空格",
                 "去除左边空格",
                 "去除右边空格",
                 "判断是不是全是字母",
                 "判断是不是全是数字",
                 "判断有数字或字母或都有",
                 "向abc每个元素后面都插入12，构造一个新字符串，结果为`a12b12c`")),
 booktabs = TRUE,
 caption = 'Python字符串内置函数（str = "hello"）'
)
```


## 列表（list）

### 列表常用操作{#ListBuildInFunctions}

列表： 以中括号表现形式的数据集合， 比如: [1, 1.2, 'bac', True]

python列表里面可以放入任意类型数据，c语言中的数组必须是同一个类型

* 查
  * mylist.len() 列表长度
  * mylist[下标] 当下标/索引超出范围会报错，索引`-1`表示获取最后一个元素
  * mylist[起始：终止：步长]
  * mylist.index('objext',start,end) 查看元素index
  * mylist.count('objext') 


* 增
  * mylist.append(object)
  * mylist.append(OtherList) 将另一个集合中的元素逐一添加到列表中
  * mylist.insert(index, object) 在指定位置`index`**前**插入元素object
  

* 改
  * mylist[1] = 'zhangsan' 确定要修改的元素索引，直接重新赋值，覆盖原来的即可
  * mylist.reverse() 将list倒序
  * mylist.sort(reverse=TRUE) 重新排序，默认小到大，reverse参数设定为true后可改为倒序
  

* 删
  * del mylist[2] 根据下标进行删除
  * mylist.pop() 删除最后一个元素
  * mylist.remove('a') 根据元素的值进行删除


## 元组（tuple）

python有另一种有序列表叫元组`tuple`。`tuple`和`list`类似，但是`tuple`一旦初始化就**不能被修改**。

```python
classmates = ("Micheal","Bob","Tracy")
```

现在classmates这个tuple就不能变了，不能像列表那样使用`append()`, `insert()`这样的方法。其他获取元素的方法和list是一样的。

不可变的tuple有什么意义？因为tuple不可变，所以代码更安全。如果可能，能用tuple代替list就尽量使用tuple。

如果要指定一个空tuple，写成`t = ()`即可。

但是，要定义一个只有一个元素的tuple，尤其是当这仅有的一个元素是数字的时候，如果写成`t = (1)`就会有歧义。这样写并不是创建了一个只含一个元素的tuple，而是创建了数字1。因为，python会把括号当作运算中的括号。为了消除歧义，当创建一个元素的tuple时可以写成：

```python
t = (1,)
t
# (1,)
```

**"可变的"tuple:**

当tuple元素内部有列表时，列表可以更改

```python
t = ("a","b",["A","B"])
t[2][0] = "X"
t[2][1] = "Y"
t
# ("a","b",["X","Y"])
```

## 字典（dict）

字典可以存储任意类型对象。

字典的每个键值对`key:value`用冒号分割，每个对之间用逗号`,`分割，整个字典包含在花括号`{}`中。

```python
dic = {"Michael":97, "Bob":89, "Tracy":92}
dic["Michael"]
# 95
```

### 字典常见操作{#DicBuildInFunctions}

* 修改元素
  * mydic['id'] = int(1245) 若原来就有id这个键，则覆盖掉原来的id对应的value
  
* 添加元素
  * mydic['id'] = int(1245) 若原来字典里没有id这个键，则新增
  
* 删除元素
  * del mydic["id"]
  * del mydic  删除整个字典
  * mydic.clear()  清空整个字典

* 查询
  * len(mydic)
  * list(mydic.keys())  返回一个字典所有的key的列表
  * list(mydic.values())  返回一个字典包含的所有value的列表
  * list(mydic.items())  返回一个包含所有键值对的元组的列表
  
## 集合（set）

`set`是一个无序的不重复元素序列。

可以使用大括号`{}`或者`set()`函数来创建集合；而创建一个空的集合**必须**使用`set()`函数，因为`{}`是用来创建空的字典的。

* 集合不支持下标赋值和取值

* 可以通过遍历获取数据

* 集合函数`set()`可以对容器类型数据去重

* 列表、元组、结合三者之间可以相互转换

```python
# 创建集合
myset = {1,4,"abc","hello"}

# 对容器类型数据去重
mylist = [1,2,1,2,3]
myset = set(mylist)
print(myset)
# [1, 2, 3]
```

### 交集/并集

```python
set1 = {1,3,5,7}
set2 = {1,2,3,5}

# #交集
print(set1 & set2)
print(set1.intersection(set2))

# #并集
print(set1 | set2)
print(set1.union(set2))

# #差集A－B＝{x|x∈A，且x不属于B}
print(set1-set2)
print(set1.difference(set2))

print(set2-set1)
print(set2.difference(set1))

# #是否是子集
set1 = {1,3,5,4}
set2 = {1,2,3,5}
print(set1.issubset(set2)) #set1是set2的子集
```

## 拓展：可变类型&不可变类型{#VariableAndInvariable}

**可变类型**：可以在原有数据的基础上对数据进行修改(添加或者删除或者修改数据)，修改后内存地址不变。列表，集合，字典，对数据进行修改后内存地址不变。

**不可变类型**: 不能在原有数据的基础上对数据进行修改，当然直接赋值一个新值，那么内存地址会发生改变。字符串，数字，元组，不能再原有数据的基础上对数据进行修改。

```python
# # 列表的可变演练
my_list = [1, 5, 6]
print(my_list, id(my_list)) # 查看内存地址
# [1, 5, 6] 4475084304
my_list.append(7)
print(my_list, id(my_list))
# [1, 5, 6, 7] 4475053152

# # 字符串的不可变演示
my_str = "hello"
print(my_str, id(my_str))
# hello 4477091504
result = my_str.replace('e','a')
print(my_str, id(result))
# hello 4477635888


```


## 练习

### 字符串遍历

**1. 单个元素一行输出整个字符串**

```python
mystr = 'My name is Python'

# enumerate(mystr) 会直接生成一个字符串下标和元素对应的字典
for index, value in enumerate(mystr):
    print(value)
```

**2. 倒序输出字符串**

```python
mystr = input("Please type a string: ")
# 方法一： 切片
print("切片："+mystr[::-1])

# 方法二： reverse()函数，先转化为list再reverse
lst = list(mystr)
lst.reverse()
print(''.join(lst))

# 方法三：字符串的倒序遍历
i = len(mystr) -1
str_list = []
while(i>=0):
    str_list.append(mystr[i])
    i = i - 1
print(''.join(str_list))
```

### 获取列表中相同元素对应的索引，并保存到字典中

例如：[1, 2, 3, 3, 2, 1]  -> {1:[0,5], 2:[1,4], 3:[2,3]}

```python
list = [1, 2, 3, 3, 2, 1]
dic = {}
myset = set(list) # 去重
# {1, 2, 3}

for key in myset:
    i = 0
    value = []
    # i计算原始列表中元素索引
    for i in range(len(list)):
        if list[i] == key:
            value.append(i)
        i = i + 1
    dic[key] = value

print(dic)
```
