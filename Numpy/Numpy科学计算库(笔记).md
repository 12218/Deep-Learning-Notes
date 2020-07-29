@[TOC](目录)
# Numpy科学计算库

## 01 多维数组
![01](https://img-blog.csdnimg.cn/20200724171136584.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)


shape: (10, 30, 5):

共有三个维度

第一个维度长度为10

第二个维度长度为30

第三个维度长度为5

## 02 创建Numpy数组


```python
import numpy # 导入numpy库
```

### (1) array


```python
a = numpy.array([1, 2, 3, 4]) # 创建一个一维数组
print(a)
print(a.shape) # 数组形状
print(type(a)) # 数组类型
print(a[1]) # 调用数组中元素的方法
```

    [1 2 3 4]
    (4,)
    <class 'numpy.ndarray'>
    2



```python
b = numpy.array([[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]]) # 创建二维数组
print(b)
print(b.shape)
print(b[1]) # 此时b[1]是表示数组第二个维度上的第二个数组
print(b[1][1]) # 取出数组第二个的维度上的第二个数字；也可使用b[1, 1]
print(b.size) # 数组中的元素总个数
```

    [[ 1  2  3  4]
     [ 5  6  7  8]
     [ 9 10 11 12]]
    (3, 4)
    [5 6 7 8]
    6
    12


### (2) 数组属性
![02](https://img-blog.csdnimg.cn/20200724171156689.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

**注:size为数组中的元素总个数**

### (3) 指定数组数据类型
![03](https://img-blog.csdnimg.cn/20200724171212496.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)



```python
a = numpy.array([1, 2, 3, 4], dtype = numpy.int64) # 给数组中的元素添加数据类型, 也可以使用int64, 'int64', 'numpy.int64'
print(a)
print(a.dtype)
```

    [1 2 3 4]
    int64


### (4) 创建特殊数组
![04](https://img-blog.csdnimg.cn/20200724171227275.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

np.arange(起始数字, 结束数字, 步长, dtype) 数字序列数组

np.ones(shape, dtype) 全1数组

np.zeros(shape, dtype) 全0数组

np.eye(shape, dtype) 单位矩阵

np.linspace(start, stop, num=50, dtype) 等差数组 (num元素个数)

np.logspace(start, stop, num=50, base=10, dtype) 等比数组 (num元素个数 base基)

### (5) asarray
![05](https://img-blog.csdnimg.cn/20200724171239885.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)


## 03 数组运算

### (1) 改变数组形状
![06](https://img-blog.csdnimg.cn/2020072417125359.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

**数组转变前后元素个数应当一定, 否则报错**

**如果reshape(shape)的shape中有一值为-1, 根据数组中元素总个数、以及其他维度的取值，来自动计算出这个维度的取值。**

### (2) 数组间的运算
#### 1. 加法


```python
a = numpy.array([0, 1, 2, 3])
b = numpy.array([4, 5, 6, 7])
print(a + b) # 对应各项相加，数组的形状应相同，除一维数组外，一维数组会加到多维数组的每行
```

    [ 4  6  8 10]


#### 2.  数组间的减法、乘法、除法
![07](https://img-blog.csdnimg.cn/20200724171308675.png)


### (3) 矩阵间的运算
#### 1. 矩阵乘法


```python
a = numpy.array([[1, 1], [0, 1]])
b = numpy.array([[2, 0], [3, 4]])
print(numpy.matmul(a, b)) # 矩阵相乘
print(numpy.dot(a, b)) # 同上
```

    [[5 4]
     [3 4]]
    [[5 4]
     [3 4]]


#### 2. 矩阵转置


```python
print(numpy.transpose(a))
```

    [[1 0]
     [1 1]]


#### 3. 矩阵求逆


```python
print(numpy.linalg.inv(b))
```

    [[ 0.5    0.   ]
     [-0.375  0.25 ]]

### (4)数组元素间的运算
![08](https://img-blog.csdnimg.cn/20200729171804773.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

![09](https://img-blog.csdnimg.cn/20200729171821164.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

**注：axis从零开始计数**


```python
a = numpy.arange(24).reshape(2, 3, 4)
print(a)
print(numpy.sum(a, axis = 0)) # 将数组0轴上的元素一一相加
```

    [[[ 0  1  2  3]
      [ 4  5  6  7]
      [ 8  9 10 11]]
    
     [[12 13 14 15]
      [16 17 18 19]
      [20 21 22 23]]]
    [[12 14 16 18]
     [20 22 24 26]
     [28 30 32 34]]



```python
a = numpy.logspace(1, 4, 4, base = 2) # 参数:(起始指数，结束指数，元素个数，基数)
print(a)
print(numpy.sqrt(a)) # 计算数组中的各元素平方根
```

    [ 2.  4.  8. 16.]
    [1.41421356 2.         2.82842712 4.        ]


### (5) 数组的堆叠
![10](https://img-blog.csdnimg.cn/20200729171842830.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)



```python
a = numpy.array([1, 2, 3])
b = numpy.array([4, 5, 6])
print(numpy.stack((a, b), axis = 0)) # 在0轴上堆叠
print(numpy.stack((a, b), axis = 1)) # 在1轴上堆叠
```

    [[1 2 3]
     [4 5 6]]
    [[1 4]
     [2 5]
     [3 6]]


## 04 矩阵和随机数
### (1) 矩阵
![11](https://img-blog.csdnimg.cn/20200729171858108.png)


```python
a = numpy.mat('1, 2, 3; 4, 5, 6') # 使用字符串创建数组，使用分号隔开行
print(a)
print(type(a))
```

    [[1 2 3]
     [4 5 6]]
    <class 'numpy.matrix'>


### (2) 矩阵相乘、转置、求逆


```python
a = numpy.mat([[1, 2], [3, 4]])
b = numpy.mat([[1, 0], [1, 1]])
print(a*b) # 此处矩阵相乘运算方法为a*b
```

    [[3 2]
     [7 4]]



```python
print(a.T) # 矩阵转置运算
print(a.I) # 矩阵求逆运算
```

    [[1 3]
     [2 4]]
    [[-2.   1. ]
     [ 1.5 -0.5]]


### (3) 随机数
![12](https://img-blog.csdnimg.cn/20200729171912654.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

**注：此处size是数组的形状**


