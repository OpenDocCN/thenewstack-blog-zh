# KubeCon Europe 2021 的 CI/CD 亮点

> 原文：<https://thenewstack.io/ci-cd-highlights-from-kubecon-europe-2021/>

[](https://www.linkedin.com/in/clarkchris1/)

 [克里斯·克拉克

克里斯是云铸造基金会的技术运营经理。他是一名软件工程师和项目经理，专注于 JavaScript 和 Node.js 开发。](https://www.linkedin.com/in/clarkchris1/) [](https://www.linkedin.com/in/clarkchris1/)

[kube con+CloudNativeCon Europe 2021–Virtual](https://events.linuxfoundation.org/kubecon-cloudnativecon-europe/)几周前已经结束，我们现在有一个会议讨论的宝库，可以在闲暇时观看。他们有 225 人！

我已经设法赶上了其中的一些。虽然从这种规模的事件中总是有相当多的收获，但我想关注一个相当明显的:随着企业优先考虑他们的 DevOps 方法，对持续集成/持续交付(CI/CD)的关注继续增加。

在这里，我想强调最近 KubeCon 的三个我认为值得一看的演讲。然后，我将得出一些结论，我认为这些结论可能对组织评估其 CI/CD 需求和构建管道的方法有价值。

[https://www.youtube.com/embed/qVvnaezEHoo?feature=oembed](https://www.youtube.com/embed/qVvnaezEHoo?feature=oembed)

视频

卡拉·德拉马克和法提赫·德吉蒙西强调了 CI/CD 中互操作性的众多好处，以及它如何帮助管理复杂性并使更改更容易。[持续交付基金会](https://cd.foundation/)正在做一些出色的工作，使这一景观更加标准化和平易近人。

[https://www.youtube.com/embed/_DgCc4-BLW8?list=PLkKJU_Jc3_rDycS3U4iE5hpOVSA_GmWPe](https://www.youtube.com/embed/_DgCc4-BLW8?list=PLkKJU_Jc3_rDycS3U4iE5hpOVSA_GmWPe)

视频

在上面的演讲中，Juergen Etzelstorfer 和 Karthik Satchitanand 深入探讨了开发和生产环境之间的奇偶校验的重要性，以及 [LitmusChaos](https://chaosnative.com/) 如何在整体应用弹性方面提供急需的帮助。他们建议:“打破开发中的所有东西，而不是生产。”

[https://www.youtube.com/embed/qjY2Df-Po-g?feature=oembed](https://www.youtube.com/embed/qjY2Df-Po-g?feature=oembed)

视频

Vibhav Bodade 和 Vincent Demeester 介绍了调试 Tekton 的各个方面。与此相关，我想指出 IBM 有一个[有用的教程](https://www.ibm.com/cloud/architecture/tutorials/introduce-tekton-pipelines-by-using-cloud-foundry-app-toolchain/)，关于创建一个基于 Tekton 的交付管道来部署一个简单的应用到 Cloud Foundry。

## 外卖食品

现在这个领域发生了很多事情，而且原因很充分。连续交付提高了生产率和部署速度，并且关于您的 CI/CD 方法的决策对您的组织的整体效率有巨大的影响。这是一个日益动态和复杂的领域，任何现代技术团队都无法忽视。

选择哪些云原生方法(包括 CI/CD 工具)适合您的组织本身就非常复杂，甚至令人望而生畏。在某些情况下，这种复杂性允许进行有价值的定制，以满足您的特定业务需求。然而，在其他情况下，这种复杂性可能会成为不必要的负担，减缓开发并阻碍重要的工作。在后一种情况下，一个固执己见的平台，比如 Cloud Foundry，可能最适合您的需求。

蓝绿色部署、金丝雀节点以及与您最喜爱的 CI/CD 工具的现成互操作性是我向任何评估其 DevOps 需求的企业推荐的一些基本基准。Tekton、Circle CI、Travis CI、GitHub Actions、Concourse CI——它们要么已经拥有对 Cloud Foundry API 的本地支持，要么可以非常容易地集成。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>