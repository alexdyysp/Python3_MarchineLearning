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
font = {'family':'MicroSoft Yahei','weight':'bold','size':'larger'}<br>
matplotlib.rc("font",**font)<br>

*pyplot*
---------
python function|用法
----|--------|
from matplotlib import pyplot as plt | #导入pyplot<br>
matplotlib.rc("font",**font)  |  #enable 中文<br>
plt.plot(x,y)  |   #传入x和y<br>
plt.show()      |  #展示图形<br>
plt.figure(figsize,dpi)  | #设置图片大小，实例化大小参数figsize,输入dip像素点参数使图像更清晰 <br>
plt.savefig("path")      | #可以保存为svg矢量图格式，放大不会有锯齿 <br>
plt.xticks(range(),xticks_label,rotation，fontproperties=my_font)|  #range(start,end,interval),label"hello,{}",rotation=degree，font字体文件<br>
plt.yticks(range())    |    #调整x,y轴刻度， <br>
_xticks_labels = ["hello,{}".format(i) for i in x]  | #显示hello,i<br>

