---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "2021 09 06 第3天 Linux学习手册 小结"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-06T21:48:17+08:00
lastmod: 2021-09-06T21:48:17+08:00
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
# 8 高级键盘技巧
>学习以下命令    
`clear `   
`history `

![](ebe9a601-ef87-428c-938d-5d5b9bb9b7bb.png)

![](0e38fdf0-8501-4e42-8c3a-65847dbd64d8.png)

![](8cc3f881-d2e1-4530-8028-f18396b8c88b.png)

![](131348c0-2628-46c1-9448-6b6b4c16ea4b.png)
# 9 权限
>`id`：显示用户身份标识。     
`chmod`：更改文件的模式。     
`umask`：设置文件的默认权限。    
`su`：以另一个用户的身份运行shell。    
`sudo`：以另一个用户的身份来执行命令。    
`chown`：更改文件所有者。    
`chgrp`：更改文件所属群组。    
`passwd`：更改用户密码。    

## 读取、写入和执行
![](120871ba-6e7b-4f4c-be61-cad115bc5486.png)
![](2856b362-b6ea-45eb-8649-a1fd2a43c02b.png)
## 更改身份
su命令和sudo命令之间的一个重要区别在于sudo命令并不需要启动一个新的shell环境，而且也不需要加载另一个用户的运行环境。这意味着，使用sudo命令的时候并不需要用单引号把命令行引起来。
## 更改用户密码
`Passwd [user]`
# 10 进程
>ps：显示当前所有进程的运行情况。             
top：实时显示当前所有任务的资源占用情况。        
jobs：列出所有活动作业的状态信息。         
bg：设置在后台中运行作业。         
fg：设置在前台中运行作业。         
kill：发送信号给某个进程。         
killall：杀死指定名字的进程。            
shutdown：关机或者重启系统。 

# 第一部分 学习shell完结