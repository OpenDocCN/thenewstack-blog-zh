# NGINX 的 Sarah Novotny:监控微服务意味着拥抱失败

> 原文：<https://thenewstack.io/nginx-sarah-novotny-case-monitoring-microservices/>

自从 AJAX 首次变得可行以来，web 浏览器一直是 web 应用程序性能监控的杠杆点。JavaScript 的执行依赖于事件，APM 监视器利用这些事件来确定在线事务是否顺利进行。

这种情况可能会很快发生戏剧性的变化。周四在佛罗里达州奥兰多举行的 [Dynatrace Perform 2015](http://www.dynatrace.com/en/perform.html) 会议上(由 New Relic 和 AppDynamics 的长期竞争对手 [Dynatrace](http://www.dynatrace.com/) 制作)， [NGINX](https://www.nginx.com/) 开发人员关系负责人 Sarah Novotny 透露，领先的微服务 web 服务器组件的商业版本现在能够为 Dynatrace 和类似的工具提供必要的关键信号，以监控其托管的任何类别的分布式应用程序的性能。

![151014 Dynatrace 006 (Sarah Novotny)](img/95b7b527deb7bca4a51c1ade122a0ec5.png)

莎拉·瓦特尼

“NGINX+对其运行方式有额外的指标和可见性，”Novotny 在回答新堆栈的一个问题时说。“如果你运行 NGINX 开源软件，会有一个‘Stub Status’页面……它会显示几个单调递增的计数器，没什么特别令人兴奋的，你会说，‘耶，它启动了。’有了 NGINX+，我们有了一个更强大的状态页面，这是一个功能强大的仪表板，可以与多个 NGINX 主机或负载平衡情况下运行的事件进行交互。"

默认情况下，该状态页面的文件扩展名为. HTML。正如 Novotny 周四在这里告诉与会者的那样，你需要做的就是从它的 URL 中删除那个扩展名，NGINX+将返回“一个巨大的 JSON 对象，包含所有这些信息。”

她解释说，这个对象可以很容易地导入 Dynatrace 或另一个 APM 系统。

## 什么特工，在哪里？

这对那些工作是监控性能的人来说意义重大——正如我和我的同事 Alex Williams 本周在这里学到的，这些人更可能不是软件开发人员，也不一定被认为是 it 管理员。但是，考虑一下软件测试人员可以立即可靠访问的工具的质量，如果这些度量是从服务器端而不是客户端提供的数据中计算出来的。

就网络浏览器而言，谷歌 Chrome(目前的使用份额领先者)、Mozilla Firefox、微软 Internet Explorer、苹果 Safari、Opera 以及现在的微软 Edge(为 Windows 10 打造的全新机箱)之间仍有相当大的行为差异。说注重性能的 It 人员很难将这些差异排除在外是不准确的，因为在大多数组织中，根本没有将它们排除在外——变量是如此的不稳定，以至于没有人会在意。

随着 NGINX+直接集成到托管微服务的容器中，微服务现在已经可以向监控代理报告关键性能数据(根据 Novotny 的说法，这不是未来的功能，而是现在的功能)。NGINX 尚未解决的问题，以及 Dynatrace 尚未宣布的问题是，在这种关系中，这样一个代理需要驻留在哪里。

在本周举行的 Perform 2015 上，与会者已经看到了 Dynatrace 称为下一代 APM 的产品，同时谨慎地将其定位为现有 Dynatrace 代理的扩展，而不是替代。新系统名为 [Ruxit](https://ruxit.com/) ，利用自动发现来确定复杂网络的组件，包括在那里运行的软件。然后，它可以测量组件的运行状态和相对性能水平，在许多情况下，还可以测量软件的运行状态和相对性能水平。

Ruxit 一直被宣传为基于云的服务，尽管该公司周四宣布增加了 Ruxit Managed，这是一个内部版本，其管理仍然可以由 Dynatrace 监督。无论哪种情况，Ruxit 技术都是基于产品工程师所说的“一个代理”。

我们尚未了解的是，这种“一个代理”将如何与 NGINX+交互。但在周四上午的主题会议上，NGINX 首席执行官 Gus Robertson 的出席足以表明 NGINX 和 Dynatrace 之间的合作已经在进行中。

![151014 Dynatrace 007 (Gus Robertson)](img/252250d715422c87d04d4715dd364005.png)

格斯·罗伯逊

罗伯逊说，改善用户体验的一个关键是应用程序架构的持续转变。

“这种建筑与过去的整体建筑非常不同，”罗伯逊说。“过去的整体建筑要简单得多。您只有一个二进制文件，如果您想要扩展，可以在许多机器上复制该二进制文件…现在，您有许多微服务。”

但罗伯逊并没有准确地在众多微服务和用户将享受的更高效率(以更快、更高效的分布式应用的形式)之间建立关联。这也是当天晚些时候与会者参加 Sarah Novotny 会议的原因。

## 重构大象

许多经验丰富的绩效监督员可能会发现 Novotny 演讲的主题有点陌生:拥抱失败。从历史上看，APM 一直被用来衡量应用程序的完整性和成熟度，无论是在现场部署之前还是在生产阶段。它被描述成一种类似岩石抛光滚筒的东西，将光线投射到坚硬的表面上，将它们抛光得光滑闪亮。

这与微服务领域不太兼容，在微服务领域，服务是短暂的，故障是可以预料的，但会得到响应，停机通过冗余得到补偿。

“这是微服务架构真正给你的东西之一，”Novotny 建议与会者，“改变你的用户体验的能力，并在组件故障时优雅地降级。它还以许多有趣的方式给你速度。但是速度不仅仅是你的应用程序加载的速度，或者你的网站加载的速度。速度也是，多快能出新功能？速度就是，当东西坏了，你能多快修好它？速度也是，你能多快适应你的业务，和你的业务流程，就像竞争对手一样？你能领先于你的竞争对手吗？”

她正在向听众演讲，其中许多人还没有考虑到部署和回滚是自动化和协调的概念。在 monolithic 领域，配置是一个手动过程，通常在周末没有其他人工作的时候进行。正如 Kubernetes、Mesosphere 和 Marathon 的用户所知，在微服务中，部署是小服务的小事件。

这些部署成为定期事件，全天而不是全年进行。因为它们是自动化的，就像呈现网页一样…所以可以对与这些部署相关的流程进行性能衡量。

Novotny 的讲话无疑对在会议上听讨论的小组产生了影响。当人们意识到这种新方式有多么不同时，他们就会露出那种表情。

改变的是工作的规模。当以自动化方式进行监控时，频率会增加一个数量级，但作业的规模会减小。度量被用作观察工作和工作进展的方法。

Novotny 将单体应用程序和伴随它们的流程(包括 APM)比作房间里众所周知的大象的不同部分。她建议每个人“重构我们现在拥有的这头大象。

> “有人知道你如何吃掉一头大象的笑话吗？一次一口。”

Dynatrace 和 New Relic 是新堆栈的赞助商。

特征图片: [daddyboskeazy](https://www.flickr.com/photos/85059977@N04/) 的:[粉象](https://www.flickr.com/photos/85059977@N04/15629696699/in/photolist-pP9hii-8bQag5-r2FFUq-pPebdd-9mhX2A-7eRWx9-6K7VSa-oxbd65-e4ULWG-e4SyrQ-e4LWk4-8YBLyg-4B7cCU-4CngHU-9zXqZi-knoEK-8AiDVV-57VcFF-dsG86-bPAEKt-82mEMu-bJSPaR-65PggD-dqoErd-dqowKt-co4dVq-ww5uy-fPstb-AvRga-5iRWXd-p1k2tT-4B43VF-7YWoD3-95Xuim-LDrBo-5ED5ih-5swfT7-6WbHbr-e4PaeZ-e4UMpy-4gNpZ-4H6NZG-h6N5Gj-5srTtF-55T3Nn-e4LVTK-e4LWeD-e4LW4n-e4SynU-e4SxVN)由[CC 2.0](https://creativecommons.org/licenses/by/2.0/)授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>