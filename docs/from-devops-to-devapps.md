# 从 DevOps 到 DevApps

> 原文：<https://thenewstack.io/from-devops-to-devapps/>

[](https://www.linkedin.com/in/markrhinkle/)

[Mark Hinkle](https://www.linkedin.com/in/markrhinkle/)

[Mark 在新兴技术和开源领域有着悠久的历史。在共同创立 TriggerMesh 之前，他是 Node.js 基金会的执行董事，也是 Citrix、Cloud.com 和 Zenoss 的高管，在那里他领导了他们的开源工作。](https://www.linkedin.com/in/markrhinkle/)

[](https://www.linkedin.com/in/markrhinkle/)[](https://www.linkedin.com/in/markrhinkle/)

当 DevOps 的创始人——[Patrick Dubois](https://twitter.com/patrickdebois)、 [Gene Kim](https://twitter.com/RealGeneKim) 、 [Andrew Clay Shafer](https://twitter.com/littleidea) 、 [Damon Edwards](https://twitter.com/damonedwards) 和[John Willis](https://twitter.com/botchagalupe)——开始支持他们称之为 DevOps 的 IT 文化变革时，他们主张像测量、共享和自动化这样的变革。需要这些变化来沟通传统上孤立的开发人员和运营团队。这一运动提高了人们对抽象基础设施和在 [DevOps 部署策略](https://thenewstack.io/deployment-strategies/)中包含自动化的认识。如今，自动化基础架构部署并提供持续的 it 系统交付是无可争议的最佳实践。

云提供商正在将许多这类服务融入他们的产品中。他们提供完全托管的服务，而不仅仅是托管容器、Kubernetes 和无服务器功能。自动化部署工具，如[谷歌的 Anthos](https://cloud.google.com/anthos) 提供了一种现代化现有应用程序的方式，并在本地构建它们，本质上是系统化开发运维实践。像亚马逊的 Amplify 这样的后端即服务(BaaS)几乎可以完全接管管理基础设施的负担。无服务器计算(Amazon Lambda、Azure Functions、OpenShift Serverless)提供托管运行时和自动伸缩(向上和向下扩展)来将代码部署为离散的微服务，这些微服务可以编织到云原生应用程序中。

像这样的高度可扩展、低延迟的自动化基础设施的发展，就是为什么我认为我们现在正在进入我所说的时代(半开玩笑地说) *DevApps* 。DevApps 使开发人员能够使用 DevOps 带来的相同类型的自动化和实时响应来构建应用程序。

## **事件驱动架构**

云原生空间中出现的一个关键设计模式是事件驱动架构(EDAs)。这是 DevApps 的一个基础。事件只是系统中的一个变化。

事件驱动架构的核心思想是这些事件作为消息在多个系统间共享。为此，您需要以下内容:

*   **事件**:这些是描述系统变化的消息(许多事件是特定于系统的，但是理想情况下可以转换成标准化的格式，比如 [CNCF 云事件](https://cloudevents.io/)规范)。
*   生产者:以某种格式产生这些事件的系统。
*   **消费者**:接受这些事件并采取一些行动的系统。
*   **Brokers** :可以管理云事件的使用和交付的服务(想想 AWS 生态系统中的亚马逊 Kinesis)。在某些情况下，它们甚至足够复杂，可以将生产者的匹配方案的事件转换成消费者可以阅读的内容。

在 EDAs 中，事件触发工作流。例如，ServiceNow 可以产生触发 AWS 中流程的事件。您可以将信息从 Zendesk 传输到 Snowflake 进行高级分析。这是 AWS 本身定义良好的流程，Amazon EventBridge 充当无服务器事件总线，将数据从一个事件源路由到 AWS 目标。在 [TriggerMesh](https://triggermesh.com/) ，我们正在努力做同样的事情，但我们希望通过我们的跨云事件总线将任何云上的任何消费者与任何生产者联系起来。

## **批处理与事件驱动**

组织看到他们的系统必须处理的数据量呈指数级增长，而他们的传统 RDBMS 无法处理这些数据。信息处理需要基于批处理的 ETL(提取-转换-加载)来提供业务洞察力。虽然数据仓库的批处理对于获得历史洞察是有意义的，但这是一种向后看的策略。

寻求敏捷的公司需要实时洞察，而这正是事件驱动架构提供最大好处的地方。通过将业务逻辑从事件处理中分离出来，服务可以在彼此不知道的情况下存在。这使得应用程序成为可以存在于几乎任何地方的服务的组合。同类最佳服务，如 Twilio 的移动服务，可以与 Amazon Lambda 中运行的无服务器功能结合使用。或者可以将 Azure 中生成的安全日志转发给 Splunk 进行更深入的审查。因为这些自动化系统是实时交互的，所以流程是流畅的，并支持最新的行动。

## **申请流程**

底线是事件驱动的应用程序开发增长的原因是因为它增加了应用程序开发的灵活性并降低了复杂性。这允许数据通过事件消息更快地在应用程序(或云服务)之间流动。

也许考虑事件驱动的一个更简单的方法是从应用程序流的角度来考虑。例如，当在 Zendesk 中创建一个故障单时，该数据可以由 Amazon understand 自动分析，以确定客户的情绪是什么(愤怒、满意或困惑)。然后，存储在像 Amazon Redshift 这样的数据仓库中的购买历史、保修信息和其他相关信息可以用于向客户服务代表提供客户的完整图片，以便更方便地解决任何问题。

一种使用事件驱动架构的方法是利用 [JAMStack](https://thenewstack.io/jamstack-vs-wordpress-which-is-the-future-of-web-architecture/) 工具，这个术语是由 Netlify 创始 CEO 马特·比尔曼创造的。虽然 WordPress 是一个被绝大多数部署网站的用户使用的平台，但 JAMStack 是一个用于交付网络内容的工具集合。JAMStack 工具可用于在网络边缘部署网站，减少数据库调用次数，通过 CDN 让内容更贴近用户。但是，您也可以通过添加额外的云原生服务来扩展这个堆栈，比如用于身份验证的 AuthO。在收集用户数据的 web 应用程序中，信息可以存储在 Airtable 中。此外，当在 Airtable 中创建记录时，它可以自动更新您的订户列表，并将其添加到 Mailchimp 中的自动程序中。

这些强大的应用程序流可以取代在批量导入和导出中可能以慢得多的方式手动执行的步骤，以及由昂贵且较慢的人力资源完成的其他步骤。

## **总结**

对数字化转型和现代化感兴趣的组织正在从单一应用转向微服务。这允许团队在独立的服务上工作，而不依赖于其他开发人员之间的广泛协调。较小的团队需要较少的协调，沟通也更容易。例如:JavaScript 生态系统，成千上万的开发者通过 NPM 提供与 Node.js 兼容的 JavaScript 软件。或者扩展 Chrome 网络浏览器的大量插件，使 Chrome 不仅仅是一个网络浏览器，而是一个平台。所有的插件开发都是谨慎进行的，并且共同提供了广泛的功能。微服务提供了同样的好处，尽管是在一个公司内部。

在 Fred Brooks 关于软件工程和项目管理的开创性著作中，“[神话中的人月；软件工程论文](https://www.amazon.com/Mythical-Man-Month-Software-Engineering-Anniversary/dp/0201835959)，“传统上复杂的编程项目不能被完美地划分成离散的任务。原因是大型产品中的协调和沟通引入了难以置信的开销。这和杰夫·贝索斯和亚马逊成立著名的两个披萨团队是一个道理。意识到拥有一个不超过两个比萨饼的团队，已经足够减少复杂组织之间的沟通和管理时间表的开销。

通过采用基于无服务器功能和事件驱动架构的微服务架构，您可以利用自己的双披萨规则——大型组织可以独立、更快地在逻辑上划分工作和功能。虽然事件驱动架构和 DevApps 不是万灵药，但它确实为希望降低复杂性、提高敏捷性和利用云原生架构强大功能的公司提供了相当大的好处。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>