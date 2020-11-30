# Chapter 3 Renewal Processes

## 定义

间隔不为指数分布，但是独立同分布发生的过程

$S_n=\sum\limits_{i=1}^nX_i$,$N(t)=\max\left\{n|S_n\le t\right\}$

$F_n(t)=P(S_n\le t)\Longrightarrow P(N(t)=n)=P(S_n\le t)-P(S_{n+1}\le t)=F_n(t)-F_{n+1}(t)$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015100018310.png" alt="image-20201015100018310" style="zoom:33%;" />

$m(t)$只需要发生一次，$f_n(t)$必须要第n此发生，因此$m(t)$是$f_n(t)$求和

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015100204911.png" alt="image-20201015100204911" style="zoom:33%;" />

$f_n(t)$是$f_n(t)$的n重卷积，则$f_n^e(s)=(f^e(s))^n$

## 基本更新定理

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015100527518.png" alt="image-20201015100527518" style="zoom:33%;" />

当$t\rightarrow\infty$时，单位时间更新的次数为$\dfrac1\mu$，假设平均$\mu$更新一次，$\mu$是间隔时间的期望，泊松过程（指数分布）中相当于$\mu=\dfrac1\lambda$

**更新类型方程**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015100927495.png" alt="image-20201015100927495" style="zoom:33%;" />

$M(t)=F(t)+\int_0^tM(t-x)f(x)dx\\\Longrightarrow M^e(s)=F^e(s)+M^e(s)f^e(s)\\\Longrightarrow M^e(s)=\dfrac{F^e(s)}{1-f^e(s)}=F^e(s)(1+f^e(s)+f^e(s)^2+...)=F^e(s)(1+m^e(s))\\\Longrightarrow M(t)=F(t)+\int_0^tF(t-x)m(x)dx$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015101749851.png" alt="image-20201015101749851" style="zoom:25%;" />

在上面这个公式中，$m(t)$和$f(t)$与更新过程中的定义类似，即$f(t)$是事件发生时间间隔的pdf，而$m(t)$是时间发生次数期望的导数。

所以才经常用类似于$P(A|X_1=x)$这种条件概率（或条件期望）来构造求解的值，因为这样可以构造出更新方程。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015101658629.png" alt="image-20201015101658629" style="zoom: 25%;" />

### 停时（Stopping time）

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201015102513362.png" alt="image-20201015102513362" style="zoom: 25%;" />

显然，$N(t)=n$与$X_1,X_2,...,X_{n+1}$有关，因此不是停时

而$N(t)+1=n$与$X_1,X_2,...,X_n$有关，与$X_{n+1},X_{n+2},...$无关，因此是停时

如果是停时，那么就可以使用瓦尔德不等式：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015102644593.png" alt="image-20201015102644593" style="zoom:25%;" />

**随机游走**

$X_1$以p的概率+1，以q的概率-1,$E(X_1)=p-q$

记$S_n=X_1+...+X_n$,记$N=\min\left\{n|S_n=1\right\}$，即$N$为从0出发，第一次到达1的时间

那么，$N=n$只与$X_1,...,X_n$有关，那么$N$是停时。

$\therefore E(S_N)=E(X)E(N)=(p-q)E(N)$

而$S_N=1\Longrightarrow E(S_N)=1\Longrightarrow E(N)=\dfrac1{p-q}$

这也就说明了，$p>q$时才有意义。若$p=q$，则平均需要无限步才能从0开始第一次到达$1$

### 寿命与年龄

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015104449875.png" alt="image-20201015104449875" style="zoom:30%;" />

但是，$T(t)=Y(t)+A(t)$不一定服从分布函数F

接下来讲了很多个例子

**灯泡寿命**

考虑剩余时间$V_t(x)=P(Y(t)\le x),\overline V_t(x)=P(Y(t)>x)$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201019175442353.png" alt="image-20201019175442353" style="zoom:33%;" />

（其中，当$X_1>t$时，说明$X_1$就是t之后的下一个事件）

构造出$V_t(x)$的方程，然后用更新类型方程和终值定理求出剩余服务时间满足：


<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015105202302.png" alt="image-20201015105202302" style="zoom:33%;" />
$$
\therefore\lim\limits_{t\rightarrow\infty}E[Y(t)]=\dfrac1{2\mu}E[X_1^2]
$$

$\because E(S_{N(t)+1})=t+E(Y(t))=\mu(M(t)+1)\Longrightarrow E(Y(t))=\mu(M(t)+1)-t$




**均匀分布时间间隔($X\sim U(0,1)$)**

