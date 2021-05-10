## Chapter 8: Behavior Decision Making

### Ultimatum Game

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201127133622721.png" alt="image-20201127133622721" style="zoom:33%;" />

假设player1可以给player2一些钱，c块钱最多。如果2接受，那么他就可以获得这些钱，然后1可以获得剩下的，否则两个人都得不到任何钱。每一个人只关心自己的所得，并且希望越多越好。

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

### Centipede Game

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201204133625930.png" alt="image-20201204133625930" style="zoom:33%;" />

一开始，1可以选择take得到钱，或者选择Pass；当遇到2时，2也有同样的选择，依次进行下去，直到游戏截止。在游戏的进行过程中，大家的payoff都在不断增加。奖金池的总数每一步都*2，但是选择T的人可以获得80%的奖金池。这就是一个动态博弈的过程。

那么，此问题存在一个子博弈纳什均衡：每个player在每一个节点上都选T。但是这样的话，这个问题总的收益就是最差的。

但是，做了一个实验，让一群人来做选择，结果只有0.7%的人在第一轮选择了T，因此这个博弈论的结果并不是可靠的。

第二种情况：奖金池不变了

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201204135034604.png" alt="image-20201204135034604" style="zoom:33%;" />

此时，在第一轮就终止的比例达到了60%

### Matching Pennies

有2个player，player1有A,B两个选择，player2也是A,B两个选择

他们的payoff为：AA或BB：(-1,1);AB或BA：(1,-1)

那么最终，存在一个混合策略纳什均衡{(0.5,0.5),(0.5,0.5)}

实验结果：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201204135843360.png" alt="image-20201204135843360" style="zoom:33%;" />

选择两个策略的比例为48%，52%，比较符合前面的纳什均衡。

但是，如果将一个收益从80提高到320，此时比例就变成了96%,4%，同时player2的比例也变成了16%,84%：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201204140037957.png" alt="image-20201204140037957" style="zoom:33%;" />

如果将一个收益从80变成44，二者的比例也会发生改变：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201204140151222.png" alt="image-20201204140151222" style="zoom:33%;" />

此时，这两个游戏的纳什均衡为：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201204140316983.png" alt="image-20201204140316983" style="zoom:33%;" />

那么，此时player1的策略是不变的，但是player2的策略会发生改变。

### Logit QRE

松弛掉player2理性的这个假设，认为player2 是有限理性的（而不是完全理性的）。他们不总是会选择更好的选择，而是以更高的可能性选择更好的选择。

在payoff中，加入一个随机量，并且此随机量的pdf已经给出。也就是用随机量来代表不完全的理性。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201204140919597.png" alt="image-20201204140919597" style="zoom:33%;" />









## Prospect Theory

### 期望收益理论

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211133326564.png" alt="image-20201211133326564" style="zoom:33%;" />

三个原则：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211133427447.png" alt="image-20201211133427447" style="zoom:33%;" />

1. prospect的总收益是其期望收益
2. 目前的状态加上一个变化，如果收益更大，那么就会接受他
3. 一个人会偏向于风险更小的选择

两个实验：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211134442951.png" alt="image-20201211134442951" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211134502945.png" alt="image-20201211134502945" style="zoom:33%;" />

但是，这两个实验结果是矛盾的，一个偏向于风险更小的选择，一个偏向于收益更大的选择。

又有两个实验：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211134808827.png" alt="image-20201211134808827" style="zoom:33%;" />

Problem3是80%获得4k，或者获得3k，然后更多人选择了稳得3000的选项；Problem4是20%获得4K，或者25%获得3K，结果更多的人选择了前者。

其中，C可以表示成(A,0.25)，D可以表示成(B,0.25)

已知B>A，但是C>D(这里的>表示选择人数的大于)。此时也就不满足所谓的替换公理。(替换公里：如果B>A，那么对于任何概率p，(B,p)>(A,p))

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211135201692.png" alt="image-20201211135201692" style="zoom:33%;" />

Problem7和8中，A和B、C和D的期望都是一样的。如果是较大概率的话，更多人会选择概率更高的；而如果两个概率都更小，更多人会选择收益大的。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211135634287.png" alt="image-20201211135634287" style="zoom:33%;" />

如果将收益反号，从正收益变为负收益，那么大家的选择会截然相反。二者的结果是镜面对称的。也就是说，在面对正收益时，人们倾向于风险规避；而面对负收益时，人们会倾向于风险追逐。

### 概率保险

一个保险，可以全价买，也可以只付一半的价格。假设需要理赔，有50%的概率，你可以付另外的一半价格，然后获得保险公司的全额理赔；另外50%，保险公司会退还保费然后不管你的理赔了。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211140350792.png" alt="image-20201211140350792" style="zoom:33%;" />

在生活中，可以归结于这样一种决策模型：安装了报警装置，并不能保证不被偷；戒了烟以后，并不能保证不会得肺癌。

实验中，80%的受访者不愿意买这样的保险。解释为：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211140505114.png" alt="image-20201211140505114" style="zoom:33%;" />

将遭受损失的概率从p变成p/2，这件事情的吸引力小于将损失的概率从p/2降到0。也就是说，从p/2减到0，只需要付出跟从p变成p/2一样的保费，因此大部分人都会选择付出所有的保费而不是只付出一半的保费。

### Isolation Effect

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211141109018.png" alt="image-20201211141109018" style="zoom:33%;" />

在第二个决策点，可以选择0.8的概率获得4000，或者直接获得3000。

所以，在这个问题中，从第二个分支上来说，3k的概率是1/4*1=0.25，4k的概率是1/4\*4/5=0.2，所以这件事情就等价于Problem4：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211141546244.png" alt="image-20201211141546244" style="zoom:33%;" />

但是在Problem4中，更多人选择了4000；而在problem中，更多人选择了3000。

如果否定掉第一阶段，那么这个问题就跟Problem3是等价的：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211142247881.png" alt="image-20201211142247881" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211142540712.png" alt="image-20201211142540712" style="zoom:33%;" />

如果本金不同，人们的决策也有所不同。

这个时候，说明金额的变化量也会影响人们的选择。

### 正式进入Prospect Theory

### Editing phase

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20201211143410116.png" alt="image-20201211143410116" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211143428686.png" alt="image-20201211143428686" style="zoom:33%;" />

### Evaluation phase

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211144002548.png" alt="image-20201211144002548" style="zoom:33%;" />

若p+q不大于1，那么以1-p-q的概率收益为0。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211144220670.png" alt="image-20201211144220670" style="zoom:33%;" />

v表示一个偏移量，相对于参考点。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211144554513.png" alt="image-20201211144554513" style="zoom:33%;" />

对于严格正的prospect，$p+q=1,x>y>0$，那么就可以得出$V=v(y)+\pi(p)[v(x)-v(y)]$，其中$v(y)$是确定的收益（至少获得的收益）,$v(x)-v(y)$为风险收益，再乘上权重$\pi(p)$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211145004825.png" alt="image-20201211145004825" style="zoom:33%;" />

两个例子：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201211145208129.png" alt="image-20201211145208129" style="zoom:33%;" />

Problem13是正收益（6k，4k+2k）

第一个选项prospect=$\pi(0.25)v(6000)<\pi(0.25)(v(4000)+v(2000))$，说明$v(6000)<v(4000)+v(2000)$。如果$v$是凹的（concave），那么这样的结果就符合。

