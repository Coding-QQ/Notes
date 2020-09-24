## 第二章 Convex Analysis: Basic Concepts

### 2.1 向量的组合

- 线性组合
- 非负线性组合（凸锥组合）
- 仿射组合

- 凸组合

### 2.2 凸集

1. 定义：任意有限个元素的凸组合仍然在该集合之中

   即：任意两点连线上的点仍然在该集合之中。

2. 凸包(Convex Hull)

   假设T是一个凸集，则有两个视角可以看：

   - 外视角：包含T的最小凸集
   - 内视角：T中任意有限个凸组合的全体构成的集合

3. 多面体

4. 多胞体

   定理：若P是一个多胞体当且仅当P是一个有界的多面体

### 2.3 锥（Cone）

1. 定义：对于集合C，若里面任意的x，对他进行伸缩后均在这个集合内，则称C为一个**锥**

   若$0\in C$，则称C是一个**尖锥（pointed cone）**

2. 若C既是锥，也是凸集，则称C为**凸锥(convex cone)**

3. 包含0的凸锥称为**尖凸锥**

4. 若多面体为尖凸锥，则称之为**多面锥**

### 2.4 仿射集

1. 定义：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200914145437098.png" alt="image-20200914145437098" style="zoom:33%;" />

2. 每个仿射集都是某个线性子空间的平移
3. 特殊的仿射集
   - 直线
   - 超平面
4. 仿射包
   - 外视角定义：包含S的最小仿射集
   - 内视角定义：S中任意有限个元素的仿射集的全体构成的集合

### 点集的维数、闭性与相关性

**维数（Dimension）**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200921134916037.png" alt="image-20200921134916037" style="zoom:50%;" />

平行子空间的维数=最多的线性无关向量的个数

**范数的定义**

范数是一种长度的推广



<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200921135128222.png" alt="image-20200921135128222" style="zoom:60%;" />

曼哈顿距离：1-范数

欧几里得距离：2-范数

**极限点与聚点**

极限点：一个数列$\left\{x_n\right\}$收敛到$x^*$

聚点：数列中的点聚集在一个点的附近

集合S的闭包$clS$是含于该集合的点列聚点的集合，即其所有极限点的集合

**几个“相对”概念**

设$x\in S,N_\epsilon(x)$表示$x$的邻域，对于某个$\epsilon>0$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200921140248794.png" alt="image-20200921140248794" style="zoom:50%;" />

**性质**

凸集的闭包和内部都是凸集

**仿射无关**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200921141148684.png" alt="image-20200921141148684" style="zoom:50%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200923195947626.png" alt="image-20200923195947626" style="zoom:50%;" />

我们可以用反正证明2，3等价：

假设存在$k_0,...,k_m$使得：$k_0(x^0,1)^T+...+k_m(x^m,1)^T=0\Longrightarrow k_0=-(k_1+...+k_m)\\k_0x^0+...+k_mx^m=k_1(x^1-x^0)+...+k_m(x^m-x^0)=0$

与$x^1-x^0,...,x^m-x^0$线性无关矛盾

那么，任意一个向量$(x,1)^T$可以用$(x^0,1)^T,...,(x^m,1)^T$表示，即：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200923200446533.png" alt="image-20200923200446533" style="zoom: 40%;" />

**也就是说：m+1个向量的凸组合相当于m个向量的线性组合**

