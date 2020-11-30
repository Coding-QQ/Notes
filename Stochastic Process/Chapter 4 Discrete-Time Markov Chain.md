# Chapter 4 Discrete-Time Markov Chain 

### 定义

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105100022438.png" alt="image-20201105095239400" style="zoom:33%;" />

时齐马氏链：

$P(X_{n+1}=j|X_n=i)=p_{ij}$

$\sum_\limits{j=1}^np_{ij}=1$

考虑一步转移概率矩阵$P$和初始分布$s(0)$

**例：猫鼠迷宫（带吸收壁的二维随机游走）**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105095850656.png" alt="image-20201105095850656" style="zoom:33%;" />

老鼠随机到相邻的格子，猫和奶酪不动

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105095239400.png" alt="image-20201105100022438" style="zoom:33%;" />

则转移概率矩阵如上，其中状态7和状态9为吸收态

考虑三个问题

* 先找到奶酪的时间随时间n的概率分布
* 先找到猫的时间随时间n的概率分布
* 先找到奶酪的概率

**排队系统**

$X_n$为第n个顾客完成时，系统内的顾客数

$A_n$为第n个顾客服务时，到达的顾客数,$P(A_n=i)=a_i,i=0,1,2,...$

设队列的总容量是3

$X_{n+1}=\begin{cases}\min\left\{3,A_{n+1}\right\}\quad if\ X_n=0\\\min\left\{3,X_n-1+A_{n+1}\quad if\ X_n=1,2,3\right\}\end{cases}$

那么，到达必须要是无记忆的泊松到达，这个排队系统才是一个马尔科夫链，因为只有在任意时间顾客完成看下一个顾客到达的时间，与此顾客的完成时间无关。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105100837268.png" alt="image-20201105100837268" style="zoom:33%;" />

**例：（S，s）库存控制策略**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105101535290.png" alt="image-20201105101535290" style="zoom:33%;" />

直接把一步转移概率矩阵给你：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109134503270.png" alt="image-20201105101611747" style="zoom:33%;" />

要想让马尔可夫性成立，那么需求必须独立

### C-K方程

$p_{ij}^{(n+m)}=\sum\limits_{k=0}^\infty p_{ik}^{(n)}p_{kj}^{(m)}$

即$P^{(n)}=P^n$，第n步的概率分布$s(n)=s(0)P^n$

**猫鼠例子**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105102723226.png" alt="image-20201105102723226" style="zoom:33%;" />

因为从1到7，从1到9必须由偶数步才能到，故$p_{17}^{(n)},p_{19}^{(n)}$在n为奇数的时候为0，所以实际上$\lim\limits_{n\rightarrow\infty}s_7(n),s_9(n)$不存在

### 状态的分类

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105103410951.png" alt="image-20201105103410951" style="zoom:33%;" />

closed class：闭集

irreducible: 不可约的

**例：带吸收壁的一维随机游走**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105104219703.png" alt="image-20201105104219703" style="zoom:33%;" />

状态1~N-1是一个暂态集（不是闭集），肯定是会通过有限步跑出去的

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105104412905.png" alt="image-20201105104412905" style="zoom:25%;" />

$T_{ij}$ 首达时间

$f_{ij}^{(n)}$ 首达概率

$f_{ij}=P(T_{ij}<\infty)=\sum\limits_{n=1}^\infty f_{ij}^{(n)}$

$\mu_{jj}=E(T_{jj})$

recurrent: 常返态, positive recurrent: 正常返，null recurrent：零常返

transient: 暂态

**例：排队系统**

是一个不可约的马氏链，显然所有状态都是正常返的。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105101611747.png" alt="image-20201105105340265" style="zoom:33%;" />

$f_{03},f_{01}$都能收敛到1，但是收敛的速度不一样。

**例：猫鼠迷宫**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105105658192.png" alt="image-20201105105658192" style="zoom:33%;" />

则13，17，19的首达时间的期望值都是无穷（因为要么有限步到，要么永远到不了，被另外的状态吸收了）

**例:延迟更新过程**

从i出发，每一次到达j视为发生一次时间。那么第一次的时间是$T_{ij}$，之后每两次间隔的时间为$T_{jj}$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105110221835.png" alt="image-20201105110221835" style="zoom:33%;" />



<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105110235174.png" alt="image-20201105110235174" style="zoom:33%;" />

因此，正常返满足

$\sum\limits_{n=1}^\infty p_{jj}^{(n)}=\infty$

$d(i)$为状态i的周期，$d(i)=1$则状态i为非周期的

