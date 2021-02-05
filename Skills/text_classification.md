# 文本分类

## 1 相关背景

### 1.1 应用场景

### 1.2 业界痛点

### 1.3 相关数据集以及SOTA算法表现

[文本分类综述 | 迈向NLP大师的第一步（下）]中列出了一些常用数据集及其规模。

### 1.4 工业界落地情况和案例分享

### 1.5 未来发展方向及挑战
1. 数据层面
  - 零样本/少样本学习。研究方向：通过学习各种语义知识来推断特征，例如学习类之间的关系和合并类描述。此外，潜在特征生成、元学习和动态记忆力机制也是有效的方法
  - 引入外部知识：如何为不同任务增加知识以及增加什么样的外部知识。研究方向：知识库或知识图谱
  - 多标签文本分类任务：如何减少训练过程中层次语义的丢失以及如何保留丰富而复杂的文档语义信息
  - 具有许多术语的特殊领域的文本分类：现有的预训练词向量难以使用
2. 模型层面
  - 如何在数据与计算资源以及预测性能之间进行权衡
3. 性能评估层面
  - 模型的语义鲁棒性：如果数据集中有一些对抗性样本，则模型的性能会大大降低
  - 模型的可解释性

## 2 技术细节

### 2.1 标准流程
![Flowchart of the text classification](https://github.com/songchangyi/Learning/blob/master/Skills/img/text_classification_flowchart.png)

### 2.2 评估指标
1. 单标签文本分类
  - Accuray, Error Rate
  - Precision, Recall, F1
  - EM
  - MRR
2. 多标签文本分类
  - Micro-F1, Macro-F1
  - P@K, R@K
  - NDCG
3. 解释
  - EM (Exact Match) : 预测中匹配到正确答案的百分比
  - MRR (Mean Reciprocal Rank) ：最靠前的真实文本的排序取倒数作为准确度，再对所有问题取平均。通常用于评估在问答(QA)和信息检索(IR)任务中排序算法的性能 ![MRR](https://github.com/songchangyi/Learning/blob/master/Skills/img/mrr.jpg)
  - P@K和R@K : 前K个文本中的查准率和查全率
  - NDCG (Normalized Discounted Cumulative Gain) : 归一化折损累计增益
    - CG：将每个推荐结果相关性累加
    - DCG：将CG中排名靠后的结构分数“打折”。按照log2_(i+1)进行打折。
    - NDCG：将DCG归一化。假设最正确的排序结果IDCG，NDCG = DCG / IDCG

### 2.3 常用算法原理

### 2.4 常用算法优缺点对比

### 2.5 技术选型指南

## 3 算法优化技巧

### 3.1 多分类多标签

### 3.2 其它技巧

## 4 工程优化技巧

### 4.1 大数据处理

### 4.2 在线学习

### 4.3 模型轻量化

### 4.4 推理延迟优化

## 参考文献
- [文本分类资料综述总结](https://github.com/xiaoqian19940510/text-classification-surveys)
- [文本分类综述 | 迈向NLP大师的第一步（下）](https://mp.weixin.qq.com/s/YqPzFcDMhgL9-1kmx3YeZg)
