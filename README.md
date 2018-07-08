# 20 Newsgroup 文档分类

## 数据
[http://www.qwone.com/~jason/20Newsgroups/](http://www.qwone.com/~jason/20Newsgroups/)

## 项目环境
- Python 3
- Tensorflow 1.0.1
- Keras 2.1.3
- NumPy
- scikit-learn
- NLTK
- RegEx
- plotly

## 运行说明

本地设备：MacBook Pro：2.6 GHz Intel Core i5；8 GB 内存；Intel HD Graphics 4000 1536 MB
AWS p2xlarge：4核 CPU；60 GB 内存；Tesla K80 12GB

项目拆分成了两个 ipynb 文件，1_document_classification_tfidf.ipynb 使用了 TFIDF 在朴素贝叶斯、支持向量机、决策树进行训练，2_document_classification_glove.ipynb 使用了 GloVe 在神经网络进行训练。

1_document_classification_tfidf.ipynb 包含了共有6种处理数据预处理方式，3种模型，一共18种组合。默认是全部运行进行对比，在 本地设备运行总共耗时42分钟（不含数据下载时间）。为了节省计算时间，可以选择性地运行一些模型组合（SVM模型运行大约需要5分钟，6种组合耗时30分钟）。

2_document_classification_glove.ipynb 使用了 GloVe 在神经网络进行训练。由于神经网络训练耗时很大，为节约时间，默认训练使用的是准确率最高的组合（glove.6B.300d, 不进行数据预处理, Dropout=0），在 MacBook Pro 训练共耗时大约70分钟（不含数据下载时间），在 AWS p2xlarge 训练共耗时3分钟（不含数据下载时间）。运行默认的模型，只需要下载 GloVe 6B（822MB）预训练模型，如果需要试验其他组合的模型，才需要下载 GloVe 840B（2.03GB）和 NLTK 数据（10MB）。神经网络所有尝试过的组合都已经导出 ipynb 文件和 html 文件，存储在 glove_result 文件夹，可以直接查看。



## 额外数据
- GloVe 6B（822MB）下载地址：[https://nlp.stanford.edu/data/glove.6B.zip](https://nlp.stanford.edu/data/glove.6B.zip)
- GloVe 840B（2.03GB）下载地址：[https://nlp.stanford.edu/data/glove.840B.300d.zip](https://nlp.stanford.edu/data/glove.840B.300d.zip)
- 文本预处理部分如需手动导入 NLTK 路径，需要将 nltk.data.path.append('nltk_data') 路径修改为本地路径，NLTK 数据（10MB）下载地址：[百度云](https://pan.baidu.com/s/1Tp-NsX9vWDgBVp14P3jNxw)
