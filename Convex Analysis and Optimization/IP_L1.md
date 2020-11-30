## Formulation, Optimality and Relaxation(Duality)

### 1 Problem and Formulation

两类问题:

1. Integer Problem (IP)

2. 0-1 Integer Problem (BIP)
3. Combinatorial Optimization Problem：组合优化问题。此类问题其实也可以用IP问题来表示。

**Formulating IPs and BIPs**

1. 定义重要的变量
2. 定义变量之间的约束条件
3. 定义目标函数

对于组合优化问题，经常会使用类似于$x^S$的向量，其中$x_j^S=1$如果$j\in S$，否则$x_j^S=1$

然后PPT中举了一些例子

### 2 Alternative Formulations

在不同的表述方法下，可能对应相同的集合：比如下图中两种表述方式，对应的整数点集相同。

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201116160822388.png" alt="image-20201116160822388" style="zoom:33%;" />

等价问题的表述方式：

方式1：保持原有的变量，但是更改或者增加一些约束条件

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116161050225.png" alt="image-20201116161050225" style="zoom:33%;" />

方式2：增加或者更改变量

 比如对于库存问题来说，增加变量$w_{it}$，表示周期$i$生产的产品满足周期$t$的量

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116161415355.png" alt="image-20201116161415355" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116161358771.png" alt="image-20201116161358771" style="zoom:33%;" />

**理想的formulation方式**

最为理想的formulation方式显然就是：最优的整数点恰好是可行域多面体的顶点。

由于X的凸包的顶点都是在X中，所以可以讲原问题的可行域转化为原可行域的凸包

在多数情况下，假设X有两种Formulation $P_1,P_2$，哪个越小哪个就越好：

显然$X\sub conv(X)\sub P$，若$P_1\sub P_2$，那么$P_1$就更好

### 3 Optimality

一个最naive的想法：每一次循环中，为最优解找到一个upper bound和lower bound。当两个bound相差值小于一个数时结束迭代。

所以就有两个bound：**Primal bound**和**Dual bound**

Primal bound：就是任意一个可行解可以作为一个primal bound

Dual bound：将原问题替换为松弛问题。其中，松弛问题的可行域不变小，目标函数不变差，那么松弛问题的最优解就是原问题最优解的上限。

### 4 Relaxation

**线性规划的松弛问题**

例子：一个整数规划问题：先看（斗）出一个可行解，得到下限；再去除整数约束，得到上限（还可以根据整数的限制，得到一个更好的上限），最终得到最优解的取值范围。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116193428410.png" alt="image-20201116193428410" style="zoom:33%;" />

**定理：**在之前判断什么样的Formulation更好的时候，认为越小的$P$越好，接下来的定理证明了$P$越小，代表松弛问题得到的上下限限制越严格。

**定理：**（1）如果松弛问题无解，那么原问题也无解（2）如果松弛问题的最优解$x^*$恰好在原问题的可行域内，那么$x^*$也是原问题的最优解

**组合优化的松弛问题**

例子：旅行商问题（TSP）

原问题的松弛问题可以是：选择的那些边组成1-tree

**拉格朗日松弛**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116194457064.png" alt="image-20201116194457064" style="zoom: 80%;" />

### Duality

弱对偶问题：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116194646845.png" alt="image-20201116194646845" style="zoom: 80%;" />

当$z=w$时为强对偶问题。

性质：

1.如果对偶问题（LD）是无界的，那么原问题是无解的。同理，如果原问题无界那么对偶问题无解。

2.如果$x^*$是原问题最优解，且存在$u^*\in U,c(x^*)=w(u^*)$，那么$u^*$是对偶问题最优解。

**Matching Dual**

对于一个图$G=(V,E)，V，E$分别表示点和边。其中$M\sub E$表示一个边的集合，其中的边互不相交（disjoint，表示无共同端点）。对这些边的覆盖（A covering by nodes）表示一个点的集合$R\sub V$，如果每个边都有至少一个端点属于$R$。

那么最大匹配问题和最小覆盖问题互为对偶问题

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116195810308.png" alt="image-20201116195810308" style="zoom: 80%;" />

证明：假设$|M|=k$，则$M$中有k个互不相交的边，对应$2k$个互不相同的点（如果有相同的点，则与相交矛盾）。由于对于这个k个边中每一条边，至少有一个端点在$R$中，因此$|R|\ge k=M$，证毕。

考虑一个图对应的邻接矩阵和边矩阵$A$，其中$A$为$|V|$行$E$列的矩阵。定义为：如果第$j$个点是第$e$个边的端点，那么$a_{je}=1$，否则为0。那么上面的问题可以写成下面的问题：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116201103278.png" alt="image-20201116201103278" style="zoom:33%;" />

其中，$x$是一个边的集合。$Ax$是一个$|V|$行的列向量，每一行表示对应的点出现在端点的次数，因此$Ax\le 1$，$1x$表示边的数量

$y$是一个点的集合，$yA$是一个$E$列的行向量，每一列表示对应的边出现在点集端点的次数，因此$yA\ge 1$，$1y$表示点的数量

这个问题是一个弱对偶问题。而如果$G$是一个二部图，那么就变成了一个强对偶问题。