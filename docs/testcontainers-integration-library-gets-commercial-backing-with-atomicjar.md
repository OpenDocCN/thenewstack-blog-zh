# Testcontainers 集成库获得了 AtomicJar 的商业支持

> 原文：<https://thenewstack.io/testcontainers-integration-library-gets-commercial-backing-with-atomicjar/>

开源集成测试库 [Testcontainers](https://www.testcontainers.org/) 的创始人推出了一家名为 [AtomicJar](https://atomicjar.com/) 的初创公司，旨在让开发者在应用投入生产之前，更容易了解这些应用与外部资源的集成情况。

[Richard North](https://github.com/rnorth) 在 2015 年担任德勤数字首席工程师时创建了 Testcontainers。联合创始人谢尔盖·叶戈罗夫(Sergei Egorov)是 Pivotal 的前员工工程师，也是许多开源项目的贡献者，五年前加入了他的努力。

在本周的 Love 大会上，他们宣布了新公司和由 Boldstart Ventures 牵头的 400 万美元的种子基金。

Boldstart Ventures 创始人兼管理合伙人 Ed Sim 表示:“这是一个巨大的机会，因为应用程序越来越分散，依赖性越来越强，公司希望在软件开发生命周期的早期发现这些集成问题。

North 创建了 Testcontainers 来解决他在咨询工作中遇到的一个常见问题:集成测试的痛苦。他说，这至关重要，但却被认为太难了，太难做对。

当“你正在开发一个软件，你有一段代码需要与一个外部依赖进行交互，比如一个数据库，或者消息队列，或者一些其他类型的资源，你想要确保你刚刚写的代码在你连接到这个东西的时候能够正常工作，”他解释道。

“传统上，有两种方法可以做到这一点:一种是你实际上把它和真实的东西联系起来。但这需要您实际配置并运行，就像您的真实数据库一样，在您的本地开发机器和 CI 机器上，并在每个开发人员的机器上拥有完全相同的配置，这是一件非常痛苦的事情。我们经历了多年的手动设置。这不是一次特别愉快的经历。

“另一种方法是，你只需说，‘好的，这是我编写的与数据库对话的代码，这是我所知道的数据库应该如何运行。我会假设，只要我的代码做了我的预期测试代码说它应该做的事情，那么它就没问题。但是当然，当你到了生产阶段，你会发现你对外部依赖行为的一些假设是错误的。然后，在生产或新的试运行环境中第一次出现故障，或者其他情况，[并且]在最初编写代码之后很长时间。"

他说，随着 Docker 越来越受欢迎，它提供了一种方法，可以轻松快速地创建您将在生产中连接到的东西的副本，让它们在测试套件期间运行，然后在之后再次被拆除。

Testcontainers 是一个开源库，允许开发人员使用他们的代码来“用容器测试”依赖项，如数据存储和数据库 Redis、PostgreSQL)，以及可以在 Docker 容器中运行的任何其他东西(Kafka、RabbitMQ、Selenium 等)。).

“所以我们为 Testcontainers 所做的是，我们创建了这个框架，它将与您的测试库集成，我们将为您提供这些依赖关系，以便您可以声明它们是什么样的——映像名称、它们需要公开的端口、需要加载到依赖关系中的初始模式之类的东西，诸如此类的东西——您可以用代码编写它，以便每个开发人员都可以获得它。他们所需要做的就是拥有这个库，并为他们的测试准备相同的代码，他们将得到一个完全相同的依赖关系的复制品，就像团队中的每个人一样，”他说。

Testcontainers 每月被 Spotify、 [Google](https://jamesward.com/2021/03/16/the-modern-java-platform-2021-edition/) 、 [Instana](https://www.instana.com/blog/towards-better-integration-tests-with-testcontainers/) 、甲骨文、 [Zalando](https://engineering.zalando.com/posts/2021/02/integration-tests-with-testcontainers.html) 等公司下载超过 100 万次。

“由于 Docker 映像的灵活性，Testcontainers 模块现在可以旋转带有数据库、web 浏览器或模拟 AWS 端点的容器。这就是 Testcontainers 对于功能测试的强大之处— 它提供了一种在代码开始之前建立依赖关系的灵活方式，”一个 Capitol One [博客](https://www.capitalone.com/tech/software-engineering/testcontainers-and-localstack-functional-testing/)如是说。

根据 Egorov 的说法，作为一家公司，AtomicJar 不打算从开源项目中拿走任何东西，并将继续发展。

“我们不想启动类似 Testcontainers Pro 或 Testcontainers for enterprises 这样的东西。但相反，我们意识到我们有一个巨大的机会获得免费产品……让运行基于 Testcontainers 的测试变得更加容易。它计划在今年年底推出一款 SaaS 产品，但目前正致力于帮助客户更好地体验测试解决方案。它希望让测试更快、更安全，并与想要测试但可能甚至不部署到生产环境中的客户合作。

根据 Egorov 的说法，竞争技术更多地基于类别，例如用于浏览器测试的 [Cypress.io](https://www.cypress.io/) 。他说，AtomJar 正在与 it 部门进行合作谈判，而诸如 [Garden.io](https://garden.io/) 和 [Tilt](https://tilt.dev/) 和 [up9](https://up9.com/) 等产品则专注于复制生产环境和 Kubernetes。

“在我们的情况下，我们提供了一个通用工具，不需要任何人开始部署到 Kubernetes，就可以测试一些东西，”他说。“有时你甚至不生产。有时候，也许你刚刚开始开发你的服务，还没有产品，但是你已经想运行你的测试了，”Egorov 说。

“Testcontainers 给了开发人员这一点。这有助于他们消除所有这些细节，消除运行测试依赖关系的复杂性，同时不必考虑，“好吧，我需要将它部署到生产环境中，以便我可以测试它”，因为这是应该如何进行测试的错误思维方式。”

AtomicJar 正在为有限数量的企业开放私人测试版，以测试该公司添加到 Testcontainers 的增强和扩展。在此加入等候名单[。](https://atomicjar.com/)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>