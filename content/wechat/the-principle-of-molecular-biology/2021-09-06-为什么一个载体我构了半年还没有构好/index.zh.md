---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "2021 09 06 为什么一个载体我构了半年还没有构好"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-06T20:13:22+08:00
lastmod: 2021-09-06T20:13:22+08:00
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
森言森语：  最近上课有老师说，曾有学生一个载体构了半年还没有构好。那么构建载体真的有这么难吗？
 【进入真题】  第一步：基因的克隆  此时如果迟迟无法克隆到目的基因，可考虑的大概有两个方向，一是引物，二是模板。
 关于引物：  因素一：选择合适的酶切位点就很重要，虽然在克隆基因时酶切位点是否正确并不影响，但在后续连接过程中就很容易出状况。关于酶切位点的选择后面再说。
 因素二：引物是否合理，这里其实主要考虑的因素也不多，两条引物的Tm值不能相差太大（5℃以内），  其次有必要的情况下可适当设置30bp左右（GC含量过高或相同碱基过多重复的情况下）。
 关于引物设计的软件很多了，但大部分过于复杂，这里推荐一个我常用的软件AnnHyb，操作简单，直接明了。
 ！[](p1.png)  关于模板：  因素一：模板污染，就需要重新获得高质量的未降解的模板进行克隆；  因素二：模板丰度不够，此时可能需要将多个模板进行混匀后使用。
 通常来说，只要引物合适，模板正常，是个基因都能克隆到，当然，这个基因不能是假基因。因为我之前仅使用一对引物克隆过长约4000 bp的序列。
 反而在使用桥接PCR时并未成功桥接。
 第二步：酶切  酶切这一步需要考虑的因素有：  因素一：酶切位点的选择，需要满足所选酶切位点在目的基因中不能出现；  因素二：酶切，选择合适的，在保质期内的buffer很重要，其次，酶切时间其实没必要过于苛刻，通常来说双酶切3h产生的载体足够我们做连接使用。
 很多时候没必要对酶切产物进行跑胶确认是否切开。毕竟连接后还会再检测嘛。
 那这里怎么检查我们的目的基因序列中有没有选定的酶切位点的序列呢？总不能一个一个去查找吧？这里给大家推荐一个在线工具。
 限制性酶切位点统计工具http://www.detaibio.com/sms2/rest_summary.html  当然SnapGene等很多工具都可以进行统计，这里只分享我常用的。
 第三步：连接、转化、检测等都不说了。这一环节通常不会出问题。
 最后，我想说，高铁正式运行之前，都会进行试运行。很多项目在正式开展之前也会进行模拟演练。
 那构建载体也一样，上述提到的几个步骤，包括基因的克隆，酶切，连接，电泳检测等，我们也可以再实验之前先行模拟。确保没有问题之后再具体展开实验。
 具体模拟过程可见推文技巧（1）——利用SnapGene构建载体，模拟基因克隆，酶切，连接及电泳检测。
     