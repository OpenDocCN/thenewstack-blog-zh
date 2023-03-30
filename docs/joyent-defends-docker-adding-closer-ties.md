# Joyent 为 Docker 辩护，增加更紧密的联系

> 原文：<https://thenewstack.io/joyent-defends-docker-adding-closer-ties/>

经过在 Docker 社区的两天交流，Joyent 宣布了两项开源计划和一项容器服务，进一步加强了与 Docker 的联系。随着新闻的发布，Joyent CTO Bryan Cantrill 也对 CoreOS [“正面攻击”Docker](https://thenewstack.io/coreos-calls-docker-fundamentally-flawed-releases-prototype-alternative/) 发表了一些精选评论。首先，这些言论非常厚颜无耻，但也反映了一些本可以预测到的事情。

“很明显，容器，尤其是 Docker，将成为基础设施的未来。坎特里尔说:“目前还不清楚这种情况将如何改变。“谁会是赢家，谁会是输家？馅饼可以分吗？”

> “我认为 CoreOS 得出的结论是，馅饼不能被分享。Docker 或 CoreOS 将会成功，但不是两者都成功，他们必须攻击 Docker 才能成功。”

除了本周的戏剧之外，Joyent 正在为希望为生产应用程序部署 Docker 的公司解决其所谓的安全、虚拟网络和持久性方面的“限制”。

产品:

**Linux 品牌区域(LXz)，**容器部署平台。这意味着您可以在安全的操作系统虚拟化上本地运行 Linux 应用程序，包括那些在 Docker 容器中运行的应用程序，而无需中间的硬件虚拟机管理程序。Cantrill 说，这也提高了安全性和性能，他说这两者是相关的。

每个容器都有自己的虚拟化网络堆栈和基于 ZFS 文件系统的持久层。LXz 构建在 SmartOS 容器及其 Crossbow 网络虚拟化层之上。

“这种基板已经过近十年的生产验证，能够提供真正的网络隔离，同时还能提供线路性能。所以…答案是两者兼而有之:公共云级多租户安全性和硬件性能。”

**将 Docker 引擎扩展到 smart data center—**Docker 运行时正被集成到 Joyent 基于 Unix 的云流程编排中，该流程编排是 Joyent 公共云的主干。用户可以在 Joyent 公共云、SmartDataCenter 或开源代码之间进行选择。测试版现已推出，并将于 2015 年第一季度广泛推出。

Cantrill 在一篇[博客文章](https://www.joyent.com/blog/dockers-killer-feature)中为 Docker 方法辩护，称“正是他们以 API 为中心的方法使他们能够实现他们宣称的目标，即‘包括电池，但可拆卸’和‘基础设施应该是可插拔和可组合到极致的’。”…我们的实现相对较新，发展很快，虽然我们发现了一些小的改进机会，但我们知道 Docker 的 API 基本上是可靠的。"

**Joyent 容器服务**将在 Joyent 公共云中提供和管理 Docker 主机和容器。该服务包括一个安全网关、私有注册表以及 Docker 容器和主机的集成日志和监控。

上个月，Joyent 为 SmartDataCenter 及其位于 ZFS 的多租户 Manta 对象存储服务[开源了代码。它在 10 月下旬宣布，它已经从现有投资者英特尔资本、Orascom TMT 投资公司和其他投资者那里额外筹集了 1500 万美元，使其总投资达到 1.2 亿美元。](https://thenewstack.io/dockers-popularity-convinces-joyent-to-open-source-its-container-based-orchestration-software/)

CoreOS 周一公布了 Docker 的原型替代产品，称 Docker 流程模型——通过中央守护程序发送一切——是“有根本缺陷的”

CoreOS 首席执行官 Alex Polvi 在宣布该项目时写道:“如果不解决这些问题，我们不能真诚地继续支持 Docker 的破碎安全模型。”

他说，虽然 CoreOS 在生产中提出了 Docker 的一些合理问题，但它没有解释它的替代火箭(Cantrill 描述为“低得多的水平和非常新生的技术”)将如何解决这些问题。

“特别是考虑到安全问题，他们对 Docker 守护程序(在主机上运行的单个守护程序)的批评似乎是唯一的实质内容。但 Docker 有远程 API，你可以实现该 API 的不同实现，而不用把 Docker 宝贝和洗澡水一起倒掉，”Cantrill 说。

“如果他们的目标是改进 Docker 并实现变革，他们绝对需要在 Docker 的范围内完成。那不是他们的目标。…这有点像珍珠港事件，是在 Docker 还年轻的时候对它进行的一次精心策划的偷袭，因为在六个月或九个月、一年内，鉴于 Docker 的势头，它不会在这个级别上受到攻击。我个人认为，在目前这个水平上，它是不可攻击的。”

他说，容器中的安全问题与 Linux 有关，而不是 Docker，Rocket 将像 Docker 一样绑定到 Linux。

与此同时，他说 Joyent 的新产品解决了这些问题，他相信 Docker 社区将为创新创造一个有效的生态系统。

“它在 SmartOS 基板上。它允许你运行 Linux 二进制文件，但你实际上是在一个 SmartOS 内核上运行，这个内核对容器有很深的支持，非常丰富的网络虚拟化支持，通过 ZFS 提供行业领先的持久性支持，”他说。

“所以你在这个工业基板上，但是在它的上面是一个接口，允许你运行你任意的 Linux 映像。但这并不是因为我们能够在一个月、六个月甚至 18 个月内解决(Linux 的问题);这需要多年的设计和完善。”

通过 Flickr 知识共享的特色图片[。](https://www.flickr.com/photos/aidanmorgan/8230802941/in/photolist-5MLrVB-aomGaV-8PgrTT-5qdRef-3eyP85-8kk7Sq-7hTSDA-agoNSq-agm3Yz-agm418-agoNyo-nZJjVZ-dxk1Xx-KkQaM-RMQ8q-6jWqbj-6jSd6p-6jWoNo-atzEWM-RMCiY-6ZL4hR-6ct11p-a7v9nh-7Fn6Xo-6ZQ2JS-5g9mjd-aaPFK4-6ZPLz3-RMCEm-RPxtD-RMC9m-RPxKx-6cqsYL-6jWgos-6jS8yF-6jWrWC-6jWetY-6jWfqA-BhxiU-6z83GT-as31nU-thMsQ-6ZytNr-m19yvt-6344n-q6Atd-EuWt7-9t4U6n-ctwWXw-aaSvLm)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>