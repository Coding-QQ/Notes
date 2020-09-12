## GitHub配置问题

首先，我在原先的电脑上已经有一个repo。我现在换电脑了，想把以前的repo克隆到新电脑上。

首先，我输入了：

```git
ssh-keygen -t rsa -C 'xxx@example.com'
```

然后将生成的公钥添加进了GitHub。

之后，输入下面的代码进行测试：

~~~git
ssh -T git@github.com
~~~

此时就出现了问题(Warning):

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200912101140801.png" alt="image-20200912101140801" style="zoom:67%;" />

相当于一次提示了两个错误（Warning）:

第一个是：Permanently added the RSA host key for IP address '52.74.223.119' to the list of known hosts.

第二个是：You've successfully authenticated, but GitHub does not provide shell access.

接下来我记录一下我是怎么解决这两个问题的。

## 第一个问题

第一个问题解决方法比较简单，我是windows系统，所以我在C:\windows\system32\drivers\etc\host文件中，添加一句：

~~~
# 52.74.223.119 github.com
~~~

添加后的效果如下图所示：

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200912101440123.png" alt="image-20200912101440123" style="zoom:33%;" />

注意，一开始这个文件夹是没有权限修改的。于是我们需要右键-属性-安全，来编辑权限：

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200912101559038.png" alt="image-20200912101559038" style="zoom:33%;" />

点击中间的“编辑(E)”按钮，选择User

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200912101639413.png" alt="image-20200912101639413" style="zoom:33%;" />

将修改和写入的权限允许：

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200912101710173.png" alt="image-20200912101710173" style="zoom:33%;" />

然后点击确定，弹出提示也不用管。然后就可以修改host文件了。

修改了host文件以后，第一个问题就解决了

<img src="C:\Users\liuqq\AppData\Roaming\Typora\typora-user-images\image-20200912102140822.png" alt="image-20200912102140822" style="zoom:50%;" />

## 第二个问题

第二个问题目前来看，并没有对我造成什么影响。所以我暂时没管。等到时候有问题了，我再来修改记录吧。

