# 耶格从 CNCF 大学毕业，看到了没有本土客户的未来

> 原文：<https://thenewstack.io/jaeger-graduates-cncf-sees-a-future-without-native-jaeger-clients/>

[Jaeger](https://www.jaegertracing.io/) ，开源的端到端分布式追踪软件，成为本周正式达到[云原生计算基金会(CNCF)](https://www.cncf.io/) 的[毕业水平](https://www.cncf.io/projects/)的第七个项目，加入了 Kubernetes、Prometheus、Envoy、CoreDNS、containerd 和 Fluentd 的行列。Jaeger first [于 2017 年加入 CNCF](https://thenewstack.io/cncf-adds-oracle-onboards-envoy-jaeger-projects/) ，同时担任特使，现在它的毕业紧随特使仅一年之后。

Jaeger 维护者 Yuri Shkuro 表示，毕业级别的项目已经获得了“批准”，说明毕业评审过程确实确保了项目可以投入生产使用。

“这是一个相当有趣的过程。从表面上看，毕业标准并没有那么难，但当我们开始与来自 Lyft 的 Matt Klein 合作时，他是我们毕业的赞助商，我们进入了尽职调查，有更多的细节需要我们提供。有很多关于项目健康、社区健康、技术本身健康、代码质量的问题，”Shkuro 告诉 New Stack。“作为先决条件，我们还进行了安全审计，这是一次相当有趣的经历。安全审计揭示了我们希望解决的某些问题，这可能是最大的一块工作。”

总之，从求婚到毕业只用了一个多月的时间。然而，为了达到这一点，Jaeger 近年来一直在建设其功能和用户群，拥有 15 个活跃的维护者，1200 多个贡献者和 375 个提交和拉请求的作者，以及 9000 个 GitHub 明星，1000 万个 Docker Hub 拉，2800 个 Twitter 关注者和 815 个 Gitter 渠道成员。Shkuro 还强调了不同存储选项和不同安全和认证选项(如 Kafka 认证)的添加，这些选项包括“对后端的大部分社区贡献”以及由核心维护者开发的新核心功能。

根据一份声明，自 2017 年开始孵化以来，耶格已经完成了 14 个版本，包括支持 [OpenTracing](https://opentracing.io/) 和替代仪器 API，如 [Zipkin](https://zipkin.io/) 。在 CNCF 内部，耶格还集成了 [OpenTelemetry](https://opentelemetry.io/) 、 [Envoy](https://www.envoyproxy.io/) 服务代理和 [Prometheus](https://prometheus.io/) 监控工具。Shkuro 指出，这种与 OpenTracing 以及后来的 OpenTelemetry 的集成，使 Jaeger 的维护人员能够专注于构建后端而不是仪器。展望未来，Shkuro 说 OpenTelemetry 可能会使原生 Jaeger 客户端不再必要。

Shkuro 说:“OpenTelemetry 的标准库默认情况下将随 Jaeger 的导出程序一起提供，因此，理论上，一旦出现某种功能极性，我们甚至可能会停止开发原生 Jaeger 客户端，因为维护它们已经没有多大意义了。”“将会有一个通用的 SDK，人们可以将它用于仪器，SDK 可以以任何格式发送数据，如果我们需要的话，包括 Jaeger 格式。我认为这是明年可能会发生的一件大事。一旦 OpenTelemetry 进入生产状态，我们可以认真考虑减少两个项目之间的一些重叠。”

展望未来，Shkuro 说，他认为以编程的方式为痕迹的数据挖掘提供一个平台和框架可能是该项目的下一个重点。

“如果你将 Jaeger 与商业应用性能管理(APM)产品进行比较，它看起来相当基础，因为我们没有资源来实际构建所有花哨的功能，”Shkuro 说。“我认为有机会建立一个可重复使用的数据挖掘组件的集合，人们可以使用这些组件并从数据中建立自己的见解。”

至于那些传统的 APM 产品，Shkuro 表示，微服务确实改变了需求，跟踪更适合微服务时代。

Shkuor 说，我认为微服务创造了“一种全新的问题”。“这不一定是传统 APM 工具的设计初衷。在微服务和深度系统的新环境中，跟踪成为您了解这些系统运行情况的唯一工具。很长一段时间以来，人们对[APM]的兴趣非常冷淡，但现在很多人都意识到，如果没有某种跟踪功能和架构，他们就无法真正摆脱这些深度微服务架构。”

云计算原生计算基金会是新堆栈的赞助商。

来自 Pixabay 的穆罕默德·哈桑特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>