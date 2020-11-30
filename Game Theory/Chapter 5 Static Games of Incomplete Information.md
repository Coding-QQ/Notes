## Chapter 5: Static Games of Incomplete Information

### 不完全信息（Incomplete Information）

比如拍卖、砍价时，不知道对面的心理预期是多少。

例：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023134519740.png" alt="image-20201023134519740" style="zoom:33%;" />

Player 1想要约会，但是不知道Player 2 想不想约会；

Player 2知道Player 1是一定想约会的。

**Key idea**

* 将Player 2分成不同的type，Player 2的决策与他的type有关。

* 我们将决策空间、及其对应的纳什均衡迁移过来

### 贝叶斯纳什均衡与贝叶斯博弈

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023135459504.png" alt="image-20201023135459504" style="zoom:33%;" />

此时，(B,(B,F))是一个贝叶斯纳什均衡。

这个(B,F)，是指的两种type下Player2的决策，跟player1的决策无关。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023140245235.png" alt="image-20201023140245235" style="zoom:33%;" />

对于每一个player，都有有限个type$\theta_i\in \Theta_i$，$p(\theta_1,...,\theta_I)$是一个联合密度函数，考虑所有的type。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023142800409.png" alt="image-20201023141555848" style="zoom:33%;" />

后面的小$u_i$是一个确定的量，因为每一个人的决策和type都知道了。

**贝叶斯纳什均衡**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023144138320.png" alt="image-20201023142518645" style="zoom:33%;" />

如果strategy和type集合都是有界闭的（紧集），并且每个player的payoff function是连续凹函数，那么贝叶斯纳什均衡存在。

**例：不完全信息库诺特模型**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023141555848.png" alt="image-20201023142800409" style="zoom:33%;" />

Firm 2 的固定cost有可能是low cost，也可能是high cost，也就是说firm 2有两个type

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023143408586.png" alt="image-20201023143356407" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023143356407.png" alt="image-20201023143408586" style="zoom:33%;" />

都是假如对方的pure strategy给定了，并且了解自己的type，那么自己的最优选择为($q_1^*,q_L^*,q_H^*$)

**例：First Price Auction**

出价最高的获胜，并且最高价成交

那么，每个人可以接受的最高价格为他的type，每个人的type可以取无穷种。每个人不知道对方的具体的心理价位(一个分布P和密度p，并且在$[\theta_l,\theta_h]$之间)

那么其payoff function如下：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023142518645.png" alt="image-20201023144138320" style="zoom:33%;" />

一个人的出价与他的心里预期（type）有关

其中$\beta_j(\theta_j)=s_j(\theta_j)$，意义都是type为$\theta_j$时的策略$s_j$，$\Phi_j$是$\beta_j$或$s_j$的反函数

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023150634533.png" alt="image-20201023144707548" style="zoom:33%;" />

所以求出期望以后，对$\theta_i$求导，得到一个微分方程。

然后由于这个游戏是对称的，也就是说两个player是完全平等的，所以可以去掉$\Phi$的下标。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023144707548.png" alt="image-20201023145349090" style="zoom:33%;" />

这个微分方程有一个边缘条件$\Phi(s_0)=s_0\Longrightarrow s_0=\beta(s_0)$，意思就是假如对于自己的价格$\theta_i$是$s_0$，那么出价就是$s_0$，否则假设出价$s_i$更高，那$\theta_i-s_i=s_0-s_i<0$就亏了。

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023145821142.png" alt="image-20201023145821142" style="zoom:33%;" />

之所以积分是从$\theta_l$到$\theta_i$，是因为出价不能超过$\theta_i$，否则就亏了。

如果是type的概率是$[\theta_l,\theta_h]$之间的均匀分布，那么最终的出价为

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201023145349090.png" alt="image-20201023150634533" style="zoom:33%;" />

