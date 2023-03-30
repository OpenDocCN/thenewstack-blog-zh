# Heptio 通过 Kubernetes 配置工具 ksonnet 摆脱了隐形模式

> 原文：<https://thenewstack.io/heptio-comes-stealth-mode-ksonnet/>

根据 Kubernetes 开源项目的创始成员 Craig McLuckie 的说法，部署 Kubernetes 容器编排将变得更加容易。麦克卢奇与[乔·贝达](https://www.linkedin.com/in/jbeda/)一起在谷歌开始了这个项目，六个月前，他与贝达共同创立了 [Heptio](https://www.heptio.com) ，让 Kubernetes 变得更容易访问。该公司在上个月的 GlueCon 开发者大会上推出了 ksonnet Kubernetes 配置工具，从而摆脱了隐身模式。

ksonnet 旨在“以一种易于共享和重用的方式”帮助自动化复杂的 Kubernetes 部署的建模和管理，首席执行官兼联合创始人[丹尼尔·洛佩斯](https://www.linkedin.com/in/daniel-lopez-ridruejo-993120/)、 [Bitnami](https://bitnami.com) 说，Bitnami 是 ksonnet 合作团队的一部分，其他合作团队还有 [Box](https://www.box.com/home) 、微软和容器软件提供商 Deis ( [微软正在收购](https://blogs.microsoft.com/blog/2017/04/10/microsoft-acquire-deis-help-companies-innovate-containers/#sm.000149d10u5dde5fx8921j2eenvb1))。

## 超越优秀的工程

麦克卢奇解释说，Kubernetes 是系统工程师为系统工程师创造的。因此，非核心系统工程师的开发人员很难获得访问权。

“Kubernetes 是一个具有巨大潜力的平台，仍然是真正的新平台，”Box services 架构师和联合创始人、ksonnet 的撰稿人 Sam Ghods 说。“一旦你有了这个平台，你就需要与这个平台互动的方式。Ksonnet 只是与该平台合作的下一步。”

在他的博客上，贝达承认现在由[云本地计算基金会](https://www.cncf.io/)管理的 Kubernetes 可能会令人生畏。“特别是，新用户在配置运行在 Kubernetes 上的系统时，经常会面临 wall 之墙’，”他说。

“我们认为 ksonnet 不仅仅是部署的代码，”他解释说，“而是我如何创作它、如何使用它、如何跨团队工作的整个体验。”

## **体验崩溃**

ksonnet 体验分为两部分。首先，ksonnet 为 Kubernetes 应用程序开发人员提供了一个可配置的类型化模板系统。“这是一个用于处理 Jsonnet 中的 Kubernetes API 的特定领域助手库，它为您提供了工作的构建块，”Beda 解释道。 [Jsonnet](http://jsonnet.org/) 是一种用于格式化 JSON 数据的数据模板语言。

Beda 提供了一个类比:有 JavaScript 语言，然后有允许你以结构化的方式使用 JavaScript 的框架。ksonnet 库(ksonnetlib)是一种以结构化的方式使用 Jsonnet 来构建 Kubernetes 配置的方法。

第二个在 Gluecon 上没有引起注意，但在 Twitter 上被提出来的是包含了 Jsonnet 的 Visual Studio 代码扩展。ksonnet 包括一个 [VSCode 扩展](https://marketplace.visualstudio.com/items?itemName=heptio.jsonnet)和一个[简单网站](http://ksonnet.heptio.com/)用于实验。

“这给了你所有你期望从现代开发环境中得到的东西，比如帮助功能，”Beda 说，“真正使创作这些东西变得更容易，而不必到处使用复制/粘贴，正如正在发生的那样。”

“你可以从一个社区提供的模板开始，并快速编辑它以支持你的需求，”他说，“将随环境变化的东西参数化，并将其绑定到你最喜欢的包管理工具(如 [Deis Helm](https://helm.sh/) )。”

## Jsonnet 连接

Beda 解释说，Jsonnet 是“一种与 JSON 兼容的纯功能、图灵完备的语言”。谷歌工程师戴夫·坎宁安(Dave Cunningham)开源了 Jsonnet 项目，贝达表示，有相当多的人正在使用它来管理 Kubernetes 的配置。他说，他们正在这样做，并取得了不同程度的成功。以下是 Jsonnet 中威士忌酸味的代码示例:

> {
> 
> 鸡尾酒:{
> 
> “酸威士忌”:{
> 
> 配料:【
> 
> {种类:“波旁”，数量:1.5 }，
> 
> {种类:【柠檬汁】，装箱数量:1 }，
> 
> {种类:【Gomme 糖浆】，数量:0.5 }，
> 
> ，
> 
> 配菜:【柠檬皮】，
> 
> 上菜:【直上】，
> 
> }，
> 
> “鸡蛋酸威士忌”:
> 
> 自我[“威士忌酸”] + {
> 
> 配料:特级配料
> 
> + [{种类:“蛋清”，数量:0.5 }]，
> 
> }，
> 
> }，
> 
> }

Jsonnet 受到谷歌配置语言(GCL)的启发，这是谷歌内部大多数团队描述该公司 Borg 配置的方式。贝达解释说，GCL 仍在谷歌内部，因为它有一些尚未解决的问题。

他解释说，所以谷歌的 Borg 和 Kubernetes 以及 GCL 和 Jsonnet 之间有相似之处。Jsonnet 超级有用，但是和很多语言一样，你可以用结构化的方式或者非结构化的方式来使用它。

Beda 说，如果你以一种非结构化的方式使用 Jsonnet，你就看不到你想要的所有功能和可组合性。Ksonnet 帮助你使用 Jsonnet 是一个有用的方法。使用 ksonnet 的一个很大的好处是人们以前很难达到的写作水平。

组合元素容易出错，而且需要大量代码，这就造成了许多用户所说的“[YAML 之墙](https://blog.heptio.com/ksonnet-intro-43f6183a97a6)”ksonnetlib 使不同的团队更容易描述不同的元素，然后以结构化的方式轻松地将它们组合在一起。例如，这是 ksonnet 中相同威士忌酸味的代码:

日志团队:

物流员::

util.mapContainers(

函数(podContainer)

podContainer +

container . volume mounts([

logTailerVolumeMount

)

) +

deployment . mixin . pod spec . volumes(

应用团队:

本地 nginxContainer =

container.default(

"nginx "，" nginx:1.13.0") +

集装箱港口(

containerPort.named("http "，80))；

deployment.default(

"nginx "，nginxContainer) +

deployment . mixin . spec . replicas(3)+

sidecar.logTailer

以下是输出:

API version:apps/v1 beta 1

种类:部署

元数据:

名称:nginx

名称空间:默认

规格:

副本:3

模板:

规格:

容器:

–图像:“nginx:1 . 13 . 0”

名称:nginx

港口:

–集装箱港口:80

名称:http

容量装载:

–安装路径:/var/applogs

名称:logTailerVolume

卷:

–名称:物流员

持续体积索赔:

声明名称:logTailerVolumeClaim

## 超越威士忌酸:盒

Box 是 Kubernetes 的一个非常早期的适配器。Ghods 说，随着 Kubernetes 的使用范围扩大，管理所有配置变得更加困难。Box 最近启动了他们自己的基础设施项目:kube-applier。该公司的工程师欣然接受了与 Heptio 合作的机会，并对 ksonnet 感到兴奋。

“在 Box，我们的价值是提供软件，”他说。“我们的客户希望我们在他们首选的服务上运行，Kubernetes 给了我们这种灵活性，允许 Box 在任何平台上运行。”ksonnet 让开发者更容易实现这一点。

他解释说，因为 Kubernetes 可以在任何地方运行，所以规范非常健壮，使用对象对于新用户来说可能是压倒性的。Ksonnet 使得编写 Kubernetes 对象变得更加容易，这使得入门和一般使用变得更加容易。

Ghods 解释说，随着越来越多的 Kubernetes 对象运行在你的基础设施上，复杂性成指数级增长。Ksonnet 将复杂的东西抽象出来，创建可重用的代码。

“这使得应用程序开发人员更容易编写和管理 Kubernetes 架构的规范，”他说。“这有助于我们开始制定一个开发 Kubernetes 对象的标准，比现在更有用。”

他解释说，这是第一次，开发者可以在 ksonnet 中编写一个规范，并让该应用程序在 Kubernetes 运行的任何云上工作。“app 放在哪里不重要，在 AWS，裸机，IBM 云，Google 云，Open Stack，都不重要。”

## 声明性配置

“正如我们所说的，管道和工具链正在开发中，”Ghods 说。

Box [上个月刚刚发布了 kube-applier](https://thenewstack.io/box-brings-declarative-configuration-kubernetes-kube-applier/) ，它为 Kubernetes 带来了声明式配置。它基本上接受 Kubernetes 对象并将它们同步到 Kubernetes API 服务器。这实际上与 ksonnet 携手合作。

新的流程是开发人员在 ksonnet 中从 JSON 编写并生成规范，然后 kube-applier 可以获取 JSON 语言并将其应用到 API 服务器，这样它就可以在需要运行它的任何地方运行它。

Ghods 说:“因此，开发人员很容易编写规范并将其部署到 API 服务器上。"所有的部分都在逐步到位。"

[云本地计算基金会](https://www.cncf.io/)是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>