# GitLab 在 AWS 上建立了一个单租户服务

> 原文：<https://thenewstack.io/gitlab-dedicated-interview/>

DevOps 巨头 [GitLab](https://about.gitlab.com/?utm_content=inline-mention) 已经[在](https://about.gitlab.com/press/releases/2022-11-30-gitlab-dedicated-launches-to-meet-complex-compliance-requirements.html)[亚马逊网络服务](https://aws.amazon.com/?utm_content=inline-mention)上发布了其在线代码库的版本作为单租户软件即服务(SaaS)。

这项名为 [GitLab Dedicated](https://docs.gitlab.com/ee/subscriptions/gitlab_dedicated/) 的服务，解决了云环境中对更加隔离的基础设施日益增长的需求。这一有限可用性版本与 AWS 云服务独家合作。它由 GitLab 托管和管理，可以部署在您选择的 AWS 云区域(适用于大多数区域)。

根据 GitLab 的 2022 年全球 DevSecOps 调查 ，安全性和合规性是开发人员、运营人员和安全性领导者的首要投资领域，这一点不足为奇。AWS 上个月举行的年度 re:Invent 用户大会充满了演讲、SaaS 平台和安全选项。虽然多租户 SaaS 平台本身没有任何问题，但 GitLab Dedicated 面向任何客户，但面向那些因为高度监管的行业(即金融或政府)而需要私人空间但不想在内部托管的客户。

GitLab 首席战略官 Ashley Kramer 在发布前接受了采访，与 AWS 讨论了产品和排他性。

## **特性**

GitLab 专用包括:

**认证**:支持实例级 SAML OmniAuth 功能。GitLab Dedicated 充当服务提供商，您必须提供必要的配置，以便 GitLab 与您的 IP 进行通信。

**联网**:支持 IP 允许列表的公共连接。通过 AWS PrivateLink 支持可选的专用连接。

**升级**:跟踪最新(n-1)版本后一个版本的每月升级，带有最新的安全版本。为高严重性版本提供了带外安全修补程序。

**备份**:定期进行备份并测试。

**云区域的选择**:在开始时，选择您想要部署实例的受支持的云区域。

**安全性**:使用最新的加密标准对静态和传输中的数据进行加密。

## **幕后**

GitLab Dedicated 花了大约一年的时间来开发，这个时间表可能会缩短，因为从事这项技术的工程师们是从多租户软件和开源产品开始的。“B 由于我们已经有了这些不同部署选项的历史，它并不像我们只是从零开始，然后说，让我们去创建它，”早期开发流程的 Kramer 说。

但是不要把有一个起点误认为是一个简单的开发过程。GitLab dedicated 仍然是一个不同的产品。尽管它建立在开源和多租户选项的独特元素之上，但新的 SaaS 平台也包含独特的组件。“好消息是，我们已经有了自我管理的权利，我们已经有了多租户，所以基本上只是将不同的组件和服务隔离为一个租户，我们可以从这个角度出发，”Kramer 说。

开发过程不仅仅是一群工程师在真空中独自工作；还有一个客户因素。“我们收到了客户的反馈，他们已经在自我管理哪些工作很好，哪些我们可以改进，”Kramer 说，并确认客户的反馈已纳入 GitLab Dedicated 的开发流程。

未来还有更多工作要做，因为迭代是 Gitlab 的核心价值之一。当被问及功能和定制的完整列表时，Kramer 回答说:“创建高度可定制的单租户 SaaS 软件是一项挑战。现在的目标是为他们广泛的客户群提供 GitLab。”

这暗示了未来的路线图和附加功能的推出。“如果您想要一个租户可以根据需要扩展到任意多的客户，您必须有一个您坚持使用的参考体系结构。然后随着时间的推移，越来越多的客户会想要一些新功能，然后你就可以把它们内置进去，”克莱默说。

**与 AWS 的独家合作**

git lab 自己的服务是基于云的，为什么要与 AWS 合作？简短的回答是，“顾客在哪里，我们就去哪里，”克莱默说。AWS 和 GitLab 已经合作了一段时间，所以这不是一种新的关系。“我们在很多事情上使用 AWS，所以它看起来很自然，很合适，”Kramer 说。合作协议也归结于客户的偏好，因为“我们做的很多事情都来自客户的反馈。”

其他功能还没有发布日期。GitLab dedicated 限量发行。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>