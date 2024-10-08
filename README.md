# 刘二大人的PyTorch深度学习实践

## 概述

典型机器学习流程： 输入，手工提取特征，建立映射函数，输出。

维度诅咒：如果维度越多对数据的需求就越大。所以就需要降维，尽量保持高维空间里的特征。

深度学习流程：输入，简单的特征（像素值变成张量，将语音变成波形），设计一组额外的层提取特征，多层神经网络当作映射函数，输出。

反向传播：重点在于计算图。每一步的计算只能进行原子计算。

深度学习神经网络的重点：将不同的模块进行组装。

## 线性模型

准备数据集dataset，选择模型model， 进行训练training， 应用推理inferring

### 数据集

+ 训练集（Training Set）：用于训练模型，即用于调整模型参数（如神经网络的权重）。
+ 验证集（Validation Set）：用于调整模型的超参数和评估模型的性能，以避免过拟合。在训练过程中，模型不会直接用验证集来更新权重。
+ 测试集（Test Set）：用于最终评估模型的泛化能力，测试集仅在模型的最终评估时使用，不参与任何训练或调优过程。
+ 通常，数据集会分成三部分：训练集、验证集和测试集。常见的划分比例是：
  + 训练集：70%-80%
  + 验证集：10%-15%
  + 测试集：10%-15%

+ 过拟合：在‌模型训练过程中，模型在训练数据上表现非常好，但在未知数据或测试数据上表现较差的现象。这种现象通常发生在模型过于复杂，能够记住训练数据中的噪声和细节，而不是学习数据的通用模式时。过拟合是机器学习中一个常见的问题，它会导致模型的泛化能力下降，即在未见过的数据上表现不佳。
+ 泛化：指一个经过训练的模型在未见过的数据（即测试数据或新数据）上的表现能力。换句话说，泛化反映了模型不仅能在训练数据上表现良好，还能在未知数据上保持同样的高效性和准确性。
+ 验证集（开发集）：用于评估模型在训练过程中的性能的一个重要数据集。它在训练过程中起到辅助决策的作用，帮助选择最佳模型，并防止过拟合。

