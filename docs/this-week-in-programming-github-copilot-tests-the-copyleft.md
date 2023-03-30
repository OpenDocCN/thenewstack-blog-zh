# 本周编程:GitHub Copilot 测试版权

> 原文：<https://thenewstack.io/this-week-in-programming-github-copilot-tests-the-copyleft/>

CoPilot，GitHub 的[机器学习辅助代码完成功能](https://github.com/features/copilot)继续在开源社区的一些地方产生争议。

上个月末，微软的 GitHub 已经将 Copilot 服务从测试版[转移到付费版](https://github.blog/2022-06-21-github-copilot-is-generally-available-to-all-developers)，起价为每月 10 美元(但对学生和大型开源项目的开发者仍然免费)。

由于这种对服务收费的举动，两个开源倡导团体，自由软件基金会和软件自由保护协会，都建议关心开源软件的开发者彻底切断与 GitHub 的联系。鉴于 GitHub 的广泛使用，这是一个很大的问题。

但对 SFC 来说，GitHub 对基于自由开源软件(FOSS)的服务收费是一个转折点。

“我们从大型科技公司的许多免费服务中学到，如果你不是客户，你就是产品。自由/开源软件的开发方法是 GitHub 的产品，在我们积极的(如果经常是不知情的)帮助下，他们已经将其专利化并重新包装，”SFC 的 Denver Gingerich 和 Bradley M. Kuhn 在[的一篇激烈的博客文章](https://sfconservancy.org/blog/2022/jun/30/give-up-github-launch/)中写道。"自由/开源软件开发者长期以来一直是众所周知的在慢慢沸腾的水中的青蛙."

自去年问世以来，Copilot 已经引起了批评的注意。GitHub 将这项服务称为“人工智能配对编程”，目的是省去开发人员在 Stack Overflow 或 Google 上寻找预先存在的解决方案的编码过程。为了建立这项服务，GitHub 与另一家微软实体 [OpenAI](https://openai.com/) 合作，通过扫描 GitHub 上的储存库来训练模型，以建立一个知识库来提供这些建议。

许多开发者喜欢这项服务，尽管其他人怀疑 GitHub 和母公司微软是否太过侵犯他人的作品。

GitHub 上的许多开源项目都有一个[copyright left 许可证，](https://www.gnu.org/licenses/copyleft.en.html)它要求用代码做的任何东西也必须开源。但在 Copilot 的例子中，代码不是直接使用的，而是作为一种输入来创建全新的代码。copyleft 也适用于代码的这种用法吗？这是摆在桌面上的问题。

> "自由/开源软件开发者长期以来一直是众所周知的在慢慢沸腾的水中的青蛙."

甚至在法律之外，还有一个伦理问题需要考虑。许多人认为这是对开源知识产权的侵略性掠夺。在[为新堆栈贡献的帖子](https://thenewstack.io/github-copilot-and-open-source-a-love-story-that-wont-end-well/)中，[源代码控制管理服务提供商](https://twitter.com/sasham1) [Diversion](https://www.diversion.dev/) 的首席执行官萨沙·梅德维多夫斯基写道:

如果开发者不希望他们的代码被用于商业应用，他们应该被赋予拒绝的权利。如果他们同意，那就没有问题。但是公司(无论是微软、谷歌还是亚马逊网络服务公司)不应该认为如果他们免费提供一些东西，他们就可以得到一些回报。

梅德韦杰夫指出，这不是微软旗下公司第一次不自量力。他指出了今年早些时候的一个事件，当时一个名为 [Marak](https://mobile.twitter.com/marak) 的开源程序员故意破坏了他的开源 [Faker](https://fakerjs.dev/) 模拟数据生成器的代码，据称是为了抗议他的受欢迎的项目缺乏资金，这些项目被数百家公司使用。

GitHub 的回应？代码库巨头恢复了恶意更改——大概是为了保护用户不运行损坏的代码——并拒绝马拉克访问他自己的项目。

在与 SFC 的讨论中，微软和 GitHub 高管声称，使用这种开源代码属于合理使用，因为这种代码是公开的。

但是证监会觉得这是不对的。GitHub 正在使用开源代码来构建一个只能通过付费订阅才能访问的专有服务。同样值得注意的是，微软没有提供任何来自其专有软件产品的代码，特别是 Office 和 Windows，因此在 SFC 看来，该项目显然不想使用微软自己的知识产权。那么，为什么使用开源代码是公平的，该组织问道。

你怎么想呢?Copilot 是否违背开源精神？或者是我们很快都会喜欢的编程的自然进化？

## 本周的节目中

*   根据最近一期 [Talk Python to Me](https://talkpython.fm/episodes/show/369/getting-lazy-with-python-imports-and-pep-690) 播客中的采访，无论何时调用[导入模块](https://docs.python.org/3/tutorial/modules.html)，Python : [Python](https://thenewstack.io/an-introduction-to-python-a-language-for-the-ages/) 都可能最终变得冷淡。一个名为 PEP 690 的提议正在浮出水面，它描述了一种 Python 解释器只在需要时才加载外部模块，而不是一次加载所有模块的方法。非常酷的是，Talk Python 的工作人员为内部独家新闻讲述了 PEP 的所有原则:Instagram 工程师 [Carl Meyer](https://twitter.com/carljm/) ，Meta 高级软件工程师[german m ndez Bravo](https://twitter.com/germbravo)，LinkedIn 高级职员工程师 [Barry Warsaw](https://twitter.com/pumpichank) 都参加了采访。虽然乍一看，Python 导入可能看起来类似于 C 的 include 指令，但他们解释说，它有更多的功能:它可以调用调用其他模块的模块，包括那些可以调用互联网的模块。Meyer 提到 Instagram 自己的经验时说，这种多个模块的级联会使服务器变慢。

[https://www.youtube.com/embed/ohTPzi9Lry0?feature=oembed](https://www.youtube.com/embed/ohTPzi9Lry0?feature=oembed)

视频

*   谁放出了机器人？我猜他现在可以谈论它了，但软件工程师[安德斯·康贝尔](http://anders.conbere.org/)发布了一个[的悲惨故事](https://gist.github.com/aconbere/1982a5eb17b77817017a3da50914732f)，讲述了 Etsy 是如何被横冲直撞的聊天机器人击倒的。开始的时候很天真。他在 2012 年至 2014 年期间为 Etsy 工作，就在该公司传奇的黑客周之前，他组装了一个基于 Scala 的机器人，可以扫描他朋友 Avi 的聊天日志，Avi 最近离开了该公司。这个机器人会把 Avi 写的所有东西都放进一个马尔可夫链中，然后当有人在内部 IRC 聊天中提到 Avi 时，它会回应一个类似 Avi 的声明。因此，对于黑客周，Conbere 在这项工作的基础上创建了一个机器人，它将采用员工的名字并相应地发布声明。这被证明是一个小麻烦，因为机器人在 IRC 上复制，所以它们被锁在一个**#炼狱**通道中被遗忘。直到那时，他才意识到机器人不仅可以复制用户账户，还可以复制公司的聊天操作，这是为了让工程师可以发出命令——例如，启动服务器——机器人可以实际执行该命令。“可怕的意识是，[他们]可以执行所有其他 chatops 命令，那些拆除服务器的命令，那些杀死进程的命令，”Conbere 写道。这些机器人在它们在网上市场变得全面[混乱猴子](https://thenewstack.io/chaos-engineering-can-give-distributed-systems-stability/)之前就被杀死了，也许一秒钟都不会太早。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>