不可约链，所有状态的周期相同

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105110922403.png" alt="image-20201105110922403" style="zoom:33%;" />

状态3是非周期的，这个MC链又是不可约的，因此所有的状态都是非周期的

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105111247171.png" alt="image-20201105111247171" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105111345156.png" alt="image-20201105111345156" style="zoom:33%;" />

那么就有3个正常返闭集和一个暂态集合

### 不可约遍历链

Ergodic Markov Chain: 不可约遍历链，即不可约非周期正常返

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105112010332.png" alt="image-20201105112010332" style="zoom:33%;" />

$\lim\limits_{n\rightarrow \infty}\dfrac1n\sum\limits_{k=1}^np_{ij}^{(k)}=\dfrac1{\mu_{jj}}$，即为单位时间到达j的次数

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105112608526.png" alt="image-20201105112608526" style="zoom: 33%;" />

$\dfrac{\pi_j}{\pi_i}$表示从状态i回到状态i的周期内，在状态j上停留的期望次数

### 平衡方程

*不可约遍历链*

一个子集合，进入与出来的rate相同

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109134228223.png" alt="image-20201109134228223" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109134249489.png" alt="image-20201109134249489" style="zoom:33%;" />

**一维随机游走**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201105105340265.png" alt="image-20201109134503270" style="zoom:33%;" />

以p的概率+1，q的概率-1，那么这个链一定是不可约非周期的
那么根据平衡方程(其实就是$\pi=\pi P$)：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109134544941.png" alt="image-20201109134544941" style="zoom:33%;" />

所以$p\ge q$，那么这个链就是非常返的（会跑到无穷远的地方去）

**M/G/1排队系统**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109134905300.png" alt="image-20201109134905300" style="zoom:33%;" />

因为排队系统实际上是一个连续马尔可夫链，所以目前只考虑每次服务完成的时间点时系统的人数，这是一个马尔可夫嵌入链。

设$A$是某次服务期间的到达次数，其概率分布$a_j$就是所有服务时间的斯蒂尔吉斯积分

所以转移概率矩阵为:

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109135507121.png" alt="image-20201109135507121" style="zoom:33%;" />

则平稳分布满足 $\pi=\pi P$: 

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109135529667.png" alt="image-20201109135529667" style="zoom:33%;" />

设$\rho=\dfrac\lambda\mu$，即到达的速率与服务的速率之比

若$\rho<1$，则到达的速率小于服务的速率，就可以解出$\pi_0=1-\rho$ (具体咋解的上课没说)，然后就可以解出所有状态的极限分布$\pi$

**GI/M/1**

服务变成了马氏链，因此站在到达的时间点来看这个系统（构成嵌入链），那么原理与之前的例子是类似的：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109140038620.png" alt="image-20201109140038620" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109140054861.png" alt="image-20201109140054861" style="zoom:33%;" />

用平衡方程+平稳分布之和为1解出平稳分布。硬解是不容易解出来的，但是有人把这个解猜了出来$\pi_j=ca^j$

然后这个时候可以解一下关于$a$的方程

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109140346429.png" alt="image-20201109140346429" style="zoom:33%;" />

$r=\dfrac1\rho=\dfrac\mu\lambda$

找$y=x$与$y=B(x)$的焦点值，方法就是：不断取值$a_i=B(a_{i-1})$，不断迭代，那么$\left\{a_n\right\}$最终会收敛到不动点$a$

**质量检测**

先每一件都检查，要是有连续$i$个合格，那么就按批次抽检，$r$个为一批，每一批随机抽一个

假设某一批的抽检品为次品，那么再恢复到每一件都检查，直到再次有连续$i$个合格

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109140917288.png" alt="image-20201109140917288" style="zoom:33%;" />

状态$X_n$表示系统已经连续多少件合格了，假设每一件商品$p$的概率为次品，$q=1-p$为

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109141047777.png" alt="image-20201109141047777" style="zoom:33%;" />

一个r批次的商品，抽一件商品为次品的概率为$p\cdot \dfrac1 r=\dfrac pr$

可以解出平稳分布，以及平均检验率和漏检率：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109141552883.png" alt="image-20201109141552883" style="zoom:33%;" />

那么可以画出漏检率与(i,r)的关系曲线

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201109141645770.png" alt="image-20201109141645770" style="zoom:33%;" />

### 周期不可约马尔科夫链

通过编号可以把P转化成这种形式：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109142225975.png" alt="image-20201109142225975" style="zoom:33%;" />

