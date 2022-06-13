## 推荐系统模块

### 漏斗形模型

- Recall
- Score
- Rank


![](https://s1.vika.cn/space/2022/06/13/4d09e3f0585e443d8af0107bf622714c)

### 深度推荐模型的发展

基于 Wide&Deep 进行不同方向的演化.

不同的模型拥有相似的模型逻辑

![](https://s1.vika.cn/space/2022/06/13/ccead0d4ea0c46a79c966613fc38416e)

## Torch-Rechub

独立开发的轻量级推荐算法框架

![](https://s1.vika.cn/space/2022/06/13/a315e64bac344f19aa4f092e2ef2c1d9)

### 数据层

#### 特征类

- DenseFeature
- SparseFeature
- SequenceFeature

#### 数据类

- DataLoader
- DataSet

和 PyTorch 的定义方式相同

#### 工具类

- 序列特征生成
- 样本构造
- 负采样
- 向量化召回
- ...

### 模型层

模型层具有基础的 Layer 类, 以及一些流行的特征建模模型.

- 浅层特征建模  
	- LR：逻辑回归  
	- MLP：多层感知机，可通过字典设置dims等参数  
	- EmbeddinLayer：通用Embedding层，含三类特征的处理，维护一个dict格式的  
	- EmbeddingTable，输出经过模型所需要的输入embedding  

- 深层特征建模  
	- FM、FFM、CIN  
	- self-attention、target-attention、transformer

通过模型层我们可以复现很多经典的推荐领域模型, 也可以自定义来个性化定制自己的模型.

已复现的论文模型: https://www.wolai.com/rechub/cNwGzNJpaouirvs3b8qxN

### Trainer 层

目前支持三种 Trainer 形式

- CTRTrainer
- MTLTrainer
- MatchTrainer