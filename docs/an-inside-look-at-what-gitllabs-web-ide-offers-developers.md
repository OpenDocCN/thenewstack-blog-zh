# 深入了解 GitLab 的 Web IDE 为开发人员提供了什么

> 原文：<https://thenewstack.io/an-inside-look-at-what-gitllabs-web-ide-offers-developers/>

Gitlab 正在重塑其 Web IDE，以更好地支持基于云的环境中的远程开发。

新的 Web IDE 上个月面向所有人推出了测试版，并且已经在 GitLab.com 默认启用。git lab Create 的首席产品经理 [Eric Schurter](https://www.linkedin.com/in/eric-schurter/) 说:它在发布后不到一个月就收到了积极、重要的反馈。

“我们选择开放测试方法的原因之一是，我们希望社区帮助我们了解哪些功能是最重要的，需要立即解决，”Schurter 告诉 New Stack。“我们已经收到了非常有价值的反馈，并实施了一些改进措施。”

## 已经计划的新功能

根据用户反馈，Gitlab 计划迭代提交和代码审查体验，并添加一些更重要的功能，如能够在 [Web IDE](https://thenewstack.io/why-cloud-ides-are-shifting-to-a-platform-as-a-service-model/) 中安装和运行第三方扩展，以及在整个项目中进行搜索。

GitLab 在[宣布测试版](https://gitlab.com/gitlab-org/gitlab/-/issues/385787)时表示，之前的 Web IDE 基于开源 [Monaco editor](https://microsoft.github.io/monaco-editor/) ，但不编译代码，也不可定制为开发者自己的工作流程。Schurter 说，新的 web IDE 基于 Visual Studio 开源项目，旨在满足开发人员的需求。

他说:“ [Visual Studio Code](https://thenewstack.io/this-week-in-programming-visual-studio-code-arrives-on-the-web/) 是最受欢迎的 ide 之一，在 GitLab UI 中为浏览器带来了熟悉的体验，这意味着开发人员可以更有效率、更有信心地进行更改，而无需花时间在本地开发环境中切换上下文。”

他告诉 New Stack，Web IDE 还建立在 VS Code 提供的基础上，添加(例如)处理文件系统跟踪更改的自定义扩展，使用 GitLab [API](https://thenewstack.io/what-tns-readers-want-in-2023-more-devops-api-coverage/) 将这些更改提交到存储库，并建立到远程开发环境的连接。

“我们很高兴能够利用频繁的上游贡献的好处，尽可能地为项目做出贡献，并根据需要实现 GitLab 特定的功能，”他说。

## IDE 中更多的云开发支持

云开发(或者 GitLab 称之为远程开发)是 beta Web IDE 的一个重点。Schurter 说，开发人员花费数小时管理和更新他们的本地依赖项或重新安装包管理器来解决冲突。他补充说，较大的团队可能会花几天，甚至有时几周的时间，让新开发人员加入一个项目。

“通过在代码中定义一个稳定的、可重复的开发环境，开发人员将能够在云中创建这些环境的短暂实例，并准备好在几分钟内从 Web IDE 或他们的本地 IDE 做出贡献，”他说。“还有其他具有类似功能的产品，但真正的好处将是在 GitLab 的单一 [DevSecOps 平台](https://thenewstack.io/3-essential-tips-for-adopting-devsecops/)中包含和管理所有这些产品。”

GitLab 团队成员一直在使用测试版网络集成开发环境来更新 [GitLab 手册](https://about.gitlab.com/handbook/)，GitLab 的高级开发者传道者迈克尔·弗里德里希说。

“我对远程开发的方向感到兴奋，以确保每个人都能做出贡献，”Friedrich 说。“这将解决本地硬件和配置开发环境的限制，并使团队和开源贡献者更加高效。”

## 开发者体验

他概述了开发人员的体验，称 Web IDE 集成到 GitLab DevSecOps 平台中，可以直接从通用工作流访问:启动新项目、编辑现有文件或从合并请求中打开 IDE 以处理审阅反馈。

“Web IDE 文件资源管理器提供了对存储库中所有文件的访问，以便进行更改，并具有智能自动完成建议和语法突出显示，”他说。一旦更改被提交给新的分支，就可以创建新的合并请求。合并请求将触发 [CI/CD 管道](https://thenewstack.io/four-steps-to-set-up-a-ci-cd-pipeline-in-20-minutes/)，安全扫描，审查应用部署，以及在 [DevSecOps 生命周期](https://thenewstack.io/best-practices-across-the-devsecops-lifecycle/)中快速反馈的可观察性。”

他补充说，Markdown preview 附带了这一功能，可以帮助文档。

弗里德里希说，前端和 web 开发人员应该知道，他们可以快速地对 web 应用程序源代码进行更改，并使用合并请求来部署它们，并在审查应用程序中提供反馈，或者他们可以使用连续交付来进行生产更改。在 Web IDE 中保存更改后， [CI/CD 管道会自动运行](https://thenewstack.io/3-ways-to-use-automation-in-ci-cd-pipelines/)。他补充说，当远程开发环境与按需云开发环境一起可用时，开发人员可以从终端开始使用开发 web 服务器进行实时预览。

## 面向老开发者和新开发者的特性

Friedrich 说，高级用户可以利用 Web IDE 的可扩展性，并补充说，在未来，用户将能够在 Web IDE 中安装 VS 代码扩展，以获得更可定制的体验。

弗里德里希说，另一个计划中的功能将使开发人员和 DevOps 工程师受益:浏览器中针对 VS 代码的 [GitLab](https://thenewstack.io/why-were-sticking-with-ruby-on-rails-at-gitlab/) 工作流扩展，具有直接的 CI/CD 管道反馈。据 Friedrich 说，这就是说，IDE 的轻量级方法和语言语法突出显示、文件树访问和搜索使它成为初学者的一个很好的选择。Schurter 说，事实上，Gitlab 在开发新的 IDE 时就考虑到了非开发人员。

“我们有兴趣让非开发者更容易获得这种开发者体验，”Schurter 说。“通过让每个人在任何时候都可以使用 Web IDE，而不需要安装或配置，我们希望让每个人都更容易做出贡献。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>