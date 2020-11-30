## Chapter 6: Mechanism Design

### Principle and Agent

Principle是一个可以设计机制（规则）的player（甲方），如苹果

Agent是那些遵守规则的player（乙方），如富士康

**例：**

* 假设甲方要委托乙方完成$q$件商品的生产

* 这批货物对于principle的价值为$S(q),S'>0,S''<0$

* 假设只有一个agent，production cost是$C(q,\theta)=\theta q$
* principle不知道agent的参数$\theta$，但是知道其概率分布:高效生产$\theta_e$，概率为$v$;低效生产$\theta_i$，概率为$1-v$，显然$\theta_e<\theta_i$
* 设principle支付的价格为$(q,t)$，指的是如果生产$q$件商品就支付$t$元

**时间线**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030134713666.png" alt="image-20201030134456186" style="zoom:33%;" />

### 完全信息情况

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030141415035.png" alt="image-20201030134713666" style="zoom:33%;" />

社会价值$W=S(q)-\theta q$，即其对于principle的价值减去其成本

$W'=S'(q)-\theta$

因为$S''<0$，则$S'(q_e^*)<S'(q_i^*)\Longrightarrow q_e^*>q_i^*$，即生产效率高了那么就多生产一点，且Social value更高

完全信息条件下，成本是多少就给多少：$t_e=\theta_eq_e^*,t_i=\theta_iq_i^*$

这种情况下，agent的收益就是0了，委托是没有代价的（costless）

### 不完全信息情况

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030134456186.png" alt="image-20201030140004364" style="zoom:33%;" />

**Incentive Compatibility Constraints.**

**甲方不愿意乙方假冒（隐瞒）自己的type**

在上述的规则下，假设我是乙方，且type为inefficient(参数为$\theta_e$)，但是我假装我是inefficient，那么甲方会给我$t_i$的支付

那么我的payment就是$t_i^*-\theta_eq_i^*=\theta_iq_i^*-\theta_eq_i^*>0$，这种情况下，假设甲方不知道agent的type，那么agent可能会虚报自己的type，这样就不好，说明这样的contract对甲方来说不好。

所以，我们要求contract应当是**incentive compatible**，即：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030140004364.png" alt="image-20201030140933854" style="zoom:33%;" />

上述条件叫IC constraints，如果满足了IC constraints，那么之前说的假冒情况就不可能发生了。

在IC限制下，$q_e\ge q_i$(将上面两个不等式相加可得)，此contract可以被执行

**Individual Rationality (IR) Constraints**

**乙方一定会愿意接受contract**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030142817041.png" alt="image-20201030141415035" style="zoom:33%;" />

乙方的获利一定不小于0，那么乙方就一定会接受这个contract

### 机制设计

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030142217445.png" alt="image-20201030142217445" style="zoom:33%;" />

决策变量为$t_e,q_e;t_i,q_i$，于是就变成了一个优化问题，将上面的目标函数进行变量替换。($t_k=U_k+\theta_k,\ k\in \left\{e,i\right\}$)

前半部分是social value，右半部分是informational rent（信息租金）

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030140933854.png" alt="image-20201030142817041" style="zoom:33%;" />

画一下可行域：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030142858858.png" alt="image-20201030142858858" style="zoom:33%;" />

逻辑：$q_e>q_i\ge 0$，是在IC条件成立的情况下满足的条件；但是我们先假设这个条件成立，相当于可行域减小了。那么在此新的可行域下，固定$q_e,q_i$，那么目标函数随着$U_e,U_i$单减，因此得到了$U_e^*,U_i^*$（都取最小值，也就是可行域的左下角），再代回去求$q_e,q_i$的解。如果确实满足$q_e>q_i$，那么就说明成立。

这里$U_i^*=0$是固定的，但是$U_e^*=\delta_\theta q_i$是一个与$q_i$有关的量，并没有固定。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030144233711.png" alt="image-20201030143518294" style="zoom:33%;" />

这里为什么是Second Best呢，因为不一定是对principle最好，考虑了agent有关的各种因素（IC,IR条件）

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030143518294.png" alt="image-20201030144233711" style="zoom:33%;" />

在这种情况下，如果agent是efficient，那么产量不变,$U_e$从完全信息的0变成了$\delta_\theta q_i^{SB}$；如果是inefficient，那么产量变小，$U_i$还是0。

也就是说，因为是不完全信息了，所以agent在efficient的情况下可以多赚一点，这也就是principle付出的informational rent（因为agent有信息上的优势）

此时，就达到了贝叶斯纳什均衡

**Mechanism Design**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030145941505.png" alt="image-20201030145613942" style="zoom:33%;" />

**General Mechanism**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201106134804622.png" alt="image-20201030145941505" style="zoom:33%;" />

决策与信息$m\in M$有关。相当于从$\theta_e,\theta_l\rightarrow M\rightarrow g(m)=(q(m),t(m))$，即principle并不知道$\theta_e,\theta_l$，但是可以知道与他们有关的信息$m$，然后决定$(q,t)$

$U_i$与自己的type和别人的type $\theta_i,\theta_{-i}$，以及allocation $y=(x,t)$都有关，于是就是一个在知道自己的$\theta_i$ 的情况下，对$\theta_{-i}$的一个期望

### Direct Mechanism

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201106134832987.png" alt="image-20201106134804622" style="zoom:33%;" />

一般的mechanism是先从$\Theta\rightarrow M\rightarrow g(m)$，那么这个$M$可能会非常大

