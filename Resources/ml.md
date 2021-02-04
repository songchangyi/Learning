# Machine Learning

## Data

【数据埋点】
- [数据埋点是什么？设置埋点的意义是什么？](https://www.zhihu.com/question/36411025)

【归一化与标准化】
- 结论：归一化是把数据缩放到0和1之间，标准化是转换为标准正态分布
- [归一化 （Normalization）、标准化 （Standardization）和中心化/零均值化 （Zero-centered）](https://www.jianshu.com/p/95a8f035c86c)
- [详解深度学习中的Normalization](https://zhuanlan.zhihu.com/p/33173246)

## Feature Engineering

【Feature Selection】
- 基本思想：有的时候模型其实很蠢，很多根本就和目标没有关联的东西，它也可以瞎扯一通和目标关联上，这种虚假的关联到测试集上当然就扑街了，
这就是我们常说的过拟合。那么回到我们一开始的问题，如何在feature importance中画出一条线，来区分这个特征是否有用呢？
思想很简单，就是将特征分数与随机假特征的分数（即Null Importance）进行对比，假如特征的分数并不能明显超过null importance，那么证明这个特征是一个无用的特征。
- [Feature Selection with Null Importances](https://www.kaggle.com/ogrellier/feature-selection-with-null-importances)
- [Automatic FE: Featuretools & Selection FE with SelectFromModel](https://www.kaggle.com/vbmokin/ashrae-automatic-fe-featuretools-selection-fe)
- [Featuretools (automatic FE&FS)](https://www.kaggle.com/vbmokin/titanic-featuretools-automatic-fe-fs)
- [谐门武学：特征选择与Null Importance](https://jonuknownothingsnow.github.io/2018/10/21/%E8%B0%90%E9%97%A8%E6%AD%A6%E5%AD%A6%EF%BC%9A%E7%89%B9%E5%BE%81%E9%80%89%E6%8B%A9%E4%B8%8ENull%20Importance/)

【Feature Aggregator】
- [FeatureAggregator: end-to-end feature engineering](https://www.kaggle.com/wrosinski/featureaggregator-end-to-end-feature-engineering)
- 特征聚合思想：选择重要的类别特征，利用pandas的groupby功能生成min/max/std/mean/median等特征。参考：https://zhuanlan.zhihu.com/p/32227873

## Modeling

【Tabnet】
- [Tabnet presentation](https://www.slideshare.net/SebastienFischman/tab-netpresentation/SebastienFischman/tab-netpresentation)
- [原始论文](https://arxiv.org/pdf/1908.07442.pdf)
- [Pytorch Tabnet](https://github.com/dreamquark-ai/tabnet)

【Model Ensemble】
- [Kaggle Ensembling Guide](https://mlwave.com/kaggle-ensembling-guide/)
- [中文翻译](http://www.6aiq.com/article/1536427413103?p=1&m=0)
- [An Introduction to StackNet by Competitions Grandmaster Marios Michailidis (KazAnova)](http://blog.kaggle.com/2017/06/15/stacking-made-easy-an-introduction-to-stacknet-by-competitions-grandmaster-marios-michailidis-kazanova/)
- [Porto Seguro Tutorial: end-to-end ensemble](https://www.kaggle.com/yifanxie/porto-seguro-tutorial-end-to-end-ensemble)
- [Kaggle提升模型性能的超强杀招Stacking——机器学习模型融合](https://www.jianshu.com/p/719fc024c0ec)

【Clustering Ensemble】
- [OpenEnsembles](https://github.com/NaegleLab/OpenEnsembles)
- [Cluster_Ensembles](https://github.com/GGiecold/Cluster_Ensembles)
- [Kaggle Ensemble Clustering](https://www.kaggle.com/noise42/ensemble-clustering)

## 参数

【Batch Size】
- [Batch Size设置](https://blog.csdn.net/weixin_36670529/article/details/107247014)

【自动调参】
- [Optuna](https://github.com/pfnet/optuna)
- [Optuna Doc](https://optuna.readthedocs.io/en/latest/tutorial/configurations.html#defining-parameter-spaces )
- [Optuna Kaggle notebook](https://www.kaggle.com/corochann/optuna-tutorial-for-hyperparameter-optimization )