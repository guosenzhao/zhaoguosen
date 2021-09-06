---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "2021 09 06 基因总是无法正确构建到载体上 你需要考虑吧这些"
subtitle: ""
summary: ""
authors: []
tags: []
categories: []
date: 2021-09-06T20:14:47+08:00
lastmod: 2021-09-06T20:14:47+08:00
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
森言森语  最初接触基因克隆和构建载体时，总会遇到这样那样的问题，构建载体作为很多实验的必须步骤，不应该成为阻挡后续实验的障碍。
 这是因为通常来说，载体构建相关的问题都过于简单，吃晚饭前花十几二十分钟就关于“正确构建载体需要格外思考的几点问题”简单写一下。
 构建载体常出现的问题  1、无法成功克隆到基因  2、基因无法成功连接至载体  3、检测质粒时发现目的基因大小不对  4、检测质粒时发现大小差不多，但测序结果不对  一般，在构建载体时，能遇到的也就这几个问题，如果有其他问题存在也大概与上述四个问题是密切相关的。
 需要说的是，如果载体构建出了状况，就不要一味的重复了，一遍不成功，十遍也绝不会对。如果出现例外，那绝对是小概率事件。
 那出现上述问题后从哪几方面思考呢？
 1、确保克隆到的基因完全正确：  如果这一步出问题，无非两点原因：引物设计不合理，模板质量不高。
 解决方法：多找几个模板同时进行克隆；重新评估引物的合理性和特异性，比如将引物长度增至40 bp左右。
 2、关于酶切  酶切其实要求并不十分严格，正常操作下，不论电泳检测是否十分清楚，酶切产物足够连接用量了，没必要纠结。
 3、关于酶切位点的选择  这一点很重要。通常很多同学在选择酶切位点时，会习惯性的选择师兄师姐们常用的酶切位点，比如BamHI等，但实际上这样是不行的。
 此时需要注意：目的基因中不能出现所选酶切位点，否则，在连接时，残留的酶会对目的基因进行切割，这将直接导致实验的失败。
 解决办法：选择酶切位点前，需要检查所选酶切位点是否存在于目的基因中。
 小结  总之，如果构建载体时出现问题，就从这几方面一一排除：  引物设计是否合理？
 酶切位点是否选择正确？
 模板质量是否较好？
 PCR程序是否设置正确？
 如果以上几点都没问题，那载体构建就不会出问题。
 最后，其实不管构建载体还是其他实验，有时做不出来，排除最本质的原因之外，如果正常操作下出现状况，  一定是哪一步做错了或者疏忽了，应该尽量避免一味的机械重复。
 还有哪些原因呢？欢迎大家在评论区留言。
