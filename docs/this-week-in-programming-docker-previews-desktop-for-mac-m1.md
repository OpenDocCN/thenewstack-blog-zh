# 本周编程:Docker 预览 Mac M1 的桌面

> 原文：<https://thenewstack.io/this-week-in-programming-docker-previews-desktop-for-mac-m1/>

世界就是这样——大规模的政府范围的违规事件和[记录每天新冠肺炎的死亡人数](https://www.npr.org/sections/coronavirus-live-updates/2020/12/17/947417443/u-s-surpasses-3-600-coronavirus-deaths-breaks-prior-hospitalization-record)——我们认为我们应该在本周为你们这些在[闪亮的新 MAC 电脑上使用 Docker 的开发者带来一点好消息:Docker Desktop for M1](https://www.apple.com/mac/m1/) 的[技术预览版已经发布，到目前为止，评论都很好。](https://www.docker.com/blog/download-and-try-the-tech-preview-of-docker-desktop-for-m1/)

如果你还没有读过苹果公司的新 M1 芯片，TLDR；是它的[快速和强大](https://www.macworld.co.uk/news/how-good-is-apples-m1-chip-really-3797893/):“新芯片据说提供 3.5 倍的 CPU 和 5 倍的图形性能，以及高达 9 倍的机器学习处理速度。”

由于至少有 150 万用户在 MAC 上开发，Docker [上个月开始着手](https://www.docker.com/blog/apple-silicon-m1-chips-and-docker/)构建一个新的 Docker 桌面，该桌面将在新的架构上运行。现在，该公司宣布了新版本的技术预览，尽管它警告说，“还不是发布质量，甚至是测试质量”，而是他们“希望让你尽快尝试。”据该帖子称，该公司面临三大挑战，其中最重要的是他们广泛使用 Go，这将在苹果芯片 1.16 发布之前不支持苹果芯片，该版本的目标是 2021 年 2 月。

用户可以期待的 M1 Docker 桌面的一大特点是多平台开发，一些用户对此表示怀疑，但 Docker 指出 Docker 一直都是这样。

“Docker 对多平台映像的支持已经有很长时间了，这意味着你现在可以在桌面上构建和运行 x86 和 ARM 映像，”他们写道。“M1 的新 Docker 桌面也不例外；您可以为 x86 和 Arm 架构构建和运行映像，而无需设置复杂的交叉编译开发环境。”

对于那些足够幸运已经拥有 M1 的人来说，M1 理工大学的 Docker 桌面预览版可供下载，该公司表示，预计它将于 2021 年初全面上市。

## 本周的节目中

*   **Rust 回顾其基础对话:**上周，Rust 团队召集社区进行了一次关于 Rust 基础的[对话](https://blog.rust-lang.org/2020/12/07/the-foundation-conversation.html)，现在他们提供了他们所认为的该对话的[后续步骤](https://blog.rust-lang.org/2020/12/14/Next-steps-for-the-foundation-conversation.html)。首先，有一个关于对话本身的[新调查](https://docs.google.com/forms/d/e/1FAIpQLSfeq4L0Rk6yXzGS19A6qLo4hpLlQiJh1nYFHsRJ9MrxO6k4iQ/viewform),但除此之外，这篇博客文章探讨了基金会和 Rust 项目如何相互联系的基本问题。本质上，基金会的使命是授权 Rust 维护者，对于大多数 Rust 团队来说，基金会不会改变他们的工作范围和决策权——显然，核心团队除外，他们将享受更轻的负担，因为“各种法律细节”将移交给基金会。因此，如果你对上述基金会仍有疑问，请务必[阅读常见问题](https://github.com/rust-lang/foundation-faq-2020/blob/main/FAQ.md)，因为它预计将于明年初正式推出。
*   **Rust 2020 调查显示…**IDE 体验正在改善，越来越多的人正在使用这种语言，并且在生产中的使用比以往任何时候都多。2020 年 Rust 调查结果显示，至少根据他们的解读，一种语言似乎兑现了其改进的承诺。“一般来说，受访者似乎不仅对 Rust 在过去一年的改进，而且对未来一年都有积极的看法，”他们写道。“特别是，许多人对该语言的新功能感到兴奋，如 **const** generics 和 generic associated types (GATs)以及 2021 版，对 **async** 的改进，Bevy 游戏引擎，公司对 Rust 的更多采用，WebAssembly 等等！”

*   **GitHub 表示，你仍然可以保留你的知识产权……某种程度上:** GitHub 正在[跟进](https://github.blog/2020-12-14-inspired-by-open-source-balanced-employee-intellectual-property-agreement-2-0/)2017 年[发布的](https://github.blog/2017-03-21-work-life-balance-in-employee-intellectual-property-agreements/)[平衡员工知识产权协议(BEIPA)](https://github.com/github/balanced-employee-ip-agreement) 的，更新和修订了 [BEIPA 2.0](https://github.com/github/balanced-employee-ip-agreement) ，由[社区反馈](https://github.com/github/balanced-employee-ip-agreement/pull/44)驱动。你看，1.0 版本在授予雇员(或雇主)专有知识产权方面“比通常更有利于雇员”。在 BEIPA 2.0 中，当知识产权是在员工的工作范围之外创建的，但与他们的工作相关时，“员工拥有此类知识产权，而雇主则获得使用它的无限许可。”其他变化包括取消保密义务，增加一个关于不共享任何受他人 NDA 或知识产权影响的信息的条款，以及增加一个“生存”条款，该条款规定如果任何条款被法院认定无效，其他条款仍然有效。
*   对许多人来说，这似乎是本周最令人兴奋的消息，GitHub 已经宣布[通过采取一个简单的步骤摆脱了 cookie 横幅](https://github.blog/2020-12-17-no-cookie-for-you/):不使用任何不必要的 Cookie。你看，这些横幅都是欧盟法律的一部分，该法律要求如果你的网站包含不需要的 cookie，你就必须使用 cookie 横幅。如果您使用了上述 cookies，横幅是一种变通办法。GitHub 现在表示，它已经“从 GitHub 中删除了所有不必要的 cookie，访问我们的网站不会向第三方分析服务发送任何信息”，并且“今后，我们将只使用我们为 GitHub.com 提供服务所需的 cookie。”撇开 cookie 不谈，该公司已经[在其之前的](https://github.blog/2020-12-15-token-authentication-requirements-for-git-operations/)[承诺](https://github.blog/2020-07-30-token-authentication-requirements-for-api-and-git-operations/)中设定了一个日期，开始要求所有经过认证的 Git 操作使用基于令牌的认证，而不是密码:2021 年 8 月 13 日。受影响的工作流将包括命令行 Git 访问，使用 Git 的桌面应用程序(但不是 GitHub Desktop)，以及直接使用您的密码访问 GitHub.com 上 Git 存储库的任何应用程序或服务。

*   **关于防止另一个黑客节:**还记得你在黑客节期间收到的所有[垃圾邮件吗？嗯，GitHub 已经对临时交互限制](https://thenewstack.io/this-week-in-programming-digitalocean-hacktoberfest-creates-spam-for-open-source-projects/)进行了一些[所谓的“强大”更新，这将允许你启用长达六个月的交互限制，甚至只需一次切换就可以](https://github.blog/2020-12-15-powerful-updates-to-temporary-interaction-limits/)[限制所有个人存储库之间的交互](https://docs.github.com/en/free-pro-team@latest/github/building-a-strong-community/limiting-interactions-for-your-user-account)。新的限制设置可在“交互限制”下的[用户设置中获得，并允许您“通过一次 toggleREST API 更新，在您的所有公共、用户拥有的存储库中启用临时交互限制。”](https://github.com/settings/interaction_limits)
*   **AWS CloudShell 提供 CLI 访问:** AWS 在 [2020 re:Invent 大会](https://reinvent.awsevents.com/)期间继续推出[越来越长的公告列表](https://aws.amazon.com/blogs/aws/aws-reinvent-announcements-2020/)，其中一个在本周的人群中引人注目的是 [AWS CloudShell](https://aws.amazon.com/cloudshell/) 的[介绍](https://aws.amazon.com/blogs/aws/aws-cloudshell-command-line-access-to-aws-resources/)。毕竟，我们知道开发人员有多喜欢(和需要)命令行访问，CloudShell 使获得支持 AWS 的 Shell 提示符变得简单而安全，提供了 [AWS 命令行界面(CLI)](https://aws.amazon.com/cli/) (v2)，预装了 Python 和节点运行时。提到的一些功能包括非常重要的暗(和亮)模式颜色主题，打开多个标签的能力，以及每个区域高达 1GB 的持久存储。而在运行时方面， [Bash](https://www.gnu.org/software/bash/) 、 [PowerShell](https://en.wikipedia.org/wiki/PowerShell) 、 [jq](https://stedolan.github.io/jq/) 、 [git](https://github.com/cli/cli) 、 [ECS CLI](https://docs.aws.amazon.com/cli/latest/reference/ecs/index.html) 、 [SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-command-reference.html) 、 [npm](https://en.wikipedia.org/wiki/Npm_(software)) 和 [pip](https://pypi.org/project/pip/) 也已经安装完毕，随时可以使用。

*   **谷歌的 MLKit 获得实体提取:**谷歌向[提供了其六个月前发布的](https://developers.googleblog.com/2020/12/announcing-the-newest-addition-to-mlkit-entity-extraction.html) [ML Kit SDK](https://developers.google.com/ml-kit) 的快速更新，写道它“很高兴将[实体提取](https://developers.google.com/ml-kit/language/entity-extraction)添加到官方 ML Kit 阵容中，并为我们的早期访问计划首次推出新的 API，[自拍分割](https://developers.google.com/ml-kit/early-access/selfie-segmentation)！”[实体提取 API](https://developers.google.com/ml-kit/language/entity-extraction) 允许您从原始文本中检测和定位实体，并基于这些实体采取行动，既可以是静态文本，也可以是实时的，支持 15 种不同语言的 11 种不同实体。请继续阅读支持哪些实体。至于[自拍分割 API](https://developers.google.com/ml-kit/early-access/selfie-segmentation) ，它确实做到了你可能想象的那样，将自拍的主体从背景中分离出来，便于添加图像效果。
*   **Java 正式成为 Jakarta:** 最后，iProgrammer 讲述了关于 Jakarta EE 9 规范发布的故事，其中包括从 Java 到 Jakarta 的正式迁移。“从 Java EE 迁移到 Jakarta EE 是必要的，因为当 Oracle 将 Java 的开源版本移交给 Eclipse Foundation 时，它保留了‘Java’和‘javax’这两个名称，并拒绝允许使用它们，”他们解释道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>