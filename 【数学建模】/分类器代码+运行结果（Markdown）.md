## 二元逻辑回归故障检测模型分类器

```python
#二元分类故障检测模型分类器
import numpy as np
import pandas as pd
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.metrics import confusion_matrix
from sklearn.metrics import classification_report

#读取数据
df=pd.read_excel('/Users/rickyx/Desktop/数学建模/2022数模校赛题目/A/数据/分类器/正常状态分类器/正常状态分类器.xlsx')
data_x=df.iloc[:,1:5]  #将数据特征值存储至data_x中
data_y=df.iloc[:,5:6]  #将数据标签值存储至data_y中

#展示部分数据，检验是否正确读入
print("数据集特征值浏览：")
print(data_x.head())
print("数据集标签值浏览：")
print(data_y.head())

#划分训练集与测试集
x_train,x_test,y_train,y_test = train_test_split(data_x,data_y, test_size=0.3,random_state=0)

#利用sklearn库训练模型
LR = LogisticRegression()
LR.fit(x_train,y_train)
y_predict=LR.predict(x_test)

#评估指标输出 
confusion_matrix = confusion_matrix(y_test, y_predict)
print("混淆矩阵：")
print(confusion_matrix)    #混淆矩阵
accuracy=accuracy_score(y_test,y_predict)*100
print("准确率: {:.2f}%".format(accuracy))
```

![image-20220522152555095](https://tva1.sinaimg.cn/large/e6c9d24ely1h2h7oulh2ej20fq0doq49.jpg)



## 多元逻辑回归故障检测模型分类器

```python
#多元逻辑回归故障检测模型分类器
import numpy as np
import pandas as pd
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.metrics import confusion_matrix
from sklearn.metrics import classification_report

#读取数据
df=pd.read_excel('/Users/rickyx/Desktop/数学建模/2022数模校赛题目/A/数据/分类器/多分类器/多分类器（总体）.xlsx')
data_x=df.iloc[:,1:5]  #将数据特征值存储至data_x中
data_y=df.iloc[:,5:6]  #将数据标签值存储至data_y中

#展示部分数据，检验是否正确读入
print("数据集特征值浏览：")
print(data_x.head())
print("数据集标签值浏览：")
print(data_y.head())

#划分训练集与测试集
x_train,x_test,y_train,y_test = train_test_split(data_x,data_y, test_size=0.3,random_state=0)

#利用sklearn库训练模型
LR = LogisticRegression(multi_class='multinomial')
LR.fit(x_train,y_train)
y_predict=LR.predict(x_test)

#评估指标输出 
confusion_matrix = confusion_matrix(y_test, y_predict)
print("混淆矩阵：")
print(confusion_matrix)    #混淆矩阵
accuracy=accuracy_score(y_test,y_predict)*100
print("准确率: {:.2f}%".format(accuracy))
```

![image-20220522153645600](https://tva1.sinaimg.cn/large/e6c9d24ely1h2h802zcx5j21340iqad8.jpg)



## XGBoost算法故障检测模型分类器

```python
#XGBoost算法故障检测模型分类器
import numpy as np
import pandas as pd
import sklearn
from xgboost.sklearn import XGBClassifier
from sklearn.model_selection import train_test_split
from sklearn.metrics import accuracy_score
from sklearn.metrics import confusion_matrix
from sklearn.metrics import classification_report

#读取数据
df=pd.read_excel('/Users/rickyx/Desktop/数学建模/2022数模校赛题目/A/数据/分类器/多分类器/多分类器（总体）.xlsx')
data_x=df.iloc[:,1:5]  #将数据特征值存储至data_x中
data_y=df.iloc[:,5:6]  #将数据标签值存储至data_y中

#展示部分数据，检验是否正确读入
print("数据集特征值浏览：")
print(data_x.head())
print("数据集标签值浏览：")
print(data_y.head())

#划分训练集与测试集
x_train,x_test,y_train,y_test = train_test_split(data_x,data_y, test_size=0.3,random_state=0)

#利用sklearn库训练模型
XGB = XGBClassifier()
XGB.fit(x_train,y_train)
y_predict=XGB.predict(x_test)

#评估指标输出 
confusion_matrix = confusion_matrix(y_test, y_predict)
print("混淆矩阵：")
print(confusion_matrix)    #混淆矩阵
accuracy=accuracy_score(y_test,y_predict)*100
print("准确率: {:.2f}%".format(accuracy))
```

![image-20220522155033140](https://tva1.sinaimg.cn/large/e6c9d24ely1h2h8efep7cj20f80fu40a.jpg)
