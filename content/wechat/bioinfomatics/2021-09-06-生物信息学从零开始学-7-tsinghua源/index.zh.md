---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "2021 09 06 生物信息学从零开始学 7 Tsinghua源"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-06T22:52:08+08:00
lastmod: 2021-09-06T22:52:08+08:00
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
## 森言森语  
>红豆生南国，    
春来发几枝。    
愿君多采撷，   
此物最相思。    
——《相思》唐·王维  

本来十一点就要回去休息了，结果安装个小软件居然等了半个小时，等着等着还终止了。

 官方软件源还是不行，本来就是想试试官网源到底行不行。
 
 事实证明不行。
 
 于是删除之前加载的官网软件源，重新换回tsinghua源。
 
 ``` 

conda config --remove-key channels 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/         conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/       
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/      
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/ 
``` 

于是，三两分钟就安装了五六个软件，tsinghua源可以。


``` 
 #!/bin/bash 
 conda install -y mafft 
 conda install -y blast 
 conda install -y fasttree 
 ...
```  
另外关于zsh：command not find:conda 的解决办法  

``` 
vi ~/.zshrc 
#末尾加入环境变量即可 
export ZSH=$HOME/.oh-my-zsh 
source ~/.zshrc 
``` 