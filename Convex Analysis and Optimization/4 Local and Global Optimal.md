## 第四章 

### 4.2 Local and Global Optimal

#### 全局最优值与全局最优点定义

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201005134945432.png" alt="image-20201005134945432" style="zoom:40%;" />

#### 局部最优点

在邻域中，$f(x^*)\le f(x),\forall x\in X ,||x-x^*||<\epsilon$

若小于号严格成立则称为严格的局部极小值

#### 凸函数与极小值

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201005135345224.png" alt="image-20201005135345224" style="zoom:40%;" />

#### 凹函数与极小点

如果凹函数的极小值点集合包含了定义域的相对内点，则该函数为常值函数（非常值凹函数的极小点不能在相对内部取到）

**凹函数的一个性质**

给定一个紧凸集$S\sub\R^n$和凹函数$f:S\rightarrow \R$，则$f$可以在$S$的某个极点处取到全局最小值(紧等价于有界闭)

### 4.3 凸函数的连续性

 Jensen不等式：

多个点凸组合的函数值不大于它们函数值的凸组合

**命题：若$f$是一个proper的凸函数，则在$dom(f)$的内部一定是一个连续函数**

**命题：一个实值函数是凸函数当且仅当它是连续的且导数非降**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201005142939501.png" alt="image-20201005142939501" style="zoom:40%;" />

### 4.4 凸函数的判定

1.（闭）凸函数的非负组合也是（闭）凸函数

2.对凸函数的自变量进行线性变换，得到的函数也是凸的

3.（闭）凸函数的上确界也是（闭）凸的



<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201005143559545.png" alt="image-20201005143559545" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201005143650154.png" alt="image-20201005143650154" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201005144811210.png" alt="image-20201005144811210" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201005145241272.png" alt="image-20201005145241272" style="zoom:33%;" />

