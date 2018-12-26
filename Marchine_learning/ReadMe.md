机器学习--Python
================
机器学习是什么？<br>
- 机器学习就是从*数据*中自动分析获取*规律(模型)*，并利用规律对*未知数据进行预测*  

为什么需要机器学习<br>
- 解放生产力
- 解决专业问题
- 提供社会便利  

机器学习在各领域价值？<br>
- 让机器学习程序替换手动步骤，减少企业成本同时提高效率<br>

机器学习知识点：<br>
- 特征工程
- 模型、策略、优化
- 分类、回归、聚类
- Tensorflow
- 神经网络
- 图像识别
- 自然语言处理

机器学习-数据集组成
------------------
数据：csv文件<br>
pandas: 读取工具<br>
numpy: 释放了GIL<br>
可用数据集：kaggle/scikit-learn/UCI<br>
数据集结构：特征值+目标值(有些数据可以没有目标值)<br>

机器学习-特征工程
----------------
缺失值，数据转换，重复值是否去重？
sklearn:特征工程工具<br>
特征工程是什么？<br>
特征工程是将*原始数据转换为更好的代表预测模型的潜在问题的特征*的过程，从而*提高了对未知数据的预测准确性*.<br>
特征工程意义:<br>
直接影响预测结果.<br>  
<br>
scikit-learn库介绍<br>
[sklearn官方文档](https://scikit-learn.org/stable/)
<br>
*数据特征抽取：*<br>
- 特征对文本等数据进行特征值化<br>
- sklearn.feature_extravtion  api
<br>
    
|function  | 作用 |
|----------|-----------|
|*sklearn.feature_extravtion.DictVectorizer  对字典数据进行特征值化*|
|DictVectorizer.fit_transform(X) | X:字典或者包含字典的迭代器；返回值：返回sparse矩阵|
|DictVectorizer.get_feature_names()  | 返回类别名称|
|DictVectorizer.transorm(X)  | 按照原先标准转换|
|*sklearn.feature_extravtion.text.CountVectorizer  文本数据特征值化*|
|CountVectorizer.fit_transform(X) | X:文本或者包含文本的迭代器；返回值：返回sparse矩阵|
|CountVectorizer.get_feature_names()  | 返回值：单词列表|
|CountVectorizer.inverse_transorm(X)  |  X:array或者sparse矩阵；返回值:转换之前数据格式|
|*jieba 分词*|
|jieba.cut(X)  | 返回值：词语生成器|
<br>
文本特征值化流程：<br>
-  1. 准备句子，jieba分词<br>
-  2. 实例化CountVectorizer<br>
-  3. 将分词结果变成字符串当做fit_transform的输入值<br>
<br>
*数据降维*

线性回归
--------

梯度下降算法：
-  批量梯度下降<br>容易得到最优解，但需要考虑所有样本，速度很慢
-  随机梯度下降<br>每次找一个样本，迭代速度快，但不一定每次都朝着收敛的方向
-  小批量梯度下降<br>每次更新选择一小部分数据来算，很实用


逻辑回归
--------  
<br>
*样本类别不平衡*
在分类问题中，有存在正反例数目差异较大的情况，这种情况叫做类别不平衡<br>
针对这种问题，解决方式主要有3种：假设正例数量大，反例数目极小<br>
1、减少正例的数量，使得数据平衡，再进一步分类，这种情况属于`欠采样`；<br>
2、增加反例的数目平衡数据，再分类，这种称为`过采样`；<br>
3、`阈值移动`：直接使用原始数据进行分类，但在用训练好的分类器进行预测时，将下式加入到决策过程中，以调整正反例的平衡性。<br>
![image](https://github.com/dyywinner/Python3_MarchineLearning/blob/master/image/%E9%98%88%E5%80%BC%E7%A7%BB%E5%8A%A8.png)

将数据集切分成两部分：train集(80%)和test集(20%)<br>
