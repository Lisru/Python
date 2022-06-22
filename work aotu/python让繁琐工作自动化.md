

# 1、input()函数：输入

```python
name = input()
```



# 2、range()函数

```python
//1.一个参数时，输出为0，1，2，3，4，5，6，7，8，9
range(10)
//2.两个参数时，输出为2，3，4，5
range(2,6)
//3.三个参数时，输出为0，2，4，6，8
range(0,10,2)
```



# 3、导入模块

## import语句

导入模块后，就可以使用该模块中的所有函数。

```python
import random
for i in range(5):
    print(random.randint(1,10))
```

## from import语句

这种形式调用random模块中的函数时不需要random.前缀，但是使用完整的名称会让代码更具可读性，所以推荐使用import语句。

```python
from random import *
```



# 4、sys.exit()函数

让程序提前终止或退出，因为函数在sys中，所以需要导入sys模块。

```python
import sys

while True:
    print('Type exit to exit')
    response = input()
    if response == 'exit':
        sys.exit()
    print('You type'+response+'.')
```



# 5、print()函数

print()函数有可选的变元end和sep，print()函数会自动在传入的字符串末尾添加换行符，可以设置end关键字参数，将他变成另一个字符串。

```python
print('hello',end='')
print('world')
```

输出的结果就会像helloworld一样。

如果向print()函数传入多个字符串值，该函数就会自动用一个空格分隔他们。可以传入sep参数，替换掉默认的分割字符串。

```python
print('cats','dogs','mice',sep=',')
```



# 6、global语句

如果需要在一个函数内修改全局变量，就使用global语句。如果在函数的顶部有global eggs这样的代码，它是在高速Python，在这个函数中，eggs指的是全局变量，不要用这个名字创建局部变量，下面程序执行结果为spam。

```python
def spam():
    global eggs
    eggs = 'spam'

eggs = 'global'
spam()
print(eggs)
```



# 一、列表

## indix()查找值

```python
spam = ['cats','dogs','mice']
spam.index('cats')
```

结果返回0



## 删除列表中的一个值

```python
spam = ['cats','dogs','mice']
del spam[0]
```

把spam中的 ’cat‘ 删除了

### remove()

如果一个值在列表中出现多次，只删除第一次出现的值

```python
spam = ['cats','dogs','mice']
spam.remove('cats')
```





## 添加一个值

```python
list = [1,2,3,4]
list = list + [5]
```

### append()

```python
spam = ['cats','dogs','mice']
spam.append('bat')
```

### insert()

```python
spam = ['cats','dogs','mice']
spam.insert(1,'chicken')
```



## in 和 not in 操作符

判断一个值是否在列表中

```python
spam = ['cats','dogs','mice']
'cats' in spam
'dogs' not in spam
```



## 多重赋值

变量的数目和列表的长度必须严格相等，否则会给出ValueError错误

```python
cat = ['fat','black','loud']
size, color,disposition = cat
```



## enumerate()函数

enumerate()函数将返回两个值，列表中表项的索引和列表中的表项本身。

```python
supplies = ['pen','staplers','flamethrowers','binders']
for index,item in enumerate(supplies):
    print('index'+str(index)+' in supplies is:'+ item)
```



## sort()排序

```python
spam = [2,5,3.14,1,-7]
spam.sort()					//从小到大
spam.sort(reverse = True)	//从大到小
```



# 二、元组

元组不可变，输入时用圆括号

```python
eggs = ('hello', 42, 0.5)
```



# 用list()和tuple()函数转换类型

```python
tuple(['cat','dog','5'])
list(('cat','dog','5'))
```



# 三、字典

字典的索引可以使用许多不同的数据类型，字典输入时带花括号

```python
maCat = {'size':'fat','color':'gray','disposition':'loud'}
```

因为字典不排序的，所以不能向列表那样切片



## values()方法

```python
spam = {'color':'red','age':42}
for v in spam.values():
    print(v)
```

输出为‘red’,42



## keys()方法

```python
spam = {'color':'red','age':42}
for v in spam.keys():
    print(v)
```

输出为‘color’,‘age’



## items()方法

```python
spam = {'color':'red','age':42}
for i in spam.items():
    print(i)
```

