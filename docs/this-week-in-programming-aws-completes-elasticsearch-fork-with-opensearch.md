# 本周编程:AWS 用 OpenSearch 完成 Elasticsearch Fork

> 原文：<https://thenewstack.io/this-week-in-programming-aws-completes-elasticsearch-fork-with-opensearch/>

本周，[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention) (AWS) [推出了 OpenSearch 项目](https://aws.amazon.com/blogs/opensource/introducing-opensearch/)，提供它所说的[一个社区驱动的、开源的 Elasticsearch 和 Kibana](https://aws.amazon.com/blogs/opensource/stepping-up-for-a-truly-open-source-elasticsearch/) 分支。我不敢说这是我们多年来一直关注的故事的最后一章。

今年早些时候，AWS 发现自己处于令人惊讶的地位[突然被誉为开源救星](https://thenewstack.io/this-week-in-programming-elasticsearch-turns-aws-into-the-open-source-champion/)，而此前它曾被[妖魔化为互联网恶霸](https://thenewstack.io/what-the-fork-amazon/)。这有点反复，但要点是这样的:AWS 之前提供了 ElasticSearch 作为付费服务，开源软件的最初创建者 [Elastic](https://www.elastic.co/) 对此有异议。在这一事件中，大部分互联网站在了 Elastic 一边，认为他们被大而坏的 AWS 利用了。毕竟，谁能与 AWS 这样的互联网巨头竞争呢？

然而，今年 1 月，当 Elastic 认为[已经受够了](https://www.elastic.co/blog/why-license-change-AWS)，将 Elasticsearch 和 Kibana 的许可证从 Apache 2.0 更改为一个双重许可证，在[服务器端公共许可证(SSPL)](https://www.mongodb.com/licensing/server-side-public-license) 和[弹性许可证](https://github.com/elastic/elasticsearch/blob/0d8aa7527e242fbda9d84867ab8bc955758eebce/licenses/ELASTIC-LICENSE.txt)下。这两个许可证都涉及到对软件使用的限制，很多东西，比如开源倡议，[对](https://opensource.org/node/1099)有异议，正如我们当时[详述的](https://thenewstack.io/this-week-in-programming-elasticsearch-turns-aws-into-the-open-source-champion/)。

现在，随着本周 OpenSearch 项目的宣布，一切都在 Apache 许可证 2.0 版(ALv2)下作为开源提供。该项目包括 [OpenSearch](https://github.com/opensearch-project/OpenSearch) (源自 Elasticsearch 7.10.2)和 [OpenSearch Dashboards](https://github.com/opensearch-project/OpenSearch-Dashboards) (源自 Kibana 7.10.2)，以及 Elasticsearch 的开放发行版，AWS 之前的 Elasticsearch 发行版。该公司在公告中写道，要让代码库达到这一步，“需要大量工作来删除弹性商业许可功能、代码和品牌，”但现在将提供“一个每个人都可以建立和创新的基础。”尽管如此，他们表示，这种代码应该在 alpha 中考虑，beta 预计将在未来几周内推出，预计将于 2021 年年中投入生产。

现在，虽然这一切听起来很好，但对于那些想辩论这一举措内在优点(或缺乏优点)的人来说，有一点小小的争议:商标。

AWS 写道，它已经“发布了对 [OpenSearch 商标](https://opensearch.org/trademark-usage.html)的许可使用指南，因此你可以使用这个名称来推广你的产品”，而微软 Java 负责人 [Bruno Borges](https://www.linkedin.com/in/brunocborges) 认为商标限制使得 OpenSearch 没有完全开放。在这一点上，AWS 工程师 Matthew Wilson 认为，OpenSearch 的商标限制远远少于其他一些产品，只是简单地定义了哪些衍生作品可以被称为，而不是它们是否可以被创建和分发。Wilson 在他的论点中指出了一个指导原则[,宣称“分叉和分发是受欢迎的”](https://discuss.opendistrocommunity.dev/t/guiding-principles-for-the-forks-of-elasticsearch-and-kibana/5290/20)

“虽然这个项目的目标是生产可直接用于广大用户的高质量软件，但它的另一个目标是生产用于构建产品和服务的多样化软件供应链的一个共享组件。鼓励这种努力“下游”的创新和创造价值，以及“[上游优先](https://www.redhat.com/en/blog/what-open-source-upstream)”的合作，以实现普遍有用的创新。我们采用开放的、非歧视性的政策，使下游能够以“分发”模式消费由此产生的软件，以正确识别其来源，并使用通用名称销售产品。我们要求 forks 重新命名他们的工作以避免混淆，我们避免引入人为的障碍来这样做。对于从根本上不同意某项决策的人来说，退出应该永远是一个选择。”

至于 Elastic，据我们所知，对 AWS 的最新举措保持沉默。

## 本周的节目中

*   **FSF 的荒唐传奇& RMS:** 几周前，我们带着[简单看了一下](https://thenewstack.io/this-week-in-programming-free-software-cant-exist-without-richard-stallman/)对[理查德·M·斯托曼(RMS)](https://en.wikipedia.org/wiki/Richard_Stallman) 回归[自由软件基金会(FSF)](https://www.fsf.org/) 的反应。从那以后，一些知名人士和大的资金来源通过抵制和收回这些资金来源，加入了将 RMS 赶出 FSF 的运动。然后，在上周，FSF 董事会和 RMS 本人都发表了声明，并对整个磨难表示了一点歉意，这让互联网更加紧张。无论哪种方式，如果你没有跟上或者不完全确定正在发生什么和什么处于危险之中， [Jennifer Riggins](https://thenewstack.io/author/jennifer-riggins/) 本周在 New Stack 这里写了一篇文章，深入探讨了[为什么(几乎)每个人都希望理查德·斯托尔曼取消](https://thenewstack.io/why-almost-everyone-wants-richard-stallman-cancelled/)，这当然值得一读。它不仅着眼于戏剧本身的细节，还着眼于开源世界及其缺乏多样性和包容性的更大问题。
*   **Perl 的“持续欺凌和敌意链”:**当我们谈论开源社区中的不当行为及其反应时，本周还有另一个故事涉及 Perl 核心社区中的一些“欺凌”。 [Sawyer X](https://github.com/xsawyerx) ，一个 Perl 开发者和 [Perl 指导委员会](https://github.com/Perl/perl5/wiki/Perl-Steering-Committee) (PSC)的成员，本周说他“[从 PSC 和 Core 辞职，立即生效](https://perl.topicbox.com/groups/perl-core/T7a4f1bf9e069641f)”，在他“敢于说 Core 的人认识到语言中有 cruft”之后，他说这被用作“这个社区中一些人抨击我的又一个机会。”Sawyer X 说，他立即收到了敌意消息，这种折磨“只是我近年来(尤其是去年)从 Perl 社区成员那里收到的一系列持续欺凌和敌意中的一个例子”，导致他决定辞职。“请记住，仅仅因为一个人担任公共角色，并不意味着另一个人可以贬低、骚扰、公开羞辱或欺负他们，”他写道。“你赢了。我不干了。”要了解更多关于迁移的背景知识，请前往 [The Register 关于 Perl 社区中待办事项的文章](https://www.theregister.com/2021/04/13/perl_dev_quits/)，该文章探讨了这种情况的来源，以及对于一种已经在努力寻找前进道路的语言来说，这意味着什么。

*   **Docker 桌面的苹果 M1 芯片支持正式上市:**去年年底， [Docker 在其 Docker 桌面应用程序中预览了对苹果 M1 芯片的支持](https://thenewstack.io/this-week-in-programming-docker-previews-desktop-for-mac-m1/)，现在该公司表示该功能现已普遍可用。该公司表示，在“近 45，000 次安装技术预览版”后，开发人员发现预览版“更快、更安静，也更容易启动和运行。”有了这种额外的支持，该公司宣传了对 ARM 和 x86 架构的支持，他们说，开发人员现在可以“在 ARM 架构上端到端地构建和运行，从 Macs 上的 Docker 桌面到基于 ARM 的云服务器，如 AWS Graviton 2。”我们知道，对于那些拥有高速新 M1 芯片组的人来说，这是一个期待已久的功能，所以[开始吧！](https://hub.docker.com/editions/community/docker-ce-desktop-mac)
*   **GitHub 在你附近的命令行界面中的动作:** GitHub 本周宣布，你现在可以[在你的终端中使用 GitHub 命令行界面](https://github.blog/2021-04-15-work-with-github-actions-in-your-terminal-with-github-cli/)来操作 GitHub 动作。你已经能够管理拉请求、问题、gists 等等，现在，GitHub Actions 也加入了进来。请继续阅读或观看下面的介绍，了解了解工作流运行、管理工作流文件等的各种方法。如果你还没有，那就直接去[安装 GitHub CLI](https://cli.github.com/) 开始吧。

[https://www.youtube.com/embed/UM73gUIoWmE?feature=oembed](https://www.youtube.com/embed/UM73gUIoWmE?feature=oembed)

视频

*   **Cloudflare Workers Unbound，Pages 也将正式发布:** Cloudflare 在上周发布了 Workers Unbound 和 Pages 功能，并于去年发布了测试版。Workers Unbound 是该公司在边缘的无服务器功能，有点像该公司几年前推出的 Cloudflare Workers 的再版，但[现在表示专注于](https://thenewstack.io/cloudflare-launches-workers-unbound-serverless-with-unthrottled-cpu-usage/)“成本效率、易用性以及最重要的合规性。”他们写道，Workers Unbound“旨在用于需要长执行时间的应用程序”，GA 包括“一个针对 Cron 触发器的[私有测试版](https://www.cloudflare.com/workers-unbound-beta/)，用于那些需要更长执行时间的应用程序，测试时间长达 15 分钟。”至于 Cloudflare 页面，新的 GA 功能是该公司“前端开发人员在 Jamstack 网站上构建、托管和协作的快速、安全和免费的方式”，包括一些新功能，如“web 分析、内置重定向、受保护的预览、实时预览和优化的图像(哦，天哪！)."展望未来，他们说用户可以期待 GitLab 和 Bitbucket 支持、Webhooks、A/B 测试等等。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>