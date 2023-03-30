# 用 Bottlerocket 进一步推动容器创新

> 原文：<https://thenewstack.io/giving-container-innovation-a-further-boost-with-bottlerocket/>

亚马逊网络服务(AWS) 赞助了这篇文章。

 [马特·阿萨伊

Matt 是 AWS 的负责人，参与了开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) 

早在 2014 年，Redmonk 分析师 [Stephen O'Grady 暗示](https://redmonk.com/sogrady/2014/08/06/atomic-unit-computing/)也许，仅仅是也许，容器将取代虚拟机——虚拟机已经取代操作系统，或 OS，成为“计算的原子单位”快进到 2020 年，奥格雷迪的预言实现了。或者将会是，一旦容器成为真正的主流。

考虑到我们谈论容器的次数，假设容器被广泛采用是很方便的。不是的。例如，2019 年 [Gartner 报告](https://www.gartner.com/doc/3955920?ref=TrackDBDailyEmail&refval=1565014105683)指出，“到 2023 年，超过 70%的全球组织将在生产中运行两个以上的容器化应用，高于 2019 年的不到 20%。”这是一种快速的采用(新的堆栈在之前已经涉及到了这一点),但是它使得大多数应用程序目前还没有容器化。

为了帮助企业获得容器带来的好处，包括增加的可移植性和更高的效率，我们需要让企业更容易大规模采用和使用容器。幸运的是，我们现在有点被选择宠坏了，Kubernetes 和其他开源创新就是为了做到这一点。一个新的选择是 [Bottlerocket](https://aws.amazon.com/bottlerocket/) ，这是一个开源的、基于 Linux 的操作系统，设计用于在虚拟机或裸机主机上运行容器。但是，如果容器是计算的新的原子单位，为什么我们仍然在谈论操作系统，甚至是一个专门为运行容器而构建的操作系统？

## 从不同的角度思考操作系统

正如无服务器没有消除对服务器的潜在需求一样，容器仍然需要操作系统。不幸的是，大多数容器运行在通用操作系统上。因为容器使得向外扩展变得容易，所以基于容器的主机环境可能会增长到数百或数千个实例。这种规模带来了操作系统安全性、更新、开销等问题。

AWS 在 2020 年开源的 Bottlerocket 不是第一个以容器为中心的操作系统，也不是唯一的选择。红帽有 CoreOS。谷歌也有自己的基于 Chromium 的容器优化操作系统。SUSE 公司则提供[微波炉](https://en.opensuse.org/Kubic:MicroOS)。在开源领域，拥有选择权是一件很棒的事情。这意味着客户有选择，但也意味着不同的项目可以相互学习，并相应地改进。

当然，多样化的选择对用户和他们的社区来说并不总是最好的事情。有时候，为现有的项目做贡献是最好的，但并不总是这样。考虑一下 Kubernetes。谷歌本可以采用 Docker 或(当时的)Mesosphere，但它拥有经过多年内部使用磨练的有趣技术，开源是一个更好的计划。Bottlerocket 也是如此。是的，有替代方案，但没有一个融合了 AWS 在无与伦比的规模下运行容器的经验。我们最好重新开始。

那么，Bottlerocket 有什么不同，你是否应该考虑投稿？

Bottlerock 使您能够自动更新托管您的容器的数千个实例，同时对您的应用程序造成最小的中断，从而提高了正常运行时间。与通用操作系统中的逐包更新不同，Bottlerocket 只需一步即可应用更新，并且在出现故障时可以回滚。Bottlerocket 还提高了可管理性，使您能够使用 orchestrators(如 Kubernetes)来服务操作系统，并在容器中运行您的应用程序，而不会引入包管理器的复杂性。此外，Bottlerocket 通过排除不需要的组件来运行容器，从而提高了资源利用率、引导时间和整体安全性。

安全仍然是[企业引用](https://www.zdnet.com/article/survey-security-is-top-worry-as-it-container-use-accelerates/)对集装箱保持警惕的主要原因之一。除此之外，Bottlerocket 使用的文件系统主要是只读的，并且在引导时通过 dm-verity 进行完整性检查。此外，如果 Bottlerocket 在底层块设备上检测到损坏，内核将被配置为重新启动，从而允许系统失败关闭。事实上，所有第一方 Bottlerocket 组件都是用 Rust 编写的，Rust 是一种安全第一的编程语言，它消除了一些内存安全问题，同时也鼓励有助于安全性的设计模式。

Bottlerocket 是 AWS 从大规模运行容器中学到的东西的顶点，让每个人都有能力通过自动化安全有效地完成这项工作。AWS 客户已经从我们运行容器的方式中受益，我们希望确保其他人，包括那些可能永远不会成为 AWS 客户的人，也能获得同样的技术。这项技术是独一无二的，我们认为这将真正有助于推动集装箱技术的发展。

## 一个充满容器创新的世界

当然，开源最大的好处之一，正如前面提到的，就是每个人都可以根据自己的长处做出贡献。比如 Weaveworks，[在 2019 年发布了 Footloose](https://www.weave.works/blog/an-introduction-to-footloose-containers-that-look-like-vms)。Footloose 创建了外观和行为都像虚拟机的容器。这解决了一个与 Bottlerocket 完全不同的问题，使这个新的容器世界对那些在虚拟机上长大的人来说更加舒适。还有 [containerd](https://www.docker.com/blog/what-is-containerd-runtime/) ，一个在 Docker 上创建的容器运行时，允许平台开发者使用容器进行构建，而不需要担心特定于操作系统的功能。或者还有 [Argo CD](https://argoproj.github.io/argo-cd/) ，这是一个连续交付工具，由 Intuit 在 2018 年开源，使自动化、审计和理解基于容器的应用程序部署和生命周期管理变得简单明了。

这些只是 Bottlerocket 诞生的蓬勃发展的开源容器生态系统的一小部分。这些项目中的每一个都以不同的方式改善了容器体验。虽然我们希望你能在 Bottlerocket 上提供帮助，但也许其他项目更适合你的需要。不管怎样，当我们有所贡献时，我们都会受益。

通过 Bottlerocket，AWS 正在贡献独特的专业知识和代码，以帮助企业消除大规模运行容器的障碍。因为 Bottlerocket 是 100%开源的，我们希望其他人能加入我们来进一步改进 Bottlerocket(你可以[在 GitHub](https://github.com/bottlerocket-os) ) *或*上开始学习 Bottlerocket 的创新，并将这些知识应用到其他项目中。这就是开源的工作方式。

如果你还没准备好投稿，但想了解更多，请[访问公告页面](https://aws.amazon.com/blogs/opensource/announcing-the-general-availability-of-bottlerocket-an-open-source-linux-distribution-purpose-built-to-run-containers/)。

通过 Pixabay 的特征图像。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特(Twitter)或脸书(T2)与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[反馈@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>