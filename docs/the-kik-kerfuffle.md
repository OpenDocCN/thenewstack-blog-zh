# 网络干扰事件后，Npm 收紧了不公开政策

> 原文：<https://thenewstack.io/the-kik-kerfuffle/>

上个月，11 行名为 left-pad 的 JavaScript 代码被从 npm 的开源代码库中删除，导致互联网中断，许多 Web 和应用程序开发人员争相修复他们的系统。

这 11 行代码的作者 Azer Koç ulu 从 [npm](https://www.npmjs.com/) 中删除了代码，npm 要求 kou Lu 重命名他的另一个模块 [Kik](https://github.com/starters/kik) ，这是一个开发引导工具，与向 npm 抗议商标侵权的移动聊天提供商同名。

现在，npm 受到移除并随后替换具有重复功能的[左键盘](https://github.com/azer/left-pad/blob/master/index.js)代码的影响，已经改变了其关于贡献者如何取消发布其代码的政策。

“本周，我们看到了很多关于为什么不公开存在的讨论。npm 公司内部也在进行类似的讨论，”开发者社区和内容经理[阿什莉·威廉姆斯](https://github.com/ashleygwilliams)在宣布这些变化的[博客文章中写道。“这项功能有重要和合理的原因，所以我们不打算删除它，但现在我们正在显著改变 unpublish 的行为和围绕它的政策。”](http://blog.npmjs.org/post/141905368000/changes-to-npms-unpublish-policy)

## 打破互联网的 11 条线

最初，npm 是在移动聊天应用[Kik.com](https://www.kik.com/)的要求下移除 Kik 的。一名 Kik 律师辩称，该公司是在捍卫其 Kik 商标，他首先试图直接向 Koç ulu 上诉。只有当双方谈判破裂后，Kik.com 才向新国家运动提出争议，而新国家运动反过来又将 Koç ulu 改名为 Kik。

相反，Koç ulu 从 npm 中发布了超过 273 个他的模块，包括 left-pad，它用带有零或空格的字符串填充左侧的一行。

当然，这是一个很小的函数，但却被广泛使用。包括 [React.js](https://facebook.github.io/react/) 和 [Babel](https://babeljs.io/) 在内的上千个项目都依赖于 left-pad。left-pad 软件被下载了 2，486，696 次，它的删除让许多人不高兴。在失去 left-pad 后，数千个自动构建系统开始失败，这些系统被脚本化以从 npm 中提取 left-pad 包。

Npm 很快做出了行政决定，以相同的名字重新发布模块 T1，但是有不同的所有者，以阻止世界各地的失败构建。这一决定，就像拆除原包装的决定一样，受到了广泛的质疑。

一位互联网评论者， [War 总裁](http://forums.theregister.co.uk/forum/2/2016/03/23/npm_left_pad_chaos/)认为，“这些都没有让 npm 作为一个组织或一个包装经理有好的形象。”。“他们会立即屈服于模糊的威胁，心甘情愿地改变一个包(kik)的所有权，去做第三方的投标，这违反了他们自己的[争议政策](https://www.npmjs.com/policies/disputes)。

“即使在 npm 内部，我们也没有一致认为这是一个正确的决定，但我不能看到每秒钟都有数百个构建失败而不修复它，”npm 首席技术官劳里·沃斯(Laurie Voss)写道，他在 Twitter 上解释了重新发布代码的理由，这些代码是在开源许可证下发布的。“这整个情况糟透了。我们将仔细考虑提出的问题，并在晚些时候公布调查结果。”

在 Reddit、Slashdot 和 Medium 上，Koç ulu 第一次发布了他正在“解放”他的代码的公告，互联网上的评论如潮。讨论涉及代码的有用性，让一个人的构建依赖于调用 11 行代码是多么糟糕，一些关于商标法的讨论，以及将 Koç ulu 称为英雄或被宠坏的孩子。

Koç ulu 的行为引发了许多问题，其中最相关的问题可能是，像 Node.js 社区这样庞大而充满活力的生态系统怎么会因为突然缺少一个软件包而如此迅速地陷入困境？

该公司指出，对于 npm 来说，最终的问题不是商标争议(kik.com 一开始就有一个站不住脚的论点)，甚至不是 npm 的[包装名称争议解决政策](https://www.npmjs.com/policies/disputes)，该政策如预期那样发挥了作用。更确切地说，它是贡献者在没有警告的情况下“取消发布”他们作品的能力。

“我们疏忽了，没有保护您免受无限制取消发布所造成的破坏。我们正在通过技术和政策的改变来解决这个问题，”npm 的“生命最高皇帝”艾萨克·施鲁特在 npm 博客上发布的事件摘要中写道。

[![Mikeal Rogers, head of community outreach for the Node.js Foundation. ](img/fea046acda537418d5fb54ace646e8ef.png)](https://twitter.com/thenewstack/status/715882606810628096)

Node.js 基金会的社区外联负责人 Mikeal Rogers 说。

周二，该公司宣布改变其关于贡献者的政策，一旦他们的包被发布，贡献者将被移除。今后，贡献者仅有权在发布代码的前 24 小时内取消发布。在那之后，要删除这个包，作者必须向 npm 请求，只有当这个包没有被列为存储库中任何其他包的依赖项时，NPM 才会这么做。如果是，作者必须将所有权转让给另一方，或者说服所有依赖包的所有者转换它们的依赖关系。

Node.js 基金会社区外联负责人迈克·罗杰斯(Mikeal Rogers)说，从本质上讲，新规则确立了“生态系统的稳定性比非常罕见的取消发布的需要更重要”。他指出，这是第一次发生这样的事情，尽管 Node.js 有超过 250，000 个模块。

罗杰斯淡化了对 Node.js 开发人员过于依赖依赖的担忧，因为依赖带来了相对丰富的好处。

“它鼓励生态系统中的创新，”他说。“你会得到这些非常深的依赖链，有许多微小的组件，但这对开发人员来说真的很好。开发者想要构建应用，而不是应用存在的所有基础设施。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>