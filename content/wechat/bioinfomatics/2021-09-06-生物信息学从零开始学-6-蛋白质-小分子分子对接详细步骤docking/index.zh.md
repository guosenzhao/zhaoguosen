---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "2021 09 06 生物信息学从零开始学 6 蛋白质 小分子分子对接详细步骤docking"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-06T22:22:18+08:00
lastmod: 2021-09-06T22:22:18+08:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
### 叠合两个蛋白质三维结构

##### 蛋白质三级结构的比对

  蛋白质三维结构比对就是对蛋白质三维空间结构的相似性进行比较。

  - 可用于探索蛋白质进化及同源关系
  - 改进序列比对的精度
  - 改进蛋白质结构预测工具
  - 为蛋白质结构分类提供依据
  - 帮助了解蛋白质功能

  结构比对的结果可以用很多种参数来衡量，最常用的是root mean squared deviations（RMSD）。如果两个结构的RMSD为0埃，则结构一致，可以完全重合；一般来说RMSD小于3埃时，认为两个结构相似。

 ###### superpose蛋白结构叠合

  ```
  http://superpose.wishartlab.com/
  ```
![](146717b1-e86f-4825-93e3-c703ad77d8ea.png)


![](47e17521-d17a-4bf6-8da4-da2c064f661a.png)

 ###### SPDVB叠合
  ```
  https://spdbv.vital-it.ch/
  ```

  载入需要叠合的两个蛋白质PDB文件。

 
![](726d4243-679c-4901-84c7-3ffb88ddd1c0.png)


  自动叠合


![](5155e5a2-c823-41bb-aa5d-d8fe50ba5426.png)

![](8e825d3d-1741-4c9a-9c83-a12071800c64.png)


  也可以选择性叠合

![](fc78520c-c911-4ef6-9517-55782b29c99e.png)

##### ## 蛋白质表面的分子性质

- 表面形状
- 表面电荷分布
- 表面残基可溶性

首先需要下载VMD插件-APBS，下载后放入VMD安装目录。

- 读取需要分析的蛋白质PDB文件jinrizhisen.PDB

![](db1b3a23-eb8f-4122-b8a9-47e72a84fbe0.png)


- 为jinrizhisen.PDB创建psf文件，psf文件是另一种存储蛋白质结构信息的文件，

![](c8280b75-fc49-4a74-9a40-5654265f9232.png)


![](e3de17f1-5151-42f4-9c54-2e2a5f7a93b0.png)


可以看到生成了以下文件

![](5d31f6af-8851-4356-be50-6fa76538e7b2.png)


到这里，准备工作结束，下面开始做电荷分布

此时需要关闭VMD再重新打开，依次载入刚创建的jinrizhisen_autopsf.pdb文件和jinrizhisen_autopsf.psf文件。
![](e1e98a3a-faac-40a5-90ef-d42b4d76ae2b.png)

![](9d49027a-4ca9-4c24-949d-c82c752af778.png)

![](e22c84a1-c4fe-4c3e-a49c-eac387a4ecc6.png)



run结束后产生了一个文件夹


![](a7f8eec0-e30e-4365-8674-2aa69b128b3c.png)


删除原来的分子，需要重新依次载入四个文件夹，分别为jinrizhisen_autopsf.pdb，jinrizhisen_autopsf.psf，jinrizhisen_autopsf.pqr，pot.dx


![](bd89a3d1-011e-49a9-984e-e14587404602.png)

![](3f37cb37-941b-4e5f-b6a8-f0ed71a7bb90.png)

上图中蓝色代表正电荷，红色代表负电荷。白色不带电荷。

换个姿势


![](661c24b9-bc28-472b-bf83-51f411c8bd07.png)


![](645902f9-8513-4609-a892-eaf4c7741bde.png)
同样的方法也可以做残基可溶性分布图

谁能猜到这个蛋白是哪一类型的蛋白呢？或者具有哪些特别的结构和功能？

## 蛋白质四级结构的获取
- 数据库获取
```
https://dip.doe-mbi.ucla.edu/dip/Main.cgi
https://thebiogrid.org/
https://string-db.org/
```
- 分子对接（docking）     
两种蛋白质-蛋白质分子对接
- Rigid Docking
- Flexible Docking

ZDOCK：全能在线对接工具
```
https://zdock.umassmed.edu/
```

![](1efc100c-a597-497d-bcc5-efb766adb168.png)

半天打不开……
分析一下
```
https://www.ebi.ac.uk/msd-srv/prot_int/cgi-bin/piserver
```
由于没有上一步结果，这里也就先不分析了。     
蛋白质-小分子对接
```
#需要安装python2.5环境，所有安装路径不能出现中文
#然后安装autodock
http://autodock.scripps.edu/
#再安装myltools
http://mgltools.scripps.edu/downloads
```
所有软件安装完毕后打开autodocktools

首先加工处理小分子ad_ligand.pdb

![](cb778b1c-0ea2-4836-a382-bbb3623ae04f.png)
给小分子加H原子

![](cf33f095-8d83-459e-8851-2f1664aac2be.png)
给小分子加电荷

![](f7fb0ac2-f025-4c8f-989b-b5310563320b.png)
加工完成后指定为要对接的ligand

