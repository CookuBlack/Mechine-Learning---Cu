# K-means算法

簇的中心称为簇质心 。

关键步骤：将每个点分配给簇质心，具体取决于最接近的簇质心。

步骤：

1. 随机初始化k个簇质心
2. 将点分配给聚类质心（遍历计算每个点的距离，$min||x^{(i)} - \mu_k ||^2$,（其中$\mu_k$表示每一个簇质心)，最小化距离进行划分。
3. 移动簇质心，更新的集群质心位置设置为分配给该集群k的点的平均值，公式：$\mu = \frac{1}{n}[x^{(1)}+x^{(2)}+\cdots + x^{(n)}]$  (如果一个簇质心分配为0个点，可以重新初始化簇质心位置，更常做的时直接删除该质心)



> **优化目标：**
>
> 符号定义：$C_i$ ：表示第i个样本点，$\mu _k$：表示第k个簇质心，$\mu _c^{(i)}$：表示第i个样本分配到了第C个簇质心的位置
>
> 成本函数：$J(C^{(1)},\cdots,C^{(m)},\mu _1,\cdots,\mu_k) = \frac{1}{m}\sum\limits_{i = 1}^{m}||x^{(i)} - \mu _{c}^{(i)}||^2$ 
>
> $\min{(C^{(1)},\cdots,C^{(m)},\mu _1,\cdots,\mu_k)} ~~~ J(C^{(1)},\cdots,C^{(m)},\mu _1,\cdots,\mu_k)$ 



## 选择聚类数量

一、 肘部法：

k的取值为1~m，分别绘出此时每一个k值的成本函数图像（x轴为k的取值，y轴为每一个k取值的成本）

二、根据实际意义进行确定，可以确定分类的下限

