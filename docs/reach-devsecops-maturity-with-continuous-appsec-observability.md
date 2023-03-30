# 通过持续的 AppSec 可观察性达到 DevSecOps 成熟度

> 原文：<https://thenewstack.io/reach-devsecops-maturity-with-continuous-appsec-observability/>

[](https://www.linkedin.com/in/kirankamity/)

[Kiran Kamity](https://www.linkedin.com/in/kirankamity/)

[Kiran 是一位充满激情的硅谷连续创业者，也是 DeepFactor.io 的创始人/首席执行官。他之前是思科 Cloud BU 的产品负责人，ContainerX(被思科收购)的创始人/首席执行官，以及 RingCube(被思杰收购)的创始人/副总裁。](https://www.linkedin.com/in/kirankamity/)

[](https://www.linkedin.com/in/kirankamity/)[](https://www.linkedin.com/in/kirankamity/)

对于许多企业来说，应用程序现代化——从 monoliths 到云原生微服务架构的整体过渡——为评估整个应用程序开发生命周期的改进提供了机会。近几年来，Kubernetes 的迅速流行见证了 DevOps 实践和平台的大量采用，使得工程部门每周、每天甚至更快地发布新的应用。

然而，这些相同的改进和流程，加上日益复杂和扩展的微服务应用，带来了对软件开发生命周期(SDLC)更多可见性的需求，应用安全团队正在努力跟上安全、隐私和合规性风险的急剧增加。根据 Kubernetes 安全报告[的 Red Hat State](https://www.redhat.com/en/engage/state-kubernetes-security-s-202106210910)显示，安全问题已经导致许多企业推迟将 Kubernetes 应用程序部署到生产环境中，94%的受访者在过去 12 个月中至少经历过一次 Kubernetes 环境中的安全事件。

许多企业未能实现和实践 DevSecOps，仅仅是因为弥合软件开发和安全性之间的差距的操作挑战。然而，随着公司开始成熟和“左移”，开发人员面临着在软件开发的早期阶段提取有意义和可操作的见解的压力。对于许多企业来说，现有的应用程序安全方法通常是不成熟和被动的。许多漏洞和安全风险在开发过程的后期未被发现，导致不合时宜的延迟和潜在的违规，因为工程人员希望将新功能开发优先于解决安全风险。

近年来，下一代应用程序监控平台已经开始引入“持续可观察性”,以此来全面了解应用程序生命周期的每个阶段。理想情况下，持续的可观察性应使组织能够持续、主动地监控应用程序，以了解哪些应用程序运行缓慢或出现故障，并快速识别潜在的性能和稳定性改进。不幸的是，许多可观察性工具并不是为解决应用程序安全性中的独特需求而设计的。

展望未来，持续的 AppSec 可观察性正迅速成为 DevSecOps 成熟度的下一个阶段，许多企业将在向云原生应用的数字化转型过程中实现这一目标。通过观察每个线程/进程/容器中的数十亿个实时遥测事件，持续的 AppSec 可观察性可以帮助开发人员、QA 和安全团队在应用从测试和试运行过渡到生产之前，识别运行期间的供应链风险、系统调用风险、数据风险和行为风险。最终，目标是“从左边开始”，安全成为 CI/CD 管道中完全集成的一部分，在运行的应用程序中可以观察到漏洞。

传统的传统应用程序安全工具，如静态应用程序安全测试(SAST)和软件组合分析(SCA)，缺乏对应用程序运行时的可见性，导致冗长、复杂的报告，具有不必要的高警报量和误报。这种“噪音”造成了压倒性的“警觉疲劳”感，阻碍了工程师快速准确地对问题进行优先排序和分类。此外，在软件组件上收集的大量信息——有些甚至从未在运行时加载——可能会影响组织为拜登总统关于改善国家网络安全的[行政命令](https://www.whitehouse.gov/briefing-room/presidential-actions/2021/05/12/executive-order-on-improving-the-nations-cybersecurity/)创建准确和精炼的软件材料清单(SBOM)的能力。

引入连续 AppSec 可观察性还可以增强其他 AppSec 工具，如 DAST(动态应用程序安全测试)和 CIS(集装箱图像扫描)，为它们提供运行应用程序“幕后”的视图。无论您是使用应用程序来发现开放 Web 应用程序安全项目(OWASP)漏洞，还是在构建过程中使用容器扫描器来生成应用程序依赖项和映像的详尽报告，持续 AppSec 观察的目标都应该是通过更深入、“语义上”更丰富的洞察来增强您的发现。

随着越来越多的企业希望通过应用程序现代化来保护投资并利用基础设施和软件进步，开发人员和应用程序安全专业人员应该评估具有以下特点的下一代安全平台:

*   满足开发、QA 和 AppSec 的需求，而不会给 DevSecOps 管道带来显著的运营开销或复杂性。这包括找到一些不需要修改代码就能提供有价值的见解的东西。
*   使用任何语言的应用程序，无论它是在容器、虚拟机还是在 Kubernetes 集群中运行。
*   通过在功能和安全测试期间提供对正在运行的应用程序的实时可见性，补充管道中的现有工具，如 SAST、SCA、DAST 和 CIS。
*   通过突出显示运行时使用的组件以及调用的函数和类路径(如果可能),为工程人员提供每个应用程序的漏洞和警报的优先化和细化列表。

最终，为了达到 DevSecOps 的成熟度，企业必须使持续的 AppSec 可观察性成为 CI/CD 管道的一部分，以快速保护源代码。这使得工程设计领导层能够加快生产效率，并减少生产前补救(MTTR)安全和合规性风险的平均时间。同时授权应用程序安全团队建立防护栏、确定警报优先级并在发布前降低安全风险。

![](img/f620400d3f58d723440a85aa65739860.png)

*要了解更多关于 DevOps 和其他云原生技术的信息，请考虑参加 10 月 11 日至 15 日举行的 [KubeCon+CloudNativeCon 北美 2021](https://events.linuxfoundation.org/kubecon-cloudnativecon-north-america/) 。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>