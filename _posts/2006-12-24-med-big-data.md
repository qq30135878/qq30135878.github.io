---
layout: post
title:  "《医疗大数据》读后感"
subtitle: "MED BIG DATA"
author: "张斌"
avatar: "authors/bin.png"
---

# 引用

* 疾病 ，是生物在一定原因的损害性作用下 ，因自稳调节紊乱而发生的异常生命活动过程 。多数是机体对病因所引起的损害发生一系列抗损害反应 ，表现为机能 、代谢和形态结构的异常变化 ，从而导致体力减弱甚至环境适应能力丧失 。

* 万维网联盟 （ W o r l d W i d e W e b C o n s o r t i u m ， W 3 C ）对前人提出的本体建设原则进行了改进 ，提出了 5条推荐标准 ，本体的构建应遵循以下原则 。（ 1 ）清晰本体必须有效地说明所定义术语的意思 ，定义应该是客观的 ，与背景独立的 ，当定义以一阶逻辑公理表达时 ，它应该是形式化的 ，定义应该尽可能地完整 ，所有定义应该用自然语言加以说明 。 （ 2 ）一致本体应该是一致的 ，也就是说 ，它应该支持与其定义相一致的推理 ，它所定义的公理以及用自然语言进行说明的文档都应该是具有一致性 。 （ 3 ）可扩展性本体应该为可预料到的任务提供概念基础 ，它应该可以支持在已有概念基础上定义新的术语 ，以满足特殊的需求 ，而无需修改已有的概念定义 。 （ 4 ）编码偏好程度最小概念的描述不应该依赖于某一种特殊的符号层表示方法 ，因为实际系统可能采用不同的知识表示方法 。 （ 5 ）约束最小本体约束应该最小 ，只要能够满足特定的知识共享需求即可 ，这可以通过定义约束最弱的公理以及只定义通信所需的词汇来保证 。根据这五条本体构建的原则 ，并结合基于本体的知识构建系统的需要 ，可以按照以下七个步骤来构建医疗本体 。（ 1 ）第一步 ：列出领域内的重要术语对各个医学系统的数据源进行数据结构 、数据语义的分析 ，列出一份医疗领域所有术语的清单 ，清单中的术语是需要解释给用户的 。这份清单的要求是要囊括医疗领域的全部术语 ，暂时先不考虑概念间会有属性及表达上的重复 。接下来确定领域的概念的同时 ，还有两个重要步骤是完善等级体系和定义概念属性 ，这是两个密不可分 、相互交织的步骤 。两者必须同时进行 ，这两个步骤在本体的设计进程中最为重要 。 （ 2 ）第二步 ：定义领域的概念将列出的术语清单中的术语分成若干组 ，使得语义接近的聚在一起 ，同时标注这些术语是概念类 、属性类还是实例类 。 （ 3 ）第三步 ：定义概念的层次建立概念的层次体系有很多种方法 ，主要的是自顶向下法 、自底向上法和中间扩展法 。自顶向下法的主要思想是 ：先由领域专家根据领域知识建立一个顶层的领域本体 ，然后以此领域本体为基础 ，从领域中提取其他概念及概念间的关系 ，并且将这些概念和概念间的关系依次添加到领域本体的相应概念下面 。此过程不断循环 ，最后形成一个比较完善的本体 。自底向上方法的主要思想是 ：由已有的小规模本体 ，通过计算概念相似度的方式 ，进行本体之间的合成 。依次进行 ，最终由多个小规模本体合成为一个大规模的本体 。中间扩展法的主要思想是 ：先由领域专家根据领域分析 ，从领域中获取部分概念和关系 ，建立一个本体雏形 。然后从这个本体雏形开始 ，将领域中的其他概念不断扩充到该本体雏形中 ，其扩充方式可以向上扩展 ，也可以向下扩展 ，直至最后构建出比较完善的本体模型 。本体库开发时采用哪种方法主要依赖于开发者对需求专业领域的理解程度 。如果开发者对该专业领域具有一套自上而下的系统的认识 ，那么采用自顶向下的方法就会很有帮助 。由于 “中层概念 ”在领域的概念中应该更具代表性 ，所以中间扩展法对许多本体的开发者而言最便捷 。如果想要收集到更多的更广泛的实例 ，那么自底向上的方法更加适合 。无论选择哪种方法 ，都要从 “类 ”的定义开始 。（ 4 ）第四步 ：确定概念之间的关系领域本体是对领域内的概念的一种形式化描述 ，这就需要一方面考虑概念的语义 ，另一方面要考虑概念之间存在的关系 。从语义上分析 ，实例表示的就是对象 ，而概念表示的则是对象的集合 ，关系对应于对象元组的集合 。概念的定义一般采用框架结构 ，包括概念的名称 ，与其他概念之间的关系的集合 ，以及自然语言对该概念的描述 。在医疗本体库会用到的关系主要有继承关系 ，部分与整体关系 ，某个概念是另一个概念的属性 ，以及同义关系等 。（ 5 ）第五步 ：本体编码选择合适的语言表达概念和术语 。 （ 6 ）第六步 ：评估根据需求描述 、能力询问等对本体以及软件环境 、相关文档进行评价 。（ 7 ）第七步 ：本体的建立对所有本体按第六步中的标准进行检验 ，符合要求的以文件的形式存放 ，否则转回第二步 ，如此循环往复 ，直至对所有步骤的检验结果均达到要求为止 。
