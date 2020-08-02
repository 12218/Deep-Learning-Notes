# Matplotlib数据可视化


```python
import matplotlib.pyplot as plt # 导入pyplot子库
```

## 01 Matplotlib 绘图基础
### (1) Figure 对象
![01.png](attachment:01.png)


```python
plt.figure(figsize = (3, 2), facecolor = 'green')
plt.plot()
plt.show()
```


![png](output_3_0.png)


### (2) 划分子图
![02.png](attachment:02.png)


```python
plt.subplot(2, 2, 1) # 参数含义：2行，2列，第1个子图
plt.subplot(2, 2, 2) # 参数含义：2行，2列，第2个子图
plt.subplot(2, 2, 3) # 参数含义：2行，2列，第3个子图
plt.subplot(2, 2, 4) # 参数含义：2行，2列，第4个子图

plt.show()
```


![png](output_5_0.png)


### (3) 设置中文字体
![03.png](attachment:03.png)

### (4) 添加标题
![04.png](attachment:04.png)
![05.png](attachment:05.png)


```python
plt.rcParams['font.sans-serif'] = 'SimHei'
plt.suptitle('全局标题', color = 'white', fontsize = 20)
plt.plot()
plt.show()
```


![png](output_8_0.png)


![06.png](attachment:06.png)


```python
plt.rcParams['font.sans-serif'] = 'SimHei'
plt.suptitle('全局标题', color = 'white', fontsize = 16, y = 1.0)
plt.subplot(2, 1, 1) # 参数含义：2行，1列，第1个子图
plt.title('第一个图', color = 'white') # 添加第一个图的标题
plt.subplot(2, 1, 2) # 参数含义：2行，1列，第2个子图
plt.title('第二个图', color = 'white') # 添加第二个图的标题
plt.show()
```


![png](output_10_0.png)


### (5) tight_layout()函数
![07.png](attachment:07.png)
![08.png](attachment:08.png)


```python

```