**例**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109142411304.png" alt="image-20201109142411304" style="zoom:33%;" />

所以每一个方块里面都是一个P矩阵（行和为1，且不可约）

极限分布：$P^\infty=[\pi^T,\pi^T,\pi^T,...]^T$（把$\pi$看成一个行向量）

所以求$P^{3n}$的极限，得到每一个子块的平稳分布（相当于求每一个子块闭集的极限分布，再归一化）

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109142913040.png" alt="image-20201109142913040" style="zoom:33%;" />

$\lim\limits_{n\rightarrow\infty}P^{3n+i}=P^i\lim\limits_{n\rightarrow\infty}P^{3n}$

### 具有吸收态的马尔科夫链

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109143234913.png" alt="image-20201109143234913" style="zoom:33%;" />

$R\ne 0$,否则永远无法从Q到达吸收态，那么这个马尔科夫链可以看作两个毫无关系的马氏链了，因此，Q一定会有一行其行和小于1.

$R_n$相当于就是在Q里面转了$i$次($0\le i\le n-1$)，然后被吸收掉，所以$R_n=(I+Q+Q^2+...+Q^{n-1})R$

由于最终肯定会被吸收，所以$\lim_\limits{n\rightarrow\infty}Q^n\rightarrow 0$

所以就可以等比数列求和：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109143703149.png" alt="image-20201109143703149" style="zoom:33%;" />

$w_{ij}$表示从i出发，经过无穷步以后，经过j的平均次数

那么被吸收之前平均移动次数的概率可以这么求:

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109144120301.png" alt="image-20201109144120301" style="zoom:33%;" />

考虑首达时间$f_{ij}^{(n)}$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109144252794.png" alt="image-20201109144252794" style="zoom:33%;" />

**银行现金管理**

银行随时的现金不能太高，也不能太低，当资金在中间波动时不做处理；当超出了范围之后进行干预

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109144856134.png" alt="image-20201109144856134" style="zoom:33%;" />

超出了$\beta,\alpha$就被拽到$\beta,\alpha$线上去

那么，就考虑随时的成本，在$\alpha,\beta$之间时有成本，跑出去以后维持现金也有一个固定成本

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109145121438.png" alt="image-20201109145121438" style="zoom:33%;" />

可以写出转移概率矩阵

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109145155494.png" alt="image-20201109145155494" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201109145235379.png" alt="image-20201109145235379" style="zoom:33%;" />

分母为初始状态为$\gamma $的情况下在普通状态的停留时间

分子为在各个状态中的时候成本之和

那么$C(\alpha,\beta,\gamma)$为单位时间的成本

**计算$\tau_{ij}$**

表示从i开始，被吸收之前经过j的次数

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119100453209.png" alt="image-20201119100453209" style="zoom:33%;" />

或者用矩阵形式表示：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119100532890.png" alt="image-20201119100532890" style="zoom:33%;" />

**计算$\tau_i$**

表示从i开始，被吸收经历的步数

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119100654273.png" alt="image-20201119100654273" style="zoom:33%;" />

**网球比赛**

发球以后有四种情况：得分（发球直接得分），不得分（发球失误），或者对方接过来了；对方接过来还可以分为strong shot和weak shot。

所以就可以分为四种状态,0,1,2,3分别表示上面的4中状态：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119101055512.png" alt="image-20201119101055512" style="zoom:33%;" />

因为有两次发球机会，如果第一次挂了还可以有第二次机会：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119101333520.png" alt="image-20201119101333520" style="zoom:33%;" />

**只有一个吸收态**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119103254635.png" alt="image-20201119103254635" style="zoom:33%;" />

其中，$p_k$为第一次到达吸收态的概率。所以考虑$\tau=k$，当$k=0$时$p_0=\alpha_{m+1}$，当$k\ge 1$时，相当于几何分布，前k-1次都在非常返状态中，最后一次到达吸收态，所以$p_k=\alpha Q^{k-1}r$

使用z变换来求$\tau$的期望:

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201121160719840.png" alt="image-20201121160719840" style="zoom: 50%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119103332388.png" alt="image-20201119103332388" style="zoom:33%;" />

**一般化的二项分布（一维随机游走）**

$X_i$是独立的几何分布，但是不一定同分布，Y是X之和

相当于是，m个状态代表m个游戏，每个游戏成功的概率为$p_i$,失败的概率为$q_i$。从第一个游戏开始，一旦游戏成功就进入下一个游戏，$Y_n$表示第n步时停留在哪一个游戏。

