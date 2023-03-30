# 在 Kubernetes 中 OpenAPI-First 意味着什么

> 原文：<https://thenewstack.io/what-it-means-to-be-openapi-first-in-kubernetes/>

OpenAPI (以前称为 Swagger)是一种规范，最初为开发人员提供了记录其 REST APIs 的能力，因此用户可以轻松了解它们提供了什么以及如何使用它们。但是因为它也是一个机器可读的规范，它允许围绕该规范的工具的繁荣，结果是围绕 REST APIs 的工具的繁荣。

## OpenAPI 不仅仅是关于 API 文档

当开发人员开始他们的 OpenAPI 之旅时，他们通常没有意识到它可能不仅仅是生成 API 的文档。OpenAPI 提供了一种构建 API 的现代方法，允许团队获得大量的生产力并拥有更好的开发体验。

让我们看看这些现代开发工作流是什么，它们实现了什么。

## 设计优先的方法

 [阿卜杜拉·阿贝德拉巴

Abdallah 是 Kubeshop 的开发者倡导者，专注于 Kubernetes 中的 API 工作流和开发者体验。他对参与开发者社区和与他人联系有着巨大的热情。他还在 GreenMobility 和 Google 拥有应用程序开发和开发人员宣传方面的经验。](https://www.linkedin.com/in/aabedraba/) 

“设计优先”是设计并同意 OpenAPI 定义的过程，只有在这之后，每个团队才能开始编写代码，以匹配现在作为 API 合同的设计的 OpenAPI 定义。

遵循这个工作流程将允许团队对 API 的外观进行更深入的讨论(毕竟，我们应该在编码之前进行思考，对吗？)并且它允许组织中的不同团队参与进来，例如消费者团队、法律团队、营销团队等。

像 [openapi-generator](https://openapi-generator.tech/) 这样的工具非常适合设计优先的方法，因为 api 生产者和消费者都可以从他们的 openapi 定义中为服务器和客户端生成样板代码。还有[无数的测试工具](https://openapi.tools/#testing)可以使用 OpenAPI 定义来生成测试框架，作为测试功能、性能和安全性的基础。

模仿工具可以接受 OpenAPI 定义，并自动为 API 生成模仿响应。通过设计优先的方法和模仿，例如，前端团队可以开始使用设计的 API，而不必等待后端团队，[开发人员生产力的巨大提高](https://kubeshop.io/blog/rapidly-prototype-your-apis-on-kubernetes-with-kusk-gateway)。

## API 部署的声明性配置

最终，需要在基础设施上部署一个 API，让消费者可以使用它。在使用声明性配置的环境中，开发人员定义一个配置文件，描述系统的预期行为，然后一些工具将使配置与系统一致，以匹配预期的行为。

Kubernetes 项目以及 Terraform 或 Puppet 等工具，通过使用 YAML 文件，极大地推动了越来越多的声明式配置的使用。这是因为他们已经解决了协调声明式配置的问题，这本身就是一个复杂的解决方案。因此，现在开发人员可以使用这些系统来部署他们的应用程序和配置他们的环境。

这种开发模式允许像 GitOps 这样的方法出现:将声明性配置放入 GitHub 存储库中，然后使用 GitHub 提供的所有功能以连续的方式部署应用程序。

理想情况下，你应该能够"[gitop 你的 API](https://thenewstack.io/can-you-gitops-your-apis)"，但是到目前为止还没有一个简单的方法来实现这一点。OpenAPI 规范已经提供了一种定义 API 的标准方法，但是 Kubernetes 生态系统没有对它的一流支持。至少现在还没有。

## 进入 Kusk，一个面向 Kubernetes 的 OpenAPI 优先的网关

当 Kubeshop 的 [Kusk](https://kusk.io) 团队着手弥合 Kubernetes 和 OpenAPI 之间的鸿沟时，我们想到从 Kubernetes 中 API 的入口点开始解决问题:网关。网关或入口控制器根据请求将流量导向不同的微服务。例如，如果用户发出 GET /cart 请求，网关应该将该请求定向到处理该特定路径的微服务。

拥有一个支持 OpenAPI 的网关是在 Kubernetes 领域释放该规范力量的第一步，但是我们没有找到真正完全解决它的工具。

## 现有的网关如何支持 OpenAPI？

我们想看看流行的网关如何解决这个问题。比如孔对 OpenAPI 的支持就极其繁琐。为了能够使用 OpenAPI 配置 Kong，您需要使用[失眠症的 CLI](https://github.com/Kong/insomnia) 将 OpenAPI 定义转换为特定于 Kong 的 YAML 定义，然后使用 [decK](https://github.com/Kong/deck) 将该 YAML 定义转换为通过管理 API 配置 Kong 的 API 调用。对我们来说，OpenAPI 显然是后来才想到的。

其他项目如 [KrakenD](https://www.krakend.io/) 支持一些 OpenAPI 的导入，但是开发者仍然需要学习一种特定的配置语言来使用 KrakenD。最后，谷歌的网关对 OpenAPI 的支持有限，大多数配置只能通过谷歌云的 GUI、REST API 或 Terraform 来完成。

不幸的是，对于开发人员来说，前面提到的网关都不允许采用 OpenAPI 优先的方法来构建 API 的团队使用流畅的迭代开发和部署工作流。

## Kusk 如何使用 OpenAPI 部署您的 API

Kusk 是一个开源的 OpenAPI 驱动的 Kubernetes 网关，由 Kubeshop 的团队构建。我们希望利用 OpenAPI 生态系统的优势，并将其应用到 Kubernetes 世界中，我们很幸运有多年 OpenAPI 规范主席 Ole Lensmar 来领导我们。

当谈到使用网关时，我们不想重新发明轮子，因为它是一个非常关键的软件。我们也希望有一个开源的解决方案，尽我们所能使用开源。我们最终选择了[特使](https://www.envoyproxy.io/)来启动我们一直在寻找的网关。Envoy 是一款经过充分测试的软件，已经被 Kubernetes 世界中的许多大型项目使用过，尽管我们知道我们需要为开发人员简化它的配置。

使用 Kusk，网关完全通过 OpenAPI 配置。我们使用一个`x-kusk`注释来扩展 OpenAPI 定义，这样开发者可以以一种非常简单的方式添加网关相关的配置，比如 CORS 规则、缓存控制、速率限制、OAuth 等等，直接添加到 OpenAPI 定义中。然后，我们将这些注释翻译成特定于 Envoy 的配置，这样我们就可以完全抽象 Envoy，让开发人员只关注 API。

我们不想成为另一个入口。我们希望开发者只需要 OpenAPI 来配置 API 的所有方面，从功能到操作，比如配置所述网关。

因为 Kusk 使用 OpenAPI 来配置 Envoy，所以有一些重要的特性可以从网关级别解锁，比如用 OpenAPI 定义中定义的字段自动验证请求，甚至启用网关级别的 API 模拟，等等。

## Kubernetes 中的 OpenAPI，终于

通过 Kusk，我们希望充分利用 OpenAPI 生态系统的力量。我们希望开发人员不仅使用网关本身，还能够使用 OpenAPI 生态系统中的其他工具，如文档、代码生成器、mocking 和所有可用的工具，以及来自 OpenAPI 社区的工具。

尝试一下 Kusk，让我们知道你的想法。该团队可以回答任何关于[不和谐](http://bit.ly/kubeshop-discord)的问题，我们总是欢迎和兴奋来自社区的[拉动请求](https://github.com/kubeshop/kusk-gateway)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>