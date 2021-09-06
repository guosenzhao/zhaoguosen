---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "2021 09 06 Typora Github同步代码库"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-06T21:14:43+08:00
lastmod: 2021-09-06T21:14:43+08:00
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
>工欲善其事必先利其器。不论是写文本，作展示，记录代码，有一款趁手的笔记工具就很必须要。

### 记录方式
首推markdown
推荐理由：直接，简约，清楚。
比如我后期的公众号都是通过markdown记录的。
### 云笔记本构建
云笔记本的构建，对我而来图床的设置最为必要。因为Typora软件如果不设置图床的话，所有的图片都是在本地，这样就很不利于分享。主要是不能很方便的同步到微信公众号。所以下面主要解决图床问题。
- **1 Typora下载与安装**
  
```
https://typora.io/
```
作为编辑器,下载安装之后就可以直接书写了。  
具体的markdown语法在下一期具体介绍。
**简单设置一下**    
第一步
![](6e37243f-3ebc-47af-a309-5ab7dc048a06.png)
第二步
![](9d1791a2-aa02-4444-bcb7-aec864aa061e.png)
简单设置以上两步足够

- **2 Git安装**    
**借助github托管笔记**   
```
https://git-scm.com/
```
安装好之后加入环境变量。
- **3 注册github账号**     
略……    
然后在github新建一个用于管理笔记的仓库。

- **4 建立ssh连接**
```
#打开terminal终端
PS C:\Users\zhaoguosen> e:
PS E:\> mkdir jinrizhisen
PS E:\> cd .\jinrizhisen\

#获取ssh公钥，保证本地和远端github可以连接
PS E:\jinrizhisen> ssh-keygen -o
PS E:\jinrizhisen> cat C:/Users/zhaoguosen/.ssh/id_rsa.pub
#然后将获得的一串公钥字符添加到github中。如下图：
#将github新建仓库的git复制到本地
PS E:\jinrizhisen> git clone git@github.com:guosenzhao/new_notes.git
#创建一个子文件夹，用于更新文献公众号推文
PS E:\jinrizhisen> mkdir wechat
```

![](7c454494-e71c-47fa-a6f0-1d5bdbfabe19.png)
准备就绪，就可以测试一下。

### 测试环节
打开刚才新建的文件夹，新建一个`test.md`
![](f42194d4-48d4-41f0-8584-6908ac832c0b.png)
随便写一点。

![](578d8684-e130-4021-930c-07809ccfb615.png)
然后通过git从本地上传到github。
```
PS E:\jinrizhisen\new_notes\wechat> git add .
PS E:\jinrizhisen\new_notes\wechat> git commit -m "add all"
[master 9884b1f] add all
 1 file changed, 15 insertions(+)
PS E:\jinrizhisen\new_notes\wechat> git push
Enumerating objects: 7, done.
Counting objects: 100% (7/7), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (4/4), 417 bytes | 14.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:guosenzhao/new_notes.git
   cfca1e5..9884b1f  master -> master
```
这样就算上传完毕了。打开github看一下。

![](57160752-49ba-4748-8422-9a9f5aa9964e.png)
好的。我主要还是想测试一下图片。看一下图片文档编辑完之后复制到微信会不会同步图片。

![](f2b254a8-4f1d-4a11-a5e7-74eca161c773.png)
这里插入了两种格式的图片。

![](d8076866-f8b3-4660-a241-6ba2d041a943.png)
可以看到，图片链接是可以显示的，而本地图片显然没有被同步。
这个问题一时半会儿也解决不了，起码代码之类的可以同步保存了。