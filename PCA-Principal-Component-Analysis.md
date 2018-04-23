#Principal Componet Analysis(PCA)


### Variance/Covariance
- why it is important in PCA?
- How to quantify them?
- How to estimate Variance in a given sample?
- How to estimate Covariance?


### Covariance Matrix
- Why it is important?
- What is CM? the defination.
- How to get it from a new co-ordinate?(diagonal/off-diagonal)
- The relationship bewteen the  

### Eigenvector/Eigenvalue


### A Low-Dim Matrix


## Main Steps in PCA

#### Introduction

when **projecting** a set of data onto **a lower dimensional subspace**, we need to do it ”intelligently” - i.e. by picking a subspace that **contains most of the variability (and structure)** of the original data.

维数约减 (Dimensionality Reduction) 是把高维度数据在损失最小的情况下转换为低维度数据的动作。

主成份分析法简称 PCA (Principal Component Analysis)是目前最常用和流行的数据降维方法。

Motivation：数据压缩，数据可视化。

#### Step 1: 数据预处理

在进行 PCA 算法前，需要对数据进行预处理。预处理包括两个步骤：

- 数据归一化 (Mean Normalization)：使数据的均值为零。加快 PCA 运算速度。
- 数据缩放 (Feature Scaling)：使不同的特征数值在同一个数量级。

#### Step 2: 计算协方差矩阵 (Covariance Matrix)

#### Step 3: 计算协方差矩阵的特征向量 (eigenvectors)：

我们如果需要把数据降维为 k 维，那么我们只需要选取前 k 个向量即可，即 $u^{(1)}, u^{(2)}, ... , u^{(k)}$。

#### Step 4: K 参数的选择

K 是主成份分析法中主成份的个数。

其中分子部分表示平均投射误差的平方；分母部分表示所有训练样例到原点的距离的平均值。这里的物理意义用术语可以描述为 99% 的数据真实性被保留下来了 (99% of variance is retianed)。

#### Step 5: 数据降维 A new low-dim matrix



向量化提高性能

#### More: 数据还原/优缺点





###Advantage/Drawback
