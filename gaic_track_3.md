## 赛道三"AI小花"团队分享

其实感觉没啥好分享的，看群里的大佬们聊天，感觉大家的思路都差不多。这篇文章主要记录一下尝试过的一些实验吧。

## 算法
  * 预训练MLM
  * finetune二分类
## 实验
* 数据增强
  
  尝试了闭包数据增强，基本没有提升；
* 预训练数据构造
  
  pair对 > 单句
* 预训练模型选择
  
  - 尝试了hfl/bert系列，uer/bert系列 和 英文bert；
  - uer系列模型比hfl效果更好；
  - google的[bert-base-multilingual-uncased](https://huggingface.co/bert-base-multilingual-uncased)效果也不错；
  - 尝试了nezha，目前我跑出来的结果没有bert好，可能是哪里搞错了吧？
* 对抗训练
  
  PGD，FGM都有提升；
* 预训练模型embedding初始化
  
  尝试了训练w2v初始化，没有随机初始化效果好；

现在线上成绩0.915(10-fold模型)，单模型最高0.906(ch12hu大佬的nezha已经0.909)，单模型并不高。