因此，$Y$就是一维随机游走，只不过在每一个状态停留和到下一点的概率分别为$q_i,p_i$

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201119102929493.png" alt="image-20201119102929493" style="zoom:33%;" />

对应的矩阵为：

![image-20201119103203689](http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119103203689.png)

因为Y是$X_i$的卷积，所以它的z变换就是他们的乘积。其中，每一个X的z变换为：

$P_Z(x)=E(z^{X_i})=\sum\limits_{k=0}^\infty z^kq_i^{k-1}p_i=\dfrac{p_iz}{1-q_iz}$

**抽卡例子**

一共有52张卡片，每一次抽一张再放回去，什么时候能把所有卡片集齐。

假设已经抽到过$i-1$张不同的卡片了，要抽到第$i$张不同卡片的概率为$p_i=\dfrac{m-(i-1)}{m}$

所以用之前的公式，计算得$ET=235.98$，即平均抽取235.98次即可集齐所有卡片。

### 截断马尔科夫链

这是一个不可约遍历链，只关注与A上面的转移概率

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119104447180.png" alt="image-20201119104447180" style="zoom:33%;" />

从i到j的概率，为从i直接到j的概率+从U到Q到R再回到T的概率

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119104831508.png" alt="image-20201119104831508" style="zoom:33%;" />

那么只考虑A里面的极限分布：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119104923670.png" alt="image-20201119104923670" style="zoom:33%;" />

发现结果就是，再A里面的极限分布就是将其在A里面的重新归一化。也就是说$\lim\limits_{n\rightarrow\infty}P(Y_n=i)=\dfrac{\pi_i}{\sum\limits_{k\in A}\pi_k}$

### Markov Reward Processes

假设对于每一个状态，对应一个奖励值$r_i$，那么平稳时每个周期平均的奖励为：$g=\sum\limits_{j=0}^\infty r_j\pi_j$

假如考虑每一个周期的折扣因子$\alpha$，假设$g_i$表示$X_0=i$情况下所有周期的奖励之和，那么假设$g$是一个列向量，用矩阵的形式可以表示为：($g$的第$i$列为$P^{(n)}$的第i列乘r再对n求和，表示通过从状态i开始，转移n步所到达每个状态的概率乘上各个状态对应的奖励，再求和.)

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201121163336947.png" alt="image-20201121163336947" style="zoom: 50%;" />

例子：汽车保险

汽车保险的客户分为几个等级：从高保费到低保费的等级分别为1,2,3,4,5。每个等级中，有一个保费$h_i$，还有一个理赔起始点$d_i$，也就是说保险公司只理赔高于$d_i$的那部分钱。如果某年客户没有索赔过，就往下降一级（保费降低），否则往上升一级（保费提高）。等级越高的保费和理赔起始点越高，即$h_i>h_{i+1},d_i>d_{i+1}$

那么对于每个等级客户来说，当损失达到$s_i>d_i$时，才愿意去找保险公司麻烦，不然假设刚比$d_i$高一点就去理赔，那第二年保费会提高不划算。假设每年损伤的分布函数为$F$，那么其等级的转移概率矩阵为：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201121164838690.png" alt="image-20201121164838690" style="zoom:50%;" />

对于客户来说，停留在等级$j$的损失$r_j$为：首先是$h_j$的保费，其次，当损失低于$s_j$时承担所有损失（计算损失的期望），当损失高于$s_j$时只承担$d_j$的损失，再考虑一个折扣因子$\alpha$。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201121164852167.png" alt="image-20201121164852167" style="zoom:50%;" />

假设损失分布函数为$F_W=1-e^{\left(-\dfrac w v\right)^\beta},\alpha=\dfrac1{1+0.1}=0.9091$

假设没有保险，那么可以计算出期望的损失为：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201121165457763.png" alt="image-20201121165457763" style="zoom:50%;" />

假设有了保险，那期望的损失与$(s_1,s_2,...,s_5)$有关，那么期望的损失结果为：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201121165539187.png" alt="image-20201121165539187" style="zoom: 50%;" />



### 逆向马尔科夫链

根据未来的信息往回推

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201119112502276.png" alt="image-20201119112502276" style="zoom:33%;" />

我们通常讨论逆向的链都是已经达到平稳的了。

如果逆向链的转移概率矩阵和正向的P相等，那么马氏链可逆。马尔可夫链总是有逆向链的，但是逆向链不一定和正向链的转移概率矩阵相等。

逆向链和正向链就算P不一样，$\pi$都是一样的。也就是说P不一样，但是$\pi=\pi P$接出来的$\pi$都是一样的

