# PHP 获得了在 PHP 核心上工作的基础

> 原文：<https://thenewstack.io/php-gets-a-foundation-to-work-on-php-core/>

考虑到最近发生的事情，这可能没有维基百科上关于这个想法的文章那么“黑色幽默”,但理论是一样的——你当前团队中有多少成员需要突然消失才能让你的组织或项目停止？这个数字被称为你的[总线因子](https://en.wikipedia.org/wiki/Bus_factor)，比如，多少人需要被一辆公共汽车撞了才会停止工作，今年早些时候， [PHP 贡献者 Joe Watkins](https://github.com/krakjoe) 认为[PHP 的总线因子是一个令人震惊的第二号](https://blog.krakjoe.ninja/2021/05/avoiding-busses.html)。

“也许只有两个人会在今天早上醒来，决定他们想要改变他们的生活，以便 PHP 项目缺乏专业知识和资源，以目前的形式和速度向前推进，”沃特金斯当时写道，这两个人分别是德米特里·斯托戈夫和尼基塔·波波夫。

好吧，上周，尼基塔·波波夫幸运地没有被公共汽车撞上，但是他决定离开他在 PHP 的角色，转而将他的活动集中在 LLVM 上。

同样值得庆幸的是，Watkins 今年早些时候的文章让人们对眼前的情况有了一些了解，正如他在本周的后续文章中所写的那样，JetBrains(波波夫的雇主)当时就创办 PHP 基金会一事联系了他。

本周，随着 Popov 的离开， [PHP 基金会](https://opencollective.com/phpfoundation)正式启动[目标是资助兼职/全职开发者在 2022 年从事](https://blog.jetbrains.com/phpstorm/2021/11/the-php-foundation/) [PHP 核心](https://github.com/php/php-src)的工作。

在启动时，PHP 基金会将统计 10 家公司——[automatic](https://automattic.com/)、 [Laravel](https://laravel.com/) 、 [Acquia](https://www.acquia.com/) 、 [Zend](https://www.zend.com/) 、 [Private Packagist](https://packagist.com/) 、 [Symfony](https://symfony.com/) 、 [Craft CMS](https://craftcms.com/) 、 [Tideways](https://tideways.com/) 、 [PrestaShop](https://www.prestashop.com/) 和 [JetBrains](https://www.jetbrains.com/) —除此之外，基金会正在使用基金会即服务提供商[开放集体](https://opencollective.com/)启动，将近 700 名捐助者已经为基金会筹集了超过 4 万美元。

创建一个基础而不是坚持现状的关键好处之一，不仅仅是增加总线因素——它使对 PHP 的影响多样化。Watkins 指出，在 PHP 历史的大部分时间里，Dmitry Stogov 的雇主 Zend 一直是主要的资金支持者，因此对该语言的发展方向有一定的影响。类似地，JetBrains 在 PHP 上使用 Popov 的时候也增加了影响力。

“要说他们没有影响整个语言的发展方向是不正确的。事实上，他们已经做到了:语言的许多部分及其内部结构都是由 Zend 推动形成的，这得益于 Zend 的预算和专注的工程师。“同样，在尼基塔与 JetBrains 相处的相对较短的时间里，他们也有某种影响，如果说他们没有影响，那就等于说尼基塔在受雇于 JetBrains 之前和期间的产出没有什么不同。”

虽然 Watkins 说一切都是光明正大的，并通过标准流程来确保如此，但影响力是不容置疑的，而且“这个基金会代表了一种推动语言向前发展的新途径。它为我们提供了提高公共汽车系数的机制，使我们永远不会面临我们今天面临的问题，也不会面临过去曾经面临的问题。”

该基金会以一个临时管理机构启动，成员包括波波夫、斯托戈夫和沃特金斯，JetBrains 写道， [php-src](https://github.com/php/php-src) 的任何贡献者都可以[向基金会申请](https://forms.gle/mk52v6FphaYr6yMS8)资金，申请期立即开始，持续 28 天。至于接下来会发生什么，PHP 基金会将在前两年集中精力雇佣开发人员来开发 PHP core。JetBrains 写道，当前的 RFC 过程“不会改变，语言决策将永远留给 PHP 内部社区。”

## 本周的节目中

*   **。随着亚马逊的 [re:Invent 2021](https://reinvent.awsevents.com/) 大会将于下周召开，该公司已经发布了几份活动指南，我们认为这一周可能值得一提。首先，有很多关于。NET 最近，与[最近。NET 6 发布](https://thenewstack.io/visual-studio-2022-and-net-6-finally-arrive/)，AWS 写了一篇关于所有事情的博文[。NET at re:Invent 2021](https://aws.amazon.com/blogs/developer/net-at-reinvent-2021/) 。该帖子列出了将对现场和虚拟与会者开放的各种分组会议，如“的新功能。NET 在 AWS 上的开发和部署”和“构建高性能。NET AWS 上的无服务器架构”以及其他几篇文章。与此同时，在 re:Invent 2021 上的 [AWS 开源与会者指南采用了类似的方法，并列出了各种关于开源的分组会议，例如“GraphQL 简介”或“使用 Rust 将环境影响降至最低”。面对面的活动从 11 月 29 日持续到 12 月 3 日，但虚拟活动将持续一周，直到 12 月 10 日，并且完全免费参加。](https://aws.amazon.com/blogs/opensource/aws-attendee-guide-for-open-source-at-reinvent-2021/)**

*   **亚马逊预览亚马逊 Linux 2022:** 亚马逊已经[预览了](https://aws.amazon.com/about-aws/whats-new/2021/11/preview-amazon-linux-2022/)一个新的通用 Linux 发行版，名为[亚马逊 Linux 2022 (AL2022)](https://aws.amazon.com/linux/amazon-linux-2022/) ，它说它“旨在提供一个安全、稳定和高性能的执行环境来开发和运行你的云应用程序。”该公司承诺每两年提供一个新的主要版本，并在随后的五年内提供支持，每季度更新一次最新软件——尽管如何更新将完全取决于您。目前，亚马逊用户可以在亚马逊 Linux 1 和亚马逊 Linux 2 之间进行选择，但 AL2022 将结合它们的优势，同时提供“可预测的两年发布周期，因此客户可以计划将操作系统升级作为其产品生命周期的一部分。”AL2022 基于上游 Fedora，默认情况下启用并强制执行 SELinux，现在可以在预览版中免费获得。前往[文档](https://docs.aws.amazon.com/linux/al2022/ug/)获取更多信息。
*   **如果你仍然对 Docker 业务感到困惑:**到目前为止，你已经听说了所有关于 [Docker 对其费用结构](https://thenewstack.io/docker-defends-desktop-pricing-says-support-led-to-faster-features/)的改变，特别是关于 Docker Desktop，但是你可能仍然有一些问题。Docker 最近举办了一个[网络研讨会](https://www.docker.com/events/webinars/management-security-at-scale-docker-business)，留下了一些问题，现在已经发布了一篇博客文章[来回答你剩余的 Docker 业务问题](https://www.docker.com/blog/your-docker-business-questions-answered/)。例如，你需要为 Docker 桌面付费吗？即使不用 Docker 桌面 UI？在 2022 年 1 月 31 日之前你必须做什么？点击查看这些问题的答案，或者查看 [Docker 订阅备忘单](https://www.docker.com/sites/default/files/d8/2021-11/Docker__Which_Subscription_Is_Right_For_You_111721_V5.pdf?utm_campaign=2021-11-16-pricing-cheat-sheet&utm_medium=blog&utm_source=cheat-sheet)或[常见问题解答](https://www.docker.com/pricing/faq)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>