输出为包含键值对的元组('color','red')('age',42 )



## get()方法

检查键是否存在于字典中，他有两个参数，分别为要取得其值的键，以及当该键不存在时返回的备用值

```python
picnicItem = {'color':'red','age':42}
picnicItem.get('age',0)		//返回42
picnicItem.get('egg',0)		//返回0，因为字典中不存在egg键
```

# 四、字符串

## 字符串前缀

### r

表示原本的字符串，没有转义

```python
pirnt(r'That is Carol\'s cat')
```

输出为 That is Carol\\'s cat。



### f

字符串插值

```python
name = 'Al'
age = 4000
f'My name is {name}. Next year I will be {age+1}'
```

输出为 My name is Al. Next year I will be 4001。



## 字符串方法

​	这些方法不改变字符串本身，返回一个新的字符串。

### upper()

```python
'Hello'.upper()
```

输出为HELLO。

### lower()

```python
'Hello'.lower()
```

输出为hello。

### isupper()

返回一个布尔值

```python
'Hello'.isupper()	#False
'HELLO'.isupper()	#True
```



### islower()

```python
'Hello'.islower()	#False
'hello'.islower()	#True
```



### join()

```python
>>>','.join(['cats','rats','bats'])
'cats,rats,bats'
>>>' '.join(['My','name','is','Simo'])
My name is Simo
```



### split()

split方法默认空格分隔，也可以向split方法中传入一个分隔字符串。

```python
>>>'My name is Simo'.split()
['My','name','is','Simo']
>>>'cats,rats,bats'.split(',')
['cats','rats','bats']
```



##  pyperclip模块

### copy()函数和paste()函数

```python
import pyperclip
pyperclip.copy('Hello, world!')
pyperclip.paste()
```

输出为Hello, world!，如果你的程序之外的某个程序改变了剪切板的内容，那么paste()函数就会返回改后的内容。



# 五、正则表达式

## 基本语法

1、用import导入正则表达式模块

2、用re.compile()函数创建一个Regex对象

3、向Regex对象的search()方法传入想查找的字符串，它返回一个Match对象

4、调用Match对象的group()方法，返回实际匹配文本的字符串

```python
import re
phoneRegex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d')
mo = phoneRegex.search('My number is 123-456-7890')
mo.group()
```

## 用括号分组

添加括号在正则表达式中创建‘分组’，然后从分组中获取匹配的文本。

第一个括号是第一组，第二个括号是第二组，传入0或不传参数，将返回整个匹配的文本。

想一次获取左右的分组，用groups()方法，返回多个值的元组。

```python
import re
phoneRegex = re.compile(r'(\d\d\d)-(\d\d\d-\d\d\d\d)')
mo = phoneRegex.search('My number is 123-456-7890')
mo.group(1)	#123
mo.group(2)	#456-7890
mo.groups()	#('123','456-7890')
```



## findall()方法

如果在没有分组的正则表达式上调用，将返回一个匹配字符串的列表。

如果在一个有分组的整租表达式上调用，将返回一个字符串的元组列表。

```python
import re
phoneRegex = re.compile(r'\d\d\d-\d\d\d-\d\d\d\d)')
phoneRegex.findall('My number is 123-456-7890 and 890-123-5678')
#['123-456-7890','890-123-5678']

phoneRegex = re.compile(r'(\d\d\d)-(\d\d\d)-(\d\d\d\d)')
phoneRegex.findall('My number is 123-456-7890 and 890-123-5678')
#[('123','456','7890'),('890','123','5678')]
```

## 正则表达式符号

p138页



## sub()方法

第一个参数是一个字符串，用于替换发现的匹配，第二个参数是一个字符串

```python
nameRegex = re.compile(r'Agent \w+')
nameRegex.sub('CENSORED','Agent Alice gave the secret documents to agent Bob')
```

## 参数

向compile()，传入的第二个参数，多个参数同时使用，用管道字符(|)将变量组合起来。

**re.IGNORECASE**:不区分大小写

**re.DOTALL**:让据点字符匹配所有字符，包括换行符

**re.VERBOSE**:忽略正则表达式字符串中的空白符和注释



