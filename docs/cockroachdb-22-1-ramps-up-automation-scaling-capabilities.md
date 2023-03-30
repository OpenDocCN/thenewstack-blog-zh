# CockroachDB 22.1 提升了自动化和可伸缩性

> 原文：<https://thenewstack.io/cockroachdb-22-1-ramps-up-automation-scaling-capabilities/>

西班牙巴伦西亚—[Kubernetes 的](https://thenewstack.io/category/kubernetes/)致命弱点一直是它从未被设计为运行有状态的工作负载—数据库、键/值存储或任何保存来自其活动的客户端数据以用于当前运营和未来活动的应用程序。

近年来，Kubernetes 推出了一些功能，如[持久卷(PV)架构和控制器，如 StatefulSet 和 DaemonSet](https://kubernetes.io/docs/tasks/run-application/run-replicated-stateful-application/) ，以允许用户创建 pod 来适应有状态的工作负载。对于一些组织来说，像[集装箱附加存储](https://thenewstack.io/stateful-workloads-on-kubernetes-with-container-attached-storage/)这样的解决方案已经填补了这个空白。

根据[蟑螂实验室](https://www.cockroachlabs.com/?utm_content=inline-mention)首席产品宣传员[吉姆·沃克](https://www.linkedin.com/in/jwwalker/)的说法，在 Kubernetes 上运行有状态工作负载的困境的核心是需要将“分布式思维”应用到堆栈的数据层。

“我认为我们正在将[云原生](https://thenewstack.io/category/cloud-native/)原则应用于基础设施层，但我们将开发人员抛在了后面，因为他们仍然在旧世界中思考，”他在本月于这个地中海城市举行的 [KubeCon + CloudNativeCon，EU](https://www.cncf.io/kubecon-cloudnativecon-events/?utm_content=inline-mention) 上告诉新堆栈。

“因此，我们的应用和我们所依赖的基础设施之间存在一点点阻抗不匹配。”

Walker 的公司认为，数据层位于应用程序和基础设施之间，应该使用相同的分布式、随处运行的原则来创建。“如果数据库真正是云原生的，”他说，“我们可以开始转移这些事务性工作负载。”

周二，它发布了 CockroachDB 22.1，这是其分布式事务数据库的最新版本，具有旨在为开发人员和架构师的工作带来更多自动化和扩展效率的新功能。

沃克说，在其客户中，无论是全球企业还是年轻的初创公司，“我们都看到了具有前瞻性思维的公司的普遍趋势”。“这实际上是关于向自动化的转变。”

## CockroachDB 22.1 中的新特性

蟑螂实验室成立于 2015 年，最近有了新的发展势头。10 月，它发布了 cocroach db server less，这是一个 SQL 数据库，可与所有主要的公共云提供商合作，并与 Postgres SQL 兼容。(它目前处于测试阶段，计划在秋季全面上市。)12 月，该公司首次被纳入 [Gartner 云数据库管理系统魔力象限](https://www.gartner.com/en/documents/4009286)。

CockroachDB 的最新版本包括增强的自动化特性。其中包括:

*   新的管理 API 有助于自动化部署和扩展。
*   一个新的 CLI 工具，使用户能够通过代码管理和扩展其集群。
*   与 Datadog、Prisma 和 Google Pub/Sub 的集成。
*   管理数据流量的服务质量技术。
*   索引建议。
*   解决数据管理法规问题的新功能。

最后一项功能旨在支持从多个地区或国家开展业务和收集数据的组织。“我们可以控制数据的存储位置，”沃克说。“在表格级别，我们可以查看德国服务器上的所有德国记录。我们这样做是因为我们希望对其进行低延迟访问。但有些人喜欢它，因为它符合监管规定。”

他补充说，这种控制的粒度性质也旨在帮助数据库恢复能力:“我们可以说，数据存在于三个不同的位置。因此，我们可以承受整个地区的失败。”

## 云原生的未来:更抽象

沃克说，对于整个云原生生态系统来说，通过抽象出越来越多与开发人员最适合做的工作不直接相关的任务，让开发人员的体验变得更容易变得越来越重要。

“人们真的需要理解我们所有服务的可组合性吗？不，”他说。“我们正在用 Yaml 文件做过去需要一天才能完成的事情，这就像一个 *10 行* Yaml 文件。我们创造的效率令人惊叹，对吧？”

但是，他补充说，“我们依靠人们来理解我们正在简化的概念。我认为我们需要让那些不简单的概念消失。

沃克说，蟑螂实验室的最终目标是“基本上将数据库抽象到后台。”

他解释说，“我们希望只是云中的一个 SQL API 遍布全球的七八个端点。您只需连接到一个端点，并在一个 SQL 查询中请求数据，该查询将保证数据的正确性—因为有参照完整性。它将允许您进行连接，您的所有交易都将得到保证，它将以某种方式做出响应。这就是我们真正要建立的。

“让开发人员做开发人员做的事情——这就是构建应用程序逻辑。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>