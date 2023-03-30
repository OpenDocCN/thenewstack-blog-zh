# JavaScript 通过开源架构工具获得一个 Onramp 到 Lambda 的无服务器

> 原文：<https://thenewstack.io/javascript-gets-onramp-lambda-serverless-open-source-architect-tool/>

JavaScript 基金会认为未来服务器将与 JavaScript 开发者无关，相反，他们可以简单地使用云来处理功能。这种观点的体现是 Architect，一个由 bot 公司[的开发者贡献给基金会的开源项目 Begin](https://begin.com/) 。

[架构师](https://arc.codes/)平台可以自动将服务部署到 Amazon Web Services 的 [Lambda](https://aws.amazon.com/lambda/) 上，方法是用。描述如何在[无服务器](/category/serverless/)代码执行服务上运行函数的 arc 扩展。

Begin.com 背后的公司 Small Wins 的首席技术官 Brian LeRoux 表示，通过部署 Lambda，开发人员可以减少向生产系统发送更新所需的时间。

这个项目最初被简单地称为“ [Lambdas](https://github.com/smallwins/lambda) ”，在过去的两年里得到了发展，以响应 LeRoux 在小胜利中提高敏捷性和速度的愿望。

“我们的整个应用程序现在是无服务器的，在云中运行，我们对此感到非常兴奋，”LeRoux 说。“我们最初的原型并不好:它只有三台服务器，通常滚动部署需要半个多小时。当你发现一个严重的错误时，那就糟了。我们现在的部署大约是 10 秒钟。”

的。arc 文件可能是这样的:

```
# this is an .arc file
@app
testapp

@html
get  /
get  /hellos
post  /hello

```

从命令行运行 **npm run create** 在开发者的机器上生成云函数代码:

```
/
|--  src
| `--  html
| |--  get-index/
| |--  get-hellos/
| `--  post-hello/
|--  .arc
`--  package.json

```

另一个 npm 命令 deploy 将代码发送到云。

他说，云功能本质上是看待云资源的另一种方式:“云功能是一个全新的概念。服务器的比喻已经不再适合我们了。”与其考虑向应用集群添加服务器，不如简单地添加一些功能，这些功能可以由托管提供商自动扩展。

“我们很早就大规模采用了云技术，我们遇到了很多问题。无论你做什么，你都需要自动化你的管道，”LeRoux 说。“当我们启动 Begin.com 时，我们就知道云功能将会很大。如今，要进入科技市场，你必须比竞争对手强 10 倍才能生存。做到这一点的一个方法是将新技术应用于该技术。”

在管理无服务器云计算基础设施领域，LeRoux 表示，目前的选择有限。“亚马逊是我的最爱。他们这样做已经有一段时间了。”

到目前为止，Architect 项目主要是 LeRoux 公司的内部工作，但他希望在 JavaScript 基金会的帮助下，它能够扩展到这个范围之外。该项目旨在能够移植到云中的其他无服务器计算平台，但目前仍专注于亚马逊。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>