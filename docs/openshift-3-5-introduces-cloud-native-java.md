# OpenShift 3.5 旨在吸引 Java 程序员使用云计算

> 原文：<https://thenewstack.io/openshift-3-5-introduces-cloud-native-java/>

你可能已经被告知，Java 不是云原生的。你可能也听说过，原因很简单:Java 与中间件绑定，中间件采用了云原生架构所没有的 *n* 层架构。取决于你当时在听谁说话，云原生架构可能会[避开中间件的本质](https://thenewstack.io/configuration-management-orchestration/)，或者[成为下一代中间件](https://thenewstack.io/cloud-native-platforms-will-take-off-2016/)。

这种二分法与依赖性有关。针对可伸缩的云原生应用的 [12 因素重构方法](https://thenewstack.io/12-factor-app-streamlines-application-development/)的目标之一是[消除隐式依赖](https://blogs.sap.com/2016/01/08/the-twelve-factors-dos-and-dont/)以实现服务的无阻碍可伸缩性。典型的中间件，如 Red Hat 的 JBoss 和 IBM 的 WebSphere，被设计成一种隐含的依赖关系——它们的供应商过去称之为“可靠性”

对于周四首次亮相的 open shift 3.5 版本，Red Hat 正在引入它所谓的*云原生 Java*——具体来说，作为现有 VM 引擎之外的容器映像。这种语言看起来不像是受某个之前在会议上见过 Java 的人的启发，而是一种真正的努力，让资深开发人员在微服务的陌生领域中有一点宾至如归的感觉。

Red Hat 的产品战略总监 Brian Gracely 在谈到新的产品组合时表示:“有很多人推动将一些东西重命名或重新命名为‘云原生的’。”。“这一切都很好，在聚会之类的场合也很棒。但是客户会说，‘看，这是我的世界的现实:我有一些有价值的 Java 开发人员，他们在过去的五年、十年，或者十五年中不断发展，我们没有任何兴趣摆脱这些人。无论是支持当前应用程序还是构建应用程序，他们都做得很好。“我们想要能够帮助我们前进的平台，”我们没有看到很多人说，'我们是一个巨大的 Java 商店，我们只是完全放弃 Java。"

## 重构因素

周四，Red Hat 的容器编排包 [OpenShift](https://www.openshift.com/) 引入了云原生 Java，这是该公司从 2015 年 11 月开始的持续努力的最新一步分阶段为容器化 PaaS 重构 Java 生态系统。

当然，Java 对 OpenShift 来说并不陌生，从一开始就已经是平台的一部分了。但是 Java 应用程序的结构在历史上依赖于隐式依赖，这就是为什么应用于无状态应用程序的基本相同的语法[被称为不同的语言(Scala)](http://readwrite.com/2011/10/26/scala-java-scaled-up/) 。无数的新语言已经出现，来解决为模块化和分布式系统重构标准的、充满依赖性的 Java 应用程序的问题，但是它们似乎都比标准 Java(或者，公平地说，比任何本地语言)更适合于分布式系统。网语)。

Red Hat 的 OpenShift 首席产品经理 Mike Barrett 告诉我们，开发人员对 Java“云原生”的印象可以分为两类。一个是创建一个 *[胖罐子](http://stackoverflow.com/questions/19150811/what-is-a-fat-jar)*——一个包含所有依赖项的 Java 包。巴雷特说，通常，如果开发人员同意限制她的部署选项，那就没问题——例如，如果要去 [Spring Cloud](http://projects.spring.io/spring-cloud/) 或直 Kubernetes，但不去其他地方。

相比之下，第二个桶包含了资深 Java 开发人员对整合他们期望的熟悉工具的期望，如 [Maven 项目经理](https://maven.apache.org/)，以及他们一直在阅读的 CI/CD 管道经理，如 Jenkins。

巴雷特说，这两种方法都没有错，也没有谁比谁更正确。它们是 Java 开发人员构建工作应用程序的两种有效方法，只是到目前为止，这两种方法都限制了他们的部署选择。他断言，所谓的“云使能”平台通常会迫使开发人员在外部运行他们的关键服务，例如持久数据库，这可能是因为这些服务需要不同的协议，或者使用特定的 IP 地址或端口，或者可能会强加持久性要求。他的断言暗示“启用云”的绰号可能只是一个掩饰，因为它只能在中途解决一个或另一个问题。

“我们在 OpenShift 中从未采用过这种方法，”Barrett 说。“我们一直试图设计部署模式，几乎可以在容器中运行任何东西。”为此，他说，Red Hat 的整个 JBoss 产品组合现在都可以用于容器映像，用于选择性绑定到容器化的 Java。

## 堆叠的堆叠

我请 Barrett 和 Gracely 说出这样一个开发人员在移民到 OpenShift 后仍然需要学习的三件事，即使 Red Hat 尽了一切努力让他们有宾至如归的感觉。

“人们需要意识到他们的应用程序将非常有弹性，”Barrett 回应道。也就是说，平台本身将对应用程序进行扩展。因此，当你在代码中使用原语时，你需要记住实例很重要，信息的来源将比过去更加不稳定。”

作用域是 Java 中一个非常重要的概念。Java 对栈*的想法与我们报头上的栈非常不同。它是分配给特定 Java 线程的内存。相比之下，*堆*由所有线程共享的内存组成，数组变量和类实例变量就是从这些内存中分配的。对于一个连续的、自包含的虚拟机来说，这是一个非常稳定的结构……但对于高度分布式的系统来说就不一样了。*

Barrett 指出，当一个 Java 应用程序的实例跨数据中心、可用性区域或地理位置进行复制时——这种事件不再被认为是偶然的或偶然的——应用程序与数据源、提要或数据流的任何连接都需要不断地进行一致性检查。

## 发现的发现

Brian 优雅地补充了这个编程新领域的一个未被重视的事实:orchestrator(在 OpenShift 的例子中是 Kubernetes)自动提供关键的系统服务，不再需要手动编码。其中最主要的是*服务发现*。

Gracely 说:“现在这些功能可能会暴露给 Java 开发人员，他们开始问自己，‘我是否想继续只使用我的 Java 框架内的本地服务，不管是旧的还是新的？’或者，他们开始探索，“我应该利用像 Kubernetes 服务发现这样的东西，或者来自 Kubernetes 的其他开发模式吗？我是想编写完全受这个 Java 框架的能力约束的代码，还是它能以某种方式帮助我利用平台的固有特性？"

对于已经习惯于依赖来自 JBoss 和 [Spring](https://docs.spring.io/spring/docs/current/spring-framework-reference/html/mvc.html) 的 Java 框架来扩展其语言能力的开发人员来说，现在有一个平台支持他们，执行不需要这种扩展的功能。Java 开发人员可能还不习惯这种共存。

这些服务中的另一个可能衍生出新的开发模式(在这种情况下我有意识地避免使用“spring”这个词)的是 [StatefulSets](https://kubernetes.io/docs/concepts/workloads/controllers/statefulset/) ，Kubernetes 正在进行的实验，从 1.5 版本开始，用于声明其容器需要持久存储和更有分寸的扩展方法的 pod。虽然 OpenShift 在过去支持有状态实例化，但对于 3.5 版本，该平台开始支持 Kubernetes 建议的标准——人们承认，这是一个正在移动的目标。

Barrett 解释说，在 StatefulSets 之前，Java 应用程序仍然可以跨多个实例共享存储，或者在允许每个实例拥有自己的块存储的同时，需要对数据库进行分片。但是将这些配置传递给 Kubernetes，然后期望 orchestrator 考虑 CPU 或内存的使用情况，或者在必要时自动添加实例，这是不可能的。

“现在有了 StatefulSets，我们有能力连接这两个世界，”他告诉新堆栈。“我们可以教给 Kubernetes 更多的复杂性，而不仅仅是添加实例——‘先停下来做 X，Y，Z，*，然后*添加实例。’"

Barrett 继续说道，当云服务的开发者正在构建供租户客户使用的部署特性时，这种情况就会出现。在数据中心内对应用程序部署的精确细节进行硬编码是非常容易的——事实上，经验丰富的 Java 开发人员已经习惯了硬连接的配置。但是，如果没有登台环境和 IT 操作员之间的某种类型的接口，将这种硬连接转换为模板(其细节是由客户填写的变量)是不可能的。

所以 Red Hat 向 Java 开发者开放了 Kubernetes 的声明集。这样做，是让他们继续做他们以前做过的事情。

“这就是 PaaS 概念。同时，我们不要失去容器平台的概念，”Mike Barrett 说。“我们在 OpenShift 中提供了这种双重关系，利用 Kubernetes，而其他一些 Kubernetes 提供商主要提供其中一种……如果您有代码，我们可以要求您提供代码。如果你不想学习任何关于容器或 Kubernetes 的东西，那再好不过了。您只需填写我们的向导，它非常适合作为 Java 开发人员的您，也许您甚至不看我们的用户界面。也许你在你的 Eclipse IDE 中。我们有这些集成，你仍然可以利用 Kubernetes 中那些非常复杂的东西。”

当两种架构如此截然不同时，我们对一方平台的最大期望就是对另一方做出让步。

[红帽](https://www.openshift.com/)是新堆栈的赞助商。

1909 年，公共领域，正在建设中的曼哈顿大桥。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>