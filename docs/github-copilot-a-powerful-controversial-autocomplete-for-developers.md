# GitHub Copilot:一个强大的、有争议的自动完成工具

> 原文：<https://thenewstack.io/github-copilot-a-powerful-controversial-autocomplete-for-developers/>

我已经研究这个应用程序开发领域很长时间了，并且看到了很多突破。有些比其他人更吸引我的眼球，GitHub 的副驾驶就是其中之一。

[GitHub](https://www.github.com) 称 Copilot 为开发者的人工智能[配对编程](https://thenewstack.io/advance-your-devops-with-pair-programming-even-remotely/)伴侣。

这项技术确实很有前途。GitHub 首席执行官 [Nat Friedman](https://www.linkedin.com/in/natfriedman/) 在介绍该技术的[博客文章](https://github.blog/2021-06-29-introducing-github-copilot-ai-pair-programmer/)中解释道:“GitHub Copilot 从你正在处理的代码中提取上下文，暗示整行或整个功能。

弗里德曼说，Copilot 帮助开发人员快速发现解决问题的替代方法，编写测试，并探索新的 API，而不必在 Stack Overflow 等网站和互联网上繁琐地搜索答案。而且，由于它是基于机器学习的，它会随着你的使用而学习。“当你打字时，它会适应你写代码的方式——帮助你更快地完成工作，”他指出。

这项技术现在处于技术预览阶段，到目前为止，无论是微软/GitHub 内部还是外部的用户都给予了很好的评价——当然也有一些反对。

隐私和安全软件制造商 Socket 的创始人[费罗斯·阿巴克哈迪贾](https://www.linkedin.com/in/feross/)在一份声明中说:“GitHub Copilot 似乎完全知道我下一步要输入什么，这让我印象深刻。”。“GitHub Copilot 在处理 React 组件时特别有用，它可以做出非常准确的预测。GitHub Copilot 已经成为我的程序员工具箱中不可或缺的一部分。”

微软研究院的高级研究员 Alex Polozov 在推特上写道，“毫不夸张地说，Copilot 将成为 2020 年代的三大技术发展之一。”

## 微软/OpenAI 交易之外

GitHub Copilot 是微软和人工智能研究和部署公司 [OpenAI](https://openai.com/) 合作的产物——两年前[微软向其投资了 10 亿美元](https://news.microsoft.com/2019/07/22/openai-forms-exclusive-computing-partnership-with-microsoft-to-build-new-azure-ai-supercomputing-technologies/)。

弗里德曼解释说，“GitHub Copilot 由 OpenAI Codex 提供动力，这是 OpenAI 创造的一个新的 AI 系统。”

Friedman 解释说，OpenAI Codex 在人们如何使用代码方面有着广泛的知识，在代码生成方面明显比 GPT-3 更有能力，部分原因是它是在包括更大浓度的公共源代码的数据集上训练的。

> 有些人似乎担心它会生成与在不允许衍生作品的开源许可下生成的代码相同的代码，但这些代码会在不知不觉中被开发人员使用。

GitHub 拒绝就此新闻采访发言人，指引我去查看技术预览版中相当全面的常见问题。例如，对于我关于 Copilot 将使用的数据源的问题，GitHub 的回答是:“它已经接受了从公开来源中选择的英语和源代码的训练，包括(但不限于)GitHub 上公共存储库中的代码。”

但是是哪些呢？

“他们肯定在使用 GitHub repos。专注于人工智能研究和分析的[cognelytica](https://www.cognilytica.com/)分析师 Ronald Schmelzer 说。“当然，问题是，他们是否也在使用私有的 GitHub repos。以及有无用户同意？也许额外的来源可以是[栈溢出](https://thenewstack.io/eyeballs-training-china-reasons-for-the-stack-overflow-acquisition/)和其他人们张贴代码以供评论的地方。但就质量而言，这是值得怀疑的。”

此外，因为它是在公开可用的源代码和自然语言上接受培训的，Copilot 既懂编程也懂人类语言。该公司表示，这使开发人员能够用英语描述任务，然后 GitHub Copilot 将提供相应的代码。

## 支持多种语言

Friedman 说，GitHub Copilot 的一个吸引人的特点是，它可以与一系列广泛的框架和语言一起工作，但这种技术预览版对于 Python、JavaScript、TypeScript、Ruby 和 Go 尤其适用。

并且根据 tech 预览页面显示:GitHub Copilot 目前只作为 Visual Studio 代码扩展提供。它适用于 Visual Studio 代码工作的任何地方——在您的机器上或者在 GitHub Codespaces 的云中。而且打字的速度也够快。

“对于各种能力的开发者来说，Copilot 看起来像是一个潜在的神奇的学习工具，”詹姆斯总督、 [RedMonk](https://redmonk.com/) 的分析师说。“它可以消除进入壁垒。它可以帮助学习新的语言，也可以帮助从事[多语言](https://thenewstack.io/netflix-builds-pipeline-polyglot-programming/)代码库工作的人们。它可以说延续了 GitHub 作为世界级学习工具的丰富传统。现在还为时尚早，但人工智能辅助编程将成为一件事，还有什么地方比 GitHub 更适合开始体验它呢？”

## 是的，但是它能扩展吗？

一些观察家认为 Copilot 对于简单的项目是有用的，但可能还没有准备好投入使用。

企业基础设施软件提供商 [WSO2](https://wso2.com/?utm_content=inline-mention) 的首席技术官 [Eric 新人](https://www.linkedin.com/in/enewcomer/)在一次采访中谈到 Copilot 时说:“这是一个非常有趣的想法，应该可以很好地用于简单的例子，但我很好奇它在复杂的代码问题上的效果如何。”。

尽管软件开发商 Vercel 的首席执行官 Guillermo Rauch 对 Copilot 很感兴趣，但他也有一个警告。

“我对自动补全的长度持怀疑态度，”他在推特上说。“一整份文件？函数体？等等。Gmail 不能写完整封邮件，但它的自动补全功能无疑非常有用。人工智能代码自动完成功能将会长期存在。”

规模问题是 GitHub 关心的问题，根据技术预览常见问题:“如果技术预览成功，我们的计划是在未来建立 GitHub Copilot 的商业版本。我们希望通过预览来了解人们如何使用 GitHub Copilot，以及如何大规模运营它。”

GitHub 去年与 OpenAI 密切合作，打造了 Copilot。几个月来，GitHub 开发人员和微软内部的一些用户每天都在内部使用它。

## 开源问题

事实上，Rauch，同时也是 Vercel 的创始人和 [Next.js](https://thenewstack.io/next-js-11-the-kubernetes-of-frontend-development/) 的创建者，在一条推文中引用了 Copilot [技术预览 FAQ](https://copilot.github.com/) 页面的一份声明，“GitHub Copilot 是一个代码合成器，而不是搜索引擎:它建议的绝大多数代码都是独特生成的，从来没有人见过。”

对此，劳奇简单地输入了:“未来。”

Rauch 的帖子是相关的，因为对 Copilot 的[打击之一是，一些人似乎担心它会生成与在不允许衍生作品的开源许可证下生成的代码相同的代码，但这些代码会在不知情的情况下被开发人员使用。](https://twitter.com/eevee/status/1410037309848752128)

## 开创性的进步？

我已经看到了许多突破性的和潜在的改变游戏规则的技术，但是我知道什么呢？不说副驾驶一定是开创性的，但它是一个该死的突破。它让我们在人工智能，尤其是人工智能，能够帮助开发者构建软件方面走得更远。例如，当我多年前第一次看到 [IBM](https://www.ibm.com/cloud?utm_content=inline-mention) 的[沃森](https://www.eweek.com/networking/ibm-s-watson-jeopardy!-win-just-the-beginning/)的能力时——即使它在 2011 年的 [Jeopardy 中“击败”了人类——我说过这项技术有一天将有助于推动软件开发的进程。只是比我预期的时间长。但是这东西不容易。我们还有很长的路要走。](https://www.eweek.com/networking/ibm-s-watson-relives-jeopardy-victory/)

例如，GitHub 首席技术官办公室的研究员 Eddie Aftandilian 在一条 tweet 帖子中描述了他认为程序合成“永远不会成功”。但在谷歌工作一段时间后，他看到了显著的进步，当他后来来到 GitHub，看到他们的进步时，他“大吃一惊”，他说。

“作为 TypeScript 和 Python 的新手，它(Copilot)对我特别有用，我们的代码就是用它们编写的，”Aftandilian 在一条推文中说。“我不必一直搜索 Stack Overflow 来找到用这些不熟悉的语言做某件事的正确方法；副驾驶会在不影响我的情况下提出这个建议。”

与此同时，Rauch 说他与 Next.js 团队共享 Copilot 该团队刚刚成为 GitHub 上第 44 个最受欢迎的项目——开发团队中的每个人都采用了它，并坚持认为他们的生产率有所提高。

他说，Next.js 团队成员在 Slack 上互相发送截图，表示不相信副驾驶的建议有多好。然而，劳奇说，他认为开发人员大多训练自己对自动补全立即做出反应，并相信它，因为传统上它只是一个单词。

然而，“这个系统(副驾驶)有时可能会自动扩展整个功能体，这是令人惊讶的，”劳奇说。“但同时，作为开发人员，我们必须小心阅读我们添加到程序中的内容。”

劳奇将这种情况比作 GitHub 提供了一种创建“内联拉式请求”的方式，提交者是一个人工智能，你可以不断地审查他们的提议，他说。

“总的来说，我认为这是一个巨大的飞跃，我迫不及待地想了解更多关于这项技术的可能性，它将如何改进以及它将释放哪些创造力。”

说够了。我完全同意。

## 推迟技术

然而，正如任何尚未完全成熟的技术一样(毕竟它还处于技术预览阶段)，反向投资者正在 GitHub Copilot 身上戳洞。有人称之为新瓶装旧酒，也有人说这是程序员大规模就业结束的开始。

“副驾驶既不是新瓶装旧酒，也不是人类编程的终结，”[intellix](https://intellyx.com/)的分析师杰森·彭博告诉我。它更像是下一代的自动完成功能。

“在我看来，Copilot 最有趣的事情是它通常会生成原始代码——也就是说，在训练数据中没有逐字表示的代码，”他说。“然而，人们必须记住，这是完全无法写出创造性的代码的。创造力——就目前而言——仍然掌握在人类手中。那么，使用 Copilot 是对编程吗？除非你不介意两个程序员中有一个没有创造力。”

[另一位](https://www.linkedin.com/in/sogrady/) [RedMonk](https://redmonk.com/) 分析师 Stephen O'Grady 表示同意，并指出 Copilot 确实是代码生成的自然进化。他指出，首先，GitHub 团队从语法自动完成开始，转向代码完成，现在转向在大量公共代码上训练的基于人工智能的生成解决方案。

“虽然这是一件大事，至少根据公众对它的巨大反应，但在我看来，Copilot 距离编程工作的结束还很远，”O'Grady 告诉我。“它只能解决现有的问题——新的解决方案仍然需要人。”

O'Grady 说，事实上，就像 Ruby on Rails 曾经通过从 web 项目中自动生成大量样板脚手架来提高开发人员的效率一样，Copilot 应该通过减少或消除开发人员重新实现基本构建模块功能的能力来节省他们的时间，这反过来有助于他们更快地移动。

## 更高的开发效率，更好的代码质量

因此，根据常见问题，开发人员的生产力是 Copilot 技术的一个目标，也是内部用户已经实现的目标。更好的代码质量是另一个目标，通过帮助新手学习编码和让现有的开发人员更快地学习新语言来扩大开发人员的范围——而不是缩小它。

[星座研究](https://www.constellationr.com/)的分析师[霍尔格·穆勒](https://www.linkedin.com/in/holgermueller/)说:“我们早就知道，这个世界没有足够的开发人员来编写需要的代码。“很高兴看到像[开发者速度](https://searchsoftwarequality.techtarget.com/news/252484206/Microsoft-fuels-developer-velocity-with-Azure-new-tools)这样的概念现在可能会通过将人工智能注入到过程中来结束‘一个开发者和他的工具链’的时代。虽然他们最初可能会持怀疑态度，但开发人员会接受他们可以从供应商那里获得的任何帮助，比如今天的 GitHub，以提高他们的工作效率。”

是的，但是霍尔格，副驾驶是开创性的还是潜在的改变游戏规则的？

“不，这是整个行业的趋势，”穆勒说。“ML 就在那里，需要尽可能经常、尽可能好地应用。所有的工具供应商都在这么做。”

Copilot 对于测试软件这个非常重要的概念也很有用。技术预览页面深刻地指出:“测试是任何健壮的软件工程项目的支柱。导入一个单元测试包，让 GitHub Copilot 建议符合你的实现代码的测试。”

## 物有所值

与此同时，Cognilytica 的 Schmelzer 表示，微软继续利用其在 OpenAI 上的 10 亿美元投资并不奇怪，因为 OpenAI 的 GPT-3 可能会在微软的许多产品以及该公司收购的产品(如 GitHub 和 LinkedIn)中担任主演或客串角色。

“使用 GPT-3 来‘填补空白’是自然语言生成(NLG)的一个很酷的用例，GPT-3 就是其中的一种，”施梅尔策说。然而，“OpenAI 显然已经建立了他们的 GPT-3 网络的扩展，专门训练 GitHub 中的“数十亿”行代码来完成你在这里看到的超级完整的魔法。”

但这是开创性的吗，罗恩？

他在一次采访中说，因为自从 GPT-3 首次亮相以来，GPT-3 在建议代码完成方面的使用就一直存在，许多人在 HTML 和其他应用程序中使用它，所以这不是一个全新的想法。GPT-3 最初于 2020 年 6 月发布。

“然而，这种能力在 ide 和开发套件中的嵌入无疑将把基于人工智能的代码建议的使用提升到一个新的水平，成为一种‘必备’，”Schmelzer 说。"当然，我们必须谨慎对待所有这些."

他说，代码是否真的是所需要的、相关的、没有错误的或适用的，取决于开发人员。

“代码建议永远不应该盲目使用，尤其是在 GitHub 代码的数量上训练时，这些代码可能质量不一，”Schmelzer 说。

质量是关键，因为系统可能建立在薄弱的基础上。在一条讽刺性的推文中，IBM Research 软件工程首席科学家 Grady Booch 引用了 Merit Capital 联合创始人 [Maxim Khailo](https://www.linkedin.com/in/mempko/) 在[的博客文章](https://www.linkedin.com/pulse/bugs-faster-than-speed-thought-maxim-khailo/)中的观察，暗示使用 Copilot 而不完全审查结果可能就像建造一座纸牌屋。

“现在想象你的脚手架本身主要是由 Copilot 编写的，”推文写道。"错误将以新的方式传播，通过构建系统的系统."

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>