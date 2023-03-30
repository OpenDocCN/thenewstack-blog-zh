# AWS Lambda 将帮助创建一个新的标准

> 原文：<https://thenewstack.io/aws-lambda-is-a-step-towards-creating-a-new-normal/>

[](http://www.vivekjuneja.in/)

 [Vivek Juneja 是一名工程师，在首尔工作，专注于云服务和移动性。他目前是 Symphony Teleca 的解决方案架构师，也是班加罗尔亚马逊网络服务用户组的联合创始人。他于 2008 年开始从事云平台工作，是 AWS 和 Eucalyptus 的早期采用者。他还是一名技术传播者，在印度的各种技术会议上发表演讲。他写@ www.cloudgeek.in 和 www.vivekjuneja.in，热爱梳理技术社区。你也可以通过 email:vivekjuneja@gmail.com](http://www.vivekjuneja.in/) 联系到他

亚马逊 Lambda 是上周在亚马逊网络服务(AWS) r [e:Invent 2014 大会](https://www.youtube.com/watch?v=9eHoyUVo-yg)上宣布的。这项服务吸引了网络上所有人的兴奋和有趣的观点。该服务承诺开发人员能够专注于他们正在做的项目，而不是历史上一直需要考虑的基础设施。在会议的众多亮点中，网络服务高级副总裁 Andy Jassy 关于“云是新常态”的声明是对云采用状况的突出证明。

将软件开发为响应数据或状态变化的事件集合并不是一种新趋势。它起源于传统的 UI 开发模型，还记得 Swing UI、Visual Basic 组件模型以及最近争论的——[事件驱动的 SOA](https://en.wikipedia.org/wiki/Event-driven_SOA) 。

最近，事件驱动编程和相关架构被定位为 SOA 的下一次发展。传统上，SOA 采用请求-响应模型，并且在设计上很大程度上是同步的。基于事件的模型引入了异步、推拉、触发和遗忘方法。今天，大多数开发人员都在进行某种形式的事件驱动编程，比如在 jQuery 中设置 onclick 事件、AJAX 回调等等。所以，这并不是一个全新的想法。

然而，[功能反应式编程](https://en.wikipedia.org/wiki/Functional_reactive_programming)将这一点带到了下一个层次。通过理想化连续的事件流和建立事件流的订阅者，它简化了事件驱动系统的概念。对于开发人员来说，这是关于最小化构建大规模事件驱动系统的活动部分。

## 那么 Lambda 在哪里，为什么它令人兴奋？

2006 年 AWS 的出现和后来的云原生服务，使大众的分布式编程民主化。AWS 的旗舰客户，如网飞、Animoto 和 Pinterest，教育了一个新时代的开发人员、架构师和系统管理员，让他们了解了在云上构建的可能性。成千上万的开发人员从仅仅使用 EC2 和 S3 作为虚拟服务器和文件存储的替代物发展到利用提倡“替代而非修复”的无状态基础设施。这种思维的演变导致围绕[不变基础设施](https://medium.com/@darrenrush/after-docker-unikernels-and-immutable-infrastructure-93d5a91c849e)的想法被大量采用，自动化供应也是如此。

现代在线应用程序的定义现在是 web 服务的集合，这些服务在其自身之外保持其状态，在独立的基础设施上独立运行，可以水平扩展和升级，以避免最终用户最少停机或不停机。期待像 AWS S3 的 11 个 9 这样荒谬的高可用性成为开发人员的普遍说法，他们从未接触过这个概念，除非他们在谷歌、脸书、雅虎、亚马逊和其他旗舰大型网络平台工作。大规模分布式应用成为新的标准。

我感觉 Lambda 可以给普通社区带来同样的进步。让反应式编程、事件驱动系统和函数式思维成为一种新的规范，将意味着这些想法在企业和初创公司的主流中得到更多的采用。

### 介绍来自 AWS 的 Lambda 服务模型

Lambda 服务不可能来得更早，因为它需要其他可伸缩、高度可用和持久的服务的基础。对于物联网爱好者和从业者来说，让你的代码在 AWS 基础设施中运行并在事件发生后几秒钟内可用的前景是一个有吸引力的开发环境。

然而，这种公开邀请也要求在代码如何运行和对事件作出反应方面有严格的纪律。它强化了 lambda 函数作为无状态实体的需求。它必须假设本地文件系统访问、特定的子进程等。[可能不存在于当前请求的领域](http://aws.amazon.com/lambda/faqs/)之外。

对 Lambda 函数的限制当前设置为 60 秒。这是另一个约束，也是一个构建服务的机会，这些服务在对事件执行何种操作方面具有正确的粒度。这也将有助于开发人员对每个为响应事件而构建的 lambda 函数的组成进行限制。架构师需要寻找一种方法将业务问题分解成[事件发射器、事件消费者或接收器，以及事件通道](https://en.wikipedia.org/wiki/Event-driven_architecture)。

Lambda 计费模型也是 AWS 希望开发者如何考虑服务的一个指标。将[计费参数设置为服务持续时间](http://aws.amazon.com/lambda/pricing/)和分配的内存大小是重新考虑功能/服务组合的新模型。

作为一名开发人员，我希望优化 lambda 函数的执行时间，以及我为此提供的内存。一个较小的微服务应该在几毫秒内相对完整地执行函数，并使用最少的内存。这是帮助架构师重新思考微服务架构组成的另一种方法。

### **问题与机遇**

Lambda 采用的增加将进一步要求更广泛的支持基础设施，特别是管理这种功能的生命周期。AWS 在发布时提供的仪表板功能仅提供这些功能的典型列表、删除、更新和基本监控。这种函数的创建目前是通过内嵌的、基于控制台的编辑工具或者通过上传压缩的 [Node.js 函数以及依赖关系](http://docs.aws.amazon.com/lambda/latest/dg/walkthrough-s3-events-adminuser-create-test-function-create-function.html)来提供的。然而，我预见了与当前编辑器如 Eclipse、IntelliJ、Sublime、TextMate 等的直接集成。像新发布的 [CodeDeploy](http://aws.amazon.com/codedeploy/) 这样的构建和部署管道以及像 Jenkins 这样的现有工具集必须与 Lambda 函数的部署模型相集成。AWS Lambda API 提供了一个上传函数 API 来上传函数代码的 ZIP 文件。

开发人员在这个新的产品中有无数的选择，这使得他们可以做出一些有趣的选择。构建一个真正有弹性、高可用性和可伸缩性的应用程序将意味着决定在传统 EC2 风格的计算实例中保留什么，以及在 Lambda 函数中加入什么。

这也意味着邀请进入新时代的架构和模式，这些架构和模式将按照网飞 OSS 的方式融入社区。

AWS 与谷歌和微软等其他公司一起努力让云成为新常态。有了 Lambda，AWS 向软件开发的反应式、事件驱动的系统和功能方法迈进了一步。这是一种让它成为新常态的努力。

对于那些较早接触到 Lambda 的少数幸运儿来说，这是一个体验未来的邀请。至于其他的，直到你收到邀请，Jeff Barr 的 AWS 博客文章是让你兴奋和开始的最好的东西。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>