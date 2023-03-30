# 背景:亚马逊的弹性分配，量子计算的业务

> 原文：<https://thenewstack.io/context-amazons-elastic-distribution-the-business-of-quantum-computing/>

[语境:亚马逊的弹性配送，量子计算的商业](https://thenewstack.simplecast.com/episodes/context-amazons-elastic-distribution-the-business-of-quantum-computing)

欢迎来到新版的新堆栈上下文播客。本周，我们采访了 [Sharone Revah Zitzman](https://www.linkedin.com/in/sharonez) ，他是 [AppsFlyer](https://www.appsflyer.com/) 的开发者关系，也是我们上周发表的一篇题为“亚马逊，什么是叉？”的文章的作者

在[上一集](https://thenewstack.io/cloud-providers-vs-open-source-the-open-source-leadership-summit/)中，我们谈到了亚马逊网络服务的[开源 Elasticsearch](https://aws.amazon.com/blogs/opensource/keeping-open-source-open-open-distro-for-elasticsearch/) 的新版本，这在开源社区中激起了很多争论和焦虑。

AWS 的阿德里安·科克罗夫特[在一篇博客文章](https://aws.amazon.com/blogs/opensource/keeping-open-source-open-open-distro-for-elasticsearch/)中认为，此举是必要的，因为 elastic 将专有代码与构成其核心的开源代码混合在一起。他用橡皮筋写道:

*无论是发行说明还是文档都没有说清楚什么是开源，什么是专有。企业开发人员可能会无意中对专有源代码进行修复或增强。这很难跟踪和管理，可能导致违反许可，并可能导致权利的立即终止(对于专有的免费和付费)。单个代码提交也越来越多地包含开源和专有代码，这使得那些只想开发开源代码的开发人员很难贡献和参与。*

特别是，AWS 发布了 Elastic 的开源组件，提供了以前仅由 Elastic 的专有代码处理的功能，即安全性、事件监控和警报。

AWS 去年在 Java OpenJDK 上做出了类似的举动，发布了自己的版本，名为 Correto，提供了超越 Oracle 自己的长期支持。尽管如此，许多人对这种方法持有异议，指责 AWS 可能会有意无意地让 Elastic 出局。

在她的帖子中，Zitzman 在新的堆栈中指出，AWS 通过启动自己的弹性发行版，正在从事“愤世嫉俗和敌对的企业行为”，即为了自己的利益劫持开源项目和社区，给项目的维护者留下什么。齐兹曼认为，与其他科技巨头——IBM、谷歌、微软——承诺投入工程时间来帮助维护他们正在使用的开源项目不同，AWS 对它为自己的商业产品劫持的开源技术的福祉表现出较少的关注。

然后在节目的后半部分，我们将回顾本周的热门播客和故事，并讨论本周在波斯顿举行的首届面向商业化的量子计算会议 [Inside Quantum Technology](https://iqtevent.com/) 。

像区块链一样，量子计算是那些潜在的革命性技术之一，迄今为止尚未以任何重大的根本方式改变世界，尽管它承诺了可能的解决方案，如果不是现成可行的话。随着硬件的进步，这种情况可能会发生变化，尽管在建立量子计算机程序员队伍方面仍有许多工作要做。

在 TNS 创始人亚历克斯·威廉姆斯(Alex Williams)和 TNS 执行主编约阿布·杰克逊(Joab Jackson)的帮助下，New Stack 编辑部主任利比·克拉克(Libby Clark)主持了这场秀。

## 这一集的其他故事

*   **[数据库管理员应询问的关于合规性法规的 5 个问题](https://www.thenewstack.io/5-questions-database-admins-should-ask-about-compliance-regulations)** :在 IT 管理软件巨头 Quest 提供的这篇文章中，高级解决方案产品营销经理 John Pocknell 为数据库管理员提供了一些需要考虑的问题，以使他们的数据符合 HIPAA、PCI 或令人畏惧的 GDPR 等合规性要求，换句话说，就是确保他们负责的数据得到正确管理、安全，并且不受不断发展的合规性要求的威胁载体的影响。
*   **[Grafana 现在提供 Flux 作为原生查询语言](https://www.thenewstack.io/grafana-now-offers-flux-as-a-native-query-language/)** :作为 6.0 版全面升级的一部分，开源 Grafana analytics 可视化软件现在支持针对时序数据的 Flux 查询语言，最初是作为一个插件，但很快就会成为 InfluxDB 时序数据库的默认查询语言。
*   **[开发具有前瞻性思维的界面以简化用户体验](/develop-a-forward-thinking-interface-to-streamline-the-user-experience/)** :在本文中，HiveIO 产品副总裁 Toby Coleridge 讨论了如何为数据中心管理员和运营人员构建一个可用的用户界面。该公司正在从其最近更新的 hyperconverged 软件包(HiveIO 7.2)中吸取经验教训，该软件包包括一个全新的用户界面，具有更多可视化，通常的菜单行被更直观的反应方法所取代。
*   **[服务网格如何成为微服务的缺失环节](/how-service-meshes-are-a-missing-link-for-microservices/)** :在本期播客中，Solo.io 的创始人兼首席执行官艾迪特·莱文就服务网格这一主题接受了采访。现在人们普遍认为，向微服务和云原生环境的转变只会带来伟大的事情——然而。随着云计算热潮的兴起，许多组织突然意识到了前进道路上的许多困难，例如 Kubernetes 和无服务器平台的出现往往是一项正在进行的工作。

Oracle 和 InfluxData 是新体系的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>