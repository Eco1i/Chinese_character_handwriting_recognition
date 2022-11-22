### 汉字手写识别

-----

#### 1、介绍

```tex
使用python+flask完成识别系统的搭建，通过用户在网页端手写的汉字处理后发送到后端对应接口，使用CNN模型进行识别，在通过PIL生成可能结果的汉字图片发送前端展示，以上便是整个系统的流程。目前只对常用的汉字进行识别（分类）。
```

#### 2、环境依赖配置 (pip install xxx=='版本号')

+ python 3.6

+ numpy 1.19.5

+ flask 0.12.2

+ tensorflow 1.3.0

+ pillow 4.2.1

+ pickleshare 0.7.4

+ ###### 下面是在跑训练集时下载的，版本号对应很重要

+ cuda 9.0

+ cudnn 7.0

#### 3、数据集下载

```tex
数据来源至中科院自动化研究所
下载链接：
		训练集：http://www.nlpr.ia.ac.cn/databases/download/feature_data/HWDB1.1trn_gnt.zip
		测试集：http://www.nlpr.ia.ac.cn/databases/download/feature_data/HWDB1.1tst_gnt.zip
注意：下载后数据集需要解压后使用data_to_png.py转为png文件，当然如果你使用我的结果就不用以上操作
```

#### 4、CNN结构

```tex
采用tensorflow库三个卷积层+三个池化层+两个全连接层的卷积神经网络
```

#### 5、我的结果

```tex
我一共迭代了80000次，取的准确率0.9453125，训练好的模型保存checkpoint文件夹中，训练的py文件保存/train_MyModel下
```

#### 6、如何运行

```tex
在配置好相关依赖时，保证你的checkpoint文件有我的模型，只需要运行run.py文件即可，控制台会显示前端的url，点击即可进行。
当你成功进入前端页面时，在手写文字却无反应，后端报错，可以尝试：pip install Werkzeug==0.16.1 
```

#### 7、如何训练

```tex
在第五点中，下载好数据集解压后放入train_MyModel/data下，数据集名字不要更改，保持HWDB1.1trn_gnt以及HWDB1.1tst_gnt。
运行data_to_png.py文件，等待转换完成，可以开始运行chinese_rec.py文件，运行过程中会生成checkpoint文件夹，保存的就是你的运行模型。运行结束后将该文件夹覆盖app/train_model/checkpoint
```

#### love and peace 喜欢的话点个star吧！





