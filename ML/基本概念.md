# 什么是梯度
梯度的本意是一个向量，表示某一函数在该点处的方向导数沿着该方向取得最大值，即函数在该点处沿着该方向（此梯度的方向）变化最快，变化率最大
- [百度百科-梯度](https://baike.baidu.com/item/%E6%A2%AF%E5%BA%A6/13014729)

# 梯度和残差的关系
1. 残差：残差在数理统计中是指实际观察值与估计值（拟合值）之间的差
2. Gradient Boosting通过拟合残存使得模型的更加精确（降低模型的偏差Bias），Residual Block的通过拟合残差使得深度网络能够变得更深更强
3. GBDT建树时拟合的是负梯度。但GBDT使用的回归树经常使用平方误差作为划分准则，所以此时拟合的目标值可以看成是残差的形式
- [一文让你读懂GBDT(梯度提升树) 和 Resnet (残差网络)的原理](https://www.jianshu.com/p/cd3be2fcc8a3)
- [gbdt的残差为什么用负梯度代替](https://www.zhihu.com/question/63560633)

# 什么是梯度下降
1. 梯度下降法是一个一阶最优化算法，要使用梯度下降法找到一个函数的局部极小值，必须向函数上当前点对应梯度（或者是近似梯度）的反方向的规定步长距离点进行迭代搜索。如果相反地向梯度正方向迭代进行搜索，则会接近函数的局部极大值点；这个过程则被称为梯度上升法
2. 为了让损失函数的数值下降，那么就需要使用优化算法进行优化，其中，损失函数值下降最快的方向称为负梯度方向，所使用的算法称为梯度下降法
- [维基百科-梯度下降法](https://zh.wikipedia.org/wiki/%E6%A2%AF%E5%BA%A6%E4%B8%8B%E9%99%8D%E6%B3%95)
- [机器学习：梯度下降算法是如何工作的](https://blog.ailemon.me/2019/10/21/machine-learning-how-gradient-descent-works/)

# 什么是梯度消失
随着算法向下传播到较低层，梯度通常会越来越小。结果梯度下降更新使较低层的连接权重保持不变，训练不能收敛到一个好的最优解。我们称其为梯度消失问题
- [【深度学习】梯度消失和梯度爆炸问题的最完整解析](https://jishuin.proginn.com/p/763bfbd2f7c9)
- [神经网络训练中的梯度消失与梯度爆炸](https://zhuanlan.zhihu.com/p/25631496)

# 什么是梯度饱和
1. 梯度饱和即自变量进入某个区间后，梯度变化会非常小，导致训练过程中梯度变化缓慢，从而造成模型训练缓慢
2. 解决方法：使用非饱和性激活函数比如ReLu。Normalization
- [梯度饱和](https://zhuanlan.zhihu.com/p/111579675)

# 怎么解决梯度消失
ReLu, Batchnorm,残差结构
- [详解机器学习中的梯度消失、爆炸原因及其解决方法](https://blog.csdn.net/qq_25737169/article/details/78847691)

没有激活函数会不会有梯度消失：梯度消失/爆炸是激活函数和权重相互作用产生的联合效果，不单单是激活函数的问题
- [为什么会有梯度爆炸和梯度消失](https://www.zhihu.com/question/290392414)

# Batch size
1. batch：相对噪声低些，幅度也大一些，你可以继续找最小值（训练快，迭代次数少，容易陷入局部最优）
2. SGD：有很多噪声的，平均来看，它最终会靠近最小值，不过有时候也会方向错误，因为随机梯度下降法永远不会收敛，而是会一直在最小值附近波动。一次性只处理了一个训练样本，这样效率过于低下。
3. mini-batch：实践中最好选择不大不小的 mini-batch，得到了大量向量化，效率高，收敛快。

# BatchNorm的原理和作用
解决什么问题：
1. ICS（Internal Covariate Shift）内部协方差漂移：在深层网络训练的过程中，由于网络中参数变化而引起内部结点数据分布发生变化
2. ICS的问题：上层网络需要不停调整来适应输入数据分布的变化，导致网络学习速度的降低。训练中参数逐渐更新并变大，网络的训练过程容易陷入梯度饱和区，减缓网络收敛速度

如何解决：
1. 归一化：输入每个特征的分布均值为0，方差为1
2. 引入两个可学习参数来恢复数据本身的表达能力

测试阶段使用整个样本的统计量来对Test数据进行归一化

优势：
1. 使得网络中每层输入数据的分布相对稳定，加速模型学习速度
2. 使得模型对网络中的参数不那么敏感，简化调参过程，使得网络学习更加稳定
3. 缓解梯度消失问题
4. 具有一定的正则化效果

- [Batch Normalization原理与实战](https://zhuanlan.zhihu.com/p/34879333)

# Bagging和Dropout有什么区别
1. 目的都是为了防止过拟合，但是bagging是针对于data，dropout是针对于特征
2. Bagging的各个模型之间是相互独立的，而Dropout各个模型之间是共享权重的
3. Bagging是随机抽样，训练多个模型投票。Dropout相当于特征选择
- [神经网络中的Dropout和Bagging](http://sofasofa.io/forum_main_post.php?postid=1000436)
- [Dropout的Bagging思想以及使用要点](https://zhuanlan.zhihu.com/p/163833907)

# Bert Embedding使用
TF中如何取第三层embedding：取出第三层outpout，hidden_states = outputs[4]
- [How to get all layers(12) hidden states of BERT](https://github.com/huggingface/transformers/issues/1827)
用Bert提取词向量是什么原理：使用某一层或者某几层的第一个位置的向量
- [bert生成句向量](https://cloud.tencent.com/developer/article/1461418)
- [使用BERT生成句向量](https://blog.csdn.net/u012526436/article/details/87697242)
