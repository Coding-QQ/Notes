# Chapter 1 Introduction

$X(t)$：时间t时系统状态

例：每天股票的收盘价格（离散）一天之内的温度变化（连续）

**独立增量过程（Independent-increment property）**

$X(t_1)-X(t_0),X(t_2)-X(t_1),...,X(t_n)-X(t_{n-1})$相互独立

**平稳增量过程（Stationary-increment property）**

$X(t+s)-X(t)$拥有相同的概率分布，对于$\forall t$

**母函数（Generating Function）**

类似于对$p_n$的Z变换

若取$a_n=p_n$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917100523073.png" alt="image-20200917100523073" style="zoom:40%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917100749209.png" alt="image-20200917100749209" style="zoom:50%;" />

用母函数可以轻松地获得随机变量的一阶矩和二阶矩

**拉普拉斯变换**

对$f(x)$的拉普拉斯变换

终值定理：$\lim\limits_{t\rightarrow\infty}F(t)=\lim\limits_{s\rightarrow0}sf(s)$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917102554629.png" alt="image-20200917102554629" style="zoom:40%;" />

也可以使用拉普拉斯变换来方便地求n阶矩

$X_1\sim exp(\mu_1)$,$X_2\sim exp（\mu_2）$,$X=min\left\{X_1,X_2 \right\}$

则$X\sim exp(\mu_1+\mu_2)$

($X>x$等价于$X_1>x,X_2>x$)

**矩母函数(Moment Generating Function)**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917105919409.png" alt="image-20200917105919409" style="zoom:40%;" />

**黎曼-斯蒂尔吉斯积分（Riemann-Stieltjes integrals）**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917110809788.png" alt="image-20200917110809788" style="zoom:40%;" />

一个换电池的例子，表现了R-S积分的作用，也就是说$\int_0^\infty xf(x)dx$和$\int_0^\infty xdF(x)$是不等价的

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917110953643.png" alt="image-20200917110953643" style="zoom:40%;" />

也就是说，连续的时候二者是等价的，但是不连续的时候需要用R-S积分来处理。

另外一个例子，构造了一个

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917111712907.png" alt="image-20200917111712907" style="zoom:40%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917111759025.png" alt="image-20200917111759025" style="zoom:40%;" />

此时，分布函数既不离散也不连续（但是右连续）

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917111856971.png" alt="image-20200917111856971" style="zoom:40%;" />

然后就引出R-S积分的定义。

**拉普拉斯-斯蒂尔吉斯变换**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200917112109612.png" alt="image-20200917112109612" style="zoom:40%;" />

注意上面那个$e^{-s\cdot1}[F(1)-F(1-)]$，就是R-S积分针对不连续情况的处理