## 输入验证

### PyInputPlus模块导入

```python
import pyinputplus
```

### PyInputPlus函数

| 函数名          | 作用                                       |
| --------------- | ------------------------------------------ |
| inputStr()      | 字符串                                     |
| inputNum()      | 数字                                       |
| inputChoice()   | 确保用户输入系统提供的选项之一             |
| inputMenu()     | 与上面类似，但提供带有数字或字母的选项菜单 |
| inputDatatime() | 日期                                       |
| inputYesNo()    | 输入为‘yes’或‘no’                          |
| inputBool()     | 接收‘True’或‘False’                        |
| inputEmail()    | 输入有效E-mail地址                         |
| inputFilepath() | 有效的文件路径或文件名                     |
| inputPassword() |用户输入时显示*字符|

### 关键字参数提示

```python
>>>response = input('Enter a number:') #普通输入的关键字参数提示
Enter a number:42		#42

>>>import pyinputplus as pyip
>>>response = pyip.inputInt(prompt = 'Enter a number:')
Enter a number: Cat		#'Cat' is not an integer
Enter a number:42		#42
```

### 关键字参数 min、max、greaterThan、lessThan

接收int和float数的inputNum()、inputInt()和inputFloat()函数具有min、max、greaterThan、lessThan关键字参数：

```python
>>>import pyinputplus as pyip
>>>response = pyip.inputNum('Enter num:3',min = 4)
Enter num:3
Input must be at minnimum 4.	#关键参数提示
```



### 关键字参数blank

在默认情况下，除非将关键字参数blank设置为True，否则不允许输入空白字符。



### 关键字参数limit、timeout、default

默认情况下，pyinputplus模块会一直要求用户提供有效输入，如果希望一定次数后停止要求用户输入，就使用limit和timeout关键字参数。

如果用户未能提供有效输入，会引发RetryLimitException或TimeoutException异常。

设置default参数，输入将默认返回default值，而不是引发异常

```python
import pyinputplus as pyip
response = pyip.inputNum(limit = 2)		#用户可以输入两次

response = pyip.inputNum(timeout = 10)	#输入等待10秒

response = pyip.inputNum(limit = 2,default = 'N/A')		#两次输入无效后，response为N/A
```



### 关键字参数allowRegexes和blockRegexes

用正则表达式确定输入内容

```python
import pyinputplus as pyip
response = pyip.inputNum(allowRegexes=[r'(I|V|X|L|C|D|M)+',r'zero'])	#匹配这些正则

response = pyip.inputNum(blockRegexes=[r'[02468]',r'zero'])	#不匹配这些正则
```



### 自定义验证函数传递给inputCustom()

```python
#输入的数字每位相加等于10
import pyinputplus as pyip

def addsUpToTen(numbers):
    numbersList = list(numbers)
    for i,digit in enumerate(numbersList):
        numbersList[i] = int(digit)
	if sum(numbersList) != 10 :
    	raise Exception('The digits must add up to 10, not %s.'%(sum(numbersList)))
        
response = pyip.inputCustom(addsUpToTen)
```



# 六、读写文件

## pathlib模块

根据不同的系统返回相应的路径格式

```python
from pathlib import Path
Path('spam','bacon','eggs')		#输出为WindowsPath('spam/bacom/eggs')

str(Path('spam','bacon','eggs'))	#'spam\\bacon\\eggs'
```



## ’/‘运算符连接路径

```python
from pathlib import Path
Path('spam')/'bacom'/'eggs'
Path('spam')/Path('bacom'/'eggs')
Path('spam')/Path('bacom','eggs')	#结果都为WindowsPath('spam/bacom/eggs')
```



## 当前工作目录

os.chdir修改当前目录，Path.cwd打印当前目录

```python
from pathlib import Path
import os
Path.cwd()		#WindowsPath('e:/VScode/program/aotu')

os.chdir('C:\\Windows\\System32')
Path.cwd()		#WindowsPath('C:/Windows/System32')
```



## 主目录

```python
Path.home()		#WindowsPath('C:/Users/Administrator')
```



## 创建文件夹

```python
import os
os.makedirs('C:\\delicious\\walnut\\waffles')	#创建delicious,在这个文件夹下创建walnut。。。
```

