Xgboost
--------  
[中文文档地址：](http://xgboost.apachecn.org/cn/latest/)
[英文文档地址：](http://xgboost.apachecn.org/en/latest/)
[中文文档 GitHub 地址：](https://github.com/apachecn/xgboost-doc-zh)  
[xgboost链接github](https://github.com/dmlc/xgboost)

测试GPU,分别执行<br>
```python
    python benchmark.py --tree_method gpu_hist
    python benchmark.py --tree_method hist
    python benchmark.py --tree_method gpu_exact
    python benchmark.py --tree_method exact
```
*xgboost调参*
Xgboost参数:
- 'booster':'gbtree',
- 'objective': 'multi:softmax', 多分类的问题
- 'num_class':10, 类别数，与 multisoftmax 并用
- 'gamma':损失下降多少才进行分裂
- 'max_depth':12, 构建树的深度，越大越容易过拟合
- 'lambda':2,  控制模型复杂度的权重值的L2正则化项参数，参数越大，模型越不容易过拟合。
- 'subsample':0.7, 随机采样训练样本
- 'colsample_bytree':0.7, 生成树时进行的列采样
- 'min_child_weight':3, 孩子节点中最小的样本权重和。如果一个叶子节点的样本权重和小于min_child_weight则拆分过程结束
- 'silent':0 ,设置成1则没有运行信息输出，最好是设置为0.
- 'eta': 0.007, 如同学习率
- 'seed':1000,
- 'nthread':7, cpu 线程数
- #GPU相关参数,GTX950M
- 'gpu_id': 0,
- 'max_bin': 64,
- 'tree_method': 'gpu_hist',
