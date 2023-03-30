# Kubernetes 和 PaaS:开发者体验和工作流的力量

> 原文：<https://thenewstack.io/kubernetes-paas-force-developer-experience-workflow/>

最近在 [Datawire](https://www.datawire.io/) 团队内部关于术语“PaaS”真正含义的对话——以及它与[开发者体验(DevEx)](https://www.datawire.io/faster/developer-experience/) 和工作流的关系——引发了许多内部对话，我认为分享这些对话会很好。我从与客户的合作和在会议上与人们的交谈中了解到，其他在(和类似平台上)部署应用程序的团队也不太确定“平台”和工作流之间的关系，我希望能提供一些清晰的信息——或者至少在我以建设性的方式被控制时能学到一些东西！

## 基础设施、平台、工作流程:三件必不可少的东西，它们是

 [丹尼尔·布赖恩特

Daniel Bryant 是一名独立的技术顾问，目前专门从事通过识别价值流、创建构建管道和实施有效的测试策略来实现组织内的持续交付。Daniel 的技术专长侧重于 DevOps 工具、云/容器平台和微服务实现。他还参与了几个开源项目，为 InfoQ、O'Reilly 和 Voxxed 撰写文章，并定期在 OSCON、QCon 和 JavaOne 等国际会议上发表演讲。](https://twitter.com/danielbryantuk) 

从基本原则开始，我相当自信地说，所有现代基于 web 的软件开发都涉及到三个层次:

*   **基础设施**:这一层是提供裸机、虚拟机、操作系统、网络、存储等原始计算资源的抽象层，最终负责处理与您的应用相关的代码和数据。我在这里避免使用“物理”一词，因为尽管一切最终都在硬件上运行，但我们越来越多地看到基础架构的抽象向软件定义一切(SDx)转变。
*   **平台**:这一层提供了一个粗粒度的系统级构建模块，它可能是特定于运行时的——比如一个集成了 JVM 或 CLR 的计算实例——以及数据存储、中间件、IAM、审计等。注意，我还避免在这里使用术语 PaaS，我将在后面介绍它。同样值得一提的是，我相信您总是将您的应用程序部署到某种形式的平台上，即使您没有有意识地组装一个。
*   **工作流**:这一层是你如何设计、构建、测试、部署、操作和观察你的应用的总结。每个开发人员都有一个工作流程(即使这是隐式的)，从一个人的独立网站构建者，到一千多人的复杂企业系统团队。

当我与朋友和客户谈论这个模型时，我通常会在概念和结构上达成某种形式的一致。当我们开始讨论概念之间的耦合，尤其是与平台即服务(PaaS)相关的概念时，分歧就开始了。

### 这些不是你要找的平台

我经常听说“一个 PaaS 总是有一个内置的工作流”，或者“如果你正在运行一个 PaaS，那么你不需要了解基础设施。”我并不特别同意这些说法，为了建立共同的理解，我通常会开始解释我对几代 PaaS 的心理模型:

*   第一代:最初的 Heroku，和朋友。这种类型的 PaaS 隐藏了底层的云基础设施(通过[可部署的 slugs](https://devcenter.heroku.com/articles/slug-compiler) 和[执行“Dynos”](https://devcenter.heroku.com/articles/how-heroku-works))，并呈现了一个非常自以为是的工作流，该工作流与平台相耦合(“git push heroku master”)。对于简单的单块 Ruby 应用程序来说，这太棒了——您可以在几分钟内精通部署工作流，并且您所有的知识都可以转移到下一个项目中。
*   第二代:[云代工厂(DEA 版)](https://docs.cloudfoundry.org/concepts/diego/dea-vs-diego.html)和朋友。这种类型的 PaaS 可以部署在您自己的基础设施上，并且不太固执己见，因为您可以自带构建包和运行时。工作流仍然是集成的(“cf push my-awesome-app-b Java _ build pack”)，但平台开始通过[上下文路径路由](https://www.cloudfoundry.org/blog/context-path-routing/)等概念支持多服务应用程序(和工作流)。
*   第三代:[Cloud Foundry(Diego edition)](https://docs.cloudfoundry.org/concepts/diego/dea-vs-diego.html)以及当前版本的 Google App Engine 和 AWS Elastic Beanstalk(两者分别由第一代和第二代 PaaS 演化而来)。这些 PaaS 对基础设施的意见甚至更少——你可以带自己的容器——文档清楚地说明了运行时和计算环境的限制。这里的工作流正在转向支持分布式系统(微服务)，并鼓励开发人员从组装自己的连续交付管道的当前“推荐实践”构建工作流，也许使用像 [Concourse](https://concourse.ci/) 或 [Spinnaker](https://www.spinnaker.io/) 这样的工具。
*   第四代: [Kubernetes](https://kubernetes.io/) ， [Docker Swarm](https://github.com/docker/swarm) ， [Mesos](http://mesos.apache.org/) ， [HashiCorp Nomad](https://www.nomadproject.io/) ， [AWS ECS](https://aws.amazon.com/ecs/) 和朋友(我很感激这些不是真正的 PaaS，但请耐心听我说一会儿)。这种类型的平台是基础设施不可知的——谁没有参加过会议并见过 Kubernetes 在 Raspberry Pi 集群上运行呢？—您几乎总是会接触到构成集群的底层计算和网络基础架构(AWS Fargate 可能是个例外)。您还可以部署您喜欢的任何类型的容器或流程。这个平台产生了构建“云原生”应用程序的愿望，这些应用程序是自然分布的。这里的“最佳实践”工作流尚未定义，或者更准确地说，目前仍在与技术共同发展，我们正在利用我们当前对 CI/CD 的理解并发展它。因此，这是一个有趣的开源和商业工具正在出现的领域:想想 Datawire 的 [Forge](https://forge.sh/) 和 [Telepresence](https://www.telepresence.io/) 用于工作流和 [Ambassador](https://www.getambassador.io/) 用于流量转移/部署，Weaveworks 的 [Flux](https://www.weave.works/oss/flux/) 和 [Scope](https://www.weave.works/oss/scope/) ，Heptio 和 Bitnami 的 [ksonnet](https://ksonnet.io/) ，微软的 [Draft](https://github.com/Azure/draft) 和 [Helm](https://helm.sh/) 和 Containous

我相信平台和工作流的耦合之间的混淆出现了，因为我们中的许多人(包括我)已经愉快地部署了我们的粗粒度(monolithic？)风格的应用程序，其中工作流与平台紧密耦合，即第一代和第二代 PaaS，或者工作流松散耦合，但定义良好，以至于我们没有注意到摩擦，即在传统基础架构或第三代 PaaS 上构建和部署特定语言的工件。

挑战随着第四代平台的出现而出现，其中的技术仍在不断成熟，架构和相关的组织最佳实践也仍在共同发展——分别想想[微服务](https://martinfowler.com/articles/microservices.html)和[无服务器](https://martinfowler.com/articles/serverless.html)，以及[逆康威策略](https://www.thoughtworks.com/radar/techniques/inverse-conway-maneuver)。对于[速度、稳定性和可见性](http://itrevolution.com/devops-handbook)的业务压力也越来越大，这通常是通过分离业务流程(形成跨职能业务单位)和将决策权下放给在一线工作的团队来实现的——这以 [holacracies](https://www.holacracy.org/) 和 Teal organizations 等业务活动为代表。

回顾我上面的软件开发层，要注意的一个关键点是，我们的基础设施和平台正变得越来越分散和分离，但它们是由一种集中力量实现的——例如，基础设施的情况下是 AWS，平台的情况下是 Kubernetes ( [Apps SIG](https://github.com/kubernetes/community/tree/master/sig-apps) )社区——它定义了通用协议、标准和接口。我们的工作流也正在变得分散，但我认为我们还没有集中力量，即一种通用的描述性语言、一套工具和预定义的(可插拔的)工作流步骤。

### 构建(雪花)定制工作流:失败是最伟大的老师

随着越来越多的组织采用 Kubernetes，我看到团队创建定制的开发人员体验工作流——通常在一个组织内的不同团队之间有所不同——这导致了脆弱的解决方案和有限的共享学习。通常，这些团队试图以这样一种方式编写他们的工作流，实际上，他们最终在 Kubernetes 上构建了一个平台。不要误解我——部署到平台上是必要的——但是平台和工作流的概念应该分开考虑和设计。平台和工作流的紧密耦合导致了不灵活的开发人员工作流。

我相信随着我们进入 2018 年，Kubernetes 的“平台”变得更加清晰。Kubernetes 本身正在很好地走向成熟，由像[特使](https://www.envoyproxy.io/)、[管道](https://github.com/runconduit/conduit)和[纤毛](https://github.com/cilium/cilium)这样的公司提供服务的承诺似乎正在填补平台的一些缺失部分。但是，围绕开发者体验还有很多思考要做。我们正看到运营领域的最佳实践被编入诸如 [Weaveworks GitOps](https://www.weave.works/blog/gitops-operations-by-pull-request) 和 [Atlassian 的 BDDA](https://developer.atlassian.com/blog/2017/07/kubernetes-workflow/) (Build-Diff，Deploy-Apply)等方法中，我相信在应用程序开发(AppDev)领域也会出现类似的东西。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>