1. 用之前介绍的方法来计算

   先计算$\overline V_1(x)$，再计算$E(Y(1))=\int_0^\infty \overline V_1(x)dx=\int_0^1 \overline V_1(x)dx$

   然后$E(S_{N(1)})=1+E(Y(1))=1.3568$

2. 用停时+Wald等式的方法来计算

   $N(1)+1$是停时，那么$E(S_{N(1)})=E(S_{N(1)+1}-X_{N(1)+1})=E(S_{N(1)+1})-\dfrac12\\=E(X)E(N(1)+1)-\dfrac12=\dfrac12(E(N(1))+1)-\dfrac12$

   算出$E(N(1))=e$，得$E(S_{N(1)})=\dfrac12 e=1.3591$



**免费更换保修政策**

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201020185225630.png" alt="image-20201020185225630" style="zoom:33%;" />

对于一个customer来说，购买了产品之后，大概每过$X_i$时间需要维修一次，$t$为保修时间长度。

那么，每次过了$t$这么长的时间以后，下一次维修就需要重新购买保修服务，并且刷新时长为$t$的保修时间

**库存管理**

从库存为S开始，每次使用$X$的库存，若库存低于$s$了则补货至$S$

那么，这里的时间$t$相当于就是$S-s$，补货的量$Z$相当于$S_{N(t)+1}$

即$Z=S-s+Y(S-s),E(Z)=S-s+Y(S-s)$

根据之前的结论，$\lim\limits_{t\rightarrow \infty}E(Y(t))=\dfrac1{2\mu}E(X^2)$

若$S-s$非常大，则$E(Z)=(S-s)+\dfrac1{2\mu}E(X^2)$

### 年龄（Current-Life）

$A(t)=t-S_{N(t)}$

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022100120802.png" alt="image-20201022100120802" style="zoom:33%;" />

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022100152993.png" alt="image-20201022100152993" style="zoom:33%;" />

因为$m(x)dt$表示$(t,t+dt)$中发生1次事件的概率。

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022100537673.png" alt="image-20201022100537673" style="zoom:33%;" />

那么$u_t(x)=m(t-x)[1-F(x)]$的意思就是，在$t-x$时刻发生了一次，然后下一次发生一定在$t$之后，即间隔$x$以上

### 年龄+剩余事件=总时长（Total-life）

即为包含t时刻的两次事件的发生间隔

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022100944736.png" alt="image-20201022100944736" style="zoom:33%;" />

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022101156637.png" alt="image-20201022101156637" style="zoom:33%;" />

然后再算一下（分类讨论一下t，x，老师也没细讲计算过程）

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201022101232931.png" alt="image-20201022101232931" style="zoom:33%;" />

所以能求出$t\rightarrow\infty$时的分布函数

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022101349361.png" alt="image-20201022101349361" style="zoom:33%;" />

例子：如果是泊松过程，那么$t\rightarrow\infty$时，服从二阶erlang分布，由于寿命是指数分布，说明此时寿命也是指数分布（只对$t\rightarrow\infty$时成立）。

### 更新奖励过程（类似于复合泊松过程）

但是$R_n$不一定是瞬间出现的，可能是慢慢更新的。

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022102036366.png" alt="image-20201022102036366" style="zoom:33%;" />

当时间趋于正无穷时，单位时间产生的奖励=一次更新周期中的reward除以周期长度。

**交替更新过程**

比如先工作$Y_i$，再休息$Z_i$，$X_n=Y_n+Z_n$

那么每两个相邻的工作开始时间为一个更新过程；相邻的休息开始时间也是更新过程。

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022102526995.png" alt="image-20201022102526995" style="zoom:33%;" />

上面之所以是$P(Y_1>t|X_1>t)=P(Y_1>t|X_1=t)$,但是因为$P(Y_1>t,X_1=t)\ne P(Y_1>t)$，因此换成$P(Y_1>t|X_1>t)$计算更方便（因为$P(Y_1>t,X_1>t)= P(Y_1>t)$）

也可以算出$g(t)$在无限长时间上的概率：

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022103034312.png" alt="image-20201022103034312" style="zoom:33%;" />

发现从两个角度来计算，两个结果相同。但是这是有问题的，因为$\lim\limits_{t\rightarrow\infty}g(t)$不一定收敛（比如隔固定时间切换状态，则$\lim\limits_{t\rightarrow\infty}g(t)$不收敛。比如30min换一次状态，那么$t\rightarrow\infty$时，在每一个整点取1，在每一个半点取0，因此，要满足上述的式子，需要满足一定的条件。

