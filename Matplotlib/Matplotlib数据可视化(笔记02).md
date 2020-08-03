# Matplotlib画图
```python
import matplotlib.pyplot as plt
import numpy
```

## 01 散点图

### (1) scatter函数
![09](https://img-blog.csdnimg.cn/20200803171221203.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)
![10](https://img-blog.csdnimg.cn/20200803171230860.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)
![11](https://img-blog.csdnimg.cn/20200803171243501.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)
![12](https://img-blog.csdnimg.cn/20200803171252952.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

```python
plt.rcParams['font.sans-serif'] = 'SimHei'
plt.rcParams["axes.unicode_minus"] = False # 防止坐标轴数字负号出错
n = 1024
x = numpy.random.normal(0, 1, n)
y = numpy.random.normal(0, 1, n)
plt.scatter(x, y, color = 'blue', marker = 'o')
plt.title('标准正态分布', fontsize = 20)
plt.text(2.5, 2.5, '均值：0\n标准差：1')
plt.xlim(-4, 4) # 设置坐标轴范围
plt.ylim(-4, 4)
plt.xlabel('横坐标x', fontsize=14) # 设置坐标轴标签
plt.ylabel('纵坐标y', fontsize=14)
plt.show()
```
![out04](https://img-blog.csdnimg.cn/20200803170948105.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

### (2) 增加图例
![13](https://img-blog.csdnimg.cn/20200803171314791.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

## 02 折线图
![14](https://img-blog.csdnimg.cn/2020080317132765.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

```python
n = 24 # 数据数量
y1 = numpy.random.randint(27, 37, n) # 温度
y2 = numpy.random.randint(40, 60, n) # 湿度
plt.plot(y1, label = '温度')
plt.plot(y2, label = '湿度')
plt.xlim(0, 23)
plt.ylim(20, 70)
plt.xlabel('小时', fontsize = 12)
plt.ylabel('测量值', fontsize = 12)
plt.title('24小时温度湿度测量值', fontsize = 20, color = 'blue')

plt.legend()

plt.show()
```
![out07](https://img-blog.csdnimg.cn/20200803170929513.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

## 03 柱形图
![15](https://img-blog.csdnimg.cn/20200803171340895.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

```python
y1 = [32,25,16,30,24,45,40,33,28,17,24,20]
y2 = [-23,-35,-26,-35,-45,-43,-35,-32,-23,-17,-22,-28]

plt.bar(range(len(y1)), y1, width = 0.8, facecolor = 'green', edgecolor = 'white', label = '统计量1')
plt.bar(range(len(y2)), y2, width = 0.8, facecolor = 'red', edgecolor = 'white', label = '统计量2')
# range(len(y1))为从0开始，每隔1画一个柱形图

plt.show()
```
![out09](https://img-blog.csdnimg.cn/20200803170909454.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDMzODc4MA==,size_16,color_FFFFFF,t_70)

