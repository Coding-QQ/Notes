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

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015101658629.png" alt="image-20201015101658629" style="zoom: 25%;" />

### 停时（Stopping time）

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201015102513362.png" alt="image-20201015102513362" style="zoom: 25%;" />

显然，$N(t)=n$与$X_{n+1}$有关，因此不是停时

如果是停时，那么就可以使用瓦尔德不等式：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015102644593.png" alt="image-20201015102644593" style="zoom:25%;" />

### 寿命与年龄

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015104449875.png" alt="image-20201015104449875" style="zoom:30%;" />

剩余服务时间满足：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201015105202302.png" alt="image-20201015105202302" style="zoom:33%;" />

