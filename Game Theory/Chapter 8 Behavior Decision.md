## Chapter 8: Behavior Decision Making

### Ultimatum Game

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127133622721.png" alt="image-20201127133622721" style="zoom:33%;" />

假设player1可以给player2 一些钱，c块钱最多。如果2接受，那么他就可以获得这些钱，然后1可以获得剩下的，否则两个人都得不到任何钱。每一个人只关心自己的所得，并且希望越多越好。

那么就可以把它写成一个博弈树（连续状态）：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127133919187.png" alt="image-20201127133919187" style="zoom:33%;" />

先考虑player2，只要$x>0$，那么他的选择一定是接受；$x=0$则接不接受均可。那么player2就有两个策略：无论如何都接受；只有$x>0$才接受

那么对于player1来说，如果他认为player2是第一个策略，无论如何都接受，那他就会取$x=0$；如果他认为player2是第二个策略，只有$x>0$才接受，在这种情况下就没有最优决策了。（因为无论如何决策，都可以找到一个更好的决策）

所以，唯一的subgamer perfect equilibrium是：player1选择$x=0$，player2无论如何都接受，此时player1和2的payoff分别为c，0。

有人做了一个实验，看下大家真实的行为是什么：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127134903630.png" alt="image-20201127134903630" style="zoom:33%;" />

发现这个与之前的理论分析不太一样。

理论解释：

* 文化偏好：蒙古人倾向于均分，另外“声誉”是比较重要的考虑因素（体面人）
* 如果进行重复实验，那么player1的offer会变少，逐渐向subgame perfect equilibrium收敛。
* 非常不平等的分配被拒绝的原因是offer太少了。

### The Trust Game

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127135429667.png" alt="image-20201127135429667" style="zoom:33%;" />

两个player一共有10块钱，player1决定把10块钱中的多少给player2。实验者可以将player1给2金额翻三倍，然后player2决定将翻倍的钱中的多少返还给player1。类似于一个投资模型。

然后就有人做了实验：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127135739994.png" alt="image-20201127135739994" style="zoom:33%;" />

大部分的player 1都选择了进行投资，表现出了无条件的善良或者对被投资者的信任。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127140015415.png" alt="image-20201127140015415" style="zoom:33%;" />

上面是Player2返还的值。平均来看，player 1可以回本，可以收回自己的投资；

个人行为偏好和社会行为偏好：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127140328391.png" alt="image-20201127140328391" style="zoom:33%;" />

实验：100%给你100和50%给你200；100%失去100和50%失去200：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127140534044.png" alt="image-20201127140534044" style="zoom:33%;" />

### 报童问题

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127141026593.png" alt="image-20201127141026593" style="zoom:33%;" />

在销售季到来之前，manager只有一次补货的机会，但是demand是随机的。如果进货量大了，那么他可以将多余的库存亏本处理掉；如果他进货量少了，那么就损失了一部分利润。所以他需要去抉择应当进多少货。

假设demand的分布函数：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127141223343.png" alt="image-20201127141223343" style="zoom:25%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127141351289.png" alt="image-20201127141351289" style="zoom:33%;" />

需求内的销售价格为P，订货定多了，需要以V的价格甩卖，如果定少了，损失为G。

最终的notation:

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127141506699.png" alt="image-20201127141506699" style="zoom:33%;" />

那么，收益为：

$\pi(Q,D)=PS-CQ+V\cdot \max(Q-S,0)-G\cdot \max(D-S,0)$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127142904076.png" alt="image-20201127142904076" style="zoom:33%;" />

期望的收益：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127142930438.png" alt="image-20201127142930438" style="zoom:33%;" />

那么就可以得出最佳的订货量$Q^*$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127143136732.png" alt="image-20201127143136732" style="zoom:33%;" />

**规避风险的选择**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127143842368.png" alt="image-20201127143842368" style="zoom:33%;" />

如果收益>0，那么就是w；如果收益<0，那么还要加入一个>1的系数。也就是说更重视这个亏损，更倾向于规避风险。

假设当$D=\bar d(q)$时，刚好保本

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127144143090.png" alt="image-20201127144143090" style="zoom:33%;" />

还有两种情况：规避订多了的风险和订少了的风险

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127144303533.png" alt="image-20201127144303533" style="zoom:33%;" />

Waste-averse里面，如果定多了就有一个惩罚项：Stockout-averse里面，如果定少了就有一个惩罚项。

还有一种针对订货量与需求量偏差的惩罚（订货量偏差最优，综合考虑多订和少订）：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127144747952.png" alt="image-20201127144747952" style="zoom:33%;" />

定理：如果需求的分布函数关于其均值对称，那么订货量偏差最优的订货量会介于平均需求与最大利润的订货量之间。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127145146305.png" alt="image-20201127145146305" style="zoom:33%;" />

### 锚定物调整

设定一个锚定物，然后根据锚定物来调整数量。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127145528990.png" alt="image-20201127145528990" style="zoom:33%;" />

可以以平均值为基准，也可以以上一个为基准。