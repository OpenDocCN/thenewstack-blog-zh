# 数据是新的堆栈

> 原文：<https://thenewstack.io/data-is-the-new-stack/>

据广泛报道，现代企业正在收集大量数据。显然，这些企业需要有人来处理所有这些事情。

有如此多的标题预示着数据科学家是我们这个时代最令人垂涎的工作，软件开发人员认为争论大数据的负担属于并且只属于拥有这一职位的神秘和罕见的个人是情有可原的。事实上，在未来十年中，管理和操作数据将成为每个软件开发人员工作的一个中心方面。

原因很简单:数据*是新的堆栈，或者至少是它的基础。*

以下是新堆栈中以数据为中心的世界与以前的技术时代的一些不同之处，以及开发人员需要做的一些事情。

> 数据定义了新世界中的应用

在过去，人们通常认为应用程序“拥有数据”应用程序开发人员和架构师面临的主要挑战之一是确定格式化和存储应用程序数据的最佳方式。在应用程序之间共享数据通常是事后的想法，并且需要昂贵的“企业应用程序集成”工作，或者最近开发的一次性 API。

在新的世界里，我们将会把这个想法视为离奇古怪。数据将存储在企业范围内的数据存储库中(一个数据仓库，或者“[数据湖](http://www.forbes.com/sites/edddumbill/2014/01/14/the-data-lake-dream/)，如果你喜欢的话)，在一个像 HDFS 这样的系统中，所有的企业应用程序将在需要时访问这个存储库。

对于开发人员来说，处理各种数据类型和格式的能力将是关键，与传统的结构化数据类型相比，处理非结构化数据的舒适性尤其重要。

> 应用程序转向数据，而不是相反

在过去，最小化延迟的关键策略是通过缓存、复制和其他方式将数据越来越靠近应用程序。当数据量很小时，这种策略非常有效。新的堆栈思维颠覆了这种想法，这在很大程度上是因为移动大量数据的高成本。在新的世界中，应用程序处理被移至尽可能靠近数据的地方，这一概念被称为“数据局部性”

第一个真正大规模利用数据局部性的系统是 Hadoop，开发人员需要围绕一种新的计算范式 MapReduce 来完成这项工作。最近， [Hadoop YARN](http://hortonworks.com/hadoop/yarn/) 的出现允许围绕替代编程模型构建的应用和工具在本地访问基于 Hadoop 的数据。掌握一个提供数据局部性的框架，无论是 MapReduce 还是其他，对于开发人员构建新的应用程序都是很重要的。

> 数学不再仅仅是游戏开发者和定量分析师的专利

在许多情况下，充分利用所有这些数据将需要一些数学和统计技能，而旧世界并不需要大多数开发人员，至少不需要游戏、研究或金融领域的开发人员。

[机器学习平台](https://www.cloudpulsestrat.com/posts/machine-learning-platforms-predictive-applications-part-2-machine-learning-platform)和统计库将承担大部分最繁重的工作，但正如开发人员理解 SQL 以充分利用 ORM 库很重要一样，他们也有责任研究一些底层统计数据，以便有效地交付依赖这些工具的新世界应用程序和系统。

虽然拥抱大数据对开发人员来说意味着巨大的变化，但它也提供了许多巨大的机会。作为开发人员，现在是磨利锯子的最好时机，因为[自由软件](https://github.com/)、[自由课程](https://www.udacity.com/)和[几乎免费的计算](http://aws.amazon.com/)环境遍布每个角落。

Sam Charrington 是 CloudPulse Strategies 的负责人，这是一家专注于云计算、大数据以及相关技术和市场的分析和咨询公司。可以在 Twitter 上关注他，地址是 [@samcharrington](https://twitter.com/samcharrington) 。

图片由 [JD Hancock](https://www.flickr.com/photos/jdhancock/8031897271/in/photolist-deKzer-7K6TWX-6UDnWP-7PMpXT-nX546-9rnTdL-6GiYkV-bf2wtK-bf2wpa-9uDrJR-i3NECz-9fLRVv-688e4k-gdMuhT-ax8z4B-8Lsgfn-7GaoYw-5NfuQU-92kp1F-22CjS2-o94Cj-6EMnyQ-i3Rby3-fY9CgE-7R6usE-FMVAH-5hrCbv-ekYLQy-4nWCrn-9U1s1d-8LCNW2-6EHcWT-gdMrKi-bf2wDV-egsmCb-dRuMzt-hypmYn-amkoeY-h4RV3y-5BK5qi-5cwAAc-hyq3Zy-i3NEbc-8Z9pht-dL8cys-fkKdFR-2dkp-kk3mZ-7fr163-7n3E7Y)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>