# 本周节目:爱上朱莉娅

> 原文：<https://thenewstack.io/this-week-in-programming-falling-for-julia/>

这个月见证了期待已久的[Julia](https://julialang.org/)1.0 版本的发布，该版本自称为“贪婪程序员的语言”为什么贪婪？正如该语言在 [2012 年首次亮相](https://julialang.org/blog/2012/02/why-we-created-julia)时所引用的，至少可以说，朱莉娅团队为自己设定的目标是崇高的。这里值得重复一下:

“我们想要一种开源的语言，拥有自由的许可。我们想要 C 的速度和 Ruby 的活力。我们想要一种同形异义的语言，既有像 Lisp 那样的真正的宏，又有像 Matlab 那样明显、熟悉的数学符号。我们想要像 Python 一样可用于一般编程，像 R 一样易于统计，像 Perl 一样自然用于字符串处理，像 Matlab 一样强大用于线性代数，像 shell 一样善于将程序粘合在一起。这种东西学习起来非常简单，却能让最严肃的黑客感到高兴。我们希望它是交互式的，我们希望它是经过编译的。”

从最初的愿望清单中可以看出，Julia 背后的一个基本想法是，他们不再想为了易用性而牺牲性能。所以，现在的问题是——他们成功了吗？或者，正如 Quartz 上的一篇文章所问，[使用 R 和 Python 的数据科学家是否应该转而使用 Julia？](https://qz.com/1360318/is-julia-a-good-alternative-to-r-and-python-for-programmers/)

当然，记住[贝特里奇头条定律](https://en.wikipedia.org/wiki/Betteridge%27s_law_of_headlines)和采用新技术的一般经验法则，答案很可能是“显然不是”和“对某些事情可能是，但对其他事情不是”的某种组合虽然 Quartz 指出 Julia 比 Python 和 R 更快，但它也指出“如果处理速度对你来说不重要，Julia 可能不如你正在使用的任何产品——至少目前如此。”他们还提到了一个简单的事实，即作为一项尚未完全开发的技术，“在调试和识别性能问题的工具方面，Julia 落后于 Python 和 R。”

与此同时，茱莉亚看起来确实吸引了一些人，她有超过 200 万的下载量，像纽约美联储一样的顾客，以及在中国明显高涨的人气。如果你发现自己正在考虑放弃 Python 和 R，转而使用新的语言，这里有[的另一篇文章，它给出了这两种语言之间的逐点比较](https://www.technotification.com/2018/08/julia-programming-language.html)，明确支持 Julia。

说真的，像这样的问题有简单的答案吗？选择语言总是项目需求、语言性能和特性以及个人偏好的某种混合。当然，随着时间的推移，我们会看着朱莉娅步步高升。它是否会取代像 Python 和 R 这样坚定的语言，还有待观察。

## 本周的节目中

*   **Twitter 为#BreakingMyTwitter 道歉:** ProgrammableWeb 本周写道 [Twitter 解释了#BreakingMyTwitter](https://www.programmableweb.com/news/twitter-explains-breakingmytwitter/2018/08/20) ，但我敢说我的标题会更准确。他们引用了 Twitter 的 Rob Johnson 的一封内部邮件和公开帖子，写道:“既然使用(用户流和网站流 API)的开发者是公司生态系统中最杰出的成员，Twitter 似乎打算与他们决裂，强烈反对是该死的。”文章最后问道，开发者是否会“继续尝试使用 Twitter 的 API 来创建有意义的应用”，或者“Twitter 的开发者生态系统是否正在缓慢地、有意识地死亡”，我发现自己在想这家公司可能有多少机会。我的意思是，它不像[我几年前写的同样的情况](https://readwrite.com/2011/02/11/twitter_kills_the_api_whitelist_what_it_means_for/)或类似的东西…
*   **模块在 Go 1.11 中到来:**也许你还记得[关于新 vgo 包版本的介绍的喧嚣](https://thenewstack.io/this-week-in-programming-vgo-and-the-onus-of-a-technical-solution-to-all-possible-scenarios/)，这个版本在二月份首次宣布，并在五月份被正式接受？嗯，随着 [Go 1.11](https://tip.golang.org/doc/go1.11) 的发布，模块将获得实验性支持。因此，看起来是时候让橡胶上路了，软件开发人员 [Roberto Selbach](https://roberto.selbach.ca/) 提供了一步一步的[介绍 go 模块](https://roberto.selbach.ca/intro-to-go-modules/)，将内部争论留在过去，转而关注[语义版本](https://semver.org/)将如何在 Go 向前发展中发挥作用。这篇帖子看起来像是任何致力于继续 Go 的人的必读之作。

*   **Npm 增加了三个新的安全特性:**在最近的一些[安全](https://thenewstack.io/npm-attackers-sneak-a-backdoor-into-node-js-deployments-through-dependencies/)[问题](https://thenewstack.io/poor-password-hygiene-enabled-eslint-supply-chain-attack-on-npm/)之后，Javascript 包管理器 [npm](https://www.npmjs.com/) 本周宣布了一些升级的安全特性，以帮助锁定事情。新功能包括“报告漏洞按钮、安全建议和防止使用泄露密码的功能。”“报告漏洞”按钮现在将出现在每个软件包页面上，允许用户快速报告可疑的安全问题，而安全咨询将告知用户软件包漏洞，并提供如何应对的建议。最后，泄露密码功能将用户密码“与特洛伊·亨特和“我被密码了吗”项目慷慨提供的 5.71 亿个密码散列的巨大列表进行比较
*   **Java & JavaScript 仍然占据着至高无上的地位:**尽管几乎每天的头条都在暗示相反的情况，但看起来 [Java 仍然活得好好的](https://sdtimes.com/java/report-finds-java-and-javascript-remain-the-top-languages-for-enterprise-development/)和它的[同名但不相关的兄弟 JavaScript](https://stackoverflow.com/questions/2018731/why-is-javascript-called-javascript-since-it-has-nothing-to-do-with-java) 。本周， [SDTimes](https://sdtimes.com/java/report-finds-java-and-javascript-remain-the-top-languages-for-enterprise-development/) 为我们带来了一份来自 [Cloud Foundry Foundation](https://www.cloudfoundry.org/) 的[报告](https://www.cloudfoundry.org/blog/java-and-javascript-are-the-dominant-languages-in-the-enterprise-according-to-new-cloud-foundry-foundation-research/)，该报告发现“企业似乎坚持使用 Java 和 JavaScript 来满足他们的企业应用程序开发需求。”根据该报告，其他进入前十的语言包括 C++、C#、Python、PHP、VB.NET、C、Visual Basic 6 和 VBA，大公司倾向于 Python 和 C#。与此同时，Java 和 JavaScript 在北美独领风骚，而 C++在亚洲取代了 JavaScript。如果您有兴趣深入了解，可以下载[完整报告](https://www.cloudfoundry.org/wp-content/uploads/Developer-Language-Report_FINAL.pdf)。
*   几个月前，GitLab [发布了基于网络的 IDE](https://about.gitlab.com/2018/06/15/introducing-gitlab-s-integrated-development-environment/) ，并发表了一篇相当长的博文，描述了它在内部争论中的起源。现在，在一篇更加直白的博客文章中，[公司宣布](https://about.gitlab.com/2018/08/22/gitlab-11-2-released/)git lab 11.2 将在 Web IDE 中获得实时预览，[使用 XML 清单文件导入 Android 项目的能力](https://about.gitlab.com/2018/08/22/gitlab-11-2-released/#support-for-android-project-import)，以及启用定制项目模板的功能。目前， [Web IDE 实时预览功能](https://about.gitlab.com/2018/08/22/gitlab-11-2-released/#client-side-evaluation-in-web-ide)支持客户端 JavaScript，但[服务器端 Ruby 支持](https://gitlab.com/gitlab-org/gitlab-ee/issues/4013)将于今年晚些时候推出。最后，GitLab 宣布[云原生头盔图表现已正式发布](https://about.gitlab.com/2018/08/22/gitlab-11-2-released/#cloud-native-gitlab-helm-chart-generally-available)以帮助在 Kubernetes 上安装 GitLab。

[https://www.youtube.com/embed/sSWu6TyubTE?feature=oembed](https://www.youtube.com/embed/sSWu6TyubTE?feature=oembed)

视频

*   有趣的历史编程花絮:作为本周的总结，我们有两篇文章探索了编程世界中一些有趣的历史。首先，在我们自己的页面上，大卫·卡塞尔带着[去看看 Vim，一个时代](https://thenewstack.io/a-look-at-vim-a-text-editor-for-the-ages/)的文本编辑器，探索从一个极短名字的编辑器到下一个编辑器的缓慢迁移，直到 Vim 诞生——一个比以前的编辑器增加了 50%名字长度的名字。这是一本很好的读物，它解释了 Vim 作为一个“为一个不再存在的世界而写”的程序的一部分的各种怪癖。接下来，再往前追溯 150 年左右， [TwoBitHistory](https://twobithistory.org/) 博客问[阿达·洛芙莱斯的程序实际上做了什么？这篇文章带领读者经历了导致 Lovelace 程序的数学思想的发展过程，甚至还把它翻译成了 C 语言。](https://twobithistory.org/2018/08/18/ada-lovelace-note-g.html)

https://twitter.com/usclearning/status/1033026134336724993

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>