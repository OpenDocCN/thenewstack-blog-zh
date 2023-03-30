# Cloudflare 对 Kiwi Farms 的支持可能很快会损害其底线

> 原文：<https://thenewstack.io/cloudflares-kiwi-farms-support-may-soon-hurt-its-bottom-line/>

云服务提供商应该在什么时候对其用户的行为负责？在美国，互联网服务提供商受《通信行为规范法》( CDA)第 230 条的保护，不会因其用户的在线声明而承担责任。但即使一家公司的不干涉政策受到法律保护，托管有争议的材料可能最终会影响其声誉，更不用说其收入来源了。

流行的缓存提供商 Cloudflare 因支持 Kiwi Farms 而受到越来越多的批评，Kiwi Farms 是一个恶意的美国极右翼互联网论坛，致力于嘲笑和骚扰在线人物，特别是跨性别和 LGBTQ 社区的人。其中一个被骚扰的人是 [Liz-Fong Jones](https://www.lizthegrey.com/) ，她是[云原生计算社区](https://thenewstack.io/category/cloud-native/)的一名受人尊敬的工程师，她在[系列直播 Twitch 视频](https://thenewstack.us11.list-manage.com/track/click?u=ab6c02b160780b8e6569144f8&id=0fa8d9a348&e=71a79208c9)中分享了她对 Cloudflare 的不满。Cloudflare 为 Kiwi 提供了缓存和拒绝服务预防服务。*(披露:Cloudflare 还托管了一些网站，这些网站[非法转贴来自 TNS 的版权材料](https://checkforcloudflare.selesti.com/?q=https://cryptonewsbtc.org/)。)*

在这些视频中，她指责 Cloudflare 故意忽视提交给 Cloudflare 的关于猕猴桃农场多种形式骚扰的投诉，扰乱了她自己和其他许多人的生活，她[将这些农场描述为“虐待狂个人的水坑，他们想得到边缘化人群的反应。”这些攻击不仅是口头上的，而且非常恶毒，还经常使用个人身份数据，通过不必要的食品交付订单甚至给受害者家里打电话来骚扰个人。在某些情况下，这引发了创伤性反应。](https://www.twitch.tv/videos/1571797397)

截至本文截稿时，Cloudflare 尚未回复我们的询问。但该公司高管过去曾回应称，他们认为 Cloudflare 是互联网平等的倡导者——每个人都应该被允许在网上建立一个论坛，在那里可以讨论问题。

“我几乎是一个言论自由的绝对主义者，”Cloudflare 首席执行官 [Matthew Prince](https://www.linkedin.com/in/mprince/) 告诉[Ars Technica，解释他基于自由主义不愿放弃对其最臭名昭著的客户，新纳粹网站 the Daily Stormer 的支持(该公司最终在公众的强烈抗议下这样做了)。](https://arstechnica.com/tech-policy/2017/12/cloudflares-ceo-has-a-plan-to-never-censor-hate-speech-again/)

但 Fong-Jones 认为，在像 Kiwi Farms 这样的情况下，这种平等绝不是平等，因为人们必须保护自己免受大规模攻击，他们没有兴趣参与这些攻击。

正如 Fong-Jones 所指出的，政府并没有强制要求每个人都必须使用缓存服务。选择和奇异果农场做生意完全是 Cloudflare 的选择。“Cloudflare 不是垄断，”她说。“它有竞争。如果 Cloudflare 选择不与特定的源服务器开展业务，该源服务器可以选择与其他提供商开展业务。”

似乎只要 Cloudflare 支持在线论坛，Fong-Jones 就会继续她的活动。她计划在太平洋时间周五下午 6 点发布另一个[直播/视频](https://www.twitch.tv/lizthegrey)，该视频将提供其他客户如何迁移 Cloudflare 服务的计划。Fong-Jones 说，这个想法是“击中 Cloudflare 的要害”。

如果这个问题继续引起公众的关注，这不仅是 Cloudflare 的问题，也是 Cloudflare 的其他客户的问题，他们可能需要解释为什么他们继续使用这项服务。

## 本周的节目中

*   **烤箱中的面包**:广泛使用但有时令人沮丧的 Node.js 服务器端运行时的替代方案获得了发展势头。几周前，我们报道了 [Deno](https://thenewstack.io/node-js-creator-blasts-node-js-offers-a-secure-typescript-based-alternative/) (更安全，更好的包管理)背后的公司已经获得了[2100 万美元](https://thenewstack.io/with-additional-funding-deno-sets-out-to-challenge-node-js/)的资金(其中一些来自 TNS 母公司 [Insight Partners](https://www.insightpartners.com/about-us/) )。现在，快速崛起的 [Bun](https://thenewstack.io/meet-bun-a-javascript-runtime-for-the-whole-dev-lifecycle/) (更快，更有利于发展)有了新的公司烤箱(明白吗？)，感谢 Kleiner Perkins、Vercel 首席执行官 Guillermo Rauch 和 YCombinator 的 700 万美元投资。基本上，Node 和 Deno——都由 Ryan Dahl 设计——都使用谷歌的 V8 JavaScript 引擎，而 Bun——由 Jared Sumner 构建——使用苹果 Webkit 的更快的 JavaScriptCore 框架，以及紧凑的 Zig T21 编程语言。

![](img/248eebc2e2c806710e2abdc097cddeba.png)

格雷迪·布奇

*   当面包供应商烤箱通过推特宣布自己的存在时，它遭遇了一些激烈的批评。尽管[警告](https://twitter.com/oven_sh)说“烤箱将会是一个苦差事，尤其是前九个月左右”,但是考虑到 Bun 仍处于发展的初期阶段，公司正在招聘工程师。如果工作与生活的平衡对你来说意味着很多时间不工作，那么现在可能不是一个很好的选择。”虽然这种[痴迷的摇滚明星编程](https://thenewstack.io/10x-programmer-just-jerk/)在十年前是常态，但围绕 dev 的文化规范目前正在发生转变，回归到更加平衡的工作与生活的平衡[。所以，不出所料，这条推文被评为非常糟糕，获得了比心脏更多的批评回应。对于我们的钱，最简洁的回答来自于 CompSci 的元老 Grady Booch:“将软件开发死亡行军的想法形式化既不是荣誉的标志，也不是好的软件开发实践。”留意格雷迪的智慧。](https://www.cnn.com/videos/business/2022/08/25/nightcap-quiet-quitting-trend-explained-clip-orig-mb.cnn)

*   **认识新的 Kubernetes** :来自[云原生计算基金会](https://cncf.io/?utm_content=inline-mention)的大家最喜欢的开源容器编排工具已经更新。Kubernetes 1.25 发布版，昵称为 Combiner 以纪念其众多贡献者，包含 46 个增强功能。其中 15 项增强功能已经升级到稳定版，15 项增强功能正在进入 beta 版，13 项增强功能正在进入 alpha 版。短暂的容器——对于调试来说非常方便——也已经升级为稳定的。多亏了 Linux 的 cgroups v2，暂时容器才成为可能，Kubernetes 现在支持它，这让各地的 K8s 管理员松了一口气。
*   **…这还不是 K8s** 的全部:Kubernetes 1.25 的另一个大卖点是混乱且难以处理的 PodSecurityPolicy 已经被移除，取而代之的是 [Pod 安全许可](https://kubernetes.io/docs/concepts/security/pod-security-admission/)。当创建 pod 时，这个新的准入控制器可以在名称空间级别实施 pod 安全标准。PodSecurityPolicy 有一些严重的问题，“不做出突破性的改变就无法解决，这就是为什么我们有一个替代者，”谷歌软件工程师和 Kubernetes 核心贡献者[黄](https://www.linkedin.com/in/cici-huang-68a6a3a5/)向 TNS 解释说。特别是，用户很容易应用比预期更广泛的访问权限，从而导致安全问题。早期的控制器也不能使用审计模式。新的 Pod 安全许可使得“用户无需深入理解产品规范就能更容易地应用安全最佳实践。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>