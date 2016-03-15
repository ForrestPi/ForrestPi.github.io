---
layout: post
title: install theano
category: project
description: 在windows7 64位系统下安装theano进行深度学习
---

##在windows7 64位系统下安装theano##
最近在学习深度学习的一些内容，需要用到深度学习的库：theano。但是theano这玩意在Linux或者mac OS 下面比较好安装，只需要先装Anaconda然后使用python的安装命令符，pip install theano即可，但是在windows中，之前装的时候经常报错出现 no module named gof这个错误让人烦躁不已，看了一些资料，后来终于在windows下安装了theano，把安装步骤说一下：
安装环境:windows7 64位 旗舰版
###step1：安装Anaconda###
这个直接去官网down就行了，下载完成之后，就点击安装就行，安装完之后其实Anaconda的环境已经配置到你的path里面了
###step2：安装mingw###
由于windows没有gcc套件，所以需要安装mingw，安装mingw的过程不复杂，不要轻信下个什么压缩包放进python的包，直接使用命令

conda install mingw libpython

就行了，然后直接给安装好了。
###step3: 修改环境变量###

需要新加几个环境变量：

在path里加一个：D:\Anaconda2\MinGW\bin;D:\Anaconda2\MinGW\x86_64-w64-mingw32\lib

###step4：安装theano###

theano安装比较方便的是使用安装命令:

pip install theano，

然后就可以等安装完成了

###step5：添加theano环境变量###

增加一个环境变量PYTHONPATH: 值为theano的安装位置 比如我的是 D:\Anaconda2\Lib\site-packages\theano

###step6：增加一个配置文件###

在cmd用户环境下增加一个 .theanorc.txt文件，这里的cmd用户环境下指的是用户身份那个文件夹下面，比如我是以管理员身份登录的，所以我需要在 C:\Users\admin这个根目录下新建一个 .theanorc.txt文件，如果你是以man账号登录的，那么这个地址就应该是:C:\Users\man 注意前面有一个点号，该文本的值是:

[global]
openmp=False
[blas]
ldflags=
[gcc]
cxxflags = -ID:\Anaconda2\MinGW

cxxflags后面的 D:\Anaconda2\MinGW是在Anaconda安装目录下面的MinGW文件路径，可以根据自己的位置做相应的修改。

###step：7 安装完之后在python环境下进行测试:###

执行下面两条命令:

import theano

theano.test

如果出现的是theano的一些安装信息，那么表示安装成功了~



[ForrestPi]: http://forrestpi.github.io/	"ForrestPi"
[1]:    {{ page.url}}  ({{ page.title }})