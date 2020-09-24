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

此时，顺序统计量不是均匀分布了，而是满足：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200924112258671.png" alt="image-20200924112258671" style="zoom:40%;" />

**计算机模拟非时齐泊松过程**

法1

1. 找一个比$\lambda\ge\lambda(t)$
2. 用$\lambda$生成一个到达时间Si
3. 以$\lambda(S_i)/\lambda$的概率接受这个到达时间（将这个到达时间设为此非时齐泊松过程的到达时间）

法2

1. 设定$\lambda=1$
2. 生成一个到达时间Si
3. 将这些事件进行转换：$Z_i=m(S_i)$

