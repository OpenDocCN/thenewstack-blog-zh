# 微分段:VMware 如何解决容器安全问题

> 原文：<https://thenewstack.io/microsegmentation-how-vmware-addresses-the-container-security-issue/>

很明显，来自 [ClusterHQ 的最新容器使用状况调查](https://clusterhq.com/assets/pdfs/state-of-container-usage-june-2015.pdf) [PDF]的最令人惊讶的结果是，229 名 IT 专业受访者中有近四分之三表示，他们的数据中心正在虚拟机管理程序虚拟化环境中运行容器，也就是说，在独立虚拟化层的安全范围内运行容器环境。大约 61%的受访者表示，安全性仍然是他们的数据中心在生产中采用容器的障碍，这一数字得到了支持。

企业还没有真正采用容器——不是他们想要的方式。他们正在虚拟环境(如 VMware 的 vSphere)中接受测试。在接受新一轮采访时，VMware 首席技术战略官 Guido Appenzeller——SDN 生产商 Big Switch Networks 的联合创始人和[前首席执行官，以及 Voltage Security](https://gigaom.com/2014/10/02/big-switch-co-founder-guido-appenzeller-joins-vmware/) 的联合创始人和前首席技术官[——表示他们这样做是因为他们担心安全性。](http://guido.appenzeller.net/wordpress/?p=178)

![Guido Appenzeller - VMware](img/5846d3fdae0314c03fa8cc75ad876810.png)

吉多·阿彭策勒

“半年前，我们开始看到我们 NSX 客户群中的第一批客户开始使用 NSX 顶部的集装箱，”Appenzeller 告诉我们。“按照他们目前的部署方式，他们实际上拥有 Docker 或 Cloud Foundry 之类的容器主机，并在虚拟机管理程序上的虚拟机内部运行。我第一次看到这个的时候，我说，‘很明显这些家伙做错了。毕竟，它应该是虚拟机或虚拟机管理程序。

“但事实证明，他们有一个很好的理由来解释为什么要这么做，”他继续说道。

> “基本上是安全的。他们说，‘如果我直接在我的物理服务器上运行容器主机，会产生几个问题。’"

## 孤立的困境

VMware 的首席网络安全专家认为，一个主要问题是，不可能在容器之间实施强有力的容器隔离。他认为，由于容器是由内核有效管理的，内核级的漏洞利用有机会危及容器内运行的应用程序。

Appenzeller 的观点得到了 Red Hat 安全工程师 Trevor Jay 的认同，他去年 12 月在公司博客上写道:

“容器都共享同一个内核。如果被包含的应用程序被特权提升漏洞劫持，所有运行的容器和主机都会受到危害。同样，两个容器不可能使用同一个内核模块的不同版本。”

Appenzeller 说，人们可以得出这样的结论:在安全问题得到充分解决之前，虚拟化集装箱化只是一种暂时的状态。但是组织已经被训练以“攻击面”的形式考虑相对安全级别可能有成千上万种方法来寻址系统内核，毕竟，它被设计成可寻址的，因为它是操作系统。另一方面，管理程序被专门设计为不可寻址的。

他说，由于这个原因，已知的内核级漏洞数量至少比管理程序级漏洞数量多两个数量级。此外，假设开发人员要构建一个绑定到后端存储卷的有状态服务，并创建一个关于如何解析请求的新漏洞。这可能会让恶意参与者在应用程序内部执行任意代码。

换句话说，恶意行为者不需要专门设计“容器利用”来有效地生产利用容器的东西。如果有人要演示一个常见的内核漏洞——比如说，在一个公开会议上——他将演示一个容器漏洞。Appenzeller 说，如果这种利用直接针对应用程序，那么老练的攻击者不仅可能而且很可能获得容器主机系统的根级权限。

换句话说，为了让每个人都能从字里行间体会到好处:内核漏洞就是容器漏洞。句号。

## 又一层抽象

Appenzeller 的评论实际上不是抱怨，而是支持解决方案的论点:一种新型的容器安全模型，它将引入一个新的抽象层次，并可能为监督容器管理的熟悉的管理环境铺平道路。

VMware 将这种模式称为“微分段”，从某个方面来说，它就像一个有状态集群，用于在容器中运行有状态或无状态服务。这种划分将通过运行在(你猜对了)管理程序上的有状态防火墙来提供。正如 CTSO 解释的那样，防火墙管理进出网段的连接。当它看到一个有问题的连接请求时，它会将该请求转发到更高级别的管理服务器，在那里至少可以记录该请求。优选地，管理服务器可以应用条件规则来确定连接是否应该继续。

在最坏的情况下，容器或节点(确切的术语可能还没有确定)表现出可疑的行为，管理服务器可以简单地重新启动它。如果容器内的服务是显式无状态的，那么它们可能拥有的任何有状态连接，比如说，到外部数据卷的连接，都将由防火墙维护。因此，从受信任的映像重新启动服务应该不会造成危险，并且只引入可以忽略的延迟…至少在理论上是这样。

Appenzeller 解释说:“我们为您提供了网络级别上正在发生的事情的完全可见性，不仅是容器主机认为应该发生的事情，而且是实际发生的事情。你所有流量的独立视角。所以如果有什么可疑的地方，你就会看到。”

Appenzeller 告诉 New Stack，一些 VMware 客户，包括一家主要银行，今天实际上正在试验运行微分段。

> “这使他们能够开发非常复杂的应用程序，否则，如果只是将它们放入普通的容器框架中，他们不会对安全级别感到满意，”他说。"下面还有一层来自 NSX 的额外防御."

他指出，为了让银行和其他金融机构保持合规性，它们必须保持特定的安全控制。例如，执行实时交易的机构被禁止对“买入”信号和“卖出”信号使用相同的数据库；支付处理中心保持控制，禁止它们在支付交易的整个生命周期中绑定到相同的数据库。不幸的是，这些机构之间仍保留着被称为“中国墙”的东西。

Appenzeller 认为，也许这些机构应用程序能够在实验阶段之后在容器内工作的唯一方法是继续利用 NSX，但以不同的身份。微分段将简化事物的协调，使容器能够突破单个虚拟机的界限，同时仍然依赖虚拟机管理程序作为协调代理。在这种情况下，没有太多关于中间层或库伯内特的讨论。

## 虚拟伙伴关系

然而，VMware 是 Docker 创建 libnetwork 的关键合作伙伴，lib network 是 Docker 容器的新本机连接框架。在开放容器项目中，VMware 与 Docker 是平等的合作伙伴，libnetwork 可能会为此做出贡献。libnetwork 框架将启用 Docker 的新插件模型 T1，该模型上周在 DockerCon 进行了演示，[思科也于上周认可了该模型 T3。](http://blogs.cisco.com/datacenter/docker-and-the-rise-of-microservices)

在上周的一篇公司博客文章中，VMware 发言人 Roger T. Fortier 总结了所有这些组件之间的最佳关系:

“VMware NSX 支持微分段。微分段支持强大的精细安全控制。Docker 支持简化的微服务架构。libnetwork 支持 VMware NSX 强大的微分段功能与 Docker 的微服务架构相集成。”

Guido Appenzeller 告诉我们:“Libnetwork 是一大进步，它走向了一个更丰富的网络模型，允许客户实施他们需要的连接和安全策略，以便将更复杂的应用程序移动到容器中。我认为我们对进展非常满意；也就是说，总有可以改进的地方。它看起来更像 OpenStack，这是我们当然希望看到的。”

然而，随着 OCP 成为现实，思科、VMware、IBM、微软、CoreOS 和 Docker 现在在一般“容器”的基线定义的开发中是平等的参与者。容器不再是“Docker”和“other”，我们应该习惯这一点。

在这个平等合作伙伴的世界中，VMware 引入了一种新的方式来考虑容器在系统中的排列，这种方式显然实现了在容器扎根时让 VMware 参与进来的目的。VMware 的业务是在系统组件之间构建抽象层，并销售连接这些层的管理控制台。

VMware 的 NSX 可能会与 Ubuntu 的 LXD 竞争，后者也是从一个不那么以 Docker 为中心的角度设计的。如果加入这样的竞争，那么关于是 systemd 还是一个独立的守护进程应该初始化容器的内容的争论将变得毫无意义。事实上，容器本身可以成为更加通用的实体，Docker、CoreOS、微软或其他任何人赋予它们的差异可能会变得多余。

这可能会使整个容器市场更适合 VMware 公司。不要认为开源市场不是资本主义企业。

思科、CoreOS、Docker、IBM 和 Red Hat 是新堆栈的赞助商。

专题图片: [Perspecsys Photos](https://www.flickr.com/photos/111692634@N04/) 拍摄的:[安全在字典](https://www.flickr.com/photos/111692634@N04/11406985424/in/photolist-inZMmu-buwS4k-bx5QaQ-cVoHYW-eaqGBK-e5Wwut-cKwP4b-anKSQ9-inZMwE-e8k4Pf-9mvmSo-aqE2zm-6Y19x9-cHQHxq-7TTf76-e2RZ14-e6TzpF-6KHmLt-daEPtd-dPd3F4-dYkGxd-hfsS1k-6fPXvQ-paVryT-9yjTfL-6o6ccS-dWrFwE-aiyMf4-LgJpn-aMH1e4-do69qz-bipm2K-b55bw-efUtQB-Xe8YN-an9vmX-dSeNmW-iTWXqp-bCGtot-eLk5x5-bw7cty-fKr3Ph-81bXun-6hTUT6-4adHGU-7G5Ats-9VR8pu-fKr2y5-nnTQJG-bEDbzT)中，在 [CC BY-SA 2.0](https://creativecommons.org/licenses/by-sa/2.0/) 下授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>