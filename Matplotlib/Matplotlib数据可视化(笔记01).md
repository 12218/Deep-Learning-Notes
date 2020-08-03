# Matplotlib数据可视化
```python
import matplotlib.pyplot as plt # 导入pyplot子库
```

## 01 Matplotlib 绘图基础
### (1) Figure 对象
![01](https://img-blog.csdnimg.cn/20200802171117947.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)
```python
plt.figure(figsize = (3, 2), facecolor = 'green')
plt.plot()
plt.show()
```
![out3](https://img-blog.csdnimg.cn/20200802171630909.png)

### (2) 划分子图
![02](https://img-blog.csdnimg.cn/20200802171328401.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

```python
plt.subplot(2, 2, 1) # 参数含义：2行，2列，第1个子图
plt.subplot(2, 2, 2) # 参数含义：2行，2列，第2个子图
plt.subplot(2, 2, 3) # 参数含义：2行，2列，第3个子图
plt.subplot(2, 2, 4) # 参数含义：2行，2列，第4个子图

plt.show()
```
![out5](https://img-blog.csdnimg.cn/20200802171610152.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

### (3) 设置中文字体
![03](https://img-blog.csdnimg.cn/20200802171342621.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)


### (4) 添加标题
![04](https://img-blog.csdnimg.cn/20200802171402706.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)
![05](https://img-blog.csdnimg.cn/20200802171411958.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

```python
plt.rcParams['font.sans-serif'] = 'SimHei'
plt.suptitle('全局标题', color = 'white', fontsize = 20)
plt.plot()
plt.show()
```
![out8](https://img-blog.csdnimg.cn/2020080217154368.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

![06](https://img-blog.csdnimg.cn/20200802171428594.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

```python
plt.rcParams['font.sans-serif'] = 'SimHei'
plt.suptitle('全局标题', color = 'white', fontsize = 16, y = 1.0)
plt.subplot(2, 1, 1) # 参数含义：2行，1列，第1个子图
plt.title('第一个图', color = 'white') # 添加第一个图的标题
plt.subplot(2, 1, 2) # 参数含义：2行，1列，第2个子图
plt.title('第二个图', color = 'white') # 添加第二个图的标题
plt.show()
```
![out10](https://img-blog.csdnimg.cn/20200802171524241.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

### (5) tight_layout()函数
![07](https://img-blog.csdnimg.cn/20200802171451328.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)
![08](https://img-blog.csdnimg.cn/20200802171502125.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

