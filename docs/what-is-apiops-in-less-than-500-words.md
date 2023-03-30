# 什么是 APIOps？(少于 500 字)

> 原文：<https://thenewstack.io/what-is-apiops-in-less-than-500-words/>

让我们省去介绍和关键字填充，直接进入您正在寻找的答案——API ops 是一个相对较新的术语，描述了一种构建 API 的方法，它结合了:

*   来自蓬勃发展的 DevOps 文化的自动化、协作、快速迭代和对质量的关注。
*   来自 GitOps 的 CI/CD 管道的唯一真实来源和重点。

APIOps 通常由平台工程团队或 API 平台团队实施和实践，他们全权负责创建和维护基础设施和防护栏，开发人员可以在其中使用整个 API 生命周期的高度迭代和自动化工作流来构建和部署[API](https://thenewstack.io/apis-are-where-fun-happens/)。

虽然这看起来令人生畏，但是即使你的操作工程师是多面手而不是 API 爱好者，APIOps 也是可以实现的。首先，APIOps 从一个契约中受益匪浅，这个契约使用像 [OpenAPI 这样的规范，作为 API 的唯一来源。](https://www.openapis.org/)该合同定义了 API 在其生命周期中的功能和操作特征，并由 git 进行管理，以确保在您的组织尝试使用该 API 解决业务问题时，它是唯一的、可审计的事实来源。

一旦您的组织完成了设计，您的前端和后端团队就可以开始用他们选择的语言/框架编写客户端和服务器端的实现。平台或运营工程师可以生成声明性配置，定义 Kubernetes 集群和微服务在部署后的行为。

这甚至可以包括部署 Kubernetes 网关本身所需的一切，这正是 [Kusk](https://kusk.io/) 所做的。

任何人都可以利用额外的工具，能够阅读您的 [OpenAPI 设计](https://thenewstack.io/what-it-means-to-be-openapi-first-in-kubernetes/)，创建工件，如最新的文档或模拟数据，以在您的团队并行实现时解除对他们的阻碍。您的平台/运营团队可以为开发人员配备自助服务工具和自动化，如直接在其 IDE(集成开发环境)中进行质量、安全性和合规性验证，以简化他们的工作，即使更多的[认知负荷](https://thenewstack.io/platform-engineering-in-2023-dev-first-collaboration-and-apis/)转移到左侧。

## APIOps 对 Kubernetes 有什么价值？

与 DevOps 和 GitOps 一样，APIOps 创建了一个标准化的流程和协作文化，以加速您的组织在整个客户/最终用户生命周期中创建和维护 API 的方式。

一些主要优势包括:

*   由于基于 OpenAPI 的模拟工具，开发人员并行工作，而不是相互阻塞。
*   将安全性、治理和代码质量转移到左边，而不用用编码的标准和验证器来压倒开发人员。
*   从前端/后端开发人员到运营/平台工程师，整个 API 生命周期的单一事实来源，了解是什么使 API 在生产中获得成功。
*   API 生命周期不同阶段之间的自动转换，支持高度迭代的工作流，无需操作或平台工程师的手动参与来“保持车轮转动”

这就是 APIOps 如何帮助您的组织以更高质量的代码更快地创建 API，同时鼓励协作文化。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>