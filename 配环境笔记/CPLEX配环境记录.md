# CPLEX+Yalmip的MATLAB环境安装

## 第一次尝试

成功安装了Yalmip，需要安装Cplex了。这次配环境主要的问题就出在cplex上面。

最开始，按照http://blog.sina.com.cn/s/blog_b041fdcb0102ydsq.html的内容来进行安装。从百度网盘中下载了一个包含cplex12.5版本的安装包和破解包（一个叫Crack的文件夹），打开安装包进行安装。

需要将从属性中，以win7兼容模式运行此程序，才可以进行安装。

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200911163318374.png" alt="image-20200911163318374" style="zoom:33%;" />

安装好之后，由于教程中并没有要求进行破解，所以我也没有对Crack文件夹进行任何操作。并且，在安装过程中并未像博客中出现需要安装VC++驱动。**（下图来源于博客，我并未遇到下图中的情况）**

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200911163409011.png" alt="image-20200911163409011" style="zoom:33%;" />

按照教程，将Cplex的路径添加进matlab，并且使用yalmiptest进行测试。

**问题来了：**

**yalmiptest中，cplex显示not found；并且运行自己编写的例程，显示'solver not found cplex'**

但是，在我的matlab\toolbox\Yalmip-master\solver文件夹下的definesolver.m文件中，是有CPLEX12.5的。（有些人安装失败是因为这个文件夹下并没有这个CPLEX版本）

于是第一次安装宣告失败

## 第二次尝试

我之前的电脑中，cplex的版本为12.6。于是，我从原来的电脑中拷贝了12.6的安装文件夹，并且按照之前的过程重新安装了一遍。在安装过程中，出现了需要安装VC++的提示，因此我进入微软官网进行了安装，最后将cplex路径添加进了matlab。

**然后问题又来了：**

只要运行与yalmip相关的代码，matlab就会崩溃。

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200911164332776.png" alt="image-20200911164332776" style="zoom:50%;" />

这次应该也是我所使用的MATLAB2016b与cplex版本冲突了。在我之前的电脑安装CPLEX时，使用matlab2018b和2016b都出现了此问题，但是最后2016b解决了这个问题，具体的方法我忘记了，总之就是我现在也不知道咋解决。

第三次尝试宣告失败

## 第三次尝试

我在之前的cplex安装教程的评论中，发现了一个评论，说cplex有问题的话就下载一个链接中的cplex(我已经分享，链接如下)：

链接：https://pan.baidu.com/s/1UIHdLbfRjqpN9WpNtmX5PA 
提取码：m70c 
复制这段内容后打开百度网盘手机App，操作更方便哦



然后我将其下载并安装，发现这是一个12.8版本的cplex。按照之前的教程安装并添加路径，就直接成功了。

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200911164834040.png" alt="image-20200911164834040" style="zoom:40%;" />

似乎12.8的子文件夹内容与之前不一样，所以着实让我慌了一下，但是最后总之还是成功了。

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200911165057419.png" alt="image-20200911165057419" style="zoom:33%;" />

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200911165129412.png" alt="image-20200911165129412" style="zoom:33%;" />

例程也计算成功，这里就不放截图了。