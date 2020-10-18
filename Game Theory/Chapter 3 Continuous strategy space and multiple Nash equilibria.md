## Chapter 3 Continuous strategy space and multiple Nash equilibria

### 重复剔除占优：

**Pure Strategy**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200927135859059.png" alt="image-20200927135859059" style="zoom:50%;" />

$S_i^k$是在上一步的策略中，选择了不劣于上步的所有策略收益的那些策略

(也就是剔除上一步的dominated策略)

**Mixed Strategy**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20200927140213137.png" alt="image-20200927140213137" style="zoom:50%;" />

**定义**

由于在一个有限的游戏中，上述的步骤一定能通过有限步完成

如果最后每个玩家只有一个解了，则称为此game solved

命题：

如果最后只剩下一共profile，那么此profile一定是纳什均衡

### 古诺竞争(Cournot Competition)

<img src="C:%5CUsers%5Cliuqq%5CAppData%5CRoaming%5CTypora%5Ctypora-user-images%5Cimage-20200927140811666.png" alt="image-20200927140811666" style="zoom:50%;" />

对$q_i$求导，得到$q_{-i}$条件下$q_i$的最优解

### Bertrand Competition

<img src="C:/Users/liuqq/AppData/Roaming/Typora/typora-user-images/image-20200927143225338.png" alt="image-20200927143225338" style="zoom:50%;" />

如果价格更高，则无收入；如果价格更低，则收入为需求量$Q(p_i)$乘上价格减成本；如果价格一样，则在上面的基础上减半

那么，在Bertrand的条件下，两者的价格都会趋于成本价

### 纯策略纳什均衡(pure Nash equilibrium)存在性定理

如果决策空间$s_i$是非空紧凑的欧几里得空间，如果收益函数$u_i$是连续的且在$s_i$拟凹的，则存在一个纳什均衡