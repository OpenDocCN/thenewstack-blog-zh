# MySQL 和 Quip 的原子数据层

> 原文：<https://thenewstack.io/mysql-atomic-data-layer-quip/>

布雷特·泰勒在硅谷有着辉煌的历史。他因开发[谷歌地图](https://www.google.com/maps)和[应用编程接口](https://developers.google.com/maps/)而声名鹊起，这些应用编程接口让这项服务变得如此流行和有用。在短暂的风险投资后，[泰勒](https://www.linkedin.com/in/brettaylor)创建并出售 [FriendFeed](http://blog.friendfeed.com/) 给[脸书](https://www.facebook.com)。现在，他是 Quip 的首席执行官和创始人，Quip 是一套在线协作生产力工具，用于文档、电子表格和其他商业活动。

构建像一套业务工具这样的东西并不是一件简单的任务，尤其是当您还托管这些工具的时候。因此，泰勒和他的团队构建的架构没有用时髦的词语或花哨的新技术装饰。相反，这家初创公司的基础设施易于其工程师理解、维护和扩展。

为此，Quip 并不是建立在像 [MongoDB](https://www.mongodb.com/) 或 [CouchDB](http://couchdb.apache.org/) 这样的花哨的 NoSQL 文档库之上。它建立在 MySQL 的基础上，增加了一些 Redis 和 Memcached。MySQL 是底层的持久性数据存储，Redis 用于非持久性的东西。

泰勒说，这是一个类似于为 FriendFeed 设计的系统。Taylor 说，数据层在协作编辑环境中工作的真正关键是尽可能以原子方式存储数据，并且从不进行连接。

“我们使用非常标准的数据存储，但在这些存储中存储不透明的对象，并且不使用连接之类的东西。这使得分片变得更容易，并且您不需要担心将数据放在一起进行复杂的连接。这也使得跨客户端和服务器的同步变得更加容易。泰勒说:“这些系列化的产品被到处复制。

## 不冲突

泰勒说，建立一个协作文档编辑系统的好处之一——这甚至可以追溯到道格拉斯·恩格尔巴特 1969 年的《所有演示之母》——是人们通常都在做他们自己的事情，而不是为一个单元格或一个单词而争斗。

[https://www.youtube.com/embed/yJDv-zdhzMY?feature=oembed](https://www.youtube.com/embed/yJDv-zdhzMY?feature=oembed)

视频

这意味着 Quip 是为效率而生的。泰勒说，他和 Quip 的人并不反对漂亮的新的以文档为中心的 NoSQL 数据存储，只是团队希望在其他地方优化创新，而不是在数据层。

“我们有一个独特的模型，它看起来不太像一个文件，尽管它本身就是一个文件，”泰勒说。“我们认为这是我们在架构上最好的决定之一，但这并不是对 MongoDB 的抨击。更多的是我们不想在那一层创新。我们的栈在服务器上非常简单。新工程师非常容易理解和使用。”

这个设计也来自于 Quip 离线工作的需要。作为一家以移动为先的公司，不稳定的互联网连接是意料之中的事。用极小的原子单元存储电子表格或文档的每一位，减少了冲突的机会。关键是将这些原子单位缩小到尽可能小的尺寸。这使得离线和在线工作更容易协调，并大大缩小了任何冲突的范围。

“我们决定不把线上线下非黑即白。相反，我们有一个架构，其中一切都优雅地降级，无论您是完全离线，还是在飞机上在线，一直到快速的办公室有线互联网连接。这真的很棒，因为这意味着我们的应用程序中根本没有加载屏幕。它来自手机的工作方式。我们的技术堆栈是在智能手机真正流行起来之后建立的。这是一个真正独特的价值主张，深深植根于技术之中，”泰勒说。

至于构建和分发实际的 Quip 二进制应用程序，这就是事情变得复杂的地方。泰勒指出安卓生态系统的分散是一个主要的头痛问题，另一个原因是谷歌的应用层在中国无法使用(T2)。

“我们有适用于 [iPhone](http://www.apple.com/iphone/) 、 [iPad](http://www.apple.com/ipad/) 、 [Apple Watch](http://www.apple.com/watch/) 、 [Android](https://www.android.com/) 手机和平板电脑、 [Mac](http://www.apple.com/macos/sierra/) 、 [Windows](https://www.microsoft.com/) 和 [web](https://www.w3.org/) 的应用，因此有八个设备类别。许多都有共享的二进制文件，但它们是独立的接口。因此，部署中最困难的事情之一就是如何在网络上跨所有这些平台发布，”泰勒说。

“你每天都释放。在 iOS 上，我们每天都向员工发布，但每个月都会向应用商店发布一次。我确实认为，管理你的发布时间表和跨所有平台的同步是一个相当大的后勤挑战，因为应用商店的审查和政策。这是现在每个创业公司都要处理的事情。那和五年十年前不一样了。我们在移动应用上所做的事情是，我们是按时间表来的，而不是按需的。这使得测试和部署过程更加合理。泰勒说:“在互联网出现之前，很多公司都是这么做的。

专题图片:Bret Taylor 在 Tech Crunch 2009 上，照片[由 Brian Solis](https://www.flickr.com/photos/50698336@N00/3707793530) 拍摄， [CC 由 2.0](https://creativecommons.org/licenses/by/2.0/) 授权拍摄。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>