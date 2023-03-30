# 本周节目:帕勒死亡的有趣故事

> 原文：<https://thenewstack.io/this-week-in-programming-the-intriguing-tale-of-parlers-demise/>

如果你在过去的一周里花了一些时间在互联网上，你可能已经阅读了所有关于“伟大的去平台化”，正如一些人所说的那样。在 1 月 6 日的事件之后，唐纳德·特朗普总统被从许多社交网络和平台上移除，包括脸书、推特、YouTube、Snapchat 等等——名单还在继续。与此同时，还有一个网络 Parler，它已经把自己称为“遵守法律的中立城镇广场”，这将是总统转移其在线存在的一个可行地点。上周末，这个选项被取消了，因为谷歌和苹果都从各自的应用商店中删除了该应用程序，亚马逊也通过设定最后期限来纠正其做法——删除某些内容并施加限制——或失去其服务的托管服务，从而对该公司进行了整顿。

接下来发生的事情展示了一项服务和一系列事件，很可能成为未来几年的禁忌。在基础设施方面，该公司的首席执行官提供了一份声明，让该领域的许多人对该公司如何快速重建感到困惑，而不是说明如何不创建弹性服务。

现在一周过去了，该网站仍然完全离线，据说已经被[永远关闭了](https://www.reuters.com/article/us-usa-trump-parler-exclusive/exclusive-parler-ceo-says-social-media-app-favored-by-trump-supporters-may-not-return-idUSKBN29I2Z7)，但是撇开基础设施不谈，亚马逊关闭网站之前发生的事情是一个值得一读、再读的故事，如果不仅仅是为了幸灾乐祸，那么这个服务是如何被一群黑客完全拥有的故事[甚至不需要努力尝试](https://thenewstack.io/how-parlers-data-was-harvested/)。

所有这些都是说，如果你本周没有阅读其他内容，那么我敦促你前往 Vice 阅读存档 Parler 的黑客的完整故事[并解释她是如何做到的](https://www.vice.com/en/article/n7vqew/the-hacker-who-archived-parler-explains-how-she-did-it-and-what-comes-next)，然后前往 Wired 快速解释让任何人获取 Parler 所有数据的荒谬的基本错误。

长话短说，Parler 将它所有的帖子编入索引，这些帖子可以通过公共 API 获得，没有任何速率限制，按照数字顺序排列。这意味着领导这项工作的黑客，在 Twitter 上被称为 [donk_enby](https://twitter.com/donk_enby?lang=en) ，能够编写一个脚本并协调其他人保存来自该服务的 56.7 万亿字节的公共数据，这些数据包括“Parler 上的每个公共帖子，总共 4.12 亿个文件——包括 1.5 亿张照片和 100 多万个视频，”所有这些都包含 GPS 位置和时间戳等元数据。

## 本周的节目中

*   **Go 提议泛型……再次:**这不是第一次，但有希望是最后一次，Go 团队写了[一份为 Go](https://blog.golang.org/generics-proposal) 添加泛型的提议。在语言设计团队的长期争论下，最新的 [Go 语言变更提议](https://golang.org/issue/43651)希望增加对类型和函数的类型参数的支持，允许某种形式的泛型编程。这种语言以前就出现过，提出了改变，但遇到了反对和障碍。正如他们所写的，“自从 Go 在 2009 年首次发布以来，对泛型的支持一直是最常见的语言特性之一。[……]虽然泛型有明确的用例，但将它们完全融入像 Go 这样的语言是一项艰巨的任务。第一个(有缺陷的)添加泛型的尝试可以追溯到 2010 年。在过去的十年里，还有其他几个例子。”这个最新的提议希望从过去的错误中吸取教训，该团队现在正在邀请“实质性的批评和意见”如果被接受，该计划是“一个完整的，尽管可能没有完全优化的实现，供人们在年底前尝试，可能是 Go 1.18 测试版的一部分。”
*   **Javascript 在 2020 年继续前行:**“尽管 2020 年很糟糕，”这是今年 JS 2020 的[状态的介绍，“Javascript 作为一个整体仍然设法向前发展。”随着新特性的出现和 TypeScript 的不断采用，80.6%的受访者认为 Javascript 确实在朝着正确的方向发展。在查看数据时，SDTimes 专注于数据显示的流行框架](https://2020.stateofjs.com/en-US/)中的[重组，其中](https://sdtimes.com/softwaredev/state-of-javascript-2020-report-reveals-shakeup-among-popular-frameworks/) [React](https://reactjs.org/) 和 [Vue](https://vuejs.org/) 仍然是最受欢迎的，而“ [Svelte](https://svelte.dev/) 正开始确立自己作为顶级竞争者的地位”，其满意度为 89%，采用率在过去一年中大幅增加。他们指出，Angular 和 Ember 同时“在过去几年中满意度大幅下降”，尽管两者的使用似乎保持稳定。和往常一样，有大量有趣的交互式图表可供阅读，所以请继续深入了解过去一年 Javascript 生态系统的状态。
*   **数字海洋增加 BYO 集装箱图片:**在最近发布的[应用平台](https://www.digitalocean.com/blog/introducing-digitalocean-app-platform-reimagining-paas-to-make-it-simpler-for-you-to-build-deploy-and-scale-apps/)的基础上，数字海洋[引入了自带集装箱图片工作流程](https://www.digitalocean.com/blog/introducing-bring-your-own-container-image-workflow-for-digitalocean-app-platform)。新的工作流程允许用户超越许多受支持的语言和框架，而不必在 repo 中提供 docker 文件。取而代之的是，App Platform 现在让你在把映像推送到[digital ocean Container Registry(DOCR)](https://www.digitalocean.com/products/container-registry/)之后[用 App Platform](https://www.digitalocean.com/docs/app-platform/how-to/deploy-from-registry/) 部署预建的容器映像。

[https://www.youtube.com/embed/YAeOzVTN4EQ?feature=oembed](https://www.youtube.com/embed/YAeOzVTN4EQ?feature=oembed)

视频

*   **Go 工具 GTA 开源:**坚持使用 DigitialOcean 一会儿，该公司还[开源了一个它创建的工具](https://www.digitalocean.com/blog/gta-detecting-affected-dependent-go-packages)来帮助检测受影响的依赖 Go 包。该工具被称为 [gta](https://github.com/digitalocean/gta) ，用于通过比较“当前分支与其目的分支的合并基础，以确定分支中发生了什么变化”,来了解在拉请求中发生变化的 Go 包的下游依赖性。然后，它会计算这些更改的所有依赖项，并输出所有受影响的包的导入路径。该公司表示，它“能够大幅减少构建和测试拉式请求所需的时间，同时仍然确保完整的分析和测试”，并将他们的 mono repo 构建时间从平均 20 分钟缩短到 2 到 3 分钟。现在可以在 Apache 2.0 许可下使用，gta 与存储在 git 中的代码一起工作，DigitalOcean 指出，代码必须“有效地”结构化，才能发挥最佳作用。

*   2021 年的缺点&黑客马拉松:最后，2021 年即将到来，我们在未来的一年中有一系列新的虚拟会议和黑客马拉松值得期待，其中一些就在本周宣布。谷歌写道，谷歌的[哈希代码 2021 将成为虚拟的](https://blog.google/technology/developers/hash-code-2021-going-virtual/)，随着[的注册现在开放](https://blog.google/technology/developers/hash-code-2021-going-virtual/)，开发者可以“提高他们的编码技能，努力优化真正的谷歌工程问题”要查看过去几年出现的问题，例如[自动化智能手机组装](https://storage.googleapis.com/coding-competitions.appspot.com/HC/2019/hashcode2019_final_task.pdf)或[设计谷歌数据中心的布局](https://storage.googleapis.com/coding-competitions.appspot.com/HC/2015/hashcode2015_qualification_task.pdf)，请查看[档案](https://codingcompetitions.withgoogle.com/hashcode/archive?utm_medium=blog&utm_source=keyword&utm_campaign=reg_promo&src=Online/TOPs/HC)。两到四人的团队可以加入现有的[虚拟中心](https://codingcompetitions.withgoogle.com/hashcode/hubs)或[申请为他们的社区组织](https://codingcompetitions.withgoogle.com/hashcode/hubs/register)一个中心，并在[脸书群](https://www.facebook.com/groups/GoogleHashCode/)上找到更新。在线资格考试将于 2 月 25 日星期四上午 9:30 开始，注册截止日期为 2 月 24 日。接下来，今年的 DockerCon 2021 将于 5 月 27 日举行，现在正在接受[预注册。该活动将是免费的，在线的，据说包括“一些新功能，包括全天的会前技术研讨会，附加内容和更多的社区活动。”最后，2021 年 OpenJS 世界](https://www.docker.com/dockercon/)定于 6 月 9 日举行，并于 2021 年 2 月 15 日开始征集论文。Javascript 开发者大会是免费的，有 YouTube 主题演讲，并表示今年的活动将“允许点播，‘网飞风格’的体验，有特定的首播时间和国际观众观看的灵活性，以及更多与演讲者讨论的机会。”现在报名是[开](https://www.cvent.com/d/17qhqx/4W)了。

由[乔希·威瑟斯](https://unsplash.com/@joshwithers?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText)在 [Unsplash](https://unsplash.com/s/photos/platform?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>