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
*图形描述函数*
from matplotlib import pyplot as plt | 导入pyplot<
matplotlib.rc("font",**font)  |  enable 中文
.show()      |  展示图形<br>
.figure(figsize,dpi)  | 设置图片大小，实例化大小参数figsize,输入dip像素点参数使图像更清晰 <br>
.savefig("path")      | 可以保存为svg矢量图格式，放大不会有锯齿 <br>
.xticks(range(),xticks_label,rotation，fontproperties=my_font)|  range(start,end,interval),label"hello,{}",rotation=degree，font字体文件<br>
.yticks(range())    |    调整x,y轴刻度， <br>
.title("" ,fontproperties=) | 显示title标题
.legend(prop) | 添加图例，prop字体，从plot函数的label中抽取图例内容
.grid(alpha=0.5)  | 设置网格，alpha透明度
*展示图形类型函数*
.plot(x,y,label,color,linestyle,linewidth,alpha)  |   折线图，传入x和y,label=""为曲线标签,color=""颜色，linestyle线条风格，alpha透明度<br>
.scatter()     |  散点图<br>
.bar()   |  条形图<br>
.hist(y,x,normed)  |  直方图,normed=1显示统计概率分布直方图<br>


* *numpy Module*
-----------------
专门用于处理数值形数据
概念:
axis 轴：在numpy中可以理解为方向，用数字0,1,2....数字表示

function|用法
------|------
*基本用法*
.array([])   |  新建数组
.shape()  |  数组形状
.reshape()   |  改变数组形状，但是原地变化，不改变原数组
.flatten()<br>numpy.reshape(1,n)  |  数组一维化
.arrange(a,b).reshape(x,y)  |  生成从a到b，形状为x,y维的数组
.loadtxt(frame, dtype, delimiter, skiprows, usecols, unpack) |  加载文件书数据，frame文件，dtype数据类型，delimiter分割字符串，skiprows跳过行，usecols读取指定列，unpack值为Ture写入不同数组变量/Flase则写入一个数组变量
.transpose()<br>   array.T<br> array.swapaxes(1,0)<br> |  转置数组,行列变换
.argmax(t, axis=0)<br>.argmin(t, axis=1) |  取最大值最小值位置，axis=0按行方向,axis=1按列方向
.eye(n)   |  新建对角线为1的矩阵
*生成随机数*
.random.rand(d0,d1,...,dn)  |  创建d0-dn维度的*均匀*分布随机数据库，浮点数(0,1)
.random.randn(d0,d1,...,dn)  |  创建d0-dn维度的*标准正态*分布随机数据库，average=0,标准差s=1
.random.randint(low,high,(shape)) |  给定上限范围选取随机数整数，(low,high),size=shape
.random.seed(n)   |  随机种子，给定n个随机值，可以让后续每次生成相应的随机数
*直接数组操作*
array+-*/value |  给数组全体进行四则运算
array.astype(elementype)   |  array转换类型，默认为float
*切片与索引 *
array[a:b]<br>array[n]<br>array[[a,b,c]]<br> |  取连续a+1到b+1行<br>取第n+1行<br>取不连续多行[a+1,b+1,c+1]<br>
array[:, a:b]<br>array[:, n]<br>array[:, [a,b,c]]<br> |  取连续a+1到b+1列<br>取第n+1列<br>取不连续列[a+1,b+1,c+1]<br>
array[a:b, c:d]   |  取a+1到b+1行，取c+1到d+1列，取行列交叉点位置
array[[a,b,c],[d,e,f]] |   取多个不相邻点，[a+1,d+1],[b+1,e+1],[c+1,f+1]
array[array>value]   |  取出array中数值大于value的数值
numpy.where(array<value,a,b)  |  将array中小于value的数值替换为a,大于的换位b
*数组拼接*
numpy.vstack((a,b))  |  竖直拼接(vertically)
numpy.hstack((a,b))  |  水平拼接(horizontally)
*行列交换*
array[[a,b],:] |  行交换
array[:,[a,b]] |  列交换
*copy and review*
a = b | 完全不复制，a与b相互影响
a = b[:] |  视图操作，切片创建新对象a，a数据完全由b保管，两个数据变化是一致的
a = b.copy()   |  轻拷贝，ab不相互影响
*nan & inf*
.isnan(num)<br>.isnan(array)   |  求num是否为nan<br>返回bool型数组在nan位置标True<br>


* *pandas Module*
pandas可以处理字符串和时间序列等数据
(pandas官网，很全面的case)[http://pandas.pydata.org/pandas-docs/stable/]
import panda as pd   #panda module导入<br>

*Series序列*
Series对象本质上由两个数组构成，一个构成对象的键(index)，一个构成对象的值(value)，index->value<br>
常配合string一起使用<br>

function|用法
------|------
基本用法
series.index   |  返回series的索引序列
series.values  |  返回series的数值序列
series创建
.Series([array], index = list(""))  | 创建array数组的索引序列, index用于指定索引
series切片&索引
s[start:end:step] |  直接传入起始结束步长
s[s>num] |  返回序列中大于num的部分
s["index1","index2"] | 直接用索引表索引
.where(condition) |  where方法，返回符合条件的序列部分<br>

*read读取外部数据*
function|用法
------|------
panda.read_csv("filepath") |  读取出的数据类型为DataFrame<br>

*DataFrame*
