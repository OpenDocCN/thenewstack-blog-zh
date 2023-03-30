# 无服务器计算平台的十个属性

> 原文：<https://thenewstack.io/ten-attributes-serverless-computing-platforms/>

无服务器计算或[功能即服务](/category/serverless/) (FaaS)正在蓄势待发。亚马逊通过将 Lambda 扩展到边缘设备和内容分发网络来推动创新。 [IBM](https://console.ng.bluemix.net/openwhisk/) 、[微软](https://azure.microsoft.com/en-us/services/functions/)和[谷歌](https://cloud.google.com/functions/)在公共云中有他们自己的 FaaS 产品。有半打以上的开源无服务器项目引起了开发人员的注意。今年，有望看到这一领域出现新的平台。

面对围绕无服务器的所有兴奋和炒作，理解什么真正定义了该平台是很重要的。这里试图强调无服务器计算平台的关键属性。对于客户来说，它可以作为选择合适产品的清单，同时帮助平台供应商优化他们的产品。

### 1.多语言平台

FaaS 的最大好处是选择最佳的语言和为特定任务优化的运行时。每个函数可以用不同的语言编写，但都有助于相同的应用程序。尽管 JavaScript 似乎是无服务器的最小公分母，支持其他语言也很重要。

[AWS Lambda](https://aws.amazon.com/lambda/) 从 JavaScript 开始，但[最终增加了对 Python、Java 和 C#的支持](https://thenewstack.io/aws-gets-serious-lambda-adds-python-cron-scheduling/)。 [Azure 函数](https://azure.microsoft.com/en-us/services/functions/)支持包括 BASH 脚本语言在内的所有流行语言。通过 Docker 集成，一些提供商将启用 BYOI(自带映像)来支持遗留代码和二进制文件。IBM OpenWhisk 就是这种 FaaS 的一个例子。多语言是 FaaS 的一个重要方面，客户应该考虑。

### 2.支持同步和异步调用

部署在 FaaS 的功能可能是同步的，也可能是异步的。某类应用程序要求立即响应，而其他应用程序可能更喜欢异步调用。例如，传感器生成的数据需要立即处理和分析，而上传到对象存储器的图像可以通过批处理转换为缩略图。

> 在 FaaS 运行应用程序类似于驾驶无人机。

不管函数的风格如何，FaaS 平台都应该支持同步和异步调用。当一个函数被异步触发时，平台返回一个标识符，这个标识符可以用来轮询状态。IBM OpenWhisk 支持这种模式，其中每个函数都被视为异步的，除非调用包含阻塞请求。

了解平台支持的并发调用数量也很重要。Azure 函数

### 3.API 网关集成

与无服务器平台集成的 API 网关的价值怎么强调都不为过。尽管部署在无服务器环境中的功能通常是由外部事件源(如流处理器和数据库)触发的，但是是 API 网关点亮了这些功能。它添加了将标准 HTTP 动词映射到各自功能的逻辑路由。

例如，可能有四个不同的函数负责数据库上的 CRUD 操作，它们被映射到 get、PUT、POST、DELETE 动词。这立即给开发人员带来了熟悉的 API 外观。API 的消费者可能甚至没有意识到他们正在处理一个无服务器的平台。

在引入 Amazon API Gateway 之后，AWS Lambda 的采用率才开始飙升。致命的组合产生了一个强大的平台，支持许多有趣的用例。

客户应该仔细评估无服务器平台是否与 API 网关良好集成。

### 4.开发人员生产力

今天开发人员使用的大多数 ide 都不是为现代 [DevOps](/category/devops/) 流程设计的。对源代码控制系统、构建自动化、CI/CD 和 A/B 测试的支持来自插件和第三方插件。传统的 IDE 厂商要支持 FaaS 还需要很长时间。近日，微软宣布在 Visual Studio 中支持 [Azure 函数。AWS 还为 Visual Studio 提供了一个插件，可以在 Lambda 中开发和部署 C#函数。但对于其他语言和框架，可供选择的并不多。](https://blogs.msdn.microsoft.com/webdev/2016/12/01/visual-studio-tools-for-azure-functions/)

### 5.支持开发操作和工具

有一种误解认为 FaaS 神奇地减少了对开发工具和工具的需求。无服务器平台应该与源代码控制系统和构建自动化工具紧密集成。它们应该支持自动化和可重复的部署模式。亚马逊再次成为首批引入无服务器应用模型的公司之一，该模型用于声明包括 AWS Lambda 资源在内的整个堆栈。这些模板可以与 git 集成，以实现一致的版本控制。微软也支持通过 ARM 部署 Azure 功能。谷歌在部署管理器中加入云功能还有很长的路要走。

IDE 支持和与现有 DevOps 管道的集成是选择 FaaS 平台时要考虑的主要因素。

Serverless，Inc .正在开发跨多个平台自动部署 FaaS 应用程序的工具。目前，在测试阶段，该产品旨在成为开发基于 FaaS 的微服务的事实框架。

### 6.响应能力和性能

在 FaaS 上设计基于微服务的应用时，响应能力起着至关重要的作用。设计不良的平台会引入启动延迟，并延迟调用过程，这对最终用户来说是显而易见的。JavaScript 和 Python 等轻量级解释语言的响应速度比 Java 和. NET 更快。如果每次调用之间存在相当大的差距，延迟就会变得明显。保持函数“温暖”的一个技巧是在循环中调用它。但是对于许多客户来说，这不是一个理想的解决方案。

一些新兴的 FaaS 平台对 Docker 容器的使用引起了关注。对一个函数的每个请求将导致一个新容器的创建，这将引入显著的延迟。尽管与虚拟机相比，容器速度更快，但它们仍不意味着是 FaaS 的部署单元。我们需要一个比容器更好的执行环境来实现 FaaS。

在部署微服务解决方案之前，客户必须对每种语言和运行时的周转窗口进行基准测试。

### 7.记录和监控

在 FaaS 运行一个应用程序类似于驾驶一架无人驾驶飞机。唯一可以控制两者的方法是通过一个强大的仪表板显示当前状态。FaaS 平台应该对日志记录和监控提供广泛的支持。写入 **stdout** 和 **stderr** 的所有内容都应该被记录到不同的流中。这对于理解应用程序的当前健康状况和调试单个功能是必不可少的。监控工具应该提供对每个函数的成功调用、不成功调用、调用时间、响应时间、内存消耗和 CPU 利用率的洞察。

尽管 FaaS 被定位为 NoOps 平台，但是日志和监控功能被 DevOps 团队大量使用。

### 8.REST 端点和自动化

像大多数基于云的交付模式一样，FaaS 必须完全自动化。只有当平台支持 API 来执行通过门户或 CLI 完成的所有操作时，这才是可能的。这一特性使开发人员和运营商能够高效地自动化部署和管理微服务的工作流程。

例如，CI/CD 系统可以利用 FaaS 的 REST API 来自动推送最新版本。这个场景可以进一步扩展，以自动化 FaaS 的 A/B 测试环境的实现。

### 9.支持长时间运行的作业和批处理

成熟的无服务器平台内置了对长时间运行的预定作业的支持。部署在 FaaS 的功能可以被周期性地调用以执行 ETL 作业。FaaS 平台可能支持同样的概念[**【cron】**](http://www.unixgeeks.org/security/newbie/unix/cron-1.html)来调度作业。

这种能力进一步扩展到支持批处理。例如，上传到对象存储桶的大量高分辨率图像可以由一个函数一次性处理。这些场景不同于异步调用模式。

### 10.可扩展性和集成性

无服务器平台的真正价值在于广泛的集成和可扩展性。例如，平台必须支持多种安全方案，包括 [oAuth](https://oauth.net/2/) 和基于 LDAP 的定制认证。它应该支持开箱即用的 HTTPS 端点，以实现安全传输。

该平台应该有足够的钩子，以便于与各种事件源集成。AWS Lambda 等专有平台将只支持与其服务的集成，如 [S3](https://aws.amazon.com/s3/) 、 [Kinesis](https://aws.amazon.com/kinesis/) 和 [DynamoDB](https://aws.amazon.com/dynamodb/) 。开源平台应该使数据库供应商和其他平台公司支持 FaaS 变得容易。 [OpenWhisk 的 Feed](https://github.com/openwhisk/openwhisk/blob/master/docs/feeds.md) 就是这种集成的一个例子。

对自定义环境变量的支持是可扩展性的另一个例子。这样，客户可以传递请求中没有包含的参数。这个简单的特性将 FaaS 变成了一个强大的执行环境。

IBM 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>