如果要通过Path()创建文件夹，调用mkdir()方法

```python
Path(r'C:\Users\Al\spam').mkdir()
```

mkdir不像makedirs可以创建多个子目录，mkdir()只能创建一个目录



## 处理绝对路径和相对路径

```python
Path.cwd().is_absolute()	#返回bool值，判断是否为绝对路径

os.path.abspath('.')	#'C:\\Windows\\System32',将相对路径转为绝对路径
os.path.isabs('.')		#是否是绝对路径

os.path.relpath('C:\\Windows','C:\\')	#'Windows'
os.path.relpath('C:\\Windows','C:\\spam\\eggs')		#'..\\..\Windows'
#第一个参数为目标路径，第二个参数为当前路径
```



## 取得文件路径的各个部分

```python
p = Path('C:/User/Al/spam.txt')
p.anchor	#'C:\\'
p.parent	#WindowsPath('C:/User/Al') 返回的是一组Path对象，代表祖先文件，详见p166
p.name		#'spam.txt'
p.stem		#'spam'
p.suffix	#'.txt'
p.drive		#'C:'	仅windows系统有

calcFile = 'C:/User/Al/spam.txt'
os.path.basename(calcFile)	#spam.txt
os.path.dirname(calcFile)	#C:/User/Al
os.path.split(calcFile)		#('C:/User/Al','spam.txt')
```



## 查看文件大小和文件内容

```python
os.path.getsize('C:/User/Al/spam.txt')	#获取文件大小
os.listdir('C:/User/Al')	#列表的形式返回文件夹下的所有文件
```



## 通配符模式修改文件列表

```python
>>>p = Path('.').absolute()
>>>list(p.glob('*'))

[WindowsPath('C:/Windows/System32/0409'),
 WindowsPath('C:/Windows/System32/69fe178f-26e7-43a9-aa7d-2b616b672dde_eventlogservice.dll'),
 WindowsPath('C:/Windows/System32/6bea57fb-8dfb-4177-9ae8-42e8b3529933_RuntimeDeviceInstall.dll'),
 WindowsPath('C:/Windows/System32/@AdvancedKeySettingsNotification.png'),
 WindowsPath('C:/Windows/System32/@AppHelpToast.png'),
 WindowsPath('C:/Windows/System32/@AudioToastIcon.png')]

>>>list(p.glob('*.txt'))	#匹配以'.txt'结尾的文件
>>>list(p.glob('*project?.txt'))	#问好表示任意单个字符

```



## 检查路径的有效性

```python
p = Path('C:\\Windows')

p.exists()	#是否存在
p.is_dir()	#是路径吗
p.is_file()	#是文件吗

#老版
os.path.exists(path)
os.path.isfile(path)
os.path.isdir(path)
```



## 文件读写过程

1、调用open()函数，返回一个File对象

2、调用File对象的read()或write()方法

3、调用File对象的close()方法，关闭该文件

### 打开文件夹

```python
helloFile = open(Path.cwd()/'busy.py')
```

### 读取文件内容

```python
content = helloFile.read()			#单个大字符串

constent1 = helloFile.readlines()	#字符串的列表
```

### 写入文件

```python
baconFile = open('bacon.txt','w')		#覆盖的写入，返回写入的字数
baconFile.write('Hello\n')
baconFile.close()

baconFile = open('bacon.txt','a')		#将在已有的文件末尾添加文本
baconFile.write('bacon is not a vegetable')
baconFile.close()
```



# 七、组织文件

## shutil模块

### 复制文件和文件夹

shutil.copy(source, destination)，将路径 source 处的文件复制到路径 destination

处的文件夹（source 和 destination 都是字符串）。如果 destination 是一个文件名，它将

作为被复制文件的新名字。该函数返回一个字符串，表示被复制文件的路径。

```python
import shutil,os
os.chadir('C:\\')
shutil.copy('C:\\spam.txt', 'C:\\delicious')	#将C盘下的spam.txt复制到delicious文件下
shutil.copy('eggs.txt', 'C:\\delicious\\eggs2.txt')	#'C:\\delicious\\eggs2.txt'
```