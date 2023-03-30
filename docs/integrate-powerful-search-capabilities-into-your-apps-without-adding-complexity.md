# 将强大的搜索功能集成到您的应用中，而不会增加复杂性

> 原文：<https://thenewstack.io/integrate-powerful-search-capabilities-into-your-apps-without-adding-complexity/>

[](https://www.linkedin.com/in/marcuseagan/)

 [马库斯·伊根

马库斯是 MongoDB Atlas Search 的高级产品经理，也是 Apache Lucene 和 Solr 项目的开源贡献者。此前，他曾在福特汽车公司 Lucidworks 工作，并成功创立和出售了一家网络安全初创公司。在业余时间，他是一名天使投资者，并积极指导那些来自传统上代表性不足的群体的人，这些人正在寻求进入技术和软件开发领域。](https://www.linkedin.com/in/marcuseagan/) [](https://www.linkedin.com/in/marcuseagan/)

搜索引擎已经成为几乎每个面向用户的应用程序的基本组件。对于零售商来说，搜索结果和推荐直接推动了收入，因为它们使用户能够快速找到产品，同时为企业提供了更好地了解每个客户并加深参与的机会。

对于社交媒体、数字媒体和电子商务应用程序来说，能够根据用户的搜索偏好定制独特的体验，以便向他们展示更多相关内容，这一点尤为重要。例如，如果我在抖音上搜索室内植物护理视频，我将更有可能收到这些类型的推荐。

将强大的搜索引擎整合到这些和其他类型的应用程序中通常是没有商量余地的。幸运的是，现在有许多搜索技术可用——其中许多都基于业界领先的开源 Apache Lucene 搜索引擎。但是，同步、缩放和维护搜索引擎以及运营数据库会给应用程序开发和运营增加严重的复杂性。

## **开发人员将搜索与运营数据库集成的考虑事项**

如今，应用程序用户希望快速、轻松地访问信息。您希望能够快速轻松地找到您正在寻找的内容，并且希望结果是可过滤的和相关的。将全文搜索整合到您的应用程序中对于满足用户期望和最大化用户体验至关重要。

此外，无论您身处哪个行业，您作为一家公司取得成功的能力都取决于您使用软件和数据进行创新的速度。这意味着您希望让您的开发团队尽可能地高效，而不是在无差别的工作上浪费时间——例如管理数据库或在系统之间同步数据。

大多数传统数据库和查询语言都没有针对全文搜索进行优化，因此开发人员通常使用不同的技术来满足他们的速度和相关性要求。对于精确匹配用例，您可以选择内置的数据库功能，为网站搜索栏提供动力的开源搜索引擎，以及为内部知识库门户提供专门的搜索引擎。

大多数开发人员在他们的操作数据存储库旁边建立一个单独的搜索数据库，以利用搜索优化的索引和查询功能。但是如果您使用不同的搜索引擎和数据库平台，您将需要在两个环境之间复制数据并保持一致性。你还需要管理和支付第二组数据所在的搜索系统。如果您有老化数据的策略(例如，最终将数据发送到冷存储),您将需要老化搜索引擎和数据库中的数据。最后，您必须考虑让人们使用和管理不同技术所需的学习曲线和资源专门化。

还有另一个选择。MongoDB 引入了 [Atlas Search](https://www.mongodb.com/atlas/search?utm_source=the_new_stack&utm_medium=paid_media_content) 让组织更容易将强大的全文搜索功能集成到应用程序中，同时最大限度地降低后端复杂性。由于 Atlas Search 与全球多云数据库服务 [MongoDB Atlas](https://www.mongodb.com/cloud/atlas?utm_content=logo-sponsorshippage&utm_source=thenewstack&utm_medium=website&utm_campaign=platform) 完全集成，因此无需复制数据和管理不同的数据环境来为您的应用程序添加搜索功能。你有一个单一的记录系统。您可以避免设置、维护和扩展单独的搜索平台。

Atlas Search 的工作原理是在 MongoDB Atlas 集群的每个节点上嵌入一个 Apache Lucene 数据库，并且设计为易于使用，不需要任何额外的基础设施设置。您为集合中的文档定义字段映射和索引选项，然后 Atlas Search 将对数据进行索引，并使其可用于基于相关性的搜索。一旦数据被 Atlas Search 索引，就可以使用 MongoDB 聚合管道构建搜索查询。

Atlas Search 有几十个搜索[操作符](https://docs.atlas.mongodb.com/reference/atlas-search/operators/?utm_source=the_new_stack&utm_medium=paid_media_content)，你可以用它们来提炼你的结果，并在一次操作中打造复杂的搜索逻辑——比如自动完成、过滤和评分。

重要的是，Atlas Search 直接在您的操作数据库中提供丰富的全文搜索功能，从而使开发人员更容易将强大的搜索体验融入到您的应用程序中。您不必为技术堆栈中的另一项服务付费、设置和维护，也不必学习新的查询语言。

## **实现完全集成搜索的真实优势**

MongoDB Atlas Search 是一个相对较新的产品，但 1000 多家公司已经看到了使用它在其数据基础上构建快速、相关的全文搜索的好处。对于刚起步的公司来说，这是一个显而易见的选择，他们不想要管理多个文档存储的复杂性。对于那些已经知道将搜索集成到应用程序中的痛苦的团队来说，这也是一个很好的选择。

[Current](https://current.com/)——美国领先的挑战者银行，拥有超过 200 万用户——正在[使用 MongoDB Atlas with Atlas Search](https://www.mongodb.com/blog/post/next-generation-mobile-bank-current-using-mongodb-atlas-google-cloud-make-financial-services-accessible-affordable-all?utm_source=the_new_stack&utm_medium=paid_media_content) 作为其定制的 ledgering 系统的一部分，该系统名为 Current Core。Atlas Search 增强了其广受欢迎的点对点支付功能，并直接向 Current Core 的 MongoDB 数据库中存储的数据添加了搜索功能，无需手动复制或同步数据。

Blerp 是一个音频表达平台，面向流媒体用户、游戏玩家和任何喜欢分享音频迷因的人。它有超过 100，000 个基于 MongoDB Atlas 和 Atlas Search 的安装，这使得 Blerp 的 It 团队能够极大地简化他们的架构。

*我们希望了解更多关于您正在开发的应用程序以及您如何利用 Atlas Search 和 MongoDB Atlas 的信息。在这里了解更多*[](https://www.mongodb.com/atlas/search?utm_source=the_new_stack&utm_medium=paid_media_content)**。**

*<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*