# Chapter 2 Poisson Processes

### 定义

Poisson过程是一个计数过程，其中相邻两个事件发生的概率为独立同分布的指数分布随机变量

**基本特性**

1. $N(0)=0$

2. 平稳增量过程：增量的分布与时间无关

   独立增量过程：发生的事件相互之间不影响

3. $P\left\{N(h)=1\right\}=\lambda h+o(h)$

4. $P\left\{N(h)\ge2\right\}=o(h)$

概率分布列：$P\left\{N(t)=n\right\}=e^{-\lambda t}\dfrac{(\lambda t)^n}{n!}$

### Poisson过程时间间隔

设$S_n$为第n次到达时的时间，$X_n=S_n-S_{n-1}\Rightarrow S_n=\sum\limits_{k=1}^nX_k$

n=1时，从补函数入手：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200924101449995.png" alt="image-20200924101449995" style="zoom:40%;" />

n=2时，用条件分布

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200924101551856.png" alt="image-20200924101551856" style="zoom:40%;" />

一直同理，得$\left\{X_n\right\}$服从独立同分布的指数分布

$S_n$服从Erlang分布（n个iid的指数分布之和）

即$S_n\sim Erlang(n,\lambda)$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200924102446859.png" alt="image-20200924102446859" style="zoom:50%;" />

上述为第n次事件在[0,t]各个时间点发生的概率密度

### 通过仿真构造指数分布的方法

先构造一个[0,1]之间的均匀分布，然后再反映射到指数分布随机变量X上去

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200924103017442.png" alt="image-20200924103017442" style="zoom:50%;" />

### 到达时间的条件分布

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200924104250374.png" alt="image-20200924104250374" style="zoom:40%;" />

生成n个[0,t]的均匀分布的变量$U_1,U_2,...,U_n$，这些对应于n个到达时间。而对于相同的到达时间$S_1,...,S_n$，可以将$U_1,...U_n$任意交换顺序，因此一个$S_1,...,S_n$对应于n!个$U_1,...,U_n$情况之和，因此概率为$\dfrac{n!}{t^n}$

### 非时齐泊松过程(Nonhomogeneous Poisson Processes)

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200924111935450.png" alt="image-20200924111935450" style="zoom:40%;" />

设$m(t)=\int_0^t\lambda(t)$为强度函数，则

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200924112121185.png" alt="image-20200924112121185" style="zoom:50%;" />

此时，发生的时间就不是均匀分布了，而是满足：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200924112258671.png" alt="image-20200924112258671" style="zoom:40%;" />

**计算机模拟非时齐泊松过程**

法1

1. 找一个比$\lambda\ge\lambda(t)$
2. 用$\lambda$生成一组到达时间Si
3. 以$\lambda(S_i)/\lambda$的概率接受这个到达时间（将这个到达时间设为此非时齐泊松过程的到达时间）

法2

1. 设定$\lambda=1$
2. 生成一组$\lambda$到达时间Si
3. 将这些事件进行转换（调整到达时间）：$Z_i=m(S_i)=\int_0^{Si}\lambda(u)du$，相当于$S_i$和$Z_i$的发生次数相等，对应的时间长度之比为$Z_i:m(S_i)$

**例**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010101447067.png" alt="image-20201010101447067" style="zoom: 50%;" />

先用极大似然估计来计算一个$\lambda(t)$

将实际的到达时间转化成参数为1的泊松分布：$Z_i=m(S_i)=\int_0^{S_i}\lambda(u)du$，看下与理论上参数为1的泊松分布的差别

### M(t)/M/s 排队系统

以$\lambda(t)$为参数的泊松到达，服务时间为$\mu$的指数分布，一共有$s$个服务台

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010102434234.png" alt="image-20201010102434234" style="zoom:40%;" />

当k个服务台一起服务时，时间间隔为参数为$k\mu$的指数分布

然后建立微分方程

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010103445487.png" alt="image-20201010103445487" style="zoom:40%;" />

假设系统稳定了，极限概率分布存在，$t\rightarrow+\infty$，则$Q(t)P(t)=0$

**对上例的数值计算**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010104330396.png" alt="image-20201010104330396" style="zoom: 40%;" />

排队长度最长为4，超过以后顾客不会进入系统

## M/G/∞ 排队系统

比如公园，泊松到达，在里面停留服从$G(t)$分布的时间

为了最终的分布平稳，那么离开也是泊松过程，且平稳之前参数为$\lambda(t)=\lambda G(t)$，当t趋于无穷时，G(t)=1，则离开也是$\lambda$的泊松过程

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010105328704.png" alt="image-20201010105328704" style="zoom:40%;" />

