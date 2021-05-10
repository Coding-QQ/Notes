# Pytorch+Python配置记录

首先说明：我的电脑显卡是Nvidia RTX 2060，之前实验室的学弟已经帮我安装好了CUDA11.1版本及其对应的cudnn，我的安装从这里开始。

我主要参照的教程为B站视频【PyTorch深度学习快速入门教程（绝对通俗易懂！）【小土堆】】，大部分安装的流程都是按照他的过程来的。视频链接：https://www.bilibili.com/video/BV1hE411t7RN

这篇文章主要是是我安装过程的流水账，并不是一个教学。我想要记录安装的过程，以及出现的bug和解决bug的过程，希望能够帮助其他出现了bug的同学。

## Anaconda的安装

首先，进入Anaconda官网，按照视频里面选择历史程序(https://repo.anaconda.com/archive/)，选择2018年5月30日的支持python3.6版本的anaconda：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321150550997.png" alt="image-20210321150550997" style="zoom: 50%;" />

下载完之后，直接一直next安装，然后得到的结果如图所示：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321150721371.png" alt="image-20210321150721371" style="zoom:50%;" />

然后，我们按照视频中的，创建pytorch环境：

```
conda create -n pytorch python=3.6
```

成功创建pytorch环境后，可以输入

~~~
activate pytorch
~~~

来进入环境，会发现命令行前面的base变成了pytorch

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321151115749.png" alt="image-20210321151115749" style="zoom:67%;" />

然后输入pip list，可以看到现在的package的列表：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321151235132.png" alt="image-20210321151235132" style="zoom:67%;" />

可以看到，现在还没有pytorch，接下来我们将进入pytorch的安装。

## 显卡驱动的安装

在安装pytorch之前，我们需要安装显卡的驱动

（这个驱动我刚装完电脑就已经装好了，所以下面只是用截图简单示意一下，并不是实时的演示。）

（说好了记流水账的。。。这一节稍微跑偏了）：

进入Nvidia的官网

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321151418319.png" alt="image-20210321151418319" style="zoom:67%;" />

搜索到了显卡驱动以后，直接下载，并且一直“下一步”无脑安装即可。安装完之后，可以看到任务管理器-性能里面出现了GPU的一栏：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321151530806.png" alt="image-20210321151530806" style="zoom:67%;" />

说明这个时候驱动已经安装完毕。（继续流水账）

## Pytorch的安装

首先，我们到达pytorch的官网https://pytorch.org/，选择想要的pytorch版本

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321151702406.png" alt="image-20210321151702406" style="zoom:67%;" />

我们的系统是windows，package当然选conda，语言当然是python，由于之前我已经安装了11.1的CUDA，所以这里的CUDA版本选择CUDA 11.1。我们可以看到下面的命令为：

~~~
conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c conda-forge
~~~

其中，前面的"pytorch torchvision torchaudio cudatoolkit=11.1"都是软件名称，后面的-c pytorch -c conda-forge意识是下载的源。因此，这里是直接从pytorch的源或者conda forge进行下载。虽然很慢，**于是我在运行上一个命令之前**，加载了清华的镜像源：

~~~
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
conda config --set show_channel_urls yes
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/pytorch/
~~~

然后紧接着，我用了下面的指令来安装：

~~~
conda install pytorch torchvision torchaudio cudatoolkit=11.1
~~~

这个时候，我以为会从清华镜像源来下载pytorch，没想到清华镜像源里面似乎没有这个版本的cudatoolkit：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321153200861.png" alt="image-20210321153200861" style="zoom:67%;" />

所以，我干脆老老实实地输入下面的命令，并且死等：

~~~
conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c conda-forge
~~~

![image-20210321152932420](http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321152932420.png)

这个下载速度着实慢的一批，我甚至还去踢了一场球，回来再一看，发现pytorch直接没下完，安装失败。

查阅资料，我发现我没有添加conda-forge的清华镜像源，导致下载失败，于是我输入：

~~~
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
~~~

然后这个时候再进行安装：

~~~
conda install pytorch torchvision torchaudio cudatoolkit=11.1
~~~

终于成功了！

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321181510016.png" alt="image-20210321181510016" style="zoom:67%;" />

输入python，再import torch来验证安装是否成功

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321181557268.png" alt="image-20210321181557268" style="zoom:67%;" />

**没有提示就是最好的提示！**

此时我们pip list，来看一下现在的package列表：

<img src="http://lqqnotes.oss-cn-beijing.aliyuncs.com/img/image-20210321181657596.png" alt="image-20210321181657596" style="zoom: 67%;" />

均安装成功了

