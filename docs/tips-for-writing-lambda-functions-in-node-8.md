# 在 Node 8 中编写 Lambda 函数的技巧

> 原文：<https://thenewstack.io/tips-for-writing-lambda-functions-in-node-8/>

由于创建新服务的速度，最近无服务器正成为一种非常流行的支持 web 服务的解决方案。但是，如果您是 Node.js 开发人员，在深入研究之前，您应该知道一些事情。

这里有几件事要记住，这样可以让你避免很多挫折，并让你的写作发挥最大的作用。

## **1。Lambdas 没有 URL，它们有触发器**

 [努阿图采盖

Nuatu Tseggai 是 Stackery 的解决方案工程总监。他是解决方案架构、站点可靠性工程以及在执行可持续的高影响力项目和快速运输之间寻找平衡的专家。在加入 Stackery 之前，Tseggai 曾在许多公司担任高级软件和系统工程职位，包括 Radware、Lockheed Martin、New Relic 和 ManTech。他还曾在美国空军担任系统专家，并在圣彼得堡学院获得了信息系统和技术管理学士学位。](https://www.stackery.io/) 

这是无服务器隐喻的一个基本部分，它将无服务器与任何类型的服务器或微服务区分开来。我发现一开始很难把握:写了一个非常基本的返回一个对象的 Lambda 之后，比如*{消息:*'你好*世界！'}* ，我会将它部署在[亚马逊网络服务(AWS)](https://aws.amazon.com/) 上，然后尝试找出我可以在某个公共 URL 上 ping 我的 Lambda 的地方。

但问题是，如果你所做的只是部署一个 Lambda，那么它根本就不是可公开寻址的。

通过 AWS 上的默认路径创建 Lambda 应该会提示您为该 Lambda 创建一些触发器。：

*   一个 API 端点——如果你创建了其中的一个并把它挂接到你的 Lambda 上，那么你的 Lambda 就会有一个 URL
*   S3 事件(如文件上传)；
*   SNS 消息；
*   AWS 资源可以生成的任何其他事件，在 [AWS 文档](https://docs.aws.amazon.com/lambda/latest/dg/invoking-lambda-function.html)中列举。

如果你想“运行”你的 Lambda 代码而不需要任何其他资源，你可以从 Lambda 仪表板发送一个测试事件给它。

## **2。要包含一个模块，使用“require()”函数，就像在常规节点**中一样

编写 Lambdas 的初始界面非常简单，仅仅由一个大约五行高的文本框和一个基本的包装器组成。当我第一次使用 Lambdas 的时候，这就是我所坚持的:Lambdas 是几行独立运行的 javascript。当我不得不解析 HTML 或做其他棘手的事情时，我会转向微服务。“无服务器”似乎是“无外部需求”的同义词

现实情况是，你可以使用大的或小的库——但是如果你在 web 界面中工作，这并不明显。

如果你将你的 Lambda 指向 GitHub 库或者使用 [Stackery](https://www.stackery.io/) 来管理你的 Lambda，你可以在本地使用你的完整 Lambda 代码。一旦你拉下你的栈的源代码，你会看到 index.js 文件在一个文件夹中，它被你需要的一个小节点应用程序所包围。这包括 package.json，它目前只依赖于 AWS SDK。

就像任何其他 Node.js 应用程序一样，您可以在这里添加包，然后在您的 Lambda 中需要它们。您还可以要求本地文件与 index.js 文件相邻。

## **1。Lambdas 由大量信息触发**

当试图确保你的 Lambda 有足够的上下文时，花时间添加“console.log(event)”来查看所有进入你的 Lambda 的参数。如果您需要知道诸如您被调用的时间、来源或者(使用 API 网关)HTTP 请求的细节；您很幸运，因为这些都是默认的——不需要添加参数。

现在，我不得不坦白一点:我第一点提到的测试事件有点欺骗性。除了三个默认参数之外，它们只包括您设置的数据，而从 API 端点发送的事件对象有超过 100 个参数。

4.  **异步/等待函数没有那么复杂！**

当 Ryan Dahl 创建 Node.js 时，他选择了 Javascript，因为它可以很容易地描述异步。具有讽刺意味的是，近 10 年后，我们仍在争论编写异步函数的最佳方式。Async/await 无疑是朝着正确方向迈出的一大步——特别是因为它看起来和感觉上更像同步代码。

一些提示:

*   我的默认 linter 在使用*异步函数* *(params){}* 格式时遇到了问题，并且完全拒绝解析*异步(params)= > {}* ，但是它们都运行得很好。所以确保你的插件是最新的是很重要的。
*   *wait some function()*只有在 *someFunction()* 返回承诺时才能正常工作。但是最令人恼火的是:如果返回值是一个简单的值，它就不会中断。这意味着它可能导致代码看起来工作正常，但最终会崩溃。
*   如果您需要等待一个不返回承诺的函数，[只需将其包装在一个承诺中](https://stackoverflow.com/questions/22519784/how-do-i-convert-an-existing-callback-api-to-promises)。

Lambdas 仍然是一个很好的方式，可以在一个下午内将一个想法变成一个有效的服务。在你掌握了编写你的前几个 Lambda 函数之后，AWS 提供了一些[伟大的工具](https://aws.amazon.com/documentation/cloudwatch/)来监控性能和健康状况。如果您真的想构建高级的无服务器应用程序，并与您的工程团队一起扩展，我强烈推荐尝试 Stackery。为了确保用 Node.js 构建微服务的长期成功，一定要跟上随着时间的推移而出现的最佳实践和语言特性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>