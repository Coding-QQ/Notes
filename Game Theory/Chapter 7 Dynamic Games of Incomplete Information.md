## Chapter 7: Dynamic Games of Incomplete Information

### 例子

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113134139930.png" alt="image-20201113134139930" style="zoom:33%;" />

* Plyaer1 有L,M,R三个选择
* Player2只知道1选择了R，或者没有选择R（也就是选择了L或者M）
* 但是player2不知道1选择的是L还是M
* player2可以选择L'和R'

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113134320847.png" alt="image-20201113134320847" style="zoom:33%;" />

这个问题中，有两个纳什均衡。

但是，这个问题中只有一个subgame，就是它本身。所以用子博弈纳什均衡不能剔除掉任何一个纳什均衡。

对于Player2来说，L' dominate R‘，也就是说Player2无论如何都会选择L’，那么player1 就不可能因为Player2选择R‘而选择R。所以（R,R'）这个纳什均衡是不可置信的纳什均衡，但是用subgame又不能将其剔除掉。所以需要想一个办法

### Perfect Bayesian Equilibrium

需要剔除一些新的要求，剔除不合理的纳什均衡。

**要求1：**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113134758217.png" alt="image-20201113134758217" style="zoom:33%;" />

在每一个信息集中，player需要知道一个概率分布，知道这个player之前是从哪里来的。

**要求2：**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113135102569.png" alt="image-20201113135102569" style="zoom:33%;" />

Player在每个信息集上的决策，依据自己的belief以及其他player的subsequent strategy，一定是最优的。

subsequent strategy: 从这个信息集开始以后的所有可能的情况

**例子**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113140043179.png" alt="image-20201113140043179" style="zoom:33%;" />

要求1：需要有一个Belief，也就是p和1-p，在做决策之前，player2 知道自己在左边结点的概率和右边结点的概率分布为p,1-p

要求2：有了这样一个belief以后，他做出两个决策的收益分别为：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113140231770.png" alt="image-20201113140231770" style="zoom:33%;" />

发现不管belief的p取值是多少，L‘都更好（$2-p>1-p$），所以player2 就会选择L’

如果要求每一个player都拥有一个belief并且按照belief进行最优的选择，那么就可以剔除掉不适合的纳什均衡（R，R'）

当然，这些belief不一定是合理的

**其他的要求**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113140608633.png" alt="image-20201113140608633" style="zoom:33%;" />

根据之前的equilibrium strategies，有一些信息集是以正概率到达的，还有一些信息集到达的概率为0。因此，只要信息集是正概率到达，就叫on the equilibrium path,否则叫off the equilibrium path.

**要求3：**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113140838730.png" alt="image-20201113140838730" style="zoom:33%;" />

对于on the quilibrium path的信息集，belief是根据贝叶斯规则来确定的。

还是之前的例子，已经把[RR']剔除掉了。如果到达了player 2 的那个information set，那么它的belief应该是$p=1$，因为仅剩下的纳什均衡是[L,L'] （因为要根据players' equilibrium strategy来选择belief），到达了这个信息集以后player1的选择一定是L，所以概率是1.

前3个要求的总结：

* 要求3使得player的belief是合理的，而不是随机的。
* 如果满足前三条要求，就叫做Perfect bayesian equilibrium(精炼贝叶斯均衡)
* 精炼贝叶斯均衡中，不仅仅是一个strategy，还包含每一个player在每一个信息集上的行动的概率（belief）。也就是说，每一个belief就决定了一个策略，所以精炼贝叶斯均衡中belief和strategy是一起存在，相互依存的。

**要求4：**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113143218596.png" alt="image-20201113143218596" style="zoom:33%;" />



**Perfect Bayesion Equilibrium（精炼贝叶斯均衡）**

满足前面4个要求的strategies和beliefs

**例子**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201113143517293.png" alt="image-20201113143517293" style="zoom:33%;" />

* 有2个subgame，一个是它本身，一个是从2开始的subgame

