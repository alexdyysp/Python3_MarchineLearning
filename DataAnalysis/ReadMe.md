Python3数据分析-2018黑马
=======================
数据分析
-------
什么是数据分析？<br>
数据分析是用适当方法对收集来的大量数据进行分析，帮助人们做出判断，以便采取适当行动。

数据分析的流程?<br>
提出问题-准备数据-分析数据-获得结论-成果可视化

* *matplotlib module*
----------------------
最流行Python的底层绘图库<br>
基本要点:<br>
axis轴:xy坐标轴
默认不支持中文，使用fc-list :lang=zh查看支持字体<br>
matplotlib.rc,查看源码<br>
1. font = {'family':'MicroSoft Yahei','weight':'bold','size':'larger'}<br>
   matplotlib.rc("font",**font)<br>
2. my_font = font_manager.FontProperties(fname="/usr/share/fonts/opentype/noto/NotoSansCJK-Bold.ttc") <br>
   fontproperties=my_font<br>

*pyplot*
---------
想查看更多绘制图形，点击下面链接<br>
[matplotlib.pyloy画图图例](https://matplotlib.org/gallery/)<br>

[还有ECHARTS前端框架,js效果](https://github.com/apache/incubator-echarts)<by>

[ployly.py，在后端直接绘图不用传给前端](https://plotly.ly/python/)<br>

seaborn<br>

function|用法
------|------
from matplotlib import pyplot as plt | #导入pyplot<br>
matplotlib.rc("font",**font)  |  #enable 中文<br>
plt.show()      |  #展示图形<br>
plt.figure(figsize,dpi)  | #设置图片大小，实例化大小参数figsize,输入dip像素点参数使图像更清晰 <br>
plt.savefig("path")      | #可以保存为svg矢量图格式，放大不会有锯齿 <br>
plt.xticks(range(),xticks_label,rotation，fontproperties=my_font)|  #range(start,end,interval),label"hello,{}",rotation=degree，font字体文件<br>
plt.yticks(range())    |    #调整x,y轴刻度， <br>
plt.title("" ,fontproperties=) | 显示title标题
plt.legend(prop) | 添加图例，prop字体，从plot函数的label中抽取图例内容
plt.grid(alpha=0.5)  | 设置网格，alpha透明度

function|展示图形类型
------|------
plt.plot(x,y,label,color,linestyle,linewidth,alpha)  |   折线图，传入x和y,label=""为曲线标签,color=""颜色，linestyle线条风格，alpha透明度<br>
plt.scatter()     |  散点图<br>
plt.bar()   |  条形图<br>
plt.hist(y,x,normed)  |  直方图,normed=1显示统计概率分布直方图<br>


*numpy*
---------
专门用于处理数值形数据
概念:
axis 轴：在numpy中可以理解为方向，用数字0,1,2....数字表示

function|用法
------|------
numpy.array([])   |  新建数组
numpy.shape()  |  数组形状
numpy.reshape()   |  改变数组形状，但是原地变化，不改变原数组
numpy.flatten()<br>numpy.reshape(1,n)  |  数组一维化
array+-*/value |  给数组全体进行四则运算
numpy.arrange(a,b).reshape(x,y)  |  生成从a到b，形状为x,y维的数组
numpy.loadtxt(frame, dtype, delimiter, skiprows, usecols, unpack) |  frame文件，dtype数据类型，delimiter分割字符串，skiprows跳过行，usecols读取指定列，unpack值为Ture写入不同数组变量/Flase则写入一个数组变量
numpy.transpose()<br>   array.T<br> array.swapaxes(1,0)<br> |  转置数组,行列变换
array[a:b]<br>array[n]<br>array[[a,b,c]]<br> |  取连续a到b行<br>取第n行<br>取不连续多行[a,b,c]<br>
array[a:b,:]<br>array[n,:]<br>array[[a,b,c],:]<br> |  取连续a到b列<br>取第n列<br>取不连续列[a,b,c]<br>

