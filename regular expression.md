[Toc]
### 1.判断是否匹配成功，并输出对应匹配信息
```python
import re
source = "1yangxinyi"
# match从字符串起始位置开始匹配
if re.match("xin",source): #if re.match is not None
    print("Found")
else:
    print("Not Found")  
if re.search("xin",source):
    print ("Found")
else:
    print ("Not Found")

>>> Not Found
>>> Found
```
### 2.找出一个字符串中是否有连续的5个数字
```python
## r相当于\转义符
## \d匹配数字 {}表示连续出现次数
## .group()和.group(0)就是将匹配出的字符串整体表示出来
print(re.search(r"\d{5}","1234aadd222222").group())
>>>22222
```
### 3.输出一个字符串中的连续5个数字，要求数字前后必须是非数字
```python
# |表示查找(\D\d{5}\D)或(^\d{5}\D)
# ^是正则表达式匹配字符串开始位置
# $是正则表达式匹配字符串结束位置
# \D与\d相反，表示匹配字符串
re.search(r'(\D\d{5}\D)|(^\d{5}\D)|(\D\d{5}$)|(^\d{5}$)','12567').group()
>>>12567
```
### 4.统计一个文件中单词的数量
```python
with open("d:\\word.txt","r") as file_obj:
    print(len(re.findall(r"(\b[A-Za-z]+\b)",file_obj.read())))
```
### 5.把a1b23c4d非字符内容拼成一个字符串
```python
# "".join将字符串连接起来
# findall函数是返回匹配的所有字符
# []类似于|
"".join(re.findall(r"[^A-Za-z]","a1b23c4d"))
>>>1234
```