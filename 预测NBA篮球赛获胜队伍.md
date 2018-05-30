### 主要内容：
- pandas 加载处理数据
- 决策树与随机森林
- 集成学习概念

代码另附，下面只记录一些功能性的函数与概念。

**1.数据加载与处理**
 csv文件：以逗号分隔的文本格式的数据文件；
 **加载csv文件**
 ```Python
 import pandas as pd
 dataset = pd.read_csv(data_filename)
 '''
 返回的数据类型为dataframe 可以向npy转换
 '''
 ```
 **数据清洗**
 - 把字符串格式的日期变为数字表示的日期对象
 ```Python
 results = pd.read_csv(data_filename, parse_dates=['Date'])  # 第二个参数表示以数字日期格式读取日期数据
 ```
 
**2.one hot 编码**

one hot编码称为独热编码，有多少个状态就有多少比特，且每个编码只有一个比特为1

使用sklearn模块里的onehotencoder转换器把整数转换为二进制数字

**由以下案例可以看出来onehot编码会按照原始数据的大小进行排序，有多少数据就会有多少比特位，然后从低位到高位依次出现1**

```Python
onehot = OneHotEncoder()
res = onehot.fit_transform(np.array([1,2,3,4,5,6]).reshape(-1,2)).todense()
res
>>>
matrix([[1., 0., 0., 1., 0., 0.],
        [0., 1., 0., 0., 1., 0.],
        [0., 0., 1., 0., 0., 1.]])
```

**2.字符串的整型数编码**

```Python
from sklearn.preprocessing import LabelEncoder, OneHotEncoder
para=['a', 'b', 'c']
encoding = LabelEncoder()  # 把字符串类型转化为整型
encoding_result = encoding.fit_transform(para)  # para为字符串列表
print(encoding_result)
>>>
[0 1 2]
```

