# 使用 Datawire 的网真调试基于 Kubernetes 的服务

> 原文：<https://thenewstack.io/debugging-kubernetes-telepresence/>

Kubernetes 开源容器编排引擎可能非常容易运行，但定制是一个负担。数据专线的联合创始人 [Richard Li](https://twitter.com/rdli) 说，实际上没有任何定制的指导，这是所有企业都想做的。

李解释说，[网真](https://www.telepresence.io)是今年早些时候由 Datawire 发布的一款开源工具，致力于让开发者更容易地使用 Kubernetes。当 Datawire 的团队开始在 Kubernetes 上构建云应用时，他们发现从开发者的角度来看有很多问题。所以它开发了一些产品来帮助减轻这种痛苦。开源项目有 [Forge](https://github.com/datawire/forge) ，李称之为 Docker Compose for Kubernetes[大使](https://github.com/datawire/ambassador)，这是一个基于特使的 API 网关，现在是[网真](https://github.com/datawire/telepresence)。

![](img/fd9ec9400e0433ee9bb7334d5e8ef423.png)

理查德李，首席牦牛剃须刀在数据线

李说，这款产品在圆周率日(3/14/17)首次发布，已经悄悄地聚集了一批追随者。这也难怪。该产品允许您使用当前的调试器实时测试在 Kubernetes 集群上运行的代码，就像在本地主机上一样。

“我们自己想要一个工具，在那里你可以立即进行代码修改和测试，”他说。在广泛搜索工具一无所获后，他们决定自己编写工具。

但是驱动它流行的是将任何调试器连接到 Kubernetes 的能力。“如果你是一名开发人员，它可以让你立即工作，”李说。"当你修改代码时，你可以立即看到它."

或者，正如 Red Hat 的开发者倡导者 Michael Hausenblas 在 OpenShift 博客上所写的，他列出了启动和运行产品的步骤，“网真让你可以将笔记本电脑上运行的本地进程代理到 Kubernetes 集群，包括 Minishift/Minikube 和远程集群。您的本地进程将透明地访问实时环境:网络、环境变量和卷。此外，来自群集的网络流量将被路由到您的本地进程。”

开发工具公司 [Stacktical](https://stacktical.com/home) 已经在自己的产品线中采用了网真技术。“像 Telepresence 这样的工具可以轻松地为现有的 Kubernetes 项目做出贡献，并重新想象我们如何比以往任何时候都更快地围绕交付代码进行合作，”一篇公司博客文章称。“这不仅仅是提供可扩展服务的问题。这也是提高团队可伸缩性的问题。”

Stackitcal 博客引导读者完成设置。首先，安装网真就像运行安装命令一样简单。

> ```
> brew cask install osxfuse
>   brew install datawire/blackbird/telepresence
> 
> ```

(注意:虽然[安装说明](https://www.telepresence.io/reference/install)有很好的文档记录，但是这段代码对于你的操作系统来说可能有点不同。)安装完成后，在您的 Kubernetes 服务上调出信息:

> ```
> kubectl get service frontend backend db
> 
> ```

这允许您从本地前端与 8888 端口上的后端通信。

**tele presence–swap-deployment**命令允许您的本地机器在会话期间以最小的努力透明地与 Kubernetes staging 集群通信:

> ```
> telepresence  --swap-deployment frontend  --expose  8080:80  --run-shell
> 
> ```

“无论何时我们调用远程后端服务，它都会回应我们的本地前端应用程序，”Stacktical 网站断言。“这种双向代理系统是远程呈现能力的基础，让您可以用本地服务替换您架构中的任何微服务。”

Datawire 将于今年 12 月在奥斯汀的 KubeCon 举办一场关于如何让网真在你的电脑上运行的闪电讲座，以及一场关于 Kubernetes 开发流程的完整会议。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>