证明：从定义证明

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010110708186.png" alt="image-20201010110708186" style="zoom:50%;" />

第一部分：证明离开满足泊松过程（因为相当于是泊松到达的顾客分为两类，一类是(s，s+r)区间内离开的，一类是非(s，s+r)区间内离开的），并且计算参数

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010110102780.png" alt="image-20201010110102780" style="zoom:33%;" />

将（s，s+r）期间离开的顾客，分为s之前到达的和（s，s+r）期间到达的

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010110155352.png" alt="image-20201010110155352" style="zoom:33%;" />

这一页PPT的解释：

考虑在y时刻到达的所有顾客和时间$t$。那么这些顾客可以分为两类：1.在t时刻前离开的 2.在t时刻后离开的，概率分别为$P(y)$和$1-P(y)$。则$P(y)=G(t-y)$。那么对于区间$D(s,s+r)$，所有的顾客可以分为两类：在$(s,s+r)$离开的和不在$(s,s+r)$离开的，那么相当于就是一个泊松分布的分流，所以服从泊松分布且强度（平均发生次数）为$\lambda pt$，其中，$p$为从$[0,t]$到达的顾客的平均分流概率，其中假设这个顾客是y时刻到达的，则概率为$P(y)$，因此需要对$P(y)$从1到t积分并且求平均值。

其中，s之前到达的顾客，停留时间为$[s-y,s+r-y]$，则概率$P(y)=G(s+r-y)-G(s-y)$。$[s,s+r]$期间到达的顾客，停留时间只能为$s+r-y$，则概率为$P(y)=G(s+r-y)$。对于$[s+r,t]$时刻到达的顾客，不可能在$[s,s+r]$离开，因此概率为0.

所以，经过计算，得到$p=\dfrac1t\int\limits_s^{s+r}G(z)dz$，那么，如果考虑整个事件尺度$t>s+r$，那么$[s,s+r]$离开的顾客平均数量为$\lambda pt=\lambda\int\limits_s^{s+r}G(z)dz$。那么相当于对于离开这个泊松分布来说，强度函数$\lambda(t)=\lambda G(t)$，即在$t$时刻离开的人数，满足强度$\lambda(t)=\lambda G(t)$的泊松分布

第二部分：对于两个不交的离开时间区间，里面的顾客的到达时间都不同，互相独立，则两个离开时间区间的人数也都是独立的。

### M/G/∞ 排队系统结论

对于$t$时刻，留在系统内的顾客数和离开系统内的顾客数均满足非时齐泊松过程。

**离开系统内的顾客数**

在$t$时刻之前到达系统的顾客，在$t$时刻前离开系统的平均概率为$p$

$p=\dfrac1t\int_0^t G(t-s)ds=\dfrac1t\int_0^t G(s)ds$，离开人数的期望为$\lambda pt=\lambda\int_0^tG(s)ds=\int_0^t\lambda_1(s)ds$

$\lambda_1(t)=\lambda G(t)$，

**留在系统内的顾客数**

在$t$时刻之前到达系统的顾客，在$t$时刻仍在系统内的平均概率为$q$

$q=1-p=1-\dfrac1t\int_0^tG(s)ds=\dfrac1t \int_0^t \overline G(s)ds$，留在系统内人数的期望为$\lambda qt=\lambda\int_0^t\overline G(s)ds=\int_0^t\lambda_2(s)ds$

$\lambda_2(t)=\lambda(1- G(t))=\lambda \overline G(t)$，

### 例：食堂

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010111047055.png" alt="image-20201010111047055" style="zoom:50%;" />

进入餐厅后选菜，为M/G/∞排队系统，然后再付款

假设打一个菜的时间指数分布，一共打两个菜，则打菜的时间为两个指数分布之和，服从erlang分布。设指数分布的$\mu=\dfrac18$，则erlang分布的参数为$2\times\dfrac18=0.25$。则erlang分布的分布函数$F(x)=1-\sum\limits_{k=0}^{2-1}e^{-0.25t}\dfrac{(0.25t)^k}{k!}=\sum\limits_{k=2}^\infty e^{-0.25t}\dfrac{(0.25t)^k}{k!}$

或者说，相当于打完两个菜的概率为$F(x)=\sum\limits_{k=2}^\infty e^{-0.25t}\dfrac{(0.25t)^k}{k!}$，即打菜的数量大于2。而每次打菜的时间为两次打菜的最小值，所以参数为$n\mu=2\cdot\dfrac18=0.25$

从上面的结论，知道此排队系统的输出为一个非时齐的泊松过程，故付款为M(t)/M/3排队系统。

