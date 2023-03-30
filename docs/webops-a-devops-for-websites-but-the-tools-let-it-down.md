# WebOps:网站开发工具，但是工具让它失望了

> 原文：<https://thenewstack.io/webops-a-devops-for-websites-but-the-tools-let-it-down/>

WebOps 是“web”和“operations”的结合体，乍一看，它似乎是 DevOps 的近亲。顾名思义，WebOps 专注于网站和 web 应用的部署和运营。这个术语至少从 2006 年的[开始就已经存在了，当时它的](https://en.wikipedia.org/w/index.php?title=Web_operations&oldid=73050269)[维基百科文章](https://en.wikipedia.org/wiki/Web_operations)首次发表(事实上，那个页面比维基百科上的 DevOps 文章更老，后者首次发表于[2010 年](https://en.wikipedia.org/w/index.php?title=DevOps&oldid=364345787))。然而，当我搜索我的 Twitter 时间轴时，自 2020 年以来，我关注的人没有提到过“网络行动”。

那么，到底发生了什么——网络运营到底是不是一种真正的趋势？为了找到答案，我采访了 [Pantheon](https://pantheon.io/) 的联合创始人兼首席战略官 Josh Koenig ，这是一家利用“网络运营”进行营销的公司。这个词在 Pantheon 的主页上被多次列出，它的[定义文章](https://pantheon.io/webops)目前在谷歌搜索中排名第一，它也在 Twitter 搜索结果中占据主导地位。

## 内容管理 SaaS

Pantheon 是一家网站管理公司，成立于 2010 年。它最初是作为一种“软件即服务”来管理 Drupal 网站的。当它于 2011 年 9 月[向公众发布](https://techcrunch.com/2011/09/30/pantheon/)时，它被 TechCrunch 描述为“Drupal 站点的英雄，因为它将 web 开发环境放在了云中。”Pantheon 最终也扩展到为 WordPress 网站提供云服务。

“我们仍然是相同的核心产品，相同的核心价值主张，今天和那时一样——我们称之为网站运营平台，”柯尼希告诉我。“你可以把 WebOps 看作是将 DevOps 和现代软件开发中所有成熟的经验应用到相当复杂的 web 用例中。具有讽刺意味的是，DevOps 诞生于早期大规模 web 实践者的经验，但通常不用于网站。

DevOps 和 WebOps 的主要区别在于，后者涉及内容管理，这通常意味着营销人员是该流程的一部分。这恰好是我深有体会的事情，尽管我从未使用过“网络运营”这个词。我告诉 Koenig，在 2000 年代的最初几年，我曾经是一名“网络经理”，当时公司不知道应该把我安排在 IT 部门还是营销部门(声明一下，我最终进入了营销部门，但在休息和午餐时间与 IT 团队混在一起！).

## 比较 WebOps 和 DevOps

像 DevOps 一样，WebOps 支持诸如版本控制和 CI/CD(持续集成和交付或部署)之类的东西。但是，柯尼希说，它把它应用于“更窄的网络技术空间[……]和更深层次的利益相关者。”因此 WebOps 的工作流程中包含了网页设计师和内容创作者。

从 IT 角度来看，网络运营通常是如何管理的？根据 Koenig 的说法，这取决于 it 部门和营销部门之间的关系。

他说，在某些情况下，营销部门“专门拨出预算来支付技术上属于 IT 部门，但致力于营销技术需求的开发人员。”但在其他情况下，他看到了“真正强大的中央 IT 组织”,在这些组织中，IT 处于领先地位，在这些情况下，他们倾向于利用现有的 DevOps 团队和实践。

在 DevOps 中，CI/CD 是工作流的一个常见部分。我问 WebOps 是否也是这种情况，如果是，CI/CD 在 web 环境中如何工作？

Koenig 回答说，对于静态网站，测试是在构建期间完成的(通常是在内容更新之后)。“更具挑战性的情况是人们有内容管理，”他说，“所以你有一个运行你的实时网站的软件，它连接到一个数据库，它有一些二进制资产，图像，pdf，等等。因此，有人在生产中使用它来发布新内容，但你也希望能够进行设计更改并添加功能。”

Koenig 继续说道，Pantheon 开发的 CI/CD 工作流可以让公司“将实时内容的当前状态与预生产应用环境同步，并确保这两个环境的所有方面都相同。”

这听起来与公司内容管理系统一直以来所做的并没有什么不同。在 21 世纪初，我使用了 Interwoven 的一个相当庞大的 CMS，名为 TeamSite，它的功能和 Koenig 描述的差不多(保持开发和生产环境的分离和同步)。这是在 CI/CD 一词被创造出来的许多年前。所以从某些方面来说，WebOps 似乎只是一个时髦的术语，指的是网站内容管理中的一个长期熟悉的过程。

## 无头 CMS 难题

在过去的二十年里，发生了明显变化的是现代网站构建和部署过程的复杂性。像 [Jamstack](https://thenewstack.io/why-netlify-is-tech-agnostic-and-its-role-in-jamstack-development/) 和“[无头 CMS](https://thenewstack.io/why-decoupled-architectures-now-make-sense-for-wordpress/) 这样的当前趋势给了 IT 团队更多的权力，但代价是增加了复杂性。例如，无头 CMS 是在 CMS 之外管理表示和发布方面(前端，或“头”)。营销团队通常使用无头 CMS 来输入他们的内容，而演示和发布则由 WebOps 团队单独管理。

原来柯尼希对无头 CMS 的状态有意见。在最近[的一篇题为“我对无头内容管理系统的误解”的文章](https://www.forbes.com/sites/forbestechcouncil/2022/06/17/what-i-got-wrong-about-the-headless-cms/?sh=1adca5882535)中，柯尼希写道，虽然他帮助推广了无头内容管理系统的趋势，但他(和整个行业)过于关注后端而不是前端。我想他的意思是，headless CMS 产品有着糟糕的用户界面的名声，而像 Google Docs 这样的现代网络应用程序更容易使用，功能也更好。因此，具有讽刺意味的是，无头 CMS 产品让内容创作者的用户体验(前端)变得更糟。

除此之外，Koenig 告诉我，无头 CMS 的趋势“在许多情况下使得对 WebOps 的需求更加清晰，因为其中涉及到编排。”换句话说，至少有“两个独立的软件需要集成——前端和后端。”他说，这就是 Pantheon 及其 WebOps 方法的用武之地，因为它提供了结构化的工作流程和更多的自动化。

## 结论

我毫不怀疑 DevOps 方法对 web 内容管理有很多潜在的好处，特别是在 IT 部门的后端。但在与 Koenig 交谈后，我意识到有许多不同的方法来实现网站的这种方法。所以我还是不清楚网络行动到底是什么。IT 和营销之间的过程似乎很大程度上取决于所使用的 CMS 工具。

说到这里，我认为近年来内容管理工具的问题过于复杂——尤其是无头内容管理系统在前端做得不够好。开发人员和操作人员可能在解耦系统(Jamstack 或 headless CMS)中过得更好，但是可怜的老营销人员却在苦苦挣扎。无论 WebOps 是什么，它都需要为最终用户做得更好。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>