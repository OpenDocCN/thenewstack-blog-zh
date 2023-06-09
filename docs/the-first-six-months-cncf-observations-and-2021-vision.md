# 前六个月:CNCF 观测和 2021 年展望

> 原文：<https://thenewstack.io/the-first-six-months-cncf-observations-and-2021-vision/>

[](https://twitter.com/pritianka)

 [普里扬卡·夏尔马

Priyanka 是云计算本地计算基金会(CNCF)的总经理。她拥有斯坦福大学的政治学学士学位，业余时间喜欢阅读和与她的狗奥利玩耍。](https://twitter.com/pritianka) [](https://twitter.com/pritianka)

作为总经理加入云计算原生计算基金会(CNCF)是一次令人惊叹的旅程。当我去年开始担任总经理时，我的目标是通过倾听了解社区的需求，然后在此基础上进行建设。然而，正如你们中的一些人可能已经听说的那样，CNCF 是实干家的基础——这意味着我在这里的这段时间里听了很多，做了很多。为了 kickstart，我与最终用户、项目贡献者、董事会成员、技术供应商和其他社区成员进行了数百次(可能是数千次)对话。我们发现了需要改进的地方，也发现了需要更深入思考的地方。在本文中，我将分享一些想法和我的理念，让# teamCloudNative 进入 2021 年。

## **在技术上**

我们在 CNCF 的使命是让原生云无处不在。该使命的一部分是确保我们为全球最终用户支持不断发展的开放技术堆栈。

在过去的六个月里，我花了很多时间探索云计算的下一步发展方向，包括电信、边缘计算、开放网络等等。云原生是实现 5G、边缘、物联网和人工智能融合的关键。跨社区协作对于我们实现这些技术的全部潜力至关重要。这就是为什么我们发起了[云本地网络功能(CNF)](https://github.com/cncf/cnf-wg) 工作组，帮助电信行业定义云本地对他们意味着什么。“毕业”成为电信公司使用的技术表明了 Kubernetes 生态系统的成熟；社区正在努力支持他们的任务关键型工作负载。

根据一些报道，边缘计算可能是比云更大的商机。它将成为下一波创新的平台，涵盖许多机会，如远程医疗保健、工业物联网、AR/VR，以及许多我们甚至还没有想到的机会。将云原生技术带到边缘将允许开发人员无缝部署到悉尼、旧金山和新加坡。让云原生技术在云中如此成功的范例——如可观察性、松耦合系统、声明式 API 和健壮的自动化——对 edge 来说甚至更加重要。虽然云计算能够依靠集中化和规模经济来构建其运营和业务模型，但这两者都不适用于边缘计算。由于硬件和软件分布在成百上千个位置，管理这些分布式系统的唯一可行方法是通过云原生技术提供的标准化和自动化。

从事云原生技术的开发人员是唯一有资格驱动在边缘上运行的应用程序的人，因为他们知道如何构建解耦的、有弹性的系统。将云原生开发人员社区连接到 edge 将为成千上万的开发人员建立职业生涯，并大大加快采用和创新。出于这个原因，随着 Kubernetes 项目和即将到来的边缘技术(如 [KubeEdge](https://kubeedge.io/en/) 、K3S 和 OpenYurt)的发展，CNCF 社区已经选择将创新推向边缘。我们正与 [LF Networking](https://www.lfnetworking.org/) 和 [LF Edge](https://www.lfedge.org/) 密切合作，发展这个社区，并将于今年在 [KubeCon Europe](https://www.cncf.io/events/kubecon-cloudnativecon-europe-2021/) 举办一次 Edge 活动。社区是云原生的一个关键组成部分，并将继续与 edge 在一起。

回到现在，Kubernetes 的开发者体验对所有雇主来说都是至关重要的。供应商已经赶上了托管发行版、干净集成等的潮流。在 CNCF，我们看到了一个明显的趋势，即转向开发人员已经熟悉的领域，即 GitOps 或基础设施即代码(IaC)。代码是如何将各种操作任务轻松集成到开发人员工作流中的。多个 CNCF 项目，如 Argo 和 OPA，使 IaC 成为可能，也有大量的供应商提供帮助。CNCF 贡献者的开发者体验正在发展、成熟和丰富。

随着 Kubernetes 的稳步发展，我们现在正在经历云原生技术的寒武纪大爆发——每一项贡献都很重要。很明显，我们必须优先考虑教育。对知识和学习的需求也相应增加，特别是因为居家订单迫使人们在没有社交陪伴的情况下在家中度过大部分生活。2020 年，70%的 KubeCon + CloudNativeCon 与会者是该活动和我们的生态系统的新成员；超过 163，000 人参加了我们的 edX Kubernetes 课程；超过 70，000 人参加了我们的认证考试。该社区正在为自己配备必要的技能，以构建跨行业和垂直领域的云原生技术。

随着原生云的激增，安全性仍然是重中之重。去年网络安全管理软件产品 Orion 软件的灾难性事件，BlueKai、Seina Weibo 等公司的违规事件，都告诉我们，除了传统的 AppSec 之外，零信任安全和 DevSecOps 对于组织保持在线安全至关重要。CNCF 主持了许多以安全为重点的项目，如法尔科、TUF 和公证人。此外，我们推出了[认证 Kubernetes 安全专家](https://training.linuxfoundation.org/certification/certified-kubernetes-security-specialist/)考试，以帮助个人和公司建立集装箱安全的工作知识。

云原生社区是开源中发展最快的社区。我们是实干家的基础。因此，我希望我们的技术领域在六个月内会有很大的改变，我期待在这里分享我的经验。

## **论领导力**

自 2016 年初以来，我一直是 CNCF 社区的一员，担任总经理一职对我来说是一种荣誉。加入后，我真正体会到了我之前的领导层对我们生态系统的能量和动力的精心打造和培育。为了推进这一目标，我的重点是推动信任，从而促进云原生生态系统的贡献和增长。虽然信任是一个抽象的术语，但它可以通过清晰的流程和透明的沟通来建立。我们正在将正确的步骤和检查点纳入我们运行的所有项目中，以确保我们通过我们所掌握的渠道与我们的社区保持联系——包括您正在阅读的这篇文章。

在组织方面，我发现成为 Linux 基金会的一员有助于 CNCF 获得规模经济和经验。与 Linux 基金会工作人员和其他 Linux 基金会项目的合作使我们能够接触到人员、技术和观点——这创造了一个远远大于各个部分的总和。Linux Foundation 团队及其基础设施提供了关键的支持和知识，使得开源社区能够取得成功。例如，我们与 [LF Events](https://events.linuxfoundation.org/) 的合作已经促成了世界上最大的开源会议:KubeCon + CloudNativeCon。在开放源代码中访问退伍军人也是非常宝贵的。在过去的一年里，我最大的收获是 Linux 基金会执行董事吉姆·泽姆林教给我的——我们必须在所有工作中运用耐心、外交手腕和同理心。

CNCF 的使命是让原生云无处不在。我的大部分职责是帮助将这些点连接起来，以识别和促进合作和创新的机会。除了直觉型的性格，我对学习和倾听他人的关注也是我的两大优势。为了不断学习，我跟随我们社区的专家，阅读他们的内容。有时候，我会玩人们分享的演示。我还在继续我的倾听之旅，这是我加入基金会时开始的。我欢迎任何阅读这篇文章的人与我分享他们的观点。

我越来越意识到我们正生活在一个前所未有的时代。领导这个社区意味着支持组成这个社区的人类。有时候，人们需要鼓励，有时候他们需要机会。最近太多时候，我们可能需要 Twitter 上有趣的迷因来减轻我们所有人感受到的痛苦和苦难。在 CNCF，我们致力于实践人性化的开源营销和社区拓展。

## 【2021 年愿景

CNCF 将继续建立终端用户驱动的开源，为开源代码和社区发展树立黄金标准。我们的目标是用资源和项目来支持项目，并将它们与技术的消费者更紧密地联系起来。我们将通过提供资源、强调他们的贡献和庆祝他们的成功来继续投资于最终用户社区。我们将始终为他们的最大利益而战。

我们将确保 CNCF 项目因其稳定性和企业就绪性而闻名。这也是我们将利用现有终端用户的知识，与 tech radars 分享成功案例和技术评估的地方。我们还将投资于一些项目，以改善项目满足基础设施需求的方式。

# teamCloudNative 将发展成为一个越来越多元化、越来越有同理心的社区，以增强我们由多元化驱动的弹性。我们将在在线节目、实体活动和讲故事方面努力工作，将我们的影响力扩展到全球各个角落。云原生将是一个欢迎所有人的地方，旗舰计划如[包容性命名](https://inclusivenaming.org/)，多样性奖学金和项目导师。2020 年，我们将根据我们在这一领域的发展，通过培训和认证，帮助所有希望在云原生原则基础上进行开发的开发人员。

在人类层面上，继毁灭性的 2020 年之后，2021 年将是充满新挑战的一年。在过去的一年里，# teamCloudNative 证明了自己的韧性。我们现在必须再做一次，创造另一个“新常态”。具有全球影响力的开源软件正是为了应对这些挑战而构建的。CNCF 将不断迭代，为我们的生态系统带来社区和增长，无论我们发现自己处于何种情况。我们的 KubeCon + CloudNativeCon 活动将尽可能以最安全、最包容的方式举行，保证会很有趣。

我领导 CNCF 的头六个月是一段激动人心的成长经历。我学到了，服务了，并将继续为生态系统尽我所能。我对我们的社区和它在逆境中表现出的多样性活力感到敬畏。我期待着在未来的六个月、几年甚至几十年里共同建设。我们开始吧！

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>