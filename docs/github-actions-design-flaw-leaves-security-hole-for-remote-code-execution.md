# GitHub Actions 设计缺陷为远程代码执行留下了安全漏洞

> 原文：<https://thenewstack.io/github-actions-design-flaw-leaves-security-hole-for-remote-code-execution/>

我们并不都使用 GitHub，但是肯定有很多人使用它来管理我们的 Git 代码库。我们中的一些人也已经开始使用 [GitHub Actions](https://github.com/features/actions) 进行持续集成/持续部署(CI/CD ),但事实证明在 Actions 中隐藏着一个安全漏洞。

据 [Google Project Zero](https://github.com/googleprojectzero) 研究员 [Felix Wilhelm](https://twitter.com/_fel1x) 称，GitHub 动作设计的一个缺陷可以让黑客写入你的存储库。如果这还不够糟糕的话，它还可以用来揭示加密的秘密。

哎呦！

Wilhelm 发现 GitHub Actions 工作流命令特性充当了动作运行器和被执行动作之间的通信通道。到目前为止，一切顺利。但是工作流命令通过解析所有已执行动作的标准输出来工作。STDOUT 携带的命令之一是" **set-env** "

你大概能猜到这将走向何方。是的，没错， **set-env** 可以定义任意的环境变量作为工作流的一部分。正如所指出的，“极易受到注入攻击”。因此，当运行程序解析每一个 STDOUT 行来寻找工作流命令时，每一个“在执行过程中打印不可信内容”的 Github 操作都是易受攻击的。

易受你所问的伤害？当然是远程代码执行。

Wilhelm 研究了一些流行的 Github 库。他发现几乎任何带有复杂 Github 动作的项目都是脆弱的。事实上，“甚至 Githubs 自己的行为也容易受到这个问题的影响。”

GitHub Action 工作流命令中可能隐藏着更多的麻烦。Wilhelm 承认他没有研究其他 workspace 命令的安全影响。

那么，你能做什么？威廉不确定。他认为，“工作流命令的实现方式从根本上来说是不安全的。放弃 v1 命令语法并用 allowlist 强化 **set-env** 可能会对直接 RCE(远程代码执行)向量产生不利影响。但是，即使能够覆盖后续步骤使用的“正常”环境变量，也可能足以利用最复杂的操作。”

当然，Wilhelm 建议，一劳永逸地解决这个问题的方法是将工作流命令移动到某个越界通道(例如，一个新的文件描述符)中，以避免解析 STDOUT。但是，这有一个小问题:它会“破坏许多现有的动作代码”。"

GitHub 还没有走到那一步，但请做好准备，您现有的一些 GitHub 操作代码将会崩溃，因为 GitHub 的开发人员正在从 Runner 中删除两个最易受攻击的命令。“runner 将在不久的将来发布一个更新，禁用 **set-env** 和 **add-path** 工作流命令。”到不久的将来，2020 年 11 月底前读完。

与此同时，GitHub 建议您“应该升级到@actions/core v1.2.6 或更高版本，并用新的环境文件语法替换工作流中的任何 **set-env** 或 **add-path** 命令实例。”如果您继续使用旧命令或旧工具包版本来使用工作流和操作，您将首先看到警告，最终，如果您继续尝试使用旧的不安全命令，您将在工作流执行期间出错。

因此，再一次，就像安全问题经常出现的情况一样，是时候准备开始打补丁和清理代码了。一个开发者的安全工作是永远做不完的。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>