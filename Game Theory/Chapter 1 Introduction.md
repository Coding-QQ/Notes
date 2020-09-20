## Introduction

### 决策理论（运筹）与博弈论

* 运筹：在一些决策变量和约束条件下，优化一个目标函数
* 博弈论：在进行决策时，不仅考虑自身的决策，还考虑其他人的决策。
  * 军备竞赛，核武器竞争
  * 竞价策略
  * 小组成员打分游戏(Grade Assignment Game)

### 小组成员打分游戏(Grade Assignment Game)

一个双人小组作业，两个人在对方不知情的情况下给自己打分，可以打分“g”（great）或者“m”（medium）

* 若两个人一个为“g”，另一个“m”，则给自己打“g”的得A，“m”的得分为C
* 若两个人均为“g”，则两个人都是B-
* 若两个人均为“m”，则两个人都是A+

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200918135650880.png" alt="image-20200918135650880" style="zoom:40%;" />

**回报**

对每个结果赋值，如：3(A),1(B+),0(B-),-1(C)

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200918140635343.png" alt="image-20200918140635343" style="zoom:40%;" />

上述的游戏叫做：strategic-form game



### Strategic-form game

被三个部分定义：

* 玩家集合
* 策略
* 回报

离散情况下：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200918140814300.png" alt="image-20200918140814300" style="zoom:50%;" />

注意：

* $u_i:S\rightarrow R$，而不是$S_i\rightarrow R$，说明$u_i$是与整体的决策有关，而不是某一个的决策。

* 集合的乘积$\prod_iS_i$表示集合的组合，即$XY={(x_i,y_j)|x_i\in X,y_j\in Y}$

  那么$S$就表示所有玩家的策略的组合

* $s_i$表示一个不包括i的策略的向量，那么$(s_i,s_{-i})$就组成一个完整的策略，即$(s_i,s_{-i})\in S$

### 占优策略（Dominant Strategy）

**囚徒困境**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200918142404080.png" alt="image-20200918142404080" style="zoom:50%;" />

“承认”严格优于(strictly dominates)“不承认”，则在此假设下，双方各可能选择“承认”

**定义**

一个策略$s_i\in S_i$是一个对于玩家i的占优策略(dominant strategy)，如果$u_i(s_i,s_{-i})>u_i(s_i',s_{-i})$对于一切$s_i'\in S_i，s_{-i}\in S_{-i}$成立

**占优策略均衡**

对于一个策略组合$s^*\in S$,每一个玩家i的策略$s_i^*$都是占优策略

占优策略均衡并不是一定存在的

## 劣势策略(Dominated Strategy)

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200918143839699.png" alt="image-20200918143839699" style="zoom:50%;" />

因此可以直接将dominated strategy给排除掉，这样就降低了策略空间的维度

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200918144538229.png" alt="image-20200918144538229" style="zoom:50%;" />

一直进行下去，直到只剩下一个单独的输出'confess，confess'，此时就可以解决问题。

### 纯策略纳什均衡（Pure Strategy Nash Equilibrium）

**定义：纳什均衡**
<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200918145703354.png" alt="image-20200918145703354" style="zoom:50%;" />

假设存在一个策略组合，对每一个玩家i，其回报都是最优的(最优的意思是，别的玩家被固定在一个策略组合$s_{-i}^*$中，而自己的选择是最优的)。

* 当告知了其他玩家的选择后，自身没有选择的余地了
* 所有玩家均猜测其他玩家选择纳什均衡.

