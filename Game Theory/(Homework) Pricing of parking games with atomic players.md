# Pricing of parking games with atomic players  

## 3 Optimal Pricing

#### 3.1 Optimal  price vector

通过定价的方式，引导所有的车辆选择全局最优解，而不是每个人的均衡解。

**Proposition 4**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201213155559084.png" alt="image-20201213155559084" style="zoom: 50%;" />

所有的全局最优价格向量是一系列的多面体的并集。这个并集$T^1=\cup_{\tilde x\in X^*} W(\tilde x) $，表示将所有的全局最优解对应的$p$都并起来，每一个$W(\tilde x)$都是一个多面体，满足(9)-(11)。

对于一个给定的$\tilde x$,由于已经是全局最优解了，所以就满足(2),(7),(8)。对于价格向量来说，需要让此全局最优解满足纳什均衡，所以只需要将(1)-(6)变成(9)-(10)即可。此时，每辆车对于每个车位的成本变成了$e_{ij}+p_j $.

以Section2中的例子来说，其全局最优解是(1,3),(2,2),(3,1)，此全局最优解同时也是一个纳什均衡解。此时，p所满足的多面体并集为：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201213162015528.png" alt="image-20201213162015528" style="zoom:50%;" />

（按理来说，应该是多个多面体的并集。但是，这个例子只有一个全局最优解，因此只有一个多面体，这个多面体是关于p的，也就是说p是未知数。）

其中，前三个式子表示(9)，后6个式子表示(10)

考虑SO的KKT条件：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201213164618931.png" alt="image-20201213164618931" style="zoom: 50%;" />

其中$\beta_i,\alpha _j$是（2）和（7）的拉格朗日乘子。那么(12)就是拉格朗日函数，即$\nabla L=\dfrac{\partial f}{\partial x_{ij}}+\beta_i\dfrac{\partial (2)}{\partial x_{ij}}+\alpha_j\dfrac{\partial (7)}{\partial x_{ij}}=e_{ij}+\alpha_j-\beta_i=0$，其中(2)式改写成$1-\sum_jx_{ij}=0$，然后不等式约束满足$\alpha_j\ge0,(1-\sum_ix_{ij})\alpha_j=0$

此时，设定$\gamma_{ij}=0,\beta_i=\mu_i,\alpha_j=p_j$，那么此时，上面的KKT条件也就包含了(9)-(11)，且此时$(...,\alpha_j,...)$就是一个最优价格向量。这至少保证了$T^1$不是空集。当然，满足这个拉格朗日乘子的价格向量$p$必然是最优价格向量，但是最优价格向量不一定是拉格朗日乘子。

#### 3.2 Valid price vectors

假设价格向量$p$确定了，有可能有多个对应的均衡解，其中至少有一个是全局最优解。但是，另外一些解可能不是全局最优解，甚至是比较差的解，这就脱离了一开始研究的初衷。因此，定义valid price vector，表示此价格向量$p$对应的所有均衡解均为全局最优解。

因此，valid price vectors所满足的多面体就是：$T^2=\cup_{x\in X^*}W(x)\backslash\cup_{x\notin X^*}W(x)$，即$p$要满足全局最优解，同时他不能满足非全局最优解。

但是，上述的$T^2$可能是空集。下面就给出了一个例子：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201213193939999.png" alt="image-20201213193939999" style="zoom: 67%;" />

所以说，必须要valid price vector存在，下面就给出了一个定理，也就是valid price存在的充分条件：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201213194333123.png" alt="image-20201213194333123" style="zoom: 67%;" />

### 4 Robust Pricing

由于valid price不一定存在，我们可以进行一个补救的方法：即设计一个pricing，使得该方案产生的最差的均衡解的成本最小。那么新的模型（RP）如下所示：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201213195410597.png" alt="image-20201213195410597" style="zoom: 67%;" />

这是一个min-max问题，非常难解决，因此采用迭代的方法，每次找到其上下限，当上下限相等时停止循环：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201213203228513.png" alt="image-20201213203228513" style="zoom:67%;" />

此问题可以求出上限

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201213203250945.png" alt="image-20201213203250945" style="zoom:67%;" />

此问题可以求出下限

因此，基于上述的方法，进行迭代：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201213203323928.png" alt="image-20201213203323928" style="zoom:67%;" />

