## Nash Equilibrium

### Pure Strategy Nash Equilibrium

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925133524075.png" alt="image-20200925133524075" style="zoom:40%;" />

假设对于某一个player，别的player的策略都不变(均为$s_{-i}^*$)，那么选择一个最好的策略。

然后对于每一个player都成立

1. 如果给定了其他player的策略，那么自己的策略也固定了
2. 每个player都猜测其他玩家按照纳什均衡制定策略

**一种不存在pure nash equilibrium的情况**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925134114895.png" alt="image-20200925134114895" style="zoom:33%;" />

如果player1和2相同，则2赢；否则1不赢，这种情况下就不存在pure纳什均衡

### Mixed Strategies（混合策略）

1. 给每一个策略附上一个概率值，即玩家的策略服从某一个概率分布。

2. 设$\Sigma_i$为player i的策略集合，每一个策略的概率为：$\sigma_i(s_i)$

3. <img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925135041184.png" alt="image-20200925135041184" style="zoom:33%;" />
4. Pure strategies被称为退化的(degenerate) mixed strategies
5. 混合策略中概率为正的pure strategy称为support

### 混合策略的收益

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925135450276.png" alt="image-20200925135450276" style="zoom:33%;" />

收益为选择所有策略的期望

对于每一个$\sigma_i$来说，此函数是线性的。也就是说若其他player的策略不变，则收益相对于自己的$\sigma_i$是线性的。同时，此函数是所有策略组合$\sigma $的多项式函数

**寻找一个均衡的取值可能**

考虑各自的$\sigma_i$是否稳定（stable），就是看他们是否有动机去改变自身的策略。

有可能某个策略本来不是严格的dominated strategy，但是可以通过制定mixed strategy将一个策略设为dominated strategy(永远不选择此策略，即选择此策略的概率为0)

### Dominated Strategy的重新定义

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925141240334.png" alt="image-20200925141240334" style="zoom:33%;" />

不论其他player怎么选择($\forall s_{-i}\in S_{-i}$,但是别的人都是某个确定的策略，而不是概率)，都存在一个混合策略比当前策略($S_i$)好，则当前策略为dominated

### Mixed Strategy Nash Equilibrium

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925142413228.png" alt="image-20200925142413228" style="zoom:33%;" />

该定义下，有两个等价的命题：

1. <img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925143609234.png" alt="image-20200925143609234" style="zoom:33%;" />
2. <img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925143623113.png" alt="image-20200925143623113" style="zoom:33%;" />

因为上面两个等价的命题成立，则可以得出推论3：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925143655049.png" alt="image-20200925143655049" style="zoom:33%;" />

对于i来说，只存在若干个策略的概率>0，这些策略为support。那么在纳什均衡下，support中的策略对应的收益都是相等的（推论3）。

所以说，当其他player的策略$\sigma_{-i}^*$定下来之后，只有收益最高的策略的概率>0。如果有多个策略收益并列最高，则他们的概率都>0。这些收益最高的策略组成support。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925144739150.png" alt="image-20200925144739150" style="zoom:50%;" />

下面的两个式子中的第一个，左边是player1选择足球的收益，右边是player1选择芭蕾的收益，二者要相等，因此求出y=2/3，同理，求出x=2/3定理

### 纳什定理（Nash's Theorem）

一个有限游戏(finite game)存在mixed nash equilibrium

**证明：**

定义一个从$\Sigma_{-i}\rightarrow \Sigma_i$的最佳映射

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200925145315509.png" alt="image-20200925145315509" style="zoom:33%;" />

此时就需要证明：1.$B(\sigma)$非空; 2.映射$B$有一个不动点，这个不动点的定义与纳什均衡定义等价

1. **Weierstrass's Theorem**

   如果A是非空紧凑的有限维欧几里得空间，f是从A到$\R$的连续函数，则优化问题$\max\limits_{x\in A}f(x)$有解

   在给定其他人策略的情况下，$\Sigma_i$是一个$|S_i|-1$维的向量，是有界闭集，因此他们的乘积也是有界闭集。那么根据Weierstrass's定理，对于函数$u(\sigma)$是一个定义域在$\Sigma$的函数，那么他的最大值有解

2. **不动点定理**

   <img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200927134356470.png" alt="image-20200927134356470" style="zoom:40%;" />

   当一个函数（映射）满足四个条件，那么这个函数一定有一个不动点

   那么检验这四个条件

   1. $\Sigma=\prod_i\Sigma_i$是一个非空凸集，因为$\Sigma_i$是一个有限维向量

   2. $B(\sigma)$是非空的，由前可知

   3. $B(\sigma)$是凸的，因为:

      <img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200927134933300.png" alt="image-20200927134933300" style="zoom:50%;" />

   4. <img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200927135003119.png" alt="image-20200927135003119" style="zoom:50%;" />



