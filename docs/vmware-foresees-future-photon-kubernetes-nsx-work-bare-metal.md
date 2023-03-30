# VMware 预见了光子、库伯内特和 NSX 在裸机上工作的未来

> 原文：<https://thenewstack.io/vmware-foresees-future-photon-kubernetes-nsx-work-bare-metal/>

对于一家经常被描绘为“虚拟机管理程序公司”的公司[，](https://virtualizationreview.com/articles/2016/06/07/vmware-has-had-the-leaders-it-needs.aspx)看到 VMware 在可能完全没有虚拟机管理程序的数据中心为自己开创未来令人惊讶。虽然 VMware 的 VSP here Integrated Containers(VIC)是为与其 ESX 虚拟机管理程序一起工作而[设计的，但其 Photon 平台满足了新兴服务器类别的独特需求，这也是本出版物的突出重点:可扩展集群。](https://thenewstack.io/vmware-integrated-containers-may-introduce-docker-enterprise/)

去年在拉斯维加斯的 VMworld 大会上，VMware 高管向 Kubernetes 承诺支持 VMware 的[光子](https://vmware.github.io/photon/)容器主机，允许开源编排与其 [NSX 网络虚拟化平台](http://www.vmware.com/products/nsx.html)一起工作。周四上午，该公司在这个方向上迈出了下一大步，告诉新的堆栈它正在启动一个项目的测试版，该项目将通过 Kubernetes 自己的[容器网络接口](https://github.com/containernetworking/cni) (CNI)将 Photon 链接到 [Kubernetes](/category/kubernetes/) 容器编排引擎。

VMware NSX 副总裁 [Milin Desai](https://www.linkedin.com/in/milin-desai-464757/) 在接受新堆栈采访时承认，通过这种方式，Kubernetes 应该能够直接支持网络微分段——根据规则，不仅按应用程序，而且按功能细分网络。他告诉我们，在微服务环境中，微分段在每个 pod 上是可行的。

“通过 Kubernetes 界面，您现在可以创建由 NSX 提供的网络和细分政策，”Desai 说。“你总是可以预先创建一个覆盖网络，然后将一个容器插入它上面的 Kubernetes pod。但在这种情况下，您是作为 [DevOps](/category/devops/) 工作流的一部分，通过 Kubernetes CLI，通过 CNI，进入 NSX，然后按需提供网络，按需提供安全组，并允许无缝集成。”

[NSX-T](https://substructurenetworks.wordpress.com/2016/05/04/the-new-release-of-nsx-codename-transformers-with-a-unified-code-stream-vdm30in30-day-4/) 是 VMware NSX 平台的替代版本，旨在支持替代的开源虚拟机管理程序，如 [KVM](http://www.linux-kvm.org/page/Main_Page) ，或管理裸机上的网络虚拟化。到目前为止，VMware 还没有公开谈论过 NSX-T，尽管私下里它是去年在代号“变形金刚”下开发的[，旨在在某些情况下取代一个名为“NSX 边缘”的组件(不打算说三次真快)。NSX Edge 最初旨在用作网络服务网关或远程逻辑路由器，但人们发现它还具有将 NSX 虚拟网络扩展到裸机的优势。](https://substructurenetworks.wordpress.com/2016/05/04/the-new-release-of-nsx-codename-transformers-with-a-unified-code-stream-vdm30in30-day-4/)

到目前为止，看似无限可扩展性的容器化的问题是，它似乎不可能确保安全。将微服务模型与当今的安全框架相结合是去年 RSA 安全会议的一个主题，这个主题似乎与美国总统与 Sally Yates 和解的希望一样大。

将微分段捆绑到 Kubernetes 上的解决方案以前也有人提出过，但通常都是禁用 Kubernetes 代理进程并移植一个开源网络控制器。VMware 推出的 NSX-T 新解决方案看起来确实没那么混乱，至少目前如此。根据德赛的说法，这是与 Kubernetes 社区共同达成的，它使用了管弦乐队现有的 CNI 框架。

去年 11 月， [Cloud Foundry 开始实施一个可插拔的网络堆栈](https://www.cloudfoundry.org/meet-new-container-networking-stack-cloud-foundry/)它称之为 [**netman-release**](https://github.com/cloudfoundry-incubator/cf-networking-release) ，它的基金会将其描述为一个过渡系统，随着时间的推移，它将把用户转移到一个新的网络模型。Desai 指出，由于该堆栈是基于为 Kubernetes 设计并打算与 CNI 一起使用的[法兰绒网络结构](https://github.com/coreos/flannel)，这为使用 Java、Ruby 或 Go 对网络层进行直接编程开辟了新的途径。他说，VMware 对这一努力的所有贡献都将“公开”，尽管这可能离完全开源的参与还差一步。

在其当前的 beta 版本中，Kubernetes + Photon 配对确实需要一个虚拟机管理程序作为其基础。但是随着项目的发展，Desai 告诉我们，VMware 打算让客户在裸机上部署 Photon，使用 NSX-T 作为网络层，使用 Kubernetes 作为编排器。

“光子平台、NSX-T 和运行在其上的 Kubernetes 的结合，是我们 VMware 正在努力实现的，”德赛说，“以安全的方式完全自动化集装箱的端到端交付。基础设施几乎看不见了。Photon 向 Kubernetes 提供了一个单一的基础设施 API，建立了 pod，保护了它们，并在未来超高效地扩展它们。”

Desai 承认，如果将正在进行的 CRI-O 项目添加到 mix 中，它将有可能自动部署来自其存储库的容器映像，直接响应网络条件，而无需 Docker 或 CoreOS **rkt** 等容器引擎的参与。

去年 8 月，VMware 官员告诉新的堆栈，Photon 最终将获得一个调度和编排组件。如果这个 Kubernetes 项目按计划进行，VMware 可能不需要或不想制作一个。

专题图片:[1932 年 2 月《惊奇故事》杂志封面](https://en.wikipedia.org/wiki/Jack_Williamson#/media/File:Wonder_stories_193202.jpg)，公共领域。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>