Direct mechanism: 如果直接从$\Theta\rightarrow g'(\theta)$，直接从typespace去做一个映射，那么问题就会被简化。

**显示原理**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201030145613942.png" alt="image-20201106134832987" style="zoom:33%;" />

只要一个direct mechanism 在第二步满足 IR Constraints， 在第三步满足IC Constriants，那么这个direct mechanism就可以替代一个general mechanism，而达到相同的效果。



假设$m_i^*(\theta_i)$是满足IR,IC 条件的pure strategy，满足纳什均衡

考虑direct mechanism，那么就可以获得一个新的allocation rule: $\overline y(\hat\theta)=y(m^*(\hat\theta))$

假设$m_i^*$s  general mechanism下的纳什均衡，那么$\hat\theta=\theta$是在direct mechanism下的纳什均衡，也就是说大家均会表述自己的真实的type（因为$\hat\theta=\theta$）

推导过程：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201106135921062.png" alt="image-20201106135921062" style="zoom:33%;" />

第一步：direct mechanism下的收益函数

第二步：general mechanism下的收益函数

第三步：由于$m^*$是一个纳什均衡，所以就要从$M_i$中所有的$m_i$,取一个收获函数最大的，这样才符合贝叶斯纳什均衡的定义。

第四步：从message space缩小到type space，而显然$\Theta_i\subset M_i$，所以从$=$变成了$\ge$，而之前$m_i$可以在$M_i$中选的，当到type space中以后，$\theta_i$就只能从映射到$m_i^*$的那些type中选择

第五步：由于全是在type space中，所以可以又回到之前的写法$\theta$

最后又回到了direct mechanism下的收益函数

### 非线性定价（p164）

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201106143344861.png" alt="image-20201106143344861" style="zoom:33%;" />

顾客可以购买商品，得到的盈利为$\theta V(q)$，并且向seller支付$T$的价格。因此，其收益函数$u_1(q,T,\theta)=\theta V(q)-T$，其中，consumer知道自己的类型$\theta$，而seller只知道它作为每一个type的概率。seller生产每件商品的成本为$c$

因此，seller的profit为：

$Eu_0=\underline p(\underline T-c\underline q)+\overline p(\overline T-c\overline q)$

考虑IR, IC constriants：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201107104615511.png" alt="image-20201107104615511" style="zoom:33%;" />

考虑IR,IC constraints：

* 如果IR1和IC2成立了，那么：

  $IR_2: \overline \theta V(\overline q)-\overline T\ge \overline \theta V(\underline q)-\underline T\ge \overline \theta V(\underline q)-\underline\theta V(\underline q)=(\overline\theta-\underline\theta)V(\underline q)\ge0$

​	即IR2成立

* IR2一定是不等式严格成立或者$\underline q=0$，根据上面的推导，IR2严格成立$\Longrightarrow V(\underline q)=0\Longrightarrow \underline q=0$
* IR1必须是等号成立，即：$\underline \theta V(\underline q)=\underline T$。否则seller 可以等量地提升$\underline T,\overline T$的值，不影响IC constraints的结果，但是知道IR1会先达到等号成立。
* IC2必须是等号成立,否则提升$\overline T$的值，由于IC2 成立时IR2一直成立，因此不影响其他不等式的方向，直到IC2取到等号。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201107110956642.png" alt="image-20201107110956642" style="zoom:33%;" />

那么现在就只剩下了两个等式约束

### 第二个例子

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201106145510734.png" alt="image-20201106145510734" style="zoom:33%;" />

当商品的价值大于seller的价值，低于buyer的价值时，交易成功。特别的，一般来说交易额是二者价值的平均值。由于4个格子有3个格子都以1的概率完成交易，因此完全信息情况下，完成交易的概率为3/4

假设，按照这个机制，变成不完全信息的，那么就可以推导：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201107125334473.png" alt="image-20201107125334473" style="zoom:33%;" />

对于weak buyer和weak seller来说，撒谎都会增加收益，因此他们就都会撒谎，这就不对了。所以需要设计新的机制。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201106150202403.png" alt="image-20201106150202403" style="zoom:33%;" />

此时需要设计一个机制y(q)，使得完成交易的概率更大，并且要满足所有的player都不会撒谎。

也就是说：现在的规则修改为：当Strong和Strong或者Weak和Weak相遇后，交易的结果是确定的。但是当Strong和Weak相遇后，不一定能够达成交易。假设$q$的概率完成交易，并且我们可以设定价格$y$。我们每设定一个价格$y$，就可以得到一个让所有player都不会撒谎的$q$的范围，然后里面$q$可以取得最大值。或者说$q$的最大值是一个关于$y$的函数。所以，我们的目标就是，确定一个$y$使得最大的$q$最大.

$IR\ constraints: \begin{cases}y\le 20\\100-y\le100\\y\ge0\\100-y\ge80\end{cases}\Longrightarrow 0\le y\le 20$

其中前两条不等式是针对buyer的，后两个不等式是针对seller的

$IC\ constraints:$ 先考虑Weak seller

$truth:\ u_t=\dfrac12 qy+\dfrac12\times 50\\lie:\ u_l=\dfrac 12\times0+\dfrac12\times(100-y)q$

$\therefore u_t\ge u_l\Longrightarrow \dfrac12 qy+25\ge\dfrac12 (100-y)q\\\Longrightarrow q\le\dfrac{25}{50-y}\bigg|_{0\le y\le20}$

$\therefore q_{max}=\dfrac{25}{30}=\dfrac56\Longrightarrow \dfrac{q+q+1}4=\dfrac23<\dfrac34$

