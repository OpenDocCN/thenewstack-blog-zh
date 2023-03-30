# Platform9 希望成为逃离亚马逊的企业的 OpenStack 服务

> 原文：<https://thenewstack.io/platform9-wants-to-be-the-openstack-service-for-businesses-fleeing-amazon/>

由 VMware vets 创立的 Platform9 公司今天发布，它的成立是为了响应这两个观察结果:

*   各公司认为，将大型亚马逊网络服务部署转移到内部更具成本效益。
*   OpenStack 没有将其作为构建私有云的独立选项。

这是根据平台 9 的首席执行官 Sirish Raghuram 的说法，该平台今天宣布从红点风险投资公司筹集了 450 万美元。他的观点说明了他认为该公司作为提供 OpenStack 即服务的提供商所采取的方向，这是一种不寻常的模式，并扭转了关于运行新堆栈意味着什么的辩论。通过这种模式，Platform9 的客户既有基础设施成本，又有来自第三方提供商的服务。企业必须在其服务器上下载一个代理，但他们可以根据兼容性使用现有设备。作为回报，他们“获得了自己的基于 OpenStack 的管理系统来运行他们的云，”他说。

这种设置的主要好处在于管理。Raghuram 说，当他在 VMware 工作时，他有一个客户，他的服务器分布在 80 个不同的孤岛中，位于不同的分支机构。每个思洛都有自己的 vCenter 安装。这意味着每当推出新版本的 vCenter，该公司都必须管理 80 次更新。

“很难升级其中一个，”Raghuram 指出。结果是，该公司总是比当前版本落后很多年，因为由于过程的复杂性，它会推迟升级。

由于 Platform9 作为服务运行，该公司代表客户管理任何升级，如与 OpenStack 相关的升级。

Platform9 的产品包括一点监控。它可能会注意到硬件问题，并提醒客户现场的 It 管理员可以修复该问题。

任何像这样作为服务提供的产品都有潜在的缺点。例如，延迟可能是一个问题。Raghuram 说，当用户访问 UI 或 API 时，可能会出现延迟。但他表示，由此产生的影响应该很小。

此外，Platform9 如何为服务定价也很关键。它还在纠结不同的可能性。定价可以基于每台服务器的模型。

目前，Platform9 还有其他一些限制。它目前只支持 KVM，但表示未来将支持 Docker 和 vSphere。此外，它并不支持所有的 OpenStack。它可以为客户运行核心计算服务 Nova 以及 Glance 和 Keystone。该公司正在努力支持雨燕，煤渣和中子。

这项服务目前还处于测试阶段，但已经有十几家公司在使用。Raghuram 说，它的三个最大用户在 AWS 拥有“数百万美元的账户”。他说，他们中的一些人意识到，六个月的 AWS 支出为他们购买了构建私有云所需的硬件。

Platform9 的产品负责人 Madhura Maskasky 说，Platform9 的一些早期客户对 AWS 的 SLA 也不满意。

事实上，Platform9 的早期用户之一是 Moz，该公司的技术运营副总裁马克·谢里曼[分享了一些关于成本比较的细节](http://gigaom.com/2013/12/07/want-to-reduce-your-cloud-costs-70-percent-heres-how/?utm_campaign=Feed%3A+OmMalik+%28GigaOM%3A+Tech%29&utm_medium=feed&utm_source=feedburner "GigaOm")，这些成本比较促使该公司决定将大部分工作从 AWS 转移出去。

Raghuram 说，但是一旦这些企业决定离开 AWS，转向内部云，他们就不一定对自己的选择感到满意。

那些喜欢 OpenStack 想法的人可能已经发现，这比他们希望承担的工作要多。“OpenStack 更像一个 SDK，它更像一个框架，而不是一个组织可以操作的东西，”Raghuram 说。

此外，在可用的 OpenStack 发行版中，有些要求客户从头开始，而不是重用现有的硬件和软件，他说。这些发行版意味着客户不得不投资数百万到新的基础设施上并自己管理它，除非他们雇佣提供发行版的公司来为他们管理它。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>