### 库存政策

顾客每隔$\left\{T_n\right\}$来一个，每次购买$\left\{D_n\right\}$件商品，补货政策与之前的$(s,S)$政策相同

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201029204828844.png" alt="image-20201029204828844" style="zoom:33%;" />

设$X(t)$为t时刻的库存，考虑$X(t)$的极限分布，我们定义$Y_n$为库存高于x的状态，$Z_1$为库存在$(s,x)$之间的状态，因此就变成了之前所说的交替更新过程了。

设$N_x，N_s$表示库存低于$x,s$的时刻（即最后一个高于$x,s$的时刻），则$E(Y_1)=E[\sum\limits_{i=1}^{N_x}T_i]=E(N_x)E(T_i)$

同理，$E(X_1)=E(N_s)E(T_i)$

之前求出的$\lim\limits_{t\rightarrow\infty}P(X(t)\ge x)=\dfrac{E(Y_1)}{E(X_1)}=\dfrac{E(N_x)}{E(N_s)}=\dfrac{M_G(S-x)+1}{M_G(S-s)+1}$

上面的分子分母类似于$N(t)+1$，之所以要+1是因为第$N(t)+1$个顾客的到达才让库存低于阈值的。

假设G满足指数分布，$G(t)=1-e^{-\lambda t}$

$\therefore \lim\limits_{t\rightarrow\infty}P(X(t)\ge x)=\dfrac{1+\lambda(S-x)}{1+\lambda(S-s)}\\\lim\limits_{t\rightarrow\infty}P(X(t)\le x)=\dfrac{\lambda(x-s)}{1+\lambda(S-s)}$

密度函数：$f_{X(t)}(x)=\dfrac\lambda{1+\lambda(S-s)}$

$\therefore P(X(t)\ge S)=P(X(t)=s)=1-\int_s^Sf_{X(t)}(x)dx\\=1-\dfrac{\lambda S}{1+\lambda(S-s)}=\dfrac1{1+\lambda(S-s)}$

**灯泡维修政策**

所有灯泡，要么坏了修，要么固定时间修。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201029210659830.png" alt="image-20201029210659830" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201029211155400.png" alt="image-20201029211155400" style="zoom:33%;" />

其中，$C(T)=\lim\limits_{t\rightarrow\infty}\dfrac{R(t)}t=\dfrac{c_1+c_2M(T)}T$

这样，对$C(T)$求导，求出最优周期

**年龄更换政策**

在上面的问题中修改一下：每一个$T$在上一次更换后开始计时，而不是在上一次固定更换（block replacement）开始计时。

方法1：

$Z=min(X,T)$

$E(Z)=\int_0^T xdF(x)+T(1-F(T))=\int_0^T(1-F(x))dx$

$E(R)=c_1(1-F(T))+c_2F(T)$

$C(T)=\dfrac{E(R)}{E(Z)}=\dfrac{c_1(1-F(T))+c_2F(T)}{\int_0^T(1-F(x))dx}$

方法2，方法3懒得看了



### 平均剩余寿命

已知剩余寿命的极限$\lim\limits_{t\rightarrow \infty}E[Y(t)]=\dfrac1{2\mu}E(X_1^2)$

考察平均剩余寿命，就是把所有t对应的剩余寿命累加再除以t。

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022111604999.png" alt="image-20201022111604999" style="zoom:33%;" />

此时，每一次事件的发生视为更新过程，取值为剩余寿命（下一次减t），所以就是一堆三角形。

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201022111713872.png" alt="image-20201022111713872" style="zoom:33%;" />





### 再生过程(Regenerative Processes)

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201029100845851.png" alt="image-20201029100845851" style="zoom:33%;" />

比如考虑排队系统，从空到空的时间是iid的，那么就可以视为更新过程。

分析$g(t)=P(Z(t)=j)$

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201029101152760.png" alt="image-20201029101152760" style="zoom:33%;" />

最后$Z(t)=j$的时间为每一个cycle处于状态为$j$的时间与一个cycle的时间之比





**动物园**

$X_n$是摆渡车间隔，$Z(t)$是t状态的顾客数，假设摆渡车容量无穷，那么人数从空到空是一个更新过程。

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201029102111047.png" alt="image-20201029102111047" style="zoom:33%;" />

那么顾客数量为i的前提是在一个cycle中至少到达i个顾客。所以求和是$j=i\rightarrow \infty$，并且时间满足均匀分布的顺序统计量

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201029102615798.png" alt="image-20201029102615798" style="zoom:33%;" />