![](646ca22d-b0cd-4169-bfc3-327f8893fbf5.png)
自动确定扭矩中心

![](d153db3e-f752-4b97-b380-75032d49ccf1.png)
确定对接过程中键的旋转与否，绿色为可旋转。

![](241e6359-3e32-48df-bd15-c7881085a2a7.png)
加工完成，将加工结果保存为pdbqt文件。

![](10512a00-6c78-446a-b9d5-9adc88e4ce7b.png)
接下来处理蛋白质分子
先把刚才载入的小分子删除

![](8c9fc626-9466-4726-9dec-012db05bc424.png)
载入蛋白质分子

![](496a7a99-b975-4ff8-8740-363fa3e86ea8.png)
然后和处理小分子的过程一样，加H，加电荷

![](0b6a1620-1dfa-4248-9b95-4842f5f272dd.png)
蛋白质处理完成后，将其指定为要对接的蛋白质

![](7e4b8b6b-834f-4b40-8b75-8a980e5e516f.png)
指定完成后，自动保存为pdbqt文件
载入要涉及到的原子

![](f77f94da-f2e7-480b-bdab-ea33d865c515.png)
指定盒子的范围

![](86e6fb5f-403a-4531-ba12-547f5f51abd4.png)
设定完成后保存

![](a8f92afe-a44a-47e5-9db0-c0fe681dd4f6.png)
保存目前的设置

![](d8d61fa8-10f2-4063-ba8c-b6e37adde1de.png)
下面运行autogrid,为蛋白质分子创建map
```
autogrid4 -p test.gpf -l test.glg

autogrid4: Successful Completion.
```
运行完成后产生了一系列map文件

![](82662457-44f3-44d2-80b6-ffc0e15264aa.png)
下面设置docking的参数文件，选定蛋白质和小分子

![](2664225e-fd39-437c-8653-17b73107e958.png)

![](98b691d1-75e3-4aac-9f09-6d8e9ece473b.png)
选择docking算法

![](317ed0fe-7b24-4079-95c9-75459887b3b4.png)

![](52289732-de85-4b39-950a-30ee91c42c9f.png)
输出docking参数文件

![](b6d7e161-5cfa-4eba-8f7a-0ad6e7002fad.png)


![](2717e853-a0a2-459b-b0be-f10a23051086.png)
开始docking
```
E:\Autodocktest>autodock4 -p test.dpf -l test.dlg

________________________________________________________________________________

autodock4: Successful Completion on "DESKTOP-H3AAFU3"

________________________________________________________________________________
```
这就是最终的输出结果文件
![](3f1dc944-e68b-4a77-a9b8-0bb9e8f52b66.png)

下面将结果显示出来，首先同样删除之前载入的所有文件

![](f9c2138e-d2b4-49e8-9a5c-5f752bc3eafe.png)

![](3ef1540c-4603-4e6a-953b-5e90d3dd0b78.png)

![](3e0def1c-cc1f-4b2d-adc7-fbe525064a74.png)
再打开蛋白质文件

![](04fd2bba-2491-4bb7-8e61-341daf3e5bc8.png)

现在小分子的位置是docking之前的位置
![](55b785a4-4813-4ccc-8610-b0d89304f531.png)
看看docking之后的位置

![](b775c2a6-faef-487c-9759-d516f8db2306.png)

看一下前50个对接结果



![](cd543d0c-f8f0-46df-bc91-b1dfc8bfd49b.png)
下面看一下排名第一的对接结果的具体情况

![](d8fe38f3-78e2-45c5-af9b-a1700d5533db.png)
可以看到小分子与蛋白质上的哪些氨基酸产生作用，并列出了产生氢键的位置
保存排名第一的对接状态
删除除了小分子之外的全部分子

![](f3361954-e021-4f91-b951-4418d3e2f304.png)
然后保存

![](3c654ccb-a880-4d78-bc17-8fbd6dd231aa.png)

![](857351c5-3ffa-4424-8846-10c0655a98f8.png)
看一下rank1.pdb

![](621c3c1a-9c17-45b2-8417-8595b53388fe.png)
将其内容拷贝至ad.protein.pdb,保存为result.pdb    
此时result.pdb就是既包含蛋白质也包含小分子的复合体结构     
然后就可以用VMD打开result.pdb进行可视化     


## 分子对接（docking）：虚拟筛选Virtual screening（VS）

>虚拟筛选(virtual screening，VS)也称计算机筛选，即在进行生物活性筛选之前，利用计算机上的分子对接软件模拟目标靶点与候选药物之间的相互作用，计算两者之间的亲和力大小，以降低实际筛选化合物数目，同时提高先导化合物发现效率。
化合物小分子库ZINC
```
https://zinc.docking.org/
```
```
http://vina.scripps.edu/tutorial.html
```
## 分子对接（docking）：反向对接
靶标数据库
```
http://bioinfo-pharma.u-strasbg.fr/scPDB/
```
## 分子动力学模拟（molecular dynamic simulation）
涉及软件：NAMD，CHARMM，DESMOND，GAUSS等
```
https://www.ks.uiuc.edu/Gallery/Movies/ChannelProteins/
```

Water Channels in Cell Membranes

How Bacteria Makes a Tail

Electrical Current through a Bacterial Toxin

注：整理自山东大学《生物信息学》  