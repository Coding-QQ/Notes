## Chapter 4 Extensive Form Game

### 库诺特模型（Cournot Competition）

每个公司确定自己的产量，而价格由产量决定。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201009133521304.png" alt="image-20201009133521304" style="zoom:40%;" />

### Stackelberg Model

为库诺特模型的变种，某个公司firm1先进行决策，然后firm2再根据firm1的决策来做决策。

称为firm1为leader，firm2为follower

决策顺序：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201009133827761.png" alt="image-20201009133827761" style="zoom:40%;" />

**决策方法：Backward Induction**

对于后决策的$q_2$来说，$q_1$是给定的。通过求导计算出$q_2$与$q_1$的关系式

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201009134123692.png" alt="image-20201009134123692" style="zoom:33%;" />

然后对于$q_1$来说，知道$q_2$与$q_1$的关系，则将$q_2$与$q_1$的关系带入，并且求出收益与$q_1$的关系，从而算出最佳的$q_1$

库诺特和斯塔克伯格的结果都是纳什均衡，但是斯塔克伯格的结果要更为合理。

### 决策树

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201009140337691.png" alt="image-20201009140337691" style="zoom:33%;" />

由两种情况不被允许出现再博弈树中

1. 闭环，这违背了传递性和对称性
2. 多个结点指向同一个结点。因为希望每个结点都是之前所有事件的一个完整描述（即从初始到当前结点只有唯一路径），则应该排除这种情况。

**结点(Node)**

表示参与人采取行动的时间点

**枝(Branch)**

代表参与人的一个行动选择

**信息集(Information Set)**

$h(x)$表示在结点$x$处player了解的信息

信息集是决策结的一个子集，满足：1. 每一个决策结都属于同一个人。 2. 该参与人知道博弈进入了该信息集的某个决策结，但是不知道具体是哪一个决策结。

引入信息集，表示参与人做出决策时可能不了解之前发生的所有事情。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201009143143002.png" alt="image-20201009143143002" style="zoom:25%;" />

在上面的例子中，每一个虚线相连的信息里，B知道A是否进行了开发，但是不知道Nature的选择（即不知道需求的大小）

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201009143222890.png" alt="image-20201009143222890" style="zoom:25%;" />

在上面的例子中，每一个信息集里，B知道需求量是大是小，但是并不知道A是否进行了开发。

每个node只属于一个信息集，即$x''\in h(x)\Rightarrow x\in h(x'')$

### 用动态的决策树表示静态决策问题

Cournot模型：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201009144140268.png" alt="image-20201009144140268" style="zoom:33%;" />

这就变成了静态模型

**完美信息博弈（Perfect Information）**

1. Perfect information

   每一个information set里面都只有一个结点

2. Imperfect information

   至少有一个information set里面有超过一个结点

**完美回忆（Perfect Recall）**

定义：所有player都不会忘记之前他了解过的信息，且所有player都知道他们之前做过的决策。

符号表达：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201009144802626.png" alt="image-20201009144802626" style="zoom:33%;" />

*predecessor 前序结点*，*immediate predecessor上一个前序结点*

*(immediate) successor （上一个）后序结点*

如果知道一个结点$x^1$和它一个信息集中的另一个结点$x^2$，并且知道该结点的前序结点$x$，并且$x$和$x^1$的操作对象相同，则存在一个$x''$为$x^2$的前序结点，且$x''$到$x^2$的操作与$x$到$x^1$的操作相同。



<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201009150514555.png" alt="image-20201009150514555" style="zoom: 33%;" />

### Pure Strategy 在动态博弈中的定义

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201016134929097.png" alt="image-20201016134929097" style="zoom:33%;" />

**Pure Strategy纳什均衡**

A假定B的战略是给定的：B将根据A的行动，按照给定的策略进行行动。

#### 混合策略在动态博弈中的定义

**Behavior Strategy**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201016135504235.png" alt="image-20201016135504235" style="zoom:33%;" />

$b_i$为一个人的行为战略，表示他在每一个信息集上策略的概率分布

**等价策略**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201016140750362.png" alt="image-20201016140750362" style="zoom:25%;" />

player 1共有两个信息集，所以player 1的所有策略集合有$(a,c),(a,d),(b,c),(b,d)$

其中$(b,c),(b,d)$是等价的，因为只要player1选择了b，那么游戏直接中止，后面选什么都无所谓。所以，这两个策略导致的结果是一样的，那么这两个策略等价。

**Mixed Strategy**

在reduced strategy form上定义的，也就是说已经消除了等价的策略。

与behavior stategy的区别

* pure strategy是一本书，每一页是一个信息集，包含上面的具体操作。那么这本书就构成了一个pure strategy
* $S_i$表示存放了所有书的一个图书馆（所有行为战略）。
* mixed strategy表示了随机在图书馆中选取一本书的方法（概率）。
* behavior strategy表示了一本书，但是每一页上的操作都是随机的。

例子：

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201016142401141.png" alt="image-20201016142401141" style="zoom:33%;" />

* B共有$2\times2=4$个pure strategy
* $b_2$是一个behavior strategy
* $\sigma_2$是一个mixed strategy，$\sigma_{21},\sigma_{22},\sigma_{23},\sigma_{24}$对应了4个pure strategy的概率

### 子博弈精炼纳什均衡

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201016143936161.png" alt="image-20201016143936161" style="zoom:33%;" />

两个条件：

* 起点是一个单结信息集
* $T(x)$表示x的后继结点，对于$x'\in T(x)$，若$x''\in h(x)\Longrightarrow x''\in T(x)$

**Subgame Perfect Equilibrium**

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201016145559986.png" alt="image-20201016145559986" style="zoom:33%;" />