### 复合泊松过程

时间发生的间隔是指数分布，但是每一次时间发生有一个强度

**几何泊松过程**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201010112349959.png" alt="image-20201010112349959" style="zoom:40%;" />



**对数泊松过程**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012133527312.png" alt="image-20201012133527312" style="zoom:33%;" />

如果已经算出来了分布函数，但是里面存在阶乘、组合数等东西，当$X(t)=x$中$x$较大时计算机算不出来。那么就可以用分布函数推出递推式，用递推式来算。

### 过滤泊松过程

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201012134313092.png" alt="image-20201012134313092" style="zoom:33%;" />

$\omega_0(s,y)=1$，意思就是只要在$t$之前发生，则记为1，说明发生了一次，那么就是普通泊松过程

$\omega_0(s,y)=y$，意思是只要在$t$之前发生，则把y记录下来，那么就是复合泊松过程。

过滤泊松过程的参数：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012140433909.png" alt="image-20201012140433909" style="zoom:33%;" />

考虑一个$M/G/\infty$排队系统

假设顾客数为$X(t)$，$Y_n$为第n个顾客的服务时间。那么$t$时刻顾客是否还在系统内就是一个过滤泊松过程。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012134716484.png" alt="image-20201012134716484" style="zoom:33%;" />

第一种情况表示$t$时刻系统中的顾客数量

第二种情况表示$t$时刻系统中所有顾客的总的剩余服务时间

第三种情况表示$t$时刻系统中所有顾客的已服务时间

### M/G/∞排队系统

之前，知道$t$时刻之前离开的概率满足$p=\dfrac1t\int_0^t G(t-\tau)d\tau= \dfrac1t\int_t^0G(s)(-ds)=\dfrac1t\int_0^tG(s)ds$

那么，$t$时刻时留下的概率$q=1-p=1-\dfrac1t\int_0^tG(s)ds=\dfrac1t\int_0^t(1-G(s))ds=\dfrac1t\int_0^t\overline G(s)ds$

那么，留下的人数满足参数服从$\lambda qt=\lambda\int_0^t \overline G(s)ds$的泊松分布

即留下的人数满足一个非时齐泊松分布,其中$\int_0^t\lambda(x)dx=\lambda\int_0^t \overline G(s)ds\Longrightarrow\lambda(x)=\lambda\cdot\overline G(x)$

现在，利用Filter Poisson Process来计算，能得到相同的结果:

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201014161227578.png" alt="image-20201014161227578" style="zoom:33%;" />

因为参数为$\lambda t$的泊松分布的z变换为$P(z)=e^{\lambda t(z-1)}$

**有线收费电视**

记录给每个人提供服务的时间，并以此收费

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012140349891.png" alt="image-20201012140349891" style="zoom:33%;" />

然后就可以用前面的公式算出期望、方差等

用全期望公式也可以算出相同的结果

### 二维泊松过程

泊松过程发生的概率与面积有关（而不是时间长度），并且在不同趋于发生的概率相互独立

例：

每T时间发一艘船，每个顾客泊松到达，且耐心等待的时间成指数分布

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012142334614.png" alt="image-20201012142334614" style="zoom:33%;" />

能坐上船的人数期望，相当于求这个斜线上方的面积

MG∞排队过程

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201012143135568.png" alt="image-20201012143135568" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012143153450.png" alt="image-20201012143153450" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012143208764.png" alt="image-20201012143208764" style="zoom:33%;" />

当事件长度无穷，$s\rightarrow \infty$时，$G(y)\rightarrow1$，则离开为参数为$\lambda $的泊松过程

### Poisson Arrivals See Time Averages(PASTA)

考虑每个顾客到达时，所观察到的系统的状态（的概率分布）

系统处于每个状态的极限概率

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012144532963.png" alt="image-20201012144532963" style="zoom:33%;" />



$V(t)$就是处于B中的状态所占时间的比例

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012144721596.png" alt="image-20201012144721596" style="zoom:33%;" />

$Y(t)$就是每个顾客到达时，系统状态为B的次数。(因为N(t)是离散的，所以只在跳跃的时候有增量1，这个时候若U(s)=1则Y(t)就加1，否则不加。)

$Z(t)=\dfrac{Y(t)}{N(t)}$，为到达顾客时系统处于B状态的概率

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012145426865.png" alt="image-20201012145426865" style="zoom:33%;" />



<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201012150615466.png" alt="image-20201012150615466" style="zoom:33%;" />
这里的输入是两个泊松过程相加（因为是泊松到达过程，再加一个泊松过程分流），但是并不是泊松过程，因为不满足独立增量过程。但是它PASTA成立。



