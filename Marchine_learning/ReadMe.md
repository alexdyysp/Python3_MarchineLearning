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

*样本类别不平衡*
在分类问题中，有存在正反例数目差异较大的情况，这种情况叫做类别不平衡<br>
针对这种问题，解决方式主要有3种：假设正例数量大，反例数目极小<br>
1、减少正例的数量，使得数据平衡，再进一步分类，这种情况属于`欠采样`；<br>
2、增加反例的数目平衡数据，再分类，这种称为`过采样`；<br>
3、`阈值移动`：直接使用原始数据进行分类，但在用训练好的分类器进行预测时，将下式加入到决策过程中，以调整正反例的平衡性  

![image](https://github.com/dyywinner/Python3_MarchineLearning/blob/master/image/Threshold_shift.png)　　

将数据集切分成两部分：train集(80%)和test集(20%)<br>
<br>
*交叉验证*:<br>
切分数据集成train和test集。比如把train集分成123三部分，1+2->3,1+3->2,2+3->1,三部分数据集互相验证模型，取消错误或者偏差数据对模型的影响<br>
```python
from sklearn.cross_validation import train_test_split
from sklearn.model_selection import train_test_split
X_train, X_test, y_train, y_test = train_test_split(X,y,test_size = 0.3, random_state = 0)
```
*模型评估方法*<br>
1.用精度评估(略微骗人)<br>
2.用recall召回率评估(更常用):<br>

Recall  | 相关(Relevant)正类 | 无关(NonRelevent)负类
----------|-----------|----------------
被检索到(Retrieved) | TruePositives(TP 正类判定为正类，正例) | FalsePositive(FP 负类判定正类，”存伪“)
未被检索到(NotRetrieved) | FalseNegitives(FN 正类判定为负类“误杀”) | TrueNegatives(TN 负类判定为负类，正例)
Recall = TP/(TP+FN)<br>

*正则化惩罚*<br>
L1：abs(w)<br>
L2: loss+1/2*w^2<br>
  
*混淆矩阵*<br>
![image](https://github.com/dyywinner/Python3_MarchineLearning/blob/master/image/ConfusionMatrix.png)  
在下采样数据集下测试，在整个数据集上测试<br>
  
*调整阈值对Logistic回归模型的影响*<br>
  
*过采样SMOTE算法*<br>
from imblearn.over_sampling import SMOTE # 过采样模块<br>

决策树
------

*树模型参数:*

-  1.criterion  gini  or  entropy 用什么作为衡量标准：gini系数或者熵

-  2.splitter  best or random 前者是在所有特征中找最好的切分点 后者是在部分特征中（数据量大的时候）

-  3.max_features  None（所有），log2，sqrt，N  特征小于50的时候一般使用所有的

-  4.max_depth  数据少或者特征少的时候可以不管这个值，如果模型样本量多，特征也多的情况下，可以尝试限制下

-  5.min_samples_split  如果某节点的样本数少于min_samples_split，则不会继续再尝试选择最优特征来进行划分如果样本量不大，不需要管这个值。如果样本量数量级非常大，则推荐增大这个值。

-  6.min_samples_leaf  这个值限制了叶子节点最少的样本数，如果某叶子节点数目小于样本数，则会和兄弟节点一起被剪枝，如果样本量不大，不需要管这个值，大些如10W可是尝试下5

-  7.min_weight_fraction_leaf 这个值限制了叶子节点所有样本权重和的最小值，如果小于这个值，则会和兄弟节点一起被剪枝默认是0，就是不考虑权重问题。一般来说，如果我们有较多样本有缺失值，或者分类树样本的分布类别偏差很大，就会引入样本权重，这时我们就要注意这个值了。

-  8.max_leaf_nodes 通过限制最大叶子节点数，可以防止过拟合，默认是"None”，即不限制最大的叶子节点数。如果加了限制，算法会建立在最大叶子节点数内最优的决策树。如果特征不多，可以不考虑这个值，但是如果特征分成多的话，可以加以限制具体的值可以通过交叉验证得到。

-  9.class_weight 指定样本各类别的的权重，主要是为了防止训练集某些类别的样本过多导致训练的决策树过于偏向这些类别。这里可以自己指定各个样本的权重如果使用“balanced”，则算法会自己计算权重，样本量少的类别所对应的样本权重会高。

- 10.min_impurity_split 这个值限制了决策树的增长，如果某节点的不纯度(基尼系数，信息增益，均方差，绝对差)小于这个阈值则该节点不再生成子节点。即为叶子节点 。
- n_estimators:要建立树的个数

