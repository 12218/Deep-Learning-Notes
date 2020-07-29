# Numpy科学计数库

## 01 多维数组
![01.png](attachment:01.png)

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
![02.png](attachment:02.png)
**注:size为数组中的元素总个数**

### (3) 指定数组数据类型
![03.png](attachment:03.png)


```python
a = numpy.array([1, 2, 3, 4], dtype = numpy.int64) # 给数组中的元素添加数据类型, 也可以使用int64, 'int64', 'numpy.int64'
print(a)
print(a.dtype)
```

    [1 2 3 4]
    int64
    

### (4) 创建特殊数组
![04.png](attachment:04.png)
np.arange(起始数字, 结束数字, 步长, dtype) 数字序列数组

np.ones(shape, dtype) 全1数组

np.zeros(shape, dtype) 全0数组

np.eye(shape, dtype) 单位矩阵

np.linspace(start, stop, num=50, dtype) 等差数组 (num元素个数)

np.logspace(start, stop, num=50, base=10, dtype) 等比数组 (num元素个数 base基)

### (5) asarray
![05.png](attachment:05.png)

## 03 数组运算

### (1) 改变数组形状
![06.png](attachment:06.png)
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
![07.png](attachment:07.png)

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
    


```python

```
