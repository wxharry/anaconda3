关于win10中安装和配置Anaconda3及python2的文档
因为了解到python2在2020年就要停止维护了，决定把电脑里的anaconda2->anaconda3
然后踩坑无数。。。
简单的目录：
	下载安装
	1. cmd使用
	2. python使用
	
1.下载安装。
如果有vpn 的话可以上官网去下载。https://www.anaconda.com/distribution/#download-section（如果直接百度搜索，找到Download，记得选择对应的系统，这里选择windows）

![image](https://github.com/wxharry/anaconda3/blob/master/images/1.png)

下载完成以后，在下载列表里面找到
![image](https://github.com/wxharry/anaconda3/blob/master/images/2.png)

双击安装一路next直到：
![image](https://github.com/wxharry/anaconda3/blob/master/images/3.png)

如果是第一次装建议是选下面这个，如果电脑环境里有就选上面那个，这个教程是记录我个人安装过程的，所以我只选了下面这个（我在安装前把Anaconda全部卸载了再来安装的）。
然后一路next直到进入安装进程，安装需要一些时间，要有耐心，快结束前会比较慢，看上去都没在动，耐心等一下，过了这个坎就会唰的一下完成finish!
然后就算是有Anaconda了

2.cmd的使用
这里windows也有很多坑，主要是要把安装的Anaconda3的环境配置一下，具体方法：
Win10用户的快捷键操作：win+Q -> 输入“高级”->查看高级系统设置
在设置中的查找“查看高级系统设置”应该都可以找到

![image](https://github.com/wxharry/anaconda3/blob/master/images/4.png)
![image](https://github.com/wxharry/anaconda3/blob/master/images/5.png)
![image](https://github.com/wxharry/anaconda3/blob/master/images/6.png)

点击“高级”-》“环境变量”-》“Path”双击-》把Anaconda3的目录添加进去
怎么知道自己成功了？cmd输入conda activate 回车 结果如下 这里坑比较多
![image](https://github.com/wxharry/anaconda3/blob/master/images/7.png)

雷区：
问题：‘conda’不是内部或外部命令，也不是可运行的程序
或批处理文件。
原因：Scripts没有添加成功，Script能让你可以在cmd使用conda命令，如果你在cmd输入说你
解决方法：检查地址是否有误

问题：很长一段的报错，最后一句：TypeError: LoadLibrary() argument 1 must be str, not None
原因：应该是没有添加libs文件，这个问题很玄学，我研究了很久，最后是在添加libs到path里面才搞定的，现在把libs删掉又不会报错了。官网上说这个问题早在2019.7就解决了，可我是在2019.8.16装的。如果添加libs也没用，那可以把所有和lib有关的都添加近path试一下。
那么到现在Anaconda就可以用了！

怎么用呢？
打开cmd，输入conda activate(base)，这里如果activate后面什么都不写是默认base的
然后输入python就可以进入python3.7愉快地用Python37 programming了！
其他还有conda命令如：conda update conda, conda init, conda search等都可以试试

3.python的使用
除了anaconda3自带的python37以外，还可以自己建一个其他版本的python环境。
比如python27：在cmd输入conda create -name python2=2.7命令，就会在anaconda3的env文件夹l里下载python27的东西了，不过大部分的包都是没有的要自己去补充

还有一个方法是下载anaconda2，下载安装步骤和3一样，不够因为电脑里面已经又anaconda3了，在之前第二张图中选择的时候可以勾选第一个，这也anaconda2就会就如anaconda3的环境了（我也没试过，但是看样子应该是这样的，我因为电脑内存有限，就没安装2）