* 从2开始的subgame，有一个唯一的纳什均衡$(L,R')$
* 所以唯一的一个子博弈纳什均衡为($D,L,R'$)
* 上面的策略以及$p=1$满足要求1~3
  * 要求1：有一个belief，显然成立
  * 要求2：有了belief以后，接下来的决策根据这个belief以及subsequent strategy是最优的。那么对于这个例子来说，从后往前看：在2结点是单一结点，所以就可以省略belief。那么根据belief，p=1且player3的决策是R‘，这样给定了以后，Player2选择L是最佳的选择；同理在1结点，选择D也是最优的选择。所以满足要求2
  * 要求3：对于on the equilibrium path的信息集，这个belief是根据贝叶斯规则来确定的。这个例子中，只有player3需要选择belief。在均衡策略（$D,L,R'$）中，根据纳什均衡，它一定在L对应的那个分支上，所以$p=1$
* 没有信息集off the equilibrium path，所以条件4也满足，所以这是一个精炼贝叶斯均衡。

**再来看一下（$A,L,L'$），p=0组合**

这是一个纳什均衡，并且也满足条件1~3.

要求1：显然成立

要求2：给定了p=0之后，如果1选择D，那么必然会在右边的分支，1的收益是0，所以1会选择A；2如果选择L是一定比R好的，所以2一定会选择L；而3又觉得自己一定是在右边，所以3会选择L’。

要求3：这个信息集不在均衡路径上，所以3也满足

但是根据要求4，2之前选了L，但是p=0，这就矛盾了，所以不满足条件4。所以（$A,L,L'$）不是精炼贝叶斯纳什均衡。

### 例子：二手车市场

想买一辆二手车，有可能买到好车，也可能买到不好的车。

* 好车的价值是H，坏车的价值是L
* 买之前不知道这个车到底是个啥水平，但是大概有一个估计：好车的比例为q
* 想买的车的挂牌价为p
* 卖车的（dealer）知道他的车是什么水平，你当然不知道。
* 坏车需要让卖家额外花费c元，来让它看起来很正常，从而能够卖出去。
* dealer可以选择卖车或者不卖车。我自己决定买还是不买。
* 假设$H>p>L$

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120134305833.png" alt="image-20201120134305833" style="zoom:33%;" />

Nature先决定了车是好是坏，然后Dealer决定买还是不买；如果Dealer决定卖，买家决定买还是不买。

**贝叶斯公式**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120135022850.png" alt="image-20201120135022850" style="zoom:33%;" />

假设Dealer的规则是：好车才卖，不好就不卖

那么，假设车卖了，那么q就可以修改为：（这是一个Separating Equilibrium）

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120135154491.png" alt="image-20201120135154491" style="zoom:33%;" />

所以belief会根据之前对方的行为做出修正。

两种纳什均衡：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120140024745.png" alt="image-20201120140024745" style="zoom:33%;" />

其中Pooling equilibria的例子：假设车不管怎么样都选择卖车

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120140103815.png" alt="image-20201120140103815" style="zoom:33%;" />

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120140617309.png" alt="image-20201120140617309" style="zoom:33%;" />

**假设dealer无论如何都卖车**

因此，假设选择买车，那么期望的收益为V

而必须要$p\ge c$，dealer才可能选择不管咋样都卖

所以，当$p\ge c$且$V\ge 0$时，上面的纳什均衡存在。



**假设dealer的选择是无论如何都不卖**，那么贝叶斯均衡就不存在了。

**假设dealer只卖好车，不卖坏车**

那么显然需要满足$p\le c$

此时纳什均衡为：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120142613186.png" alt="image-20201120142613186" style="zoom:33%;" />

**假设dealer只卖坏车，不卖好车（脑子坏掉了）**

此时要是好车选择不卖，只能说明$p=0$，也就是说卖不卖都一样

而此时，$p-c<0$，那么就不满足序贯理性（sequential ratinality)，所以此时不满足PBE的条件。

### 混合策略PBE

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120142934955.png" alt="image-20201120142934955" style="zoom:33%;" />

* 讲consumer看作是一个群体，想要找到一个比例x，有占比为x的顾客愿意买车。
* 如果是好车，那么就会选择卖
* 如果是坏车，那么会以b的概率卖车
* 如果$0<x<1$，说明一部分人买一部分人不买，说明买不买的收益都相同。所以买车的收益为0，即$P(good|offer)\times(3000-2000)+(1-P(good|offer))\times(0-2000)=0$，可以解出来后验概率$P(good|offer)=\dfrac23$。也就是说假设均衡存在，那么belief应该就是这么多。

那么，就可以解出$b$：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120143640838.png" alt="image-20201120143640838" style="zoom:33%;" />

又假设，对于拥有坏车的dealer，应该Offer和hold都一样，也就是说offer的收益也是0

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120144105853.png" alt="image-20201120144105853" style="zoom:33%;" />

所以混合策略PBE为：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120144128038.png" alt="image-20201120144128038" style="zoom:33%;" />

### MBA Worth

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120145536682.png" alt="image-20201120145536682" style="zoom:33%;" />

有两类人：高能力概率为q，低能力概率为1-q，Output分别为H,L

他们可以选择学不学习MBA

高能力和低能力的cost不一样，分别为$c_H,c_L,s.t.c_L>H-L>c_H$。

工资为期望的output

是否读MBA，会影响到老板对你的能力的判断，自然也会影响到你的工资水平



**假设老板可以看出来这个员工是高水平还是低水平，那么直接按照产出来给工资就好了：**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120144452521.png" alt="image-20201120144452521" style="zoom:33%;" />

**假设老板根据你的学历来判断你的能力**

那么就要引入一个belief，算出MBA和College学历的期望产出为：

$w_M=p_M\times H+(1-p_M)\times L$

$w_C=p_C\times H+(1-p_C)\times L$

其中，$p_M,p_L$分别为MBA,College学历下为高水平人的概率，这均为先验概率

**Separating: 假设是只有高产出才MBA，低产出不MBA**

则$p_M=1,p_L=0$

那么直接可以算出$w_M=H,w_C=L$

但是这种情况下，高产出的人的收益就是$H-c_H\ge L$，这样才能保证高产出的人读一个MBA会比他不读MBA收益高。

低产出的人的话也要求$L\ge H-c_L$

所以，现在的情况就是，当满足条件：$c_L\ge H-L\ge c_H$，此时的情形就是比较合理的。

**Separating: 假设只有低产出才MBA，高产出不MBA**

此时$w_M=L,w_C=H$

所以对于高产出的人来说：$H\ge L-c_H$

对于低产出的人来说来说：$L-c_L\ge H$，这显然不可能。所以这个先验概率不合理。

**Pooling: 假设都读MBA**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120150020543.png" alt="image-20201120150020543" style="zoom:33%;" />

**Pooling: 假设都不读MBA**

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20201120150045697.png" alt="image-20201120150045697" style="zoom:33%;" />