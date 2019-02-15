tensorflow-gpu: 1.4.0<br>
tensorflow: 1.12.0<br>
cuda-8.0 & cuddnV6.0<br>

tensorflow属于计算密集型框架:
- 1  图
- 2  会话：运算程序的图
- 3  tensor: 张量
- 4  变量
- 5  模型保存与加载
- 6  自定义命令行参数

operation: 运算操作节点，所有操作是一个op

图：图默已经注册，一组表示tf.operation计算单位的对象和tf.Tensor表示操作之间流动的数据单元的对象.
获取调用：
- tf.default_graph()
- op, sess, tensor的graph属性
