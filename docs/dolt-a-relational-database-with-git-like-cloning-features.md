# Dolt，一个具有类似 Git 克隆特性的关系数据库

> 原文：<https://thenewstack.io/dolt-a-relational-database-with-git-like-cloning-features/>

蒂姆·塞恩多年来一直想知道为什么互联网上没有一个地方可以进行数据合作。

他曾是 Snapchat 的工程副总裁，但在他探索下一步的过程中，直到 Snapchat 的 Brian Hendriks 和 T2 Aaron Son 同意加入他的团队，他们才着手解决这个问题，开发出了具有类似 Git 功能的关系数据库 T4 Dolt T5。

“我当时想，你可以租一台电脑，你可以租一个数据库，但你不能获得访问数据库中数据的权利。没有简单的方法做到这一点，”Sehn 谈到他们着手解决的问题。

“我们有点想建立一个 API 市场，有点像 [mashape 或 rapidapi](https://rapidapi.com/blog/rapidapi-and-mashape-api-marketplace-join-forces/) 。现在有了独特的分支合并功能，就像你在源代码中发现的那样，比如在 Git 中——在 API 之上进行分支合并。

“我们意识到 API 不是人们在新的数据世界中想要的。因此，我们更深入地研究了数据库本身，希望在数据库之上提供分支合并。”

## 基于 Noms 构建

[Sanjeev Sharma](https://www.linkedin.com/in/realsanjeevsharma/) ，加速策略集团的分析师[写道](https://accelst.com/the-quest-for-the-holy-grail-of-git-for-data/):

*最近，人们一直在寻找一种类似 Git 的数据解决方案。为数据开发一个类似 git 的解决方案并不是一件容易的事情。这一探索的障碍，……与数据不像代码这一事实有关。随着代码技术如 Chef、Puppet、Terraform、OpenStack HEAT 等的出现，基础设施最终能够作为代码在分支上进行版本化和管理。这是可能的，因为这些技术允许基础设施及其配置被表示为良好的代码。数据并非如此。*

Sehn、Hendriks 和 Son 在 2018 年推出了他们位于洛杉矶的公司 Liquidata。一年前，他们发布了 Dolt 开源软件。它的名字来自英国俚语，意为“白痴” [DoltHub](https://www.dolthub.com/) ，一个基于云的存储网站，用于托管 Dolt 数据库，随后于 2019 年 9 月发布。它包含公共数据集，如新冠肺炎，人口普查和按邮政编码的所得税数据。

> “如果你去 DoltHub，你会发现一堆不同的数据是开放的，免费使用的，你可以克隆它，并在不到五分钟的时间内用三个命令得到一个正常运行的 SQL 数据库”——Tim Sehn

“如果你去 DoltHub，你会发现一堆不同的数据是开放的，免费使用的，你可以克隆它，并在不到五分钟的时间里用三个命令获得一个功能正常的 SQL 数据库，而用其他[技术]做其他数据集至少需要一个小时，例如，如果你有一个 CSV，并想在数据库中获得它，”该公司的首席执行官蒂姆·塞恩说，称这是在互联网上分发 CSV，JSON 文档和 API 的更好方式。今年秋天，它将增加选举数据。

Dolt 基于 [noms](https://github.com/attic-labs/noms) 开源数据库，是前谷歌工程师 [Aaron Boodman](https://github.com/aboodman) 和 [Rafael Weinstein](https://www.linkedin.com/in/rafael-weinstein-21718?authType=NAME_SEARCH&authToken=0m7L&locale=en_US&trk=tyah&trkInfo=clickedVertical%3Amynetwork%2CclickedEntityId%3A34867%2CauthType%3ANAME_SEARCH%2Cidx%3A1-1-1%2CtarId%3A1470047040046%2Ctas%3ARafael%20Weins) 的心血结晶。他们的公司 Attic Labs 于 2018 年初被 Salesforce 收购。用 Go 编写的 Noms 允许用户在多台机器上复制数据并离线编辑，然后同步编辑内容。

几年前，我在一篇关于 Noms 的文章中指出，Noms 不是为了取代企业使用的流行数据库，而是为了更容易编写软件来消费和理解数据以及数据是如何变化的。

Dolt 版本表取代了 SQL 数据库中的版本文件。数据和模式一起被版本化。Liquidata 团队希望依靠用户对 SQL 和 GitHub 的熟悉程度来使 Dolt 易于使用。

## 使用 Merkle 树

Dolt 使用 Merkle 树架构，使用户能够在不同版本之间共享数据。

“如果你有一个 5000 万行的表，你增加了一行，我们只增加存储额外的行，以便为它提供版本控制，”Sehn 说。“在以前的技术中，你必须制作一个副本，整整 5000 万行的副本，这将非常慢。因此，这种内容寻址 Merkle 树技术使我们能够有效地做到这一点，并以 Git 允许您快速轻松地提供文件版本控制的方式，为数据库提供基本的完整版本控制。”

Dolt 用户创建一个本地存储库，其中包含可以使用 SQL 读取和更新的表。与 Git 类似，写操作将被暂存，直到用户发出提交命令，然后被发送到永久存储。对数据和模式的所有更改都存储在提交日志中。

[分支-合并语义](https://dbdb.io/db/dolt)允许表以[多个](https://www.kaggle.com/)用户的速度增长，提供数据的松散协作以及同一核心数据的多个视图。Dolt 提供了跨数据和模式的特定于表的差异和冲突检测。数据冲突是基于单元的，而不是基于行的，具有高效的 diff 计算。远程存储库允许存储库实例之间的合作。克隆、推和拉语义是可用的。

Dolt 是一个拥有自己的存储层、查询引擎和查询解析器的数据库，根据 Sehn 的说法是[。在这一点上，Dolt 不能轻易分发——数据必须放在一个硬盘上。他说，有了足够的牵引力，该团队将为大数据构建“big Dolt”。](https://news.ycombinator.com/item?id=23013215)

Dolt 使用速度优先于大小的 [Snappy](https://github.com/google/snappy) 开源压缩库将数据存储到磁盘。这意味着必须解压缩数据块来处理查询。

公共数据集在 DoltHub 上免费托管；私人存储库每月 50 美元。

[https://www.youtube.com/embed/L8DtI3BtxiU?feature=oembed](https://www.youtube.com/embed/L8DtI3BtxiU?feature=oembed)

视频

## 众多的对手

事实上，[关于黑客新闻的讨论](https://news.ycombinator.com/item?id=22731928)已经注意到了“Git for data”项目中“每月流行”的性质。

Sehn 将 GitHub 本身视为 Dolt 的主要竞争对手，尽管在一篇[博客文章](https://www.dolthub.com/blog/2020-03-06-so-you-want-git-for-data/)中，他概述了诸如[棉被](https://github.com/quiltdata/quilt)和 [qri](https://github.com/qri-io/qri) 和 [Kaggle](https://www.kaggle.com/) 等项目，以及包括[厚皮动物](https://github.com/pachyderm/pachyderm)和 [DVC](https://github.com/iterative/dvc) 在内的数据管道版本选项。

展望未来，该公司有四个重点领域，他说:

*   改进 Dolt 和 DoltHub，例如它最近在网上增加了数据查询，允许用户在 Dolt 上看到查询的 Excel 审计日志。(“能够在你的数据库中看到多达数百次的任何细胞的历史对人们来说都是非常有趣的，”他说。)
*   添加社交功能等功能，使协作变得更加容易。
*   添加功能以完全兼容 MySQL。
*   添加更多的 Git 功能，比如[rebase](https://git-scm.com/book/en/v2/Git-Branching-Rebasing)，这使得用户无需创建分支就可以查看历史或数据库。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>