## 第三章 Operations and Decomposition of Convex Sets

### 3.1 Operations of Convex Sets

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200921142409201.png" alt="image-20200921142409201" style="zoom:50%;" />

**相对内部的非空性**

给定一个非空的凸集，则其相对内部一定是非空的。

证明：构造了一个集合X，此集合的相对于$aff(S)$是一个相对开集，即所有的点都在其相对内部。那么既然X均在其相对内部，且X非空，那么非空凸集的相对内部一定非空。

**S相对内部的仿射集=S的仿射集**

**引理**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200921143448343.png" alt="image-20200921143448343" style="zoom:50%;" />

证明：

1. 若$\overline x\in S$，

   首先，$x$的$\epsilon$邻域内的点$N_\epsilon$均在相对内部，那么设$x_\alpha$为$[\overline x,x]$线段上一点,设：

   <img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200923203736058.png" alt="image-20200923203736058" style="zoom:40%;" />

   对于$\forall z\in N_{\alpha\epsilon}(x_\alpha)$，可以构造:

   <img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200923205824962.png" alt="image-20200923205824962" style="zoom:40%;" />

   即$z'\in N_\epsilon(x)$

   则$N_{\alpha \epsilon}\cap aff(S)$为$N_\epsilon\cap aff(S)$和$\overline x$的凸组合

   由于$N_\epsilon\cap aff(S)$和$\overline x$都属于S，则$N_{\alpha \epsilon}\cap aff(S)$也属于S

   则$x_\alpha\in ri(S)$

2. 若$\overline x\notin S$，则$\overline x\in cl(S)$，用点列$\left\{x^k\right\}$来逼近它，$x^k\in S$

   当k足够大时，$N_{\frac{\alpha\epsilon}{2}}(x_\alpha)\sub N_{\alpha\epsilon}(x^k)$，由于之前已经证了$N_{\alpha\epsilon}(x^k)\cap aff(S)\sub S$，则$N_{\frac{\alpha\epsilon}{2}}(x_\alpha)\cap aff(S)\sub S$

   

   

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200921144920781.png" alt="image-20200921144920781" style="zoom:50%;" />

### 3.2 回收锥定理

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200921145814024.png" alt="image-20200921145814024" style="zoom:50%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200921145838469.png" alt="image-20200921145838469" style="zoom:50%;" />



