# MongoDB 从关系系统迁移数据的新工具

> 原文：<https://thenewstack.io/mongodbs-new-tool-to-move-data-from-relational-systems/>

MongoDB 非常希望将数据从关系数据库转移到它的文档存储中。

为了让它变得真正简单，该公司发布了 [Relational Migrator](https://www.mongodb.com/products/relational-migrator#:~:text=MongoDB%20Relational%20Migrator%20is%20a,the%20relational%20database%20to%20MongoDB.) ，这是上周在 MongoDB World 2022 上推出的许多新产品之一。

[MongoDB](https://www.mongodb.com/cloud/atlas/register?utm_content=rlsapostreg&utm_source=google&utm_campaign=gs_americas_uscan_search_brand_dsa_atlas_desktop_rlsa_postreg&utm_term=&utm_medium=cpc_paid_search&utm_ad=&utm_ad_campaign_id=14383025495&adgroup=129270225274&gclid=CjwKCAjw46CVBhB1EiwAgy6M4s_4nB3SSyeDgGWOf3G7GYMacWHW5mZDT4LZrje93OawD_kKRujXSBoCiJAQAvD_BwE) 的新关系迁移器是一个工具，它将关系模式转换为非关系模式，并允许用户分析其原始模式，决定如何将模式表示为 MongoDB 模式，并将数据从关系数据库迁移到 MongoDB。

“还有其他工具可以将数据从一个地方转移到另一个地方。MongoDB Relational Migrator 的产品经理[汤姆·霍兰德尔](https://www.linkedin.com/in/tomholl/)在接受新堆栈采访时说:“关系迁移器的独特之处在于，将关系模式转换为文档模式的问题不是其他任何人关注的问题。

Relational Migrator 深入挖掘了关系数据库和非关系数据库之间的哲学差异，并弥合了这两个世界之间的差距。

## **为什么是这样，为什么是现在？**

“客户倾向于为新应用程序选择 MongoDB，但这些客户也有一个相当大的数据存储，并且它几乎总是倾向于一个关系数据库，”Hollander 说，并补充说，“很容易找到一个体验过 MongoDB 并喜欢它的客户，但也在使用一些 Oracle 和 SQL Server，但在敏捷性或成本方面不太好。”

正如 Hollander 所解释的那样，关系迁移器的用例变化很大，“一些客户希望更改最少的代码，以使他们脱离关系数据库，但通常情况下，这些应用程序实际上已经寿终正寝，因此不仅仅是数据库需要现代化。”

因为数据库支持一个或多个应用程序，所以迁移不仅需要考虑模式和数据库本身，还需要将更大的应用程序(应用程序)作为一个整体来考虑，这往往会使这个过程更加复杂。

除了模式转换之外，还创建了该工具来展示可能性，并减轻客户在考虑现代化和从关系数据库切换到非关系数据库时的恐惧。由于不熟悉的领域和与任何数据丢失相关的后果，用户将完全放弃现代化。

关系迁移器并不能解决所有问题，但它确实应对了“我的数据会发生什么变化？”正如霍兰德所说。关系迁移器向客户表明，“您的数据不会丢失。他说，你的数据不会被迫停留在同一个模式中，“尽管那些相同的客户仍将不得不考虑其他严峻的挑战。

## **工程团队及其面临的挑战**

虽然 MongoDB 想解决将关系数据库转换为 MongoDB 的负担已经有一段时间了，但在 MongoDB 首席技术官[马克·波特](https://www.linkedin.com/in/marklovestech/)于 2020 年加入 MongoDB 后，该项目才真正起飞。

总部位于澳大利亚悉尼的 Relational Migrator 团队最初只有一个人——汤姆·霍兰德尔。最初，Hollander 不确定这将是一种工程工具、一种伙伴关系还是一种收购。在确定该工具不存在并且需要被构建之前，花费了数月的研究。

团队二号成员，[马克·别列兹尼茨基](https://www.linkedin.com/in/mark-bereznitsky/)，工程主管，大约 12 个月前加入。虽然直到几个月后更多的团队成员加入进来，才编写了很多代码，但是进行了大量的计划、白板和文档编写。这个团队已经发展到总共九个人，包括一个项目经理，一个设计师，和六个工程师，另一个工程师很快就要开始了。大部分工程工作已经在过去六个月内完成。

至于该团队迄今为止面临和克服的一些具体技术挑战，MongoDB 前端工程师 [Lavender Chan](https://www.linkedin.com/in/%F0%9F%8C%BC-lavender-c-10b215b6/) 分享道:“我们面临的一些最大的技术挑战无疑是围绕性能。使用 Relational Migrator，您可以与拥有一个或多个数据库以及这些数据库中的表的客户打交道。”

前端团队确实进行了大量研究，以决定哪些技术最适合在屏幕上直观地显示数据。在关系迁移器的性能降低之前，我们做了大量的测试来确定屏幕上可以显示多少个表。

关于后端特定的技术挑战，由于这是数据迁移，这些挑战主要集中在保留数据上，而不是损坏或丢失文件。

Hollander 解释了所需的解决方案，“硬计算机科学问题，特别是当你考虑到网络不可靠，机器可能会停机，消息可能会无序到达，后端的性能必须是可接受的。”

总的来说，该团队对解决技术挑战的方式和他们推出的 MVP 感到满意，但没有人假装旅程已经结束，因为 Hollander 兴奋地说，“当我们开始考虑连续复制时，会有一波全新的挑战。”

例如，连续复制是管道中的一个新特性，它将在源数据库更新时更新迁移的数据库。目前没有连续复制的发布日期。连续复制只是关系迁移器的众多新功能之一。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>