pandas是一个能够提供表格和一定程度的快速分析的库，但是对于更加专业细分的工具（譬如点过程，深度学习等）并没有提供，所以如果有需要我们则要调用别的库。

## Dataframe
dataframe是pandas提供的一种数据结构，简要介绍一下它的用法。
注意以下的代码示例都只给出局部。
### 创建
#### 通过字典方式创建
```python
import pandas as pd
...
dic={
"id":[001,002,003,004]
"score":[91,61,98,100]
"name":["Bob","Alice","steve"]
}
df=pd.Dataframe(dic)
#注意这个创建D要大写
```
#### 通过导入.csv文件创建
```python
df=pd.read_csv(A_CSV_PATH)

#我们还有写入某个.csv文件的方法
df=pd.to_csv(A_CSV_PATH,index=False)
#注意这个index，决定的是生成的csv会不会带行号
```
简要举个例子说明一下index的作用
```python
import pandas as pd

df = pd.DataFrame({"game_id": ["A", "B"], "E_v": [0.3, 0.5]})

# 默认：带行号
df.to_csv("with_index.csv", index=True)   # 可省略 index=True
# 文件内容：
# game_id,E_v
# 0,A,0.3
# 1,B,0.5

# 去掉行号
df.to_csv("no_index.csv", index=False)
# 文件内容：
# game_id,E_v
# A,0.3
# B,0.5
```

#### 通过列表（python中所谓数组）创建
```python
import pandas as pd
data=[["Genshin"，0],["DicoElysium",10],["FindinParadise",10]]
df=pd.Dataframe(data,)
```

#### 我们在最后给出这个创建函数的部分重要参数
```python
pandas.DataFrame(
    data=None,
    index=None,
    columns=None,
    dtype=None,
    copy=None
)
'''
这里的data表示创建df所基于的具体数据，它的类型可以是list,array,dict,Dataframe...
这里index作用前面说了
这里的columns目的是指定列的顺序
这里的
'''
```


### 数据访问
#### 看前后几行
```python
df.head(n)
df.tail(n)
#这里没有n默认为5
```
#### 取某几列
```python
df["game_id"]
df[["game_id","score"]]
#注意取多列需要再用一个list
```
#### 通过条件筛选行
```python
df[[df["score"]>60]]
```

### 数据添加修改删除
#### 添加/修改
```python
df["column_name"]=df["another_column_name"]*2
#只要右边是一个原column的式子就可以了，如果没有则创建有就修改
```
#### 删除
pop, deal, drop
```python

```
### 数据筛选
### 数据排序
### 统计分析部分
