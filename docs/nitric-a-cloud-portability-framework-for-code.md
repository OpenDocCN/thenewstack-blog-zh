# Nitric，代码的云可移植性框架

> 原文：<https://thenewstack.io/nitric-a-cloud-portability-framework-for-code/>

[](https://hashnode.com/@rsiv)

 [拉克·西瓦

拉克是硝酸队的一名工程师，他对云的本地运动和改进开发经验充满热情。他在软件行业拥有 15 年的经验，最近的职位是一家领先的金融科技公司的工程主管。在业余时间，他喜欢旅游和自然摄影。](https://hashnode.com/@rsiv) [](https://hashnode.com/@rsiv)

云托管服务正成为任何人在云中构建应用程序的最快方式。这些服务提供的好处是有代价的:供应商锁定。如果另一个解决方案在未来变得更适合您，那么离开您的提供商的成本会很高。

我自己也经历过。找到云服务的初始速度和成功，充分利用其功能，然后遇到成本增加和技术限制。似乎不可避免地会陷入两个糟糕的选择之间:迁移或吸收缺点。

[Nitric](https://nitric.io/) 是一个开源框架，支持团队开发和管理可部署到任何云的单一代码库。我们目前支持亚马逊网络服务、Azure 和 GCP，并计划扩展到其他有社区兴趣和参与的网站。

## 专有云的可移植性

在我们为一个项目研究云提供商时，Nitric 的想法开始成形。我们注意到，在这个竞争激烈的市场中，云提供商从彼此那里获得灵感，并在其基础服务中提供相同的功能。

这些服务的接口、配置和部署都存在差异。针对这些细节进行开发有助于锁定，但是最佳实践最终是与云无关的。我们开始利用共性将最佳实践提升到一个可重用的框架中。

我们框架的核心是 [Nitric Server](https://nitric.io/docs/concepts) ，它包含了针对每个受支持服务的特定于云提供商的插件。Nitric 服务器负责将应用程序请求翻译成合适的云所需的格式。

例如，访问 Nitric 文档集的请求将转化为从 AWS 中的 DynamoDB 读取。SDK 层和 Nitric 服务器通过 [gRPC](https://nitric.io/blog/why-nitric-chose-grpc) 进行通信，利用 HTTP/2 中的连接管理效率，使用[协议缓冲区](https://developers.google.com/protocol-buffers)来优化有效载荷大小。

Nitric 框架提供了一组一致的 API 来公开云资源，包括存储、文档、事件、秘密和队列。这些基础资源是许多应用程序的核心，可用于计算服务，这些服务可以作为 API 网关中的路由或方法公开。我们已经选择了在 Nitric 框架中支持的关键[服务，在社区的帮助下，我们的目标是扩大这个列表(在我们的](https://nitric.io/docs/reference) [GitHub 库](https://github.com/nitrictech)中寻找“好的第一期”标签)。

Nitric 通过利用来自云原生社区的开源工具来处理部署， [Pulumi](https://www.pulumi.com?utm_content=inline-mention) —一个基础设施即代码平台。我们的框架建立在他们致力于云无关部署的基础上，为开发人员提供在单一部署中构建应用所需的基础设施和资源。我们还解决基本的政策问题，例如，对所有部署的资源应用最小特权原则。

供应商锁定并不是云开发的唯一挑战，虽然我们开始应对可移植性的挑战，但我们的使命是从整体上改善云原生开发体验。让我介绍一下我们关注的两个重要领域。

## 消除配置

部署到托管服务的应用程序需要大量配置，当您将其他技术(如开放 API)加入其中时，配置量会开始影响工作效率。

Nitric 框架的第一个版本需要配置文件。一旦我们开始将它用于实际规模的项目，我们就会发现所涉及的工作不仅仅是编写代码本身。我们知道我们必须改进这一点，因为配置行写起来很耗时，容易出错，并且很难检查。

我们考虑的第一个想法是在配置前面放置一个 UI。至少我们可以最小化错误，但这看起来像是一个创可贴式的解决方案。相反，我们问自己一个重要的问题:配置文件真的有必要吗？头脑风暴和对这个主题的研究产生了一个新特性，我们称之为“代码配置”

Nitric APIs 消除了开发人员需要编写的大部分配置。部署时，Nitric 将自动提供和设置权限，如集合、桶、秘密等。，通过检查代码和检测资源声明。

只需几行简单的代码，我们就可以开始调配了:

*   名为“example”的 API 公开了路径“/welcome”上的 get 方法。
*   一种只能写入的存储桶。
*   一个名为“example”的文档集合，可读写。

```
import  {  topic,  api,  collection  }  from  '@nitric/sdk';

const exampleApi  =  api('example');
const exampleBucket  =  bucket('example').for('writing');
const exampleCollection  =  collection('example').for('reading','writing');

// Implement a get method

exampleApi.get('/welcome',  async  (ctx)  =&gt;  {

...

});

```

## 保持框架开放

一个好的开发者体验应该是不受限制的，允许开发者专注于解决问题和编写代码。Nitric 的 API 不限制其他框架的使用；我们是来加入令人惊叹的开发框架生态系统的。

本着这种精神，我们感谢帮助我们为社区做出有用贡献的建议。如果你对我们的工作感兴趣，并跃跃欲试，硝酸文档是一个很好的起点。在 [GitHub](https://github.com/nitrictech/nitric) 上查看我们所有的源代码，并贡献或寻求反馈！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>