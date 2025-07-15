# NLP 关系抽取模型集合

本项目包含两种基于深度学习的关系抽取方法，分别基于传统的 BiLSTM+注意力机制以及预训练模型 BERT。

## 项目结构

| 文件名                                                 | 方法简介                                                     |
| ------------------------------------------------------ | ------------------------------------------------------------ |
| `Approach1_bilstm+multi_head_attention+gate_nyt.ipynb` | 基于 BiLSTM + 多头注意力机制 + 门控机制 的关系抽取模型，适用于 NYT 数据集。 |
| `Approach2_bert_mlp_EPCA_final.ipynb`                  | 基于 BERT 表征 + MLP 分类器 的关系抽取模型，实现了 EPCA 结构（可能为特定策略优化）。 |



##  方法简介

### 1️⃣ Approach 1: BiLSTM + 多头注意力 + 门控机制

- 利用双向 LSTM 进行句子建模，提取上下文特征。
- 引入 **Multi-head Attention** 机制增强句子的关键特征建模能力。
- 使用门控机制融合不同信息通道（如句法、语义等），提升模型鲁棒性。
- 适用于远程监督下的 NYT 数据集。

### 2️⃣ Approach 2: BERT + MLP + EPCA

- 基于预训练语言模型 **BERT** 提取全局句子语义。
- 利用 **多层感知机（MLP）** 进行关系分类。
- 融入 EPCA（Enhanced Position-aware Contextual Attention）结构，增强位置感知能力，提升对实体关系的建模效果。
- 通常在准确率和泛化能力上优于传统模型。

------



## 运行环境

建议使用如下配置：

- Python 3.8+
- PyTorch / TensorFlow（具体依赖见笔记本）
- `transformers`（适用于 BERT 模型）
- Jupyter Notebook 或其他可交互执行环境

建议使用 GPU 进行训练和推理。

------



## 数据集说明

模型默认使用 **NYT（New York Times）** 数据集进行训练与评估。若需使用其他数据集，需根据数据格式修改数据加载部分代码。
