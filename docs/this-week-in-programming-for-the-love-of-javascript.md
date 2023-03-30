# 本周编程:为了对 JavaScript 的热爱

> 原文：<https://thenewstack.io/this-week-in-programming-for-the-love-of-javascript/>

好了，各位——深呼吸，你们已经通过了今年的[开发者大会](https://thenewstack.io/this-week-in-programming-google-i-o-and-microsoft-build-for-the-developers/)马拉松，并且毫发无损地从另一边出来了。我的意思是，我敢肯定还有很多，但在脸书、微软和谷歌之间，过去两周发布的工具和公告比你可能跟上的还要多。

虽然我们试图跟上一切，但我们仍然错过了一些东西——所以本周，我们将看看新的东西，并对上次我们不得不跳过的一些新闻进行一点回顾。但在此之前，让我们谈谈你最喜欢取笑的语言，以及用 JavaScript 构建的任何东西，不，绝对不是 PHP。

本周，无处不在的互联网常客[阿尼尔·达什](https://anildash.com/)问了一个简单的问题——[如果 JavaScript 赢了会怎样？](https://medium.com/@anildash/what-if-javascript-wins-84898e5341a)——并指出，JavaScript 不仅仅是一种越来越流行的编程语言，“作为一个网络，作为一个相关技术的生态系统，它可能正在达到逃逸速度。”

这篇文章中我最喜欢的两个要点是，第一，[阿特伍德定律](https://blog.codinghorror.com/the-principle-of-least-power/)，它指出“任何可以用 JavaScript 编写的应用程序，最终都将会用 JavaScript 编写”，第二，[精彩的合成子编辑](https://www.reddit.com/r/atwoodslaw/)，它展示了这些证据，展示了 JavaScript 近来的无处不在。除此之外，本周我的 feed 中还出现了另一个[漫画，它展示了某人坐下来用 JavaScript 编写一些东西，最终得到了](https://dzone.com/articles/yet-another-about-javascript-comic)[又一个 JavaScript 框架](https://medium.com/tastejs-blog/yet-another-framework-syndrome-yafs-cf5f694ee070)，这似乎是最近的事态。JavaScript 无处不在。

Dash 进一步阐述了这一观点:从 Typescript 到 npm，再到 Node，再到“ECMAscript 标准中描述的开放语言”，“如今有很多东西被认为是‘JavaScript’”，他认为，正是这种网络效应可能意味着“前瞻性平台为了未来过度投资 JavaScript 可能是有意义的。”只是，嗯，随着 JavaScript 被用于“从电子表格宏到物联网硬件的一切”，更不用说“全球数十亿设备上的网络浏览器”，它可能会赢得*。*

对某些事情来说，似乎已经发生了。尽管本周另一篇关于 JavaScript 的文章——一篇认为 [JavaScript 是好的，实际上是](https://ashfurrow.com/blog/javascript-is-good-actually/)——在[黑客新闻](https://news.ycombinator.com/item?id=17079952)上遇到了相当大的阻力。所以，如果你对自己说“这是一大堆……”就去那里逛逛，看看评论，觉得有道理。毕竟，你总是可以依靠黑客新闻来扳倒对手，不是吗？

至此，是时候来看看上周编程世界的新闻和想法了。但首先，花一点时间，前往一个奇妙的创造，它将我们所有人带回 90 年代互联网的美好往昔——一个呼吁我们所有人克服自我的网站，让[再次制造前端屎](https://makefrontendshitagain.party/)。

https://Twitter . com/JohnnyVonRotten/status/994572282319200257

## 本周的节目中

*   **Vim 8.1 的异步终端:**在 Vim 8.0 中[引入的一些异步特性的基础上，](https://laravel-news.com/vim-8-0-is-released) [Vim 8.1](https://www.vim.org/vim-8.1-released.php) 的发布增加了一个令人兴奋的新特性——支持在 Vim 窗口中运行终端。终端窗口可以用来在继续编辑的同时运行“make”命令，可以用来运行一个 shell 来执行其他命令，甚至可以使用新的终端调试器插件在 Vim 内部进行调试。
*   **获得您的。app 在这里！**只是对谷歌最近公告的一个快速跟进。app 现已开放普通注册。。app 是一个顶级域名，它通过要求 HTTPS [与所有域名连接而与众不同。app 网站](https://security.googleblog.com/2017/09/broadening-hsts-to-secure-more-of-web.html)。
*   **Slack GitHub 集成的更新:**虽然我还不相信许多聊天机器人工具，但它们真正闪光的地方是在开发人员的世界里。Slack 上的 GitHub 集成也不例外。本周，这两家公司宣布了对 Slack 和 GitHub 集成的一些[改进](https://blog.github.com/2018-05-17-new-improvements-to-slack-and-github-integration/)，这允许开发者“对拉请求、问题等采取行动”有了 [GitHub 和 Slack 应用](https://slack.github.com/)中的新功能，你现在可以“使用/github [action] [resource]从 Slack 开始下一步常用 GitHub 操作的斜线命令”，以及“通过共享私有 GitHub 库的链接来预览内容”
*   **Rust 离开了它可怕的两个版本:**好吧，好吧，看起来这种“自发布以来的三年里被选为 StackOverflow 上最受欢迎的语言”的语言在它的生命中并没有经历过可怕的一年。现在，这种语言正在庆祝它的第三个生日，并在博客上总结了它做得有多棒。举个例子，事实上“监督该项目的[官方团队](https://www.rust-lang.org/en-US/team.html)的规模在去年翻了一番”,它现在被谷歌、脸书、Twitter、Dropbox、微软、Red Hat、npm，当然还有 [Mozilla](https://blog.rust-lang.org/2017/11/14/Fearless-Concurrency-In-Firefox-Quantum.html) 使用，并在 GitHub 上成为今年的前 15 种语言。事实上，如今人们甚至可以从 Rust 的代码中获得报酬。当然，正如我们之前多次讨论的那样，2018 年将会看到 Rush 的新版本，它将“汇集项目每个领域的改进”，正如[路线图](https://blog.rust-lang.org/2018/03/12/roadmap.html)中所详述的。总而言之，“接下来的几个版本将包括[稳定的 SIMD](https://github.com/rust-lang/rust/issues/48556) 支持、过程宏、定制分配器等等。”请继续阅读，快速总结我们上周错过的内容，了解 Rust 1.26 的详细信息。
*   **构建你自己的 X:** 这只是一个快速链接，因为它不言自明，看起来非常有用——[一个 GitHub 库，它只是一个关于如何构建你自己的教程列表](https://github.com/danistefanovic/build-your-own-x)…嗯，一切。3D 渲染、区块链、编程语言、机器人、框架，应有尽有。
*   **TypeScript 2.9 发布候选:**距离 [2.8 宣布](https://blogs.msdn.microsoft.com/typescript/2018/03/27/announcing-typescript-2-8/)已经过去了几个月，现在 [TypeScript 2.9 RC](https://blogs.msdn.microsoft.com/typescript/2018/05/16/announcing-typescript-2-9-rc/) 已经揭开了面纱。 [InfoWorld](https://www.infoworld.com/article/3249607/javascript/whats-new-in-typescript.html?upd=1526655456652) 总结了所有的变更，包括那些可能破坏您现有代码的变更，所以请注意:“候选版本通过 keyof 操作符和映射的对象类型支持对象文字和数字类型。Keyof 已经是 TypeScript 的一部分，它提供了一种查询现有类型的属性名的方法。但是这个操作符早于 TypeScript 推理唯一符号类型的能力，所以它从不识别符号键。TypeScript 2.9 更改了 keyof 的行为，以考虑唯一的符号和文字类型。此外，Partial 和 Readonly 等映射对象类型可以识别符号和数字属性键；由符号命名的属性将不再被删除。

## 本周的新闻黯然失色

*   **Rust 1.26 到来:**在脸书、谷歌和 IBM 的喧嚣声中，Rust 团队[上周宣布推出 Rust 1.26](https://blog.rust-lang.org/2018/05/10/Rust-1.26.html) ，称其为“可能是自 Rust 1.0 以来功能最丰富的版本”首先，发布的是第二版的“[Rust 编程语言，](https://doc.rust-lang.org/book/)”，它可以在网上免费获得，或者，如果你喜欢，“你可以从 NoStarch Press 预订这本书的死树版本[”然而，除此之外，还有许多你可以期待的新特性，在帖子和](https://www.nostarch.com/Rust)[详细发布说明](https://github.com/rust-lang/rust/blob/master/RELEASES.md#version-1260-2018-05-10)中有详细介绍。
*   以研究的名义:在脸书和谷歌等其他公司的带领下，Netflixed】上周宣布了网飞研究网站，它将提供“我们在网飞所做研究的概述”网飞在处理大规模问题和推荐引擎方面一直处于领先地位，现在他们“创建了这个网站来提供我们研究的广泛概述”，希望它“提供更多关于我们工作的一些领域、我们所做的研究以及我们在继续让网飞变得更好方面所面临的挑战的见解。”
*   **GitHub 的 Checks API:** GitHub 也[公布了其 Checks API](https://blog.github.com/2018-05-07-introducing-checks-api/) ，已经在[公测](https://developer.github.com/v3/checks/)发布。该 API“允许您在 GitHub 上为持续集成(CI)、林挺和验收测试构建复杂的工具”，并且“与 GitHub REST API 一起工作，GraphQL 支持即将推出。”有关更多详细信息，请务必阅读新 API 的[应用程序开发人员时代摘要。](https://adtmag.com/articles/2018/05/10/github-checks-api.aspx)
*   **亚马逊让你时光倒流:**提示[雪儿合唱](https://www.youtube.com/watch?v=BsKbwR7WXN4)，因为亚马逊上周宣布[极光回溯](https://aws.amazon.com/blogs/aws/amazon-aurora-backtrack-turn-back-time/)，给了开发者他们所说的“在现有技术条件下，我们尽可能接近现实的撤销选项。”
*   C#的未来:最后，微软的最后一件事——关于 C#语言的未来。即将推出的特性包括可空引用类型、递归模式、异步流等等。

[https://www.youtube.com/embed/QZ0rWLaMZeI?feature=oembed](https://www.youtube.com/embed/QZ0rWLaMZeI?feature=oembed)

视频

谷歌和微软是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>