# 自然语言处理

## 背景与展望
- [NLP综述（思维导图）](https://zhuanlan.zhihu.com/p/56802149)
- [BERT时代与后时代的NLP](https://zhuanlan.zhihu.com/p/66676144)

## 对话机器人chatbot
- [智能客服机器人分类图](https://blog.csdn.net/u011646912/article/details/102816281)
- [知乎专栏：对话机器人](https://www.zhihu.com/column/c_1154767675480821760)
- [五八同城智能客服系统“帮帮”技术揭秘](https://mp.weixin.qq.com/s/5ewD2xD8J08W89-Rwixw4Q)
- [智能机器人在滴滴出行场景的技术探索](https://mp.weixin.qq.com/s/MSy8OHzR3avObmOq9uSSFQ)
- [搜索query意图识别的演进](https://mp.weixin.qq.com/s/0Hh_iV8tNFd0eEpXSxy9nA)
- [智能问答算法原理及实践之路笔记](https://www.jianshu.com/p/c47a1d1cff7a)

【Rasa】
- [rasa文章导引（用于收藏）](https://zhuanlan.zhihu.com/p/88112269)
- [Rasa教程系列](https://blog.csdn.net/ljp1919/category_9656007.html)
- [Rasa算法官方教程](https://www.youtube.com/playlist?list=PL75e0qA87dlG-za8eLI6t0_Pbxafk-cxb)
- [Chatbot_CN](https://github.com/charlesXu86/Chatbot_CN)
- [rasa_chatbot_cn](https://github.com/GaoQ1/rasa_chatbot_cn)
- 从源码看，rasa中的transformer只使用了encoder

Rasa NLU Pipeline
- [Rasa教程系列-NLU-4-组件](https://blog.csdn.net/ljp1919/article/details/103975263)
- [Finetune BERT Embeddings with spaCy and Rasa](https://github.com/JulianGerhard21/bert_spacy_rasa)
- [EmbeddingIntentClassifier官方文档](https://legacy-docs-v1.rasa.com/nlu/components/#embeddingintentclassifier)
- [Understanding Rasa Tensorflow intent classifier](https://medium.com/@tatiana.parshina/understanding-rasa-tensorflow-intent-classifier-e9d4ef019c6)
- [StarSpace: Embed All The Things!](https://blog.csdn.net/Forlogen/article/details/91345913)
- [论文阅读——StarSpace:Embed All The Things!](https://www.jianshu.com/p/35c15221c1c4)
- [Triplet Network and Mining and Loss](https://allenlu2007.wordpress.com/2019/06/08/triplet-network-and-loss-and-tensorflow-face-recognition-%E4%BA%BA%E8%87%89%E8%AD%98%E5%88%A5/)
- [How to Use BERT in Rasa NLU](https://blog.rasa.com/how-to-benchmark-bert/)
- [检索式回答](https://github.com/RasaHQ/rasa/blob/master/rasa/nlu/selectors/response_selector.py)
- [在Rasa中使用其它预训练模型](https://medium.com/@expanded_blue_elk_810/rasa-loading-fasttext-vectors-with-spacy-1aad2a2431b)

Rasa Core Policies
- [Policy官方文档](https://rasa.com/docs/rasa/policies/)
- [Rasa教程系列-Core-5-Policies](https://blog.csdn.net/ljp1919/article/details/104002385)

Rasa Test CI/CD
- [Test](https://rasa.com/docs/rasa/testing-your-assistant/)
- [CI/CD](https://rasa.com/docs/rasa/setting-up-ci-cd)

## 命名实体识别 NER

【实战链接】

Rasa中的NER
- 结论：可以使用ner_spacy实现人名提取
- [rasa blog - 深入理解rasa NLU: Part2 - 实体识别 (翻译)](https://zhuanlan.zhihu.com/p/84220988)
- [原文链接](https://blog.rasa.com/rasa-nlu-in-depth-part-2-entity-recognition/)

Spacy官方NER demo
- [displaCy Named Entity Visualizer](https://explosion.ai/demos/displacy-ent)

经典建模实现NER
- 结论：CRF，BiLSTM以及BiLSTM+CRF都有不错的表现，超过HMM
- [NLP实战-中文命名实体识别](https://zhuanlan.zhihu.com/p/61227299)

Bert实现NER
- [基于BERT 的中文数据集下的命名实体识别(NER)](https://github.com/xuanzebi/BERT-CH-NER)
- [BERT-BiLSTM-CRF命名实体识别应用](https://www.omegaxyz.com/2020/05/18/bert-bilstm-crf/)
- [Bert-NER](https://github.com/binhking/Bert-NER)

Kashgari - 一个工业级NLP迁移学习框架
- [Kashgari](https://github.com/BrikerMan/Kashgari/)

CRF详解
- [如何用简单易懂的例子解释条件随机场](https://www.zhihu.com/question/35866596)
- [CRF损失计算](https://zhuanlan.zhihu.com/p/44042528)

【领域背景】

5种框架在NER上的表现对比
- 结论：TextSpace > StanfordNLP > spaCy > IBM MAX = Dialogflow
- [Benchmarking Named Entity Recognition: StanfordNLP, IBM, spaCy, Dialogflow, and TextSpace](https://towardsdatascience.com/benchmarking-named-entity-recognition-stanfordnlp-ibm-spacy-dialogflow-and-textspace-af6615eb7930)

## 分词 Tokenization

【中文】

中文NLP分词
- 结论：分为基于词典和基于统计的算法。常见的分词器都是使用两者的结合。
- 存在问题：分词标准不一，歧义（组合型，交集型，真歧义），新词
- [中文分词利器 jieba 和 HanLP](https://www.jianshu.com/p/009671e56027)
- [中文分词原理和工具总结](https://blog.csdn.net/sinat_26811377/article/details/102802044)
- [中文分词器分词效果评估对比](https://github.com/ysc/cws_evaluation)

## 特征抽取

【子词嵌入】
- [BytePair Encoder算法](https://zhuanlan.zhihu.com/p/38130825)

【通用句编码器】
- [Universal Sentence Encoder论文分享](https://zhuanlan.zhihu.com/p/35174235)
- [Universal Sentence Encoder论文详解](https://blog.csdn.net/qq_33624866/article/details/106279666)

【文本关键词提取】
- [TF-IDF计算文本相似度](https://zhuanlan.zhihu.com/p/113017752)
- [用sklearn的TF-IDF模块进行短文本关键词提取](https://zhuanlan.zhihu.com/p/58474443)
- [关键词抽取示例-sklearn的TfidfVectorizer](https://zhuanlan.zhihu.com/p/67753695)
- [Quest2keys](https://github.com/ArmandGiraud/quest2keys)
- [短文本关键词提取](https://zhuanlan.zhihu.com/p/163426574)
- [关键词智能提取](https://zhuanlan.zhihu.com/p/25889937)
- [SIFRank_zh](https://github.com/sunyilgdx/SIFRank_zh)

## 情感分析
- [Word2vec情感分析和分类](https://cloud.tencent.com/developer/article/1061949)

## 主题建模
- [LDA模型应用：一眼看穿希拉里的邮件](https://github.com/NLP-LOVE/ML-NLP/blob/master/Machine%20Learning/5.3%20Topic%20Model/HillaryEmail.ipynb)
- [gensim LDA模型的优劣评估](https://zhuanlan.zhihu.com/p/33053850)
- [手把手教你学会 LDA 话题模型可视化 pyLDAvis 库](https://toutiao.io/posts/c7853u/preview)
- [Gensim LDA](https://radimrehurek.com/gensim/wiki.html#latent-semantic-analysis)

## 文本匹配
- [实践DSSM召回模型](https://zhuanlan.zhihu.com/p/136253355)

## 文本分类聚类

【UMAP聚类可视化】
- [Rasa官方分块标注示例](https://github.com/RasaHQ/rasalit/blob/master/notebooks/bulk-labelling/bulk-labelling.ipynb)

【聚类模型】
- [DBSCAN聚类原理](https://www.jianshu.com/p/e8dd62bec026)
- [利用sklearn训练LDA主题模型及调参详解](https://blog.csdn.net/TiffanyRabbit/article/details/76445909)

【大规模文本聚类】
结论：使用增量聚类算法，比如single-pass。对每条文本，计算与已有类的相似度，高于则加入该类，低于则创建新类。
- [大数据量的文本聚类](https://www.zhihu.com/question/59920681/answer/760343357)

【大规模文本分类】
- [深度学习解决大规模文本分类问题](https://cloud.tencent.com/developer/article/1399904)
- [文本分类效果对比](https://github.com/brightmart/text_classification)
- [短文本分类，腾讯AI Lab联合港中文提出主题记忆网络](https://www.jiqizhixin.com/articles/2018-10-23-6)

聚类小结：
- [聚类之层次聚类、基于划分的聚类（k-means）、基于密度的聚类、基于模型的聚类](https://blog.csdn.net/qq_16365849/article/details/50646679)
- [聚类算法评估指标](https://zhuanlan.zhihu.com/p/115752696)
- [聚类算法评估指标](https://www.biaodianfu.com/cluster-score.html)
- [中文文本聚类实验](https://github.com/FesonX/cn-text-classifier)

## 知识图谱
- [知识图谱在贝壳找房的从0到1实践](https://mp.weixin.qq.com/s?__biz=MzU1NTMyOTI4Mw==&mid=2247485923&idx=1&sn=27735f64a2196ba7210503da84c90c33&chksm=fbd4bb8fcca3329939fbec3673773f005839b68cc41471075917b6063fb80ac045b01678164f&scene=21#wechat_redirect)

## 知识追踪
- [深度知识追踪入门](https://zhuanlan.zhihu.com/p/134707265)
- [知识追踪代码](https://github.com/sulingling123/Knowledge_Tracing)

## 搜索引擎
- [神马搜索技术演进之路](https://mp.weixin.qq.com/s?__biz=MzU1NTMyOTI4Mw==&mid=2247485830&idx=1&sn=621393b30e179660de9b35d57da60752&chksm=fbd4bbeacca332fcfe9733a126f07386ad66c3a0381b5e0c2daa81c70d88d0d19048fad645c1&scene=21#wechat_redirect)

## 模型

【Word2Vec】
- [Word2Vec的参数解释](https://blog.csdn.net/laobai1015/article/details/86540813)
- [Word2Vec的簡易教學與參數調整指南](https://www.kaggle.com/jerrykuo7727/word2vec)

【Fasttext】
- [官方模型链接](https://github.com/facebookresearch/fastText/blob/master/docs/crawl-vectors.md#models)

【TextCNN】
- [TextCNN的优化经验](https://www.cnblogs.com/ModifyRong/p/11442661.html)

【RNN】
- [RNN GRU LSTM参数计算](https://blog.csdn.net/imhuay/article/details/80267269)

【Transformer】
- [Transformer论文翻译](https://so.csdn.net/so/search/s.do?q=Transformer%E8%AE%BA%E6%96%87%E8%AF%A6%E8%A7%A3%EF%BC%8C%E8%AE%BA%E6%96%87%E5%AE%8C%E6%95%B4%E7%BF%BB%E8%AF%91&t=&o=&s=&tm=&v=&l=&lv=&u=&ft=)
- [放弃幻想，全面拥抱Transformer](https://zhuanlan.zhihu.com/p/54743941)
- [Transformer和Bert相关知识解答](https://zhuanlan.zhihu.com/p/149634836)
- [NLP中 batch normalization与 layer normalization](https://zhuanlan.zhihu.com/p/74516930)
- [关于batch normalization和layer normalization的理解](https://blog.csdn.net/HUSTHY/article/details/106665809)
- [超细节的 BERT/Transformer 知识点](https://cloud.tencent.com/developer/article/1748590)
- Transformer使用Adam优化器

【Bert】
- [BERT模型原理详解系列](https://zhuanlan.zhihu.com/p/46652512)
- [超细节的BERT/Transformer知识点](https://zhuanlan.zhihu.com/p/132554155)
- [BERT是如何分词的](https://cloud.tencent.com/developer/article/1524436)
- [BERT encoder参数量计算](https://lsc417.com/2020/06/19/bert_parameter/)
- [CPU上的Bert性能优化](https://blog.roblox.com/2020/05/scaled-bert-serve-1-billion-daily-requests-cpus/)
- [跨语种语言模型](https://zhuanlan.zhihu.com/p/139630839)
- [后BERT时代：15个预训练模型对比分析与关键点探究](https://cloud.tencent.com/developer/article/1491568)

Bert的位置编码可以有PE，正弦余弦编码。还可以使用层次分解位置编码来处理超长文本
- [层次分解位置编码，让BERT可以处理超长文本](https://mp.weixin.qq.com/s/bSOHfuwKZRY7WkqfXVkAPA)

为什么不需要decoder：作为一个预训练的模型，我们只需要学习到句子对应的向量，然后给下游任务使用
- [详解谷歌最强NLP模型BERT](https://www.mdeditor.tw/pl/2ihW)

在具体的NLP任务上，BERT模型的输入输出会有细微的差别
- [图示详解BERT模型的输入与输出](https://www.cnblogs.com/gczr/p/11785930.html)

- Bert的前馈层使用Gelu激活函数

【Bert变种】
- [RoBERTa 和 ALBERT](https://www.jianshu.com/p/769e66e085fe)
