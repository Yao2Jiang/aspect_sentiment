# Attention-based LSTM for Aspect-level sentiment Classification
## 原始论文
 Duyu Tang, Bing Qin,Xiaocheng Feng,Ting Liu
proceeding of the 26th internation Conference on Computational Linguistics(COLING 2016,full paper)
[ https://arxiv.org/abs/1512.01100 ]
## 论文复现
### 主要的函数接口
 - 数据操作模块通过class data（）；返回词向量矩阵（w2v)(a2v)单词到id的映射表(word2id)(aspect2id)。
  > load_word2vec:根据路径取出词向量文件，通过词向量文件，构造基础word2id（dict)
  > load_word2vec_file():将词向量文件与训练集进行combine，生成完整的word2id,词向量矩阵。
  > change_y_2_onehot():数据集中的标签为-1，0，1形式将其转化为onehot类型-1 to [1,0,0]
  > load_aspect_id():生成aspect的词向量矩阵a2v和aspect2id(dict)
 - class construct_data(),读取测试数据，标准化测试数据
 > load_raw_data():从目标位置读取数据
 > tokenization_sentence(self,word2id):对word进行标记化，word转化成对应ID
 - class lstm_attention():网络结构
 > embedding 层：将单词ID映射为特征
 > combine 操作：将word与aspect进行融合
 > attention 权重生成：将每个单词产生的hidden与aspect的特征相乘，然后进行softmax操作。
 > logsoftmax: 进行三分类
 
 
 