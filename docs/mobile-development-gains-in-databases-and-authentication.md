# 数据库和认证方面的移动开发收益

> 原文：<https://thenewstack.io/mobile-development-gains-in-databases-and-authentication/>

本期[新堆栈制造商](/podcasts/makers)播客系列与 [Okta](https://www.okta.com/) 探讨保护移动应用的数据库和认证要求。

[MongoDB](https://www.mongodb.com/cloud/atlas/?utm_content=inline-mention) 移动高级产品经理 [Ian Ward](https://www.linkedin.com/in/ianpward) 和 Okta 高级安全架构师 [Aaron Parecki](https://www.linkedin.com/in/aaronparecki/) 是本次播客的嘉宾，由 API 安全公司 [Okta](https://developer.okta.com/?utm_content=inline-mention) 的开发者权益负责人 [Alex Williams](/author/alex/) 和 [Randall Degges](https://www.linkedin.com/in/rdegges) 主持。

Ward 是移动数据库领域的主要开发者之一，Parecki 是 OAuth 工作组的规范编辑和成员，OAuth 是广泛用于 web 应用程序的行业标准授权协议。Parecki 也是一个多产的博客作者，他提到了他对 OAuth 如何“与身份和在线隐私和安全世界相关联”的着迷

[Okta 系列–移动安全开发、数据库和认证视点](https://thenewstack.simplecast.com/episodes/okta-series-mobile-security-dev-a-database-and-authentication-pov)

对话的一部分集中在从 OAuth 到 OAuth 2 的迁移上，这种迁移是如何使开发者受益的。

据 Parecki 称，OAuth 的前一版本对开发人员不太友好。“OAuth 1 做了许多让开发人员非常沮丧的事情，基本上是让开发人员在自己的代码中完成加密层的规范化请求和签名等工作，这不是一个好的开发人员体验。这基本上是 OAuth 1 最终大部分失败的原因，谢天谢地，OAuth 2 很快就解决了，”Parecki 说。

Parecki 说，OAuth 2 的主要特点之一是它如何“优先考虑规范应用程序的开发人员体验”，以便“使用 OAuth 2 规范的人可以更容易地开始作为开发人员编写 OAuth 服务器”。

“这是我自己和大多数其他人都牢记在心的事情:我们希望确保规范易于开发人员使用，这样当人们使用规范编写服务时，那些服务也易于开发人员使用。所以，[我们]肯定会优先考虑开发者体验，”他说。

沃德说，对于使用 Realm 的移动开发者来说，价值在于“没有开发者需要编写的网络代码和数据传输”。

沃德说:“如果你在后台线程中本地写入 Realm，同步线程会试图将数据复制到 [MongoDB Atlas](https://thenewstack.io/mongodb-clusters-can-now-be-run-across-multiple-clouds/) ，应用这些更改，并从 Atlas 中下载离线时写入的任何数据。“因此，这里的一大价值是，这些移动应用程序可以离线，你可以像在线一样使用它们——它保留了所有操作的队列。”

Realm 也是一个对象数据库，“所以你习惯于使用对象，因为这是所有移动应用程序内置的，它是面向对象的编程，”沃德说。“我们在你的 iOS 代码中有一个类，那是你的数据库的模式。因此，开发者在这方面使用 Realm 是非常自然的。”

Parecki 解释说，保护移动应用程序的部分固有困难是“如果你想隐藏 API 密钥，就不能在其中嵌入 API 密钥”。Parecki 说:“因此，如果你在 app store 中发布一个移动应用程序，并试图将 API 密钥放入该应用程序，任何人都可以对其进行反编译并找到 API 密钥。”“因此，你不能像在服务器端代码中那样使用它来保护对数据库的访问，这基本上意味着你的选择开始变得有限。”

但是，使用 OAuth 2，可以安全地与后端 API 或服务进行通信，而无需向设备发送密钥。Parecki 说:“它之所以有效，是因为你让用户批准这个流程并登录。因此，通过 OAuth 流程，使用应用程序的用户将实际使用他们自己的凭据

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>