# Realm 的移动开发平台链接到 PostgreSQL 以绑定企业数据

> 原文：<https://thenewstack.io/realms-mobile-development-platform-links-postgresql-tie-enterprise-data/>

帮助开发人员创建实时反应应用程序的移动平台 Realm 周二发布了其与 PostgreSQL 数据库管理系统的新连接器，试图更好地将世界上最受欢迎的数据库之一与现代移动应用程序联系起来。

Realm 的联合创始人兼首席执行官 [Alexander Stigsen](https://www.linkedin.com/in/astigsen/) 在声明中表示:“移动应用需要具有反应性和协作性，才能引人注目，但它们也需要连接到遗留系统才能发挥作用。”。

Realm 移动平台用于 NCAA 三月疯狂应用程序，以及星巴克、NFL 和百威啤酒的应用程序。[网飞](http://techblog.netflix.com/2017/03/downloads-on-android.html?m=1)选择它来帮助其用户实现离线功能。

Realm 选择创建 20 岁的 Postgres 的连接器，因为它在企业中广泛使用。斯蒂格森说，与其他广泛使用的企业系统的链接正在进行中。

“使用[Postgres]有很多很好的理由，但就像许多在移动革命之前就已经存在的技术一样，它不是为移动而设计的。很慢。它要求开发人员编写请求，然后在开发人员可以更改应用程序正在处理的数据之前获得响应。Realm 首席营销官保罗·科帕奇说:“如果你试图建立一种非常敏捷、协作式的体验，Postgres 需要编写一大堆代码来实现这一点。

他说，在代码中，你向数据库请求一点信息，然后等待信息返回。而你正在做的正是用户想要体验的时候。

他说，“它有点儿用，但有点儿笨重。”他补充说，在移动应用程序中使用时，它们往往很脆，不灵活。

斯蒂格森说，使用 Realm Mobile 数据库及其相关的对象同步和事件处理服务器，连接器链接到您的数据，并确保移动设备上的每个更改都传输到数据库，反之亦然，实时同步到所有移动设备。

Postgres 与 Realm 平台对话，Realm 在后台自动实时更新应用程序。Kopacki 说，它不需要开发者编写额外的代码，没有脆弱性，没有将数据从 Postgres 翻译到移动应用程序的复杂排列。

## **‘活’物体**

在之前关于新堆栈的故事中， [EnterpriseDB](https://www.enterprisedb.com/) 、[的产品开发高级副总裁 Marc Linster](https://twitter.com/marclinster) 指出 [JSON-B](http://json-b.net/) 是 Postgres 中更好地支持移动的一个特性。

“从浏览器到数据库，一直到堆栈，你都可以使用 JSON-B。其他数据库要求你为移动浏览器解构文档，然后从零碎的部分进行处理。在 Postgres 中，你可以使用整个文档，”林斯特说。EnterpriseDB 赞助开源项目，并提供 PostgreSQL 的商业发行版。

Kopacki 认为，大多数 Postgres 公司专注于扩展流行的数据库，而不是改善其在移动设备上的使用。Realm 被认为是作为移动开发工具的 [SQLite](https://www.sqlite.org/) 和[核心数据](https://developer.apple.com/library/content///documentation/Cocoa/Conceptual/CoreData/index.html)的替代品，提供由后台数据库驱动的实时数据同步。

Realm Mobile Platform 是一个轻量级的对象容器，它称之为 Realm，在这个容器中，数据可以被查询、过滤、互连和持久化。该公司解释说，对象是本地的:

“您不必从数据库中复制对象，修改它们，然后再保存回来——您总是在与“活的”真实对象打交道。如果一个线程或进程修改了一个对象，其他线程和进程可以立即得到通知。对象总是保持同步。

领域对象服务器上的对象将在应用程序需要时被下载，然后领域[容器]的本地副本将与对象服务器的副本保持完全同步。

领域总是以“离线优先”的方式运行:读写发生在领域的本地副本上。同步是自动的和完全事务性的，一旦数据连接可用就开始同步。"

Kopacki 认为，如果连接不稳定或丢失，确保用户体验是 Realm 的另一个关键方面，这是 Postgres 不可能做到的。另一方面，Realm 在客户端使用嵌入式数据库，同步实时发生。

“如果你失去了信号，你已经得到了最新的数据集，因为在后台领域不断保持同步，”他说。

“所以如果火车进入隧道，你可以继续工作。如果你正在使用电子商务应用程序，你可以继续交易，当你走出隧道时，它会从停止的地方重新开始并重新同步。你甚至不会知道。感觉不会有什么不同，”他说。

Realm Mobile 数据库可用于 Android (Java)、iOS (Objective-C 和 Swift)、 [Xamarin](https://www.xamarin.com/) 、React Native 和 [Node.js](/tag/node.js/) 。

Realm Object Server 可用于 Red Hat/CentOS 和 Ubuntu Linux，以及 Amazon EC2。

红帽是新堆栈的赞助商。

专题图片:[手机](https://www.flickr.com/photos/kiwoo/31913481230/in/photolist-QC5W81-T7gWTP-SQVd6e-9EXXy1-T1Bxch-SXkdwm-5We4kH-Qy6g2S-Rvspuw-dYGU1i-RvrfWw-wEpPfx-RRBWV8-pAZUn-T2TZg3-6UUbBF-n9TLAB-ofjWiH-vHoxPU-ofjFUJ-vHozJq-5fhetf-wC63dh-8dLsEP-wnMECU-wnMJgf-omVWjD-RQeWiM-RRBXg8-oFbm1p-9cwGHs-2QUato-vacRX-owBwLC-firTKX-oD9K1g-ab6Akd-ouMGXJ-SAAzuz-4JCsEi-nRhieu-2gsAtW-T1ZBNM-mXmTUX-dRXdRu-nbWc8a-8EPzhy-981U95-RPBHbj-b1S3YF)作者[丹尼尔·朱利亚·伦德格伦](https://www.flickr.com/photos/kiwoo/)，授权 **[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)** 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>