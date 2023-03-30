# GitHub 动作容易受到铁锈工件的毒害

> 原文：<https://thenewstack.io/github-actions-were-vulnerable-to-rust-artifact-poisoning/>

人们太倾向于相信，仅仅因为一些程序、语言、操作系统或其他任何东西比其他的更安全，它就是安全的。不，不，它不是。以[锈](https://www.rust-lang.org/)为例。比 C 安全吗？你打赌！它绝对安全吗？见鬼不！ [Legit Security](https://www.legitsecurity.com/) 最近在 [GitHub Actions](https://github.com/features/actions) 和 Rust 中披露了一类新的软件供应链漏洞。

该漏洞利用工件中毒来攻击底层软件开发管道。在工件中毒中，攻击者用恶意负载替换合法工件的内容。这个上下文中的工件是持续集成/持续交付(CI/CD)管道产品。这些包括作业完成后供以后使用的持久工作流数据，如日志文件、核心转储、测试结果、图片等。，以及同一工作流中作业之间的通信通道。

## 对 GitHub 操作的攻击

一旦就位，这些恶意数据可能会被用来使用 [GitHub Actions](https://thenewstack.io/8-github-actions-for-setting-up-your-ci-cd-pipelines/) 和 Rust 发起攻击。具体来说，该漏洞存在于“rust-lang/rustc_codegen_gcc”存储库中。这使得任何用户都可以在特权管道中执行代码。然后，黑客可以提取像云凭证这样的存储库秘密，修改项目设置，甚至使用 GitHub API 篡改源代码。

根据 Legit Security 的说法，“根据 Rust 的具体配置，熟练的攻击者可能会使用这些权限将攻击扩展到易受攻击的存储库之外的其他 Rust 资产，并在组织内部横向移动。”

GitHub Actions 的部分问题在于它的工件存储机制。它的跨工作流工件通信不能区分合法的项目工件和由项目分支创建的工件。这使得攻击者可以创建一个分支，然后可以创建一个恶意的工件。

任何 GitHub 用户都可以发起攻击，这使得潜在的攻击更加危险。要做到这一点，您可以简单地创建一个 pull 请求，然后上传一个恶意的工件。攻击者甚至不需要代码审查批准，因为易受攻击的构建操作在被项目正式接受之前就与恶意代码一起运行。

因此，Legit Security 的联合创始人兼首席技术官 Liav Caspi 解释说:“这是一种不同类型的漏洞，可能会导致攻击和修改开发管道本身，而不仅仅是修改代码。一个简单的类比就是汽车装配线。对装配线本身的攻击可能包括窃取敏感部件、关闭某些步骤，或者用任何有效部件替换恶意部件。这是一个强大的攻击载体，给网络犯罪分子带来了很多破坏的选择。”

简而言之，这是个坏消息。虽然这种特殊的供应链攻击变种是新的，但我们以前见过类似的攻击。例如，我想起了 [CodeCov 软件供应链攻击](https://thenewstack.io/not-your-usual-supply-chain-hack-the-codecov-bash-uploader-blunder/)。但这是一种更复杂的攻击手段。

## 漏洞已修复

幸运的是，这都是理论上的。Rust 和 GitHub 开发人员已经修复了该漏洞。然而，其他 GitHub 行动项目仍然存在潜在的漏洞。

为了减少使用这种利用这种漏洞的方法的其他潜在攻击，Legit Security 建议

*   在使用工件之前，您可以指定从哪个运行 id 或提交散列下载工件。
*   过滤掉由拉请求创建的工件。
*   永远不要相信跨工作流工件内容。使用有效负载前，请务必对其进行消毒。例如，如果您期望一个拉取请求数，请确保该值是一个数字。
*   通过在存储库→设置→操作→常规中启用**“需要所有外部协作者的批准”**，确保您控制允许运行哪些工作流。

如果你做到了这一切，你就不用担心这种攻击。也就是说，这也再次强调了你必须确切地知道你用来构建你的程序的每个组件是什么。如果你还没有使用[软件材料清单(SBOM)和软件工件的供应链级别(SLSA)，那么](https://thenewstack.io/sboms-are-great-for-supply-chain-security-but-buyers-beware/)是时候开始了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>