# Google 的 Maya Kaczorowski 讲述了容器安全的责任开始和结束的地方

> 原文：<https://thenewstack.io/googles-maya-kaczorowski-on-where-responsibility-for-container-security-begins-and-ends/>

[Twistlock](https://www.paloaltonetworks.com/prisma/cloud) 赞助了这篇帖子。

[一位谷歌产品经理讲述你的容器安全从何开始，又从何结束](https://thenewstack.simplecast.com/episodes/a-google-product-manager-on-where-your-container-security-begins-and-ends)

人们可以合理地假设，集装箱安全将在近期经历许多变化，尤其是考虑到最近广为人知的安全漏洞(更不用说那些我们还不知道的了)。但是[谷歌](https://www.linkedin.com/in/mayakaczorowski)产品经理玛雅·卡佐罗夫斯基不同意这个观点。当谈到组织与云和工具提供商分担的责任时，Kaczorowski 说，这种模式本身并没有改变。相反，“人们越来越不担心他们不必管理的部分，或者他们过去必须管理的部分——但无论出于什么原因，它们都没有变得更简单，”Kaczorowski 说。

共同责任、谷歌的容器安全方法以及最近暴露的漏洞和其他相关主题是 Kaczorowski 的最新[新堆栈制造商播客](https://thenewstack.io/podcasts/makers)的主题，该播客于 5 月在巴塞罗那的 [KubeCon + CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/) 录制。

谷歌在共享安全领域也发挥了越来越大的作用。例如，Kubernetes 中内置的更多安全默认设置“正在从用户那里承担责任，”Kaczorowski 说。Kaczorowski 说，虽然用户仍然有责任申请[谷歌 Kubernetes 引擎]自动升级，但他们也可以“启用一项功能，让他们不再负责”。“如果他们愿意，他们仍然有能力做到这一点，但他们没有必要这样做，”Kaczorowski 说。“这是一个巨大的安全优势。”

Kaczorowski 说，谷歌对容器安全的看法分为三类:基础设施安全，涉及组织的容器开发环境如何安全。这涉及网络政策、用户身份管理、秘密管理和其他类似的政策。第二类是谷歌所谓的“软件供应链”，包括确保组织的容器安全地构建和部署，”Kaczorowski 说。通过这种方式，第二类涉及“在将映像部署到您的环境之前，通过扫描它们的漏洞并检查它们是否符合您的要求来了解您的映像来自何处，”Kaczorowski 说。Kaczorowski 说，第三类适用于容器运行时安全性和“确保你的容器安全运行”。

不过，Kaczorowski 说，谷歌 Kubernetes 引擎(GKE)和 Kubernetes 的共同责任模式可能很难理解。Kaczorowski 说，谷歌负责控制平面和升级组织的节点和“公司的二进制文件本身，但你要对你拥有的工人节点负责，然后应用这些升级”。“我认为许多其他云提供商也有类似的模式。因此，[组织需要确保所有这些都有良好的文档记录，并让用户了解他们负责什么。”

Kaczorowski 说，谷歌也对最近 Docker 暴露的漏洞和其他供应链攻击做出了反应，其许多客户也是如此。所以对我们来说，我相信对我们的许多客户来说，我们如何验证我们没有使用它，如果我们在使用，我们可以撤销它或重新部署它，或修补它或其他任何东西，”Kaczorowski 说。

扫描将继续在集装箱安全方面发挥关键作用。可用工具的范围也应该进一步扩大。Kaczorowski 说:“扫描容器漏洞扫描特别有趣，因为如果你能在第一时间阻止它进入你的环境，这比你在事后发现它要好。”

Kaczorowski 说:“因此，只要您能够将这些安全决策转移到左边，并让开发人员在它进入您的环境之前修复它，从安全的角度来看，它对您更好。”“因此，人们肯定对扫描和安全工具很感兴趣，”比如 Twistlock 提供的工具。

[https://www.youtube.com/embed/g2QtYQ0HjzE?feature=oembed](https://www.youtube.com/embed/g2QtYQ0HjzE?feature=oembed)

视频

### 在这个版本中:

[1:10:](https://thenewstack.simplecast.com/episodes/a-google-product-manager-on-where-your-container-security-begins-and-ends?t=1:10)Google 对容器安全性的看法是什么？
[5:49:](https://thenewstack.simplecast.com/episodes/a-google-product-manager-on-where-your-container-security-begins-and-ends?t=5:49) 那么，当您考虑集装箱扫描时，例如 Twistlock 提供的服务，您如何看待这一细分市场？
[13:26:](https://thenewstack.simplecast.com/episodes/a-google-product-manager-on-where-your-container-security-begins-and-ends?t=13:26) 最近的 Docker Hub 攻击对你有什么启示吗？
[17:52:](https://thenewstack.simplecast.com/episodes/a-google-product-manager-on-where-your-container-security-begins-and-ends?t=17:52) 在您描述的环境中，您是否看到任何开源项目开始考虑这个问题？
[24:00:](https://thenewstack.simplecast.com/episodes/a-google-product-manager-on-where-your-container-security-begins-and-ends?t=24:00) 有没有零信任模型的 Google 方法？
[28:01:](https://thenewstack.simplecast.com/episodes/a-google-product-manager-on-where-your-container-security-begins-and-ends?t=28:01) 您如何看待开源安全领域目前的发展？

[KubeCon + CloudNativeCon](https://events.linuxfoundation.org/events/kubecon-cloudnativecon-europe-2019/) 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>