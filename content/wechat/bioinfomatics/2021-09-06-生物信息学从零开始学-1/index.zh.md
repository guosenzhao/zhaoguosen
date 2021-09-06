---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "2021 09 06 生物信息学从零开始学 1"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-06T21:51:29+08:00
lastmod: 2021-09-06T21:51:29+08:00
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
# 森言森语 
>有一个现象蛮有趣，以前在东北的时候，每天都要奔跑，定期还要考核，偶尔5公里跑进21分半的时候，还很沾沾自喜。后来我可以以很快的速度跑完30公里或更远，甚至5公里可以跑进18分30秒的时候，反而觉得平静。

 ## 1 Python shell 
 ##### 案例1 计算ATG水解的△G  
 ![](487033d5-ca92-4657-b525-2688fe92b698.png)  
 ```python 
 ATP = 3.5 
 ADP = 1.8 
 Pi = 5.0 
 R = 0.00831 
 T = 298 
 deltaGO = -30.5 
 import math 
 print(deltaGO + R * T * math.log(ADP * Pi / ATP)) 
 ``` 
 ##### 案例2 如何计算两点间距离？
 ![](68675baa-8354-4101-8e67-0579b740f100.png) 
 ```python 
 from math import * 
 x1 , y1 , z1 = 0.1 , 0.0 , -0.7 
 x2 , y2 , z2 = 0.5 , -1.0 , 2.7 
 dx = x1 - x2 
 dy = y1 - y2 
 dz = z1 - z2 
 dsquare = pow(dx, 2) + pow(dy, 2) + pow(dz , 2) 
 print(sqrt(dsquare)) 
 ``` 
 ## 2 第一个Python程序 
 ##### 案例3 如何计算胰岛素序列中的氨基酸频率 
 
```python 
 # insulin [Homo sapiensl GI:386828 
 # axtracted 51 amino acids of A+B chain 
 insulin = "GlVEQCCTSICSLYQLENYCNFVNQHLCGSHLVEALYLVCGERGFFYTPKT" 
 for amino_acid in "ACDEFGHIKLMNPQRSTVWY":     
     number = insulin.count(amino_acid)   
     print(amino_acid, number) 
``` 

##### 案例4 如何创建随机序列 
```python 
import random 
alphabet = "AGCT" 
sequence = "" 
for i in range(10):     
index = random.randint(0, 3)     
sequence = sequence + alphabet[index] print(sequence) 
``` 

##### 案例5 如何在序列中运行滑动窗口 
```python 
seq = "PRQTEINSEQWENCE"  
for i in range(len(seq)-4):     
print(seq[i:i+5]) 
``` 

通过案例代码来想输出。哈哈。
