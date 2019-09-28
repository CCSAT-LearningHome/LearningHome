### 1.判断是否匹配成功，并输出对应匹配信息
import re
source = "1yangxinyi"
####从字符串起始位置
'''python
if re.match("xin",source): #if re.match is not None
print("Found")
else:
print("Not Found")  
if re.search("xin",source):
    print ("Found")
else:
    print ("Not Found")
'''
### 2.找出一个字符串中是否有连续的5个数字
# r相当于\转义符
# \d匹配数字{}连续出现次数
# .group()和.group(0)就是将匹配出的字符串整体表示出来
>>>print(re.search(r"\d{5}","1234aadd222222").group())