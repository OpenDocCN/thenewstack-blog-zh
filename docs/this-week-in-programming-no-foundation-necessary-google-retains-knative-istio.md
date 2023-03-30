# 本周编程:不需要基础？谷歌保留了 Knative，Istio

> 原文：<https://thenewstack.io/this-week-in-programming-no-foundation-necessary-google-retains-knative-istio/>

本周早些时候， [Knative](https://knative.dev/) 指导委员会成员、[的产品经理、](https://groups.google.com/forum/m/#!topic/knative-dev/YmL2vgMC4rc) [Donna Malayeri](https://www.linkedin.com/in/donnamalayeri) 提供了 Knative 基金会状态的更新，写道“自从 Knative 项目开始以来，就有人质疑 Knative 是否会捐赠给一个基金会，比如云本地计算基金会(CNCF)。谷歌领导层已经考虑到了这一点，并决定在可预见的未来不会向任何基金会捐赠 Knative。”

许多人用“令人失望”这个词来形容这条新闻。

Sebastien Goasguen 称该公告是“一封令人失望的电子邮件”，并回应指出“基金会为竞争各方提供了一个中立的平台，让他们能够一起工作、开发软件并构建一个对软件的长期生存至关重要的生态系统”，并且“没有中立的平台，这个‘社区’就只是让负责的公司受益的免费劳动力。”他继续进一步谴责这一举动，写道“很明显 Knative 是谷歌的一个项目，并打算保持这种方式，这不会导致一个强大的社区的创建。”

虽然 Joe Beda 指出，Istio 也将在一个不那么供应商中立的治理下继续存在，但其他人指出，并非一切都是黑白分明的，CNCF 也有自己的问题，即指导委员会的观点不完全平衡，Beda 承认这一点。

为了不被排除在对话之外，Bouyant 首席执行官兼 Linkerd 维护者[威廉·摩根](https://www.linkedin.com/in/wmorgan/)写了一篇[对新闻](https://linkerd.io/2019/10/03/linkerds-commitment-to-open-governance/)的回应，指出虽然“bubby 仍然是该项目的主要赞助商，并且到目前为止，Linkerd 中的大部分代码都来自于 bubby 支付了他们的时间和精力的人”，但他晚上睡得很香，因为他作为首席执行官和维护者的角色从来没有冲突，“bubby 的商业模式没有要求我们保持对 Linkerd 的控制。”

至于这一举动背后的“为什么”,一些人提出了一些理论——显然与保持控制和竞争优势有关，同时保持对开放治理的要求。

https://Twitter . com/AzureAndChill/status/1179369278258241538

## 本周的节目中

*   **TypeScript 3.7 测试版增加了可选链接和更多功能:**TypeScript 3.7 的[测试版刚刚发布](https://devblogs.microsoft.com/typescript/announcing-typescript-3-7-beta/)，提供了静态类型语言下一版本的完整功能预览，该团队称这些功能是“我们最需要的功能之一”他们写道，3.7 的突出特性是可选链接，这一特性“允许我们编写代码，如果遇到空的或未定义的表达式，我们可以立即停止运行这些表达式”。。接线员。给出的例子是“设 x = foo？. bar . baz()；"也就是“一种说法，当 foo 被定义时，foo.bar.baz()将被计算；但是当 foo 为空或未定义时，停止我们正在做的事情，只返回 undefined。”在这种情况下，操作符是选项属性访问，但它也可以用于选项元素访问和访问非标识符属性，如任意字符串、数字和符号。要了解完整的细节，以及一些更好的代码示例，请点击查看帖子或[阅读提案](https://github.com/tc39/proposal-optional-chaining/)。类似地，TypeScript 3.7 引入了一个 nullish 合并操作符？？—本质上是“在处理空值或未定义值时‘退回’到默认值的一种方式。”根据 beta 发布公告，TypeScript 3.7 的最终版本将在 11 月初发布，几周前将有一个候选版本。

*   **Rust 获得了大家期待已久的 Async-await:**对于语言爱好者来说，这是一个类似的大消息，Rust 表示等待终于结束了，随着 [Async-await 测试版](https://blog.rust-lang.org/2019/09/30/Async-await-hits-beta.html)和 sytactic 支持在 Rust beta 频道发布，预计将于 11 月 7 日发布稳定的 1.39 版本。虽然 Rust 团队表示，该版本“将标志着多年来在 Rust 中实现高效和符合人体工程学的异步 I/O 的努力的高潮”，但他们也指出，“然而，这并不标志着道路的终结。”还有一些错误需要修复，一些特性需要完善。简而言之，async-await 是“一种编写可以‘暂停’的函数的方法，将控制返回给运行时，然后从停止的地方继续。”它是 JavaScript 和 C#等语言中可用的功能，Rust 指出，它自己的版本将有一些关键差异，主要是处理语法和“零成本未来”的想法。本质上，“在 Rust 中，调用一个异步函数本身并不做任何调度，这意味着我们可以组成一个复杂的未来嵌套，而不会产生每个未来的成本，”这与其他语言形成对比，后者会立即创建一个未来并调度它的执行——这意味着为每个创建的未来带来开销。

*   **Rust 1.25 中的货物漏洞:**再给你们 Rust 开发者一点消息，你们现在肯定已经看到了，但如果没有的话，这绝对值得一提。本周早些时候，Rust 1.25 中的一个 Cargo 漏洞被发现，它会忽略包密钥并下载一个错误的依赖项。可以在 [CVE-2019-16760](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-16760) 下看到漏洞详情，影响 Rust 1.0 到 Rust 1.25，但不影响 Rust 1.26 到 Rust 1.30。要了解完整的细节，请务必查看关于该漏洞的 [Rust 博客帖子](https://blog.rust-lang.org/2019/09/30/Security-advisory-for-cargo.html)。哦，对于 Rust 的朋友们，最后一点需要注意的是，团队刚刚[推出了内部 Rust 博客](https://blog.rust-lang.org/2019/10/03/inside-rust-blog.html)，对于那些关心 Rust 发展的人来说，它将进入 Rust 发展的“本质”。
*   **TensorFlow 2.0 推出紧密的 Keras 集成:** SDTimes 报道了本周 TensorFlow 2.0 发布的细节，称[扩展了机器学习能力，并为其视觉人工智能产品组合提供了更新](https://sdtimes.com/ai/google-expands-machine-learning-capabilities-with-tensorflow-2-0-and-updates-to-its-vision-ai-portfolio/)。他们写道，TensorFlow 2.0“为寻求拓展机器学习边界和构建可扩展的机器学习驱动的应用程序的开发人员和研究人员提供了一个工具生态系统”，现在“与 Python 深度学习库 Keras、默认急切执行和 Python 函数执行紧密集成”，这一切都是为了让 TensorFlow 受到 Python 开发人员的喜爱。要了解全部细节，请务必查看[谷歌的博客文章](https://cloud.google.com/blog/products/ai-machine-learning/announcing-updates-to-automl-vision-edge-automl-video-and-video-intelligence-api)。对于那些从 TensorFlow 1.0 过渡到 2.0 的人，HackerNews 上的一条[顶级评论](https://news.ycombinator.com/item?id=21118018)预测“一场巨大的混乱的过渡”，而不是建议“如果你需要从 TF1 过渡到 TF2，考虑做 TF1 到 PyTorch 的过渡。”

*   **有 99 个 API，但一个可执行的不是一个:**我不确定我在解释或写作方面能比 TechDirt 的 Mike Masnick 做得更好，所以我可能会简单地把你的注意力引向他的故事，关于一个[顶级甲骨文律师试图通过坚持 API 是可执行的来欺骗整个软件社区](https://www.techdirt.com/articles/20190929/23221543096/top-oracle-lawyer-attempting-to-gaslight-entire-software-community-insists-apis-are-executable.shtml)。这是一个律师语言与技术现实和 Twitter 上众多开发者的观点相遇的例子。在你阅读关于这个案例中可怕的 hijinx 的所有内容之前，这里有一个简短的片段:“从字面上讲，没有人否认软件源代码受版权保护。问题是应用程序编程接口——API——是否受版权保护。正如我们从一开始就说过的，整个案件中最令人沮丧的事情是，一些不懂技术的律师和法官拒绝理解 API 不是软件。它不是可执行代码。它不是软件的“源代码”。API 是一组允许访问数据、应用程序或服务的规范。这是一种‘操作方法’，简单来说就是[不受版权法约束。”请继续阅读更多来自一位律师的推文，她似乎认为，既然她在这个案件中愚弄了法官，她在技术上是正确的。](https://www.law.cornell.edu/uscode/text/17/102)
*   **GitHub 为动作提供了新的工作流编辑器:**最后，本周，没有一些 GitHub 新闻的“本周编程”是什么，对吗？(他们真的知道如何保持稳定的鼓点，不是吗？)那么，GitHub 已经为 GitHub Actions 发布了一个[新的工作流编辑器，它提供了“内联自动完成和 lint as you type，这样你就可以告别 YAML 缩进问题，探索完整的工作流语法，而不用去文档。”](https://github.blog/2019-10-01-new-workflow-editor-for-github-actions/)

云计算原生计算基金会、甲骨文和红帽是新体系的赞助商。

来自 Pixabay 的 dewikinanthi 的特写图片。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>