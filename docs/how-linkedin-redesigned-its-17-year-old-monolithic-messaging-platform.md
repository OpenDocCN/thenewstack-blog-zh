# LinkedIn 如何重新设计其 17 岁的单一消息平台

> 原文：<https://thenewstack.io/how-linkedin-redesigned-its-17-year-old-monolithic-messaging-platform/>

微软的 [LinkedIn](https://www.linkedin.com/feed/) 上的第一条消息是在 2003 年 5 月 5 日服务推出的当天发出的。LinkedIn 消息平台现在存储了 17 年的消息(由 17 年不同的产品功能创建)，并且发送的消息数量不断增加。在过去的四年里，它翻了两番，但是在四月的第一个星期，与前一年相比，消息增加了 14%;3 月底，同事之间每周发送的消息数量激增(增长了 21%)，用户之间通过 LinkedIn 新闻源互相发送消息的数量激增(增长了 14%)。

最初那些信息看起来很像电子邮件；现在它们看起来更像聊天，有线程、群组对话、表情符号，没有主题行。驱动该消息系统的代码已经更新，变得越来越复杂，但驱动所有不同 LinkedIn 消息体验的通用基础架构多年来没有发生太大变化。

消息平台基础设施团队的工程经理 [Manny Lavery](https://www.linkedin.com/in/mannylavery/) 告诉 New Stack:“虽然只有很少的代码从 2003 年保留下来，但很多基础设施还是一样的。”。

最初的基础架构是在单个数据中心运行的单个 Oracle 数据库，两个表支持两个服务:一个用于存储消息，其中包括多个 LinkedIn 产品的消息的所有业务逻辑，另一个负责消息的不同交付方式—推送通知、不同的电子邮件格式以及跟踪消息的接收。

随着时间的推移，LinkedIn 增加了新的数据中心，并使用自己的 NoSQL JSON 数据库 [Espresso](https://engineering.linkedin.com/espresso/introducing-espresso-linkedins-hot-new-distributed-document-store) 切换到具有分片架构的分布式数据存储。然而，向外扩展也带来了自身的复杂性；不同的邮箱被划分到不同的碎片中，个人数据路由服务跟踪谁的收件箱在哪个碎片上，双向复制将每个碎片的副本放入不同的数据中心，以防可用性问题。

2016 年，LinkedIn 进行了重大的产品重新设计，并不断添加更多功能，最终将名称改为 Messaging。但它仍然建立在为两个人之间的电子邮件式对话设计的数据架构上，使用的代码库已经超过十年，这使得很难正确地分割数据以进行扩展，关键的业务逻辑仍然嵌入在消息存储的代码中。

## 解开混乱

当任何 LinkedIn 产品团队想要为消息传递添加功能时，基础架构团队都会参与进来——有时会为他们编写代码或与他们合作开发——并负责在生产中维护所有新代码。但是，虽然他们拥有代码，不同的产品团队拥有业务逻辑、背后的推理以及对其进行任何更改的决策。

[消息平台](https://engineering.linkedin.com/blog/2020/designing-our-new-messaging-system)支持五种不同的 LinkedIn 业务线:消费者网站，为人力资源和招聘团队提供一种电子邮件消息的“人才解决方案”，提供不同类型电子邮件的销售解决方案，LinkedIn 的营销解决方案和具有高级消息选项的高级服务(以及一些其他内部客户)。所有这些产品都有自己的业务规则来处理消息传递中的特定功能。

“所有这些业务用例都存在于 messenger 团队负责长期维护的单一代码库中，”Lavery 告诉我们。“随着公司的扩张，随着我们在 17 年间增加了更多的业务线，用例变得更加复杂，数量也越来越多，这对我们的工程师来说真的很难。没有人能够完全理解平台中发生的每一个业务用例。”在重新设计之前，大约有 60 种不同的定制业务逻辑。

基础设施设计使得编写新代码变得更加困难和缓慢，开发人员对最简单的更改变得过于谨慎，因为团队越来越多的时间都花在了保持运行上。"维修费用消耗了大部分工程时间."

由于担心随着时间的推移，新的架构可能会成为同样多的维护负担，新平台不仅改变了数据架构，以关注对话和内容，而不是单个消息。它还被设计成一个插件基础设施，服务所有权分布在基础设施和产品团队之间。

“我们开始分解内容，以便可以共享的内容被共享，不必共享的内容被隔离到单个服务中，我们围绕责任归属设计我们的系统，然后用提供数据的数据库来备份这些责任服务。”

“我们确保我们可以作为一个平台运营，不知道正在我们身上执行的业务逻辑。从我们的角度来看，信息只是内容，一旦你做出决定，很容易说‘我只是要获取内容并为你存储，我要以你给它的完全相同的状态检索给你’，然后他们可以按照他们想要的方式呈现它。”

消息传递的基本单元不再是整个收件箱，而是对话，这使得提供快速搜索和检索时间变得更容易，因为对话和消息可以被分解并传播到整个数据库。对话与其中的消息分开存储，并引用回消息，以避免非常活跃的数据库记录的“热键”问题，这些问题可能会降低系统速度。

“现在，当成员获取他们的收件箱时，他们不是固定的邮件列表；他们正在获取一个对话列表，如果他们访问其中一个对话，我们就可以访问其中的信息，”Lavery 解释道。最初，只检索最近的对话，并且只检索那些对话中的前几条消息，因为这是用户最可能寻找的。为了速度，最近的对话都存储在数据库的同一个部分。

“现在，你已经将搜索问题从‘我如何在数十亿次对话中找到数据’简化为‘我只需要找到与一个人的前十次对话，并且对于这些对话中的每一次，我只需要找到前几条消息。’现在你的数据检索问题非常小，而且是完全相同的数据大小检索问题，不管他们的对话列表变得有多大。"

这个列表可能会很大:一个新的 LinkedIn 会员可能只有几百条消息。其他人有 75 万或 100 万条消息。“如果你是一名在这个平台上工作了 10 多年的招聘人员，你可能一天会发几百封电子邮件，一周有五六天。无论你的收件箱有多大，你的检索时间都应该是一样的。”

当用户回读一段对话时，会检索到更多的消息。“Espresso 就是为了进行分页式检索而构建的，因为它是 NoSQL，因为只有我们必须存储的引用，没有连接，所以数据库检索变得非常快。”

新设计确实占用了更多的存储空间，因为它有多个表和多个索引来加快检索速度。但是 Lavery 坚持认为，性能和可靠性的提高远远弥补了这一点。

“工程时间很贵。尽管新系统在存储方面确实有一些额外成本，但与你为非常困难的问题提出技术解决方案所花费的维护和工程时间相比，这相对较低。”

## 拥有问题

同样的决策决定了平台服务，故意保持较低的数量，而不是选择完整的微服务架构，作为获得长期有效团队结构的一种方式。

消息传递平台的服务不到一打，有些很小，但有些相当大，每个服务都可以由一个高级技术领导拥有。“我们在许多工程师中传播领导力，这真的让我们在开发过程中加快了速度，因为我们可以引入对平台整体不太熟悉的工程师，将他们组织在这些技术领导者周围，并快速执行。”Lavery 可以给开发人员更多的责任，而不会让团队中的两个专家中的一个成为瓶颈。

当平台的初始部署计划失败时，这很有帮助。该团队计划让旧消息保留在现有系统中，当他们将成员转移到新系统时，新消息会在新系统中创建。然后，他们意识到他们意外地创建了一个具有最终一致性的分布式系统，因为对于没有迁移到新服务的成员，消息必须复制到旧系统。

“我们开始看到非常糟糕的会员体验，等待那些消息出现，并确保一切都是同步的。”这意味着回滚已经迁移到新系统的 1%的成员，并从整个公司引入额外的工程师来重新制定部署计划。

通常在项目中增加更多的员工会使项目速度变慢，但是因为每项服务都由一名技术负责人负责，所以他们能够指导额外的工程师，回到正轨，并加快推广速度，达到每两周一次。

“你见过多少其他系统花了三年多的时间才构建出 ramp，而且每隔几周就没有问题？在两个月内，它现在为每周创建的数亿条消息提供服务，为数亿名成员提供服务，并在其数据库中存储了数十亿条消息。”

服务所有权方法也在为构建新功能而努力。产品团队仍然与基础设施团队一起工作，但是所有定制的业务逻辑都从消息存储中迁移出来，并封装到插件中以实现其功能，不同的服务所有者可以在需要帮助时与他们一起工作。“我认为，如果我们有 20 多个服务，今天就很难确保我们有这些技术领导者来帮助我们，”Lavery 建议道。

新的架构意味着产品团队可以试验和测试新的想法，而不需要几个月的开发。“如果你的用例在我们已经建立的插件风格架构内工作，并且你不需要额外的改变，你应该能够在一个月内建立并准备好你的插件，”他说。“如果不成功，我们可以轻松退出；如果成功，我们可以加倍下注。”

这也加快了一些长期要求的功能的工作，如能够编辑和删除消息，尽管在技术上不是不可能的，但在旧系统上构建这些功能非常困难。过去，向两个人发送一条消息会创建三条记录，发件人一条，收件人一条，这意味着一致性问题。

如果我想编辑该邮件，我必须编辑三次，并确保这三次编辑都成功现在，该消息是三个人都可以引用的记录。

“该引用告诉我们该邮件在哪里，它还包括诸如您是否读过它、它是否被设置为删除之类的内容。这大大简化了编辑和删除，因为我只编辑一条记录。我只需要确保编辑成功，我们有系统来确保编辑尽快在世界各地进行，以便我们所有的数据中心都得到更新。”

另一个受欢迎的功能已经开始推出，让同一组的人发送消息请求与还没有 LinkedIn 联系的人开始对话。“这是我们很长一段时间以来收到的最大的投诉之一:为什么我必须连接才能与另一个成员进行对话？”

消息传递团队提出的设计原则帮助他们逐步交付特性。LinkedIn 消息是加密的，在被创建到消息数据库之前，会被检查是否是垃圾邮件。但 LinkedIn 并没有阻止垃圾邮件，而是向用户显示一条消息可能是垃圾邮件的通知，让他们忽略或阅读它。现在，如果一个成员后来确认一条消息是垃圾邮件，它可以在整个服务中异步删除。

由于该系统是可扩展的，LinkedIn trust 团队能够像垃圾邮件检查一样添加反性骚扰检查，现在该系统正在扩展到其他形式的骚扰，以及通知用户有关帐户被接管和密码重置等问题——旧系统不够灵活，无法发现这些问题。

采用这种更结构化的方法来设计平台意味着用户将更快地获得新的功能，这对从事该项目的工程师的职业发展更有利。

“火灾确实会吸走房间里的大量氧气，所以如果你的系统不断出现这类问题，人们往往会求助于几个已知能够解决这类问题的工程师，但这些工程师不断解决问题并不是一个好的职业选择，团队不断解决这些问题也不健康。”

“我见过的所有工程师都是解决问题的人，但他们也有自己想要构建的东西或想要实现的东西。如果你能真正专注于这些问题，团队的整体士气就会得到提升。”

由[Gunnar ridderstrm](https://unsplash.com/@gunnarridder?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/library?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

*目前，新堆栈不允许在该网站上直接发表评论。我们邀请所有希望讨论某个故事的读者通过 [Twitter](https://twitter.com/thenewstack) 或[脸书](https://www.facebook.com/thenewstack/)访问我们。我们也欢迎您通过电子邮件发送新闻提示和反馈: [feedback@thenewstack.io](mailto:feedback@thenewstack.io) 。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>