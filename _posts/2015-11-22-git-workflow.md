---
layout: post
title:  "Git更好，不过需要工作流"
subtitle: "The better tools, the better work!"
author: "张斌"
avatar: "authors/bin.png"
image: "git-workflow/git-workflow-cover.jpg"
date:   2015-11-22 23:01:12
---

### 前言
最近接手负责了[聪头](http://icongtou.com)项目，发现代码还在使用svn管理，为了更好的进行开发迭代，我强烈要求使用git来管理项目，所以最近把所有项目都已经迁移到git，托管在github。至于git和svn的比较我就不做赘述了，总之git比较svn还是有优势的。但是我想说一下为什么我们要不遗余力选用先进的工具，根据[黑客与画家](http://www.amazon.cn/%E9%BB%91%E5%AE%A2%E4%B8%8E%E7%94%BB%E5%AE%B6-%E7%A1%85%E8%B0%B7%E5%88%9B%E4%B8%9A%E4%B9%8B%E7%88%B6Paul-Graham%E6%96%87%E9%9B%86-Paul-Graham/dp/B00ALPRKH0/ref=sr_1_1_twi_kin_2?ie=UTF8&qid=1448270401&sr=8-1&keywords=%E9%BB%91%E5%AE%A2%E4%B8%8E%E7%94%BB%E5%AE%B6)作者所述，先进的工具可以让团队立于不败或者说占尽先机。这是非常有道理的，互联网到处都是聪明又勤奋的人，在相同努力（花一样的时间精力）的情况下，辅助（工具）是脱颖而出的唯一途径。不怕竞争对手强大，就怕强大，又勤奋，再使用先进工具的对手，这样的对手很难超越。所以我平时会花一定的时间研究技术趋势和先进框架，工具等。好了说了这么多题外话，我们言归正传说说git workflow。

### 正题
结合我们自己的情况，统一了git workflow，目前团队都使用该工作流进行开发迭代，争取做到忙中不出错。

#### master和develop
首先每个repo有两个基本的branch，master和develop，这两个分支是稳定长期存在的。

* master：用来最终上线的分支，该分支是比较神圣的，不能轻易做合并，做合并后必然产生版本号和tag。
* develop：用来开发的分支，比较弹性，最后的功能都需要汇总到develop分支。

#### feature，fix，improve和release
其次是feature，fix，improve，release分支，这些分支是从develop分岔的，临时的，合并后就能删除。分支用这些单词开头，后跟中划线－，名字需要有意义，不能是feature-1，feature-2这样无意义的命名。

* feature：开发新功能的分支，从develop分岔出来。
* fix：修复不是太紧急的bug，一般针对已经线上的功能缺陷，也是从develop分岔。
* improve：用于改进代码，重构，优化数据结构，排版等，功能不发生变化，用户也察觉不到变化，应该理解为纯粹程序员级别的修改。
* release：上线前，决定哪些branch需要合并，例如feature-x，fix-a，improve-b等，然后定一个版本号，比如2.2.0，最后给这个branch命名为release-2.2.0，合并好后就不应该再次改动被合并的分支(或者干脆删掉被合并的分支)。release-2.2.0分支为上线前做准备，进行修改，测试，全部完毕后合并到master上线产生版本号并且打tag。别忘了还是需要合并回develop分支。

#### hotfix
* hotfix分支，用于发布紧急版本，其实就是紧急修复bug，唯一从master分岔出来的branch，修复完，合并到master产生版本号打上tag，我们规定用版本号第三位表示，比如：2.2.1。这样也方便以后统计每个版本迭代有多少hotfix，hotfix是越少越好，是没办法的情况下才进行的。也是需要合并回develop分支。

#### 总结
* 从master分岔的分支有：hotfix，develop（也可以在master没有的时候就创建起来，就看你怎么理解了）
* 从develop分岔的分支有：feature，fix，improve，release。
* 被master合并后又需要被develop合并的有：release，hotfix。
* master神圣不可侵犯，一旦合并到master，就产生版本，打tag。


这张图片很好的诠释了git workflow

![git workflow](./content/images/git-workflow/git-workflow.jpg)


***PS：以上规定是针对我们自己公司的自己项目制定的，不是教条式一成不变的，请根据自己的项目进行调整。***

深入阅读与参考：

[Atlassian Git Workflow](https://www.atlassian.com/git)

[Nvie's Post](http://nvie.com/posts/a-successful-git-branching-model)
