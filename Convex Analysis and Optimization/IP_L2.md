## Well-Solved Problems

### 1 Properties of a Well-solved Problem

**Separation Problem**

如果可以用一个超平面将原问题的可行域与非可行域分开，则是一个COP问题的Separation problem。

一般来说，一个Well-solved-problem 通常含有下面的性质：

1. Efficient optimize property: 对于问题$P$，有一个多项式复杂度的算法可以求解此问题
2. Strong dual property: 存在一个强对偶问题D，且可以很快地验证：$x^*\in X$是$P$的最优解当且仅当存在一个$u^*\in U$且$c^Tx^*=w(u^*)$
3. Efficient separation property: 有一个高效的算法来求解$P$的separation problem
4. Explicit convex hull property: 假设$conv(X)$是一个已知的紧集，那么可以用一个线性规划$\max\left\{cx: x\in conv(X)\right\}$

### IPs with Totally Unimodular matrices

可以将线性规划中$Ax\le b$中的$A$分解为$A=(B,I)$，其中$I$对应0变量的子矩阵，$B$对应那些非负分量的子矩阵。

$(B,I)(x_m,x_{n-m})^T= b$，也就是说$B$是基矩阵，$B$的列所对应的分量$X$是基本可行解。（下图中$(P_{k(1)},...,P_{k(m)})=B$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116204540668.png" alt="image-20201116204540668" style="zoom:33%;" />

也就是说，最优解$x=(x_B,x_N)=(B^{-1}b,0)$，其中$B^{-1}b\ge 0$

当基矩阵$B$的行列式值为$det(B)=\pm1$时，线性规划的最优解也为整数规划的最优解。

**全幺模矩阵(totally unimodular matrix)**

若矩阵$A$的任何子方阵的行列式值均为$\pm1,0$，那么$A$为全幺模矩阵（TU）

全幺模矩阵的性质（假设$A$为全幺模矩阵）：

1. $A$的所有元素$a_{ij}=0,\pm1$
2. $A$是TU当且仅当$A^T$是TU
3. 矩阵$(A,I)$是TU

$A$是全幺模矩阵的充分条件：

$a_{ij}=0,\pm1$，每一列包含最多2个非零元素，且存在一个行分割$(M_1,M_2)$，使得两个分割中的行向量先在分割内求和，然后作差，结果为0.

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116210248299.png" alt="image-20201116210248299" style="zoom: 80%;" />

$A$是全幺模矩阵的充要条件：任意$A$的行子矩阵是equitable bicoloring的

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116210434787.png" alt="image-20201116210434787" style="zoom: 80%;" />

推论：若$a_{ij}=0,\pm1$，每一列包含最多2个非零元素，且A满足equitable bicoloring

定理：对于$\max\{c^Tx|Ax\le b,x\in\R^n_+\}$，对于任意的整数向量$b$都存在有界的整数最优解，当且仅当A是全幺模的。

### 3 Optimal Trees

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116211436325.png" alt="image-20201116211436325" style="zoom: 80%;" />

一个没有环的图为一棵树；若干棵树叫森林。

图论中，$G=(V,E)$是一棵树当且仅当：

1. 它是一个森林（无圈），且包含$n-1$条边
2. 它是$V$的一个最小支撑树（用最少的边将所有的点连接起来）
3. T中任意两点有唯一的一条通路
4. 增加任意一条边，都会得到唯一一个圈。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116212143419.png" alt="image-20201116212143419" style="zoom: 50%;" />

**最大支撑树问题**

寻找一个最大的支撑树，拥有最大的权重（寻找一个拥有最大权重的森林）

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116212307454.png" alt="image-20201116212307454" style="zoom: 80%;" />

其中$x_e$表示边$e$选中与否，S表示森林的集合，也就是说每一个$S$是一个森林

两种解法:

1. 先选择最大的边，将其相连的两点加入到子集合中（子集和最开始为空集）。然后观察连接子集和内外的边，将最大的边连接的子集和外的点加入到子集和中，直到所有的点都被加入到子集和中。(迪杰斯特拉算法)

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116213247378.png" alt="image-20201116213247378" style="zoom:50%;" />

2. 先将边长度从大到小排序，然后再从小到达选择边，并且已经选择的边不能成环。（克鲁斯卡尔算法）

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201116213337919.png" alt="image-20201116213337919" style="zoom: 50%;" />

### 4. Submodularity and Matroid

一个自变量为集合的函数为**次模的**：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116213658174.png" alt="image-20201116213658174" style="zoom:80%;" />

一个自变量为集合的函数为**非降的**：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116213716911.png" alt="image-20201116213716911" style="zoom:80%;" />

次模函数的例子：

考虑一个图$G=(V,E)$, 定义此图的一个“割集”为一个边集$F=\delta(S)\sub E,S\sube G$, 其中$\delta(S)=\{e\in E|e=(u,v),u\in S,v\notin S \}$, 即运筹学里面讲的：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201121110714208.png" alt="image-20201121110714208" style="zoom: 33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201121110848119.png" alt="image-20201121110848119" style="zoom:33%;" />

那么，设$f(S)=|\delta (S)|$，即$f$为连接集合$S$内外的边的数量，那么$f$就是次模的:

$|\delta (S)|+|\delta(T)|=|\delta(S\cap T)|+|\delta(S\cup T)|+2|(T\backslash S):(S\backslash T)|\\\ge |\delta(S\cap T)|+|\delta(S\cup T)|$

即S的割集+T的割集=$S\cap T$的割集+$S\cup T$的割集+起点为$T\backslash S$，终点为$S\backslash T$中的边数*2

所以$f$为次模函数，但是显然$f$不一定是非降的。



定理：一个函数是非降且次模的当且仅当：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201116213858549.png" alt="image-20201116213858549" style="zoom:80%;" />

