### 主要内容：
- pandas 加载处理数据
- 决策树与随机森林
- 集成学习概念

**1.数据加载与处理**
 csv文件：以逗号分隔的文本格式的数据文件；
 加载csv文件
 ```Python
 import pandas as pd
 dataset = pd.read_csv(data_filename)
 '''
 返回的数据类型为dataframe 可以向npy转换
 '''
 ```
