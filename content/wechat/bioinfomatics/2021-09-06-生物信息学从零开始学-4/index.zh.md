---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "2021 09 06 生物信息学从零开始学 4"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-06T22:09:49+08:00
lastmod: 2021-09-06T22:09:49+08:00
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

>时间的付出，方法论的改变。

 #### 先决条件 
 - 应熟悉linux操作系统 
 - 应基本熟悉linux环境配置、文件管理等基本知识点      
 
总而言之，先决条件就是尽可能熟悉linux，越熟悉越好。
#### Xshell和Xftp的安装 

使用`edu`邮箱在Xshell网站`https://www.netsarang.com/en/xshell-download/`申请，获取到下载连接后按照常规的Windows软件安装即可。

- Xshell用来远程连接服务器（基于linux操作） 
- Xftp用来传输文件 

#### 拥有一个服务器 

- 学校有服务器有申请一个账号用呗 
- 没有就自己买个低配版的，比如腾讯云、阿里云、华为云之类，买最低配的随便玩玩就好，比如一年几十块那种   

注意，如果购买服务器，需要选择ubuntu或者centos吧。购买之后先重置密码，设置一个好记的新密码后记住。

#### 为什么需要一个服务器 

其实可以使用虚拟机，也一样玩，但是一般的电脑，安装个虚拟机，再在虚拟机中安装linux就感激很笨重，如果电脑性能不是很好的话，其实稍微大一点的数据也跑不了，而且对电脑硬件都是很大的损伤，有时候一个任务跑好几天，电脑就会烫的厉害，还耽误干别的事，就很不好。所以有一个服务器就是刚需了。


#### Xshell和Xftp建立连接 

这一步就也很简单，新建之后输入： 
- 主机：公网IP 
- 密码：上面重置之后的密码        

然后就可以登陆了。Xshell和Xftp都通过这种方法登录。

#### conda的安装与使用 

为什么要用conda，因为方便。
- 安装conda      
conda分为anaconda和miniconda。anaconda已经安装了一些常用的包，而miniconda是精简版，需要什么包就装什么包。

```
# 基于linux的安装 
wget -c https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh       
#给执行权限 
chmod 777 Miniconda3-latest-Linux-x86_64.sh       
#运行       
bash Miniconda3-latest-Linux-x86_64.sh       
``` 

由于之前没安装过其它包，所以就一路yes往下安装即可。
- 添加镜像        
###### 添加官网镜像（不推荐，可能慢）       
```
conda config --add channels bioconda 
conda config --add channels conda-forge 
``` 

###### 添加tsinghua镜像（推荐） 

```
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/ 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/ 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/ 
conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/ 
``` 

###### 检查一下 

``` 
显示安装的频道        
conda config --set show_channel_urls yes      
查看已经添加的channels      
conda config --get channels      
已添加的channel在哪里查看      
vim ~/.condarc      
``` 

###### 退出环境 

```
conda deactivate 
```  

## 小结 

到这里就基本上有了可以操作的环境，就可以尽情使用咯。不过，说一千道一万，想要物尽其用，还是要多花时间琢磨，没有什么是可以速成的。就像开头说的，只有时间的付出加上方法论的改变，才有可能慢慢进阶。