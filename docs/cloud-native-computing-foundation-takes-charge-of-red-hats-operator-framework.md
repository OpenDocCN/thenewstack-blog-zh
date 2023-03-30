# 云计算原生计算基金会负责红帽的运营商框架

> 原文：<https://thenewstack.io/cloud-native-computing-foundation-takes-charge-of-red-hats-operator-framework/>

红帽的[运营商框架](http://operatorframework.io)已经在孵化层面加入了[云原生计算基金会](https://www.cncf.io/) (CNCF)，跳过了沙盒，就像上周早些时候 [Contour 加入](https://thenewstack.io/contour-ingress-controller-join-cncf-at-incubation-level/)一样。该项目最初由 CoreOS 在该公司于 2018 年被 Red Hat 收购之前创建，是一个开源工具包，用于以自动化和可扩展的方式管理 Kubernetes 原生应用程序，称为 Operators。

Red Hat 运营商框架维护者兼社区发展总监 Diane Mueller[表示:“被认可为 CNCF 景观的一部分的好处是，真正获得了与 CNCF 生态系统中的所有其他项目和所有其他人合作，继续开发该框架的平台和空间。“CNCF 的主要好处之一是培育这些项目，加上我们可以与其他 CNCF 项目进行对话。这真的会扩大运营商框架的范围，我们真的很高兴。”](https://ca.linkedin.com/in/muellerdiane)

[Red Hat 的产品经理、运营商框架维护者 Rob Szumski](https://www.linkedin.com/in/robszumski) 解释说，运营商框架解释了项目的起源。

“CoreOS 对运行非无状态应用程序非常感兴趣，推动了 Kubernetes 的边界，并开始进入第三波应用程序；不仅仅是无状态，不仅仅是有状态，这些都需要高度的协调，最有可能的是，嵌入式应用程序知识和操作知识，”Szumski 说。“我们不想就此止步。我们希望每个工作负载都以这种方式表达，因此我们必须构建一套工具来帮助您做到这一点。运营商框架就是在这里诞生的。”

操作员框架由两个主要组件组成:操作员 SDK[和操作员生命周期管理器(OLM)](https://github.com/operator-framework/operator-sdk)和[两者都可以独立运行。](https://github.com/operator-framework/operator-lifecycle-manager)

Operator SDK 提供高级 API 和脚手架来更容易地构建、测试和验证操作符，使用[控制器-运行时](https://github.com/kubernetes-sigs/controller-runtime)库来使编写操作符更容易。OLM 提供了一种在集群中安装、管理和升级操作员及其依赖项的声明性方法，以及从“目录”中发现、安装和自动更新操作员的能力目录是 OLM 中的一种打包格式，允许操作员表达对平台和其他操作员的依赖关系。除了这些目录之外，OLM 还提供了操作员可发现性和集群稳定性，防止冲突的操作员拥有相同的 API。

[https://www.youtube.com/embed/0ctHLb5DPp8?feature=oembed](https://www.youtube.com/embed/0ctHLb5DPp8?feature=oembed)

视频

在讨论运营商时，Mueller 和 Szumski 都强调了运营商的“第二天”方面，这可以使他们超越 Helm 等公司可能提供的简单安装功能。通过 Operator SDK 和 OLM 的结合，他们说 Operator Framework 可以将操作知识添加到软件中，并在示例中指出了操作员能力级别的图表。

Szumski 关注的另一个关键特性是测试，他说这需要一种不同于标准应用程序的思考方式。

“这是一种不同的编程风格，因为您不断地与状态不断变化的 Kubernetes 集群对话。如你所知，吊舱来来去去，周围的东西变得分散，吊舱在毫秒内启动，这个软件对此做出反应，以便采取补救措施。例如，如果应用程序的一个重要部分出现故障，it 部门可以将其恢复。这个 SDK 帮助你开发并测试它。可以想象，在 Kubernetes 集群的动态环境中，您希望确保这些事情能够很好地运行。因此，我们内置了一些测试工具来帮助您，”Szumski 说。

在这方面，他说团队正致力于对 [KUbernetes 测试工具(KUTTL)](https://github.com/kudobuilder/kuttl) 的新整合，该工具提供了测试 KUbernetes 操作者的声明性方法。

至于[运营商中心](http://operatorhub.io)的未来，它将与运营商框架分开，目前不会捐赠给 CNCF。

云计算原生计算基金会是新堆栈的赞助商。

专题图片由来自 Pixabay 的 Gerry Carley 提供。

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特(Twitter)或脸书(T2)与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[反馈@thenewstack.io](mailto:feedback@thenewstack.io) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>