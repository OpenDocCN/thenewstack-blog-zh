# 本周编程:代码能帮助种族公正吗？

> 原文：<https://thenewstack.io/this-week-in-programming-can-code-help-with-racial-justice/>

每年，IBM 都会领导一个名为 [Call for Code](https://callforcode.org/) 的项目，这是一个基于代码的社会问题解决方案的竞赛。最近，这个问题已经成为环境问题，竞赛的获胜者可以获得一些运营现金，并从 IBM 自己那里获得基础设施支持。在过去的一周，IBM 决定将目光放在一些不同的事情上，而是宣布了[呼吁种族正义准则](https://developer.ibm.com/callforcode/racial-justice/)，它说这将集中在三个具体领域:警察和司法改革和问责制，多元化的代表性，以及政策和立法改革。如需更多信息，请查看他们的介绍视频:

[https://www.youtube.com/embed/O9esH4LHV-E?feature=oembed](https://www.youtube.com/embed/O9esH4LHV-E?feature=oembed)

视频

我立即想到的一个问题是，技术是否能够有所帮助，或者是否会在无意中使事情变得更糟，但是在视频中，IBM Cloud 的总经理 Evaristus Mainsah 说了一件突出的事情:“我们认识到单靠技术无法解决数百年来的种族不公正和不平等，但是当你把它放在黑人社区和他们的盟友手中时，技术可以开始弥合差距。”

到目前为止，我们已经看到太多技术只是嵌入其创造者的偏见和成见的例子，但也许通过专注于将创造行为交给黑人社区及其盟友，这可以被克服。至少，这似乎是这里的希望。作为代码呼吁的一部分，IBM 发布了五个开源解决方案，它表示正在要求开发人员和生态系统合作伙伴帮助测试、扩展和实现，并贡献“他们自己的不同观点和专业知识，使他们变得更加强大。”事实上，一些包含的解决方案利用技术直接针对这种偏见。这些项目都可以在中央 [GitHub 库](https://github.com/Call-for-Code-for-Racial-Justice)中找到，它们是:

*   [Five fifth Voter](https://github.com/Call-for-Code-for-Racial-Justice/Five-Fifths-Voter)，一个赋予黑人和其他少数民族权利的网络应用程序，通过行使投票权来确保他们的声音被听到。
*   [Legit-info](https://github.com/Call-for-Code-for-Racial-Justice/Legit-Info) ，一款帮助居民以他们自己的语言了解基于他们的国家、州、县、市和地区位置的立法和政策的影响的应用程序。
*   [事件准确性报告系统](https://github.com/Call-for-Code-for-Racial-Justice/Incident-Accuracy-Reporting-System/blob/master/README.md)，这是一个警方事件报告平台，允许证人和受害者证实来自多个来源的证据，并根据官方警方报告进行评估，以努力创建一个更可靠的事件所有记录。
*   [Open pending](https://github.com/Call-for-Code-for-Racial-Justice/Open-Sentencing)，这是一款帮助公设辩护人更好地为其客户服务的应用程序，通过识别人口统计等数据中的种族偏见，可以帮助提出更强有力的案件。
*   [Truth Loop](https://github.com/Call-for-Code-for-Racial-Justice/Truth-Loop) ，一款帮助社区了解对他们影响最大的政策、法规和立法的应用。

现在，令人惊讶的是，网上对该倡议的讨论很少，但我们会继续关注，看看它会带来什么影响。

## 本周的节目中

*   Git 2.29 关注安全性:Git 的最新版本已经发布，GitHub 提供了一些来自版本的[亮点，包括实验性的 SHA-256 支持。长话短说，当许多提交同时被写时，它们可能会相互冲突并导致问题，这种可能性极小。正如他们](https://github.blog/2020-10-19-git-2-29-released/)[写的](https://github.blog/2017-03-20-sha-1-collision-detection-on-github-com/)，“我们估计，即使有 500 万程序员每秒写一次提交，在太阳吞没地球之前，你也只有 50%的机会意外发生冲突”——所以，是的，非常小。尽管如此，小机会仍然比不存在的机会更不安全，[一些](https://shattered.io/static/shattered.pdf) [发布的](https://eprint.iacr.org/2019/459.pdf) [攻击](https://eprint.iacr.org/2020/014.pdf)的存在增加了这种机会，因此“Git 项目已经准备了一个过渡计划，开始使用一种没有已知攻击的新对象格式:SHA-256。”除了安全性，Git 2.29 引入了负 refspecs 和新的 git shortlog 技巧，你可以在 GitHub 的帖子或 2.29 的[发行说明中了解更多。](https://github.com/git/git/blob/v2.29.0/Documentation/RelNotes/2.29.0.txt)
*   **Node.js 15 增加了 npm 7 支持和更多:** Node.js 15 已经[到达](https://medium.com/@nodejs/node-js-v15-0-0-is-here-deb00750f278?source=rss-96cd9a1fb56------2)，团队注意到这将推动 Node.js 14 进入长期支持，这是 15 作为奇数版本不会发生的事情。因此，他们建议您“在生产部署中使用 Node.js 15 时要记住这一点。”至于特性，Node.js 15 包括 AbortController 的实验性实现，N-API 版本 7(它带来了使用 ArrayBuffers 的附加方法)，新的 V8 8.6 JavaScript 引擎，以及对 npm 7 的支持，它引入了工作区和新的 package-lock.json 格式。哦，当我们在这里谈论 Node 的时候，也许你听说过 Node 替代品，它是由制造 Node 的同一批人创造的。嗯，如果你想了解更多，Twilio 有一个[有用的介绍](https://www.twilio.com/blog/hello-deno)。

*   **摆脱专有的 Oracle Java:** 对于那些正在使用 Java 并且正在寻找摆脱 Oracle 专有的 Java SE 的人来说，Azul 已经发布了[一个答案](https://www.azul.com/azul-migration-services/)——一系列迁移服务来帮助团队从 OpenJDK 过渡到 [Zulu 版本。这些服务包括库存和使用审计软件，以及应用程序级测试和验证，以帮助组织迁移其整个 Java 资产，尽管他们说这是“关于与过渡相关的挑战的错误信息”对于更复杂的过渡，Azul 表示，它还与合作伙伴一起提供咨询支持和项目管理。](https://www.azul.com/downloads/zulu-community/)
*   我们应该留下还是应该离开？又到了一年中的这个时候，Go 语言团队开始反思，而[想知道你对语言](https://blog.golang.org/survey2020)的看法。如果你正在犹豫是否要花时间，他们说，今年的 [Go 开发者调查](https://google.qualtrics.com/jfe/form/SV_1O0A5f70Q38dlVr)已经被简化，以使它更快更容易获得。不仅如此，这也是你驾驭这门语言的机会，因为在过去的四年中，他们说开发者的反馈“在推动我们的语言、生态系统和社区的变化中发挥了巨大的作用，包括 gopls 语言服务器、最新的泛型草案、模块镜像等等。”出于好奇，你可以看看之前所有调查的结果。您必须在 11 月 8 日之前参与。

*   **Eclipse 关注物联网开发人员:**在调查的主题上，ADTMag [在](https://adtmag.com/articles/2020/10/20/eclipse-iot-survey.aspx) [Eclipse Foundation 的 2020 年物联网开发人员调查](https://outreach.eclipse.foundation/eclipse-iot-developer-survey-2020)的结果中达到顶峰，这是其第六次年度调查，该调查首次将边缘计算作为一个主题，并将“影响 [Eclipse Edge 原生工作组](https://www.globenewswire.com/Tracker?data=jZP3LIWHiMwGLssEPfWIqO-s6n_pUx0YUmTpQ1Pi8Kmoc-qEr_yWxPnLKkptFVFJopVc2FbvNxvpenXZHsmo--uNVggyTj87hMiu-oz-NMzkDh54mUE_r71d_nWUk8Jb)的路线图”，据该基金会称。根据 ADTMag 的说法，一些关键的发现包括 Java 作为边缘和云中使用最广泛的语言的主导地位，AI 是边缘最常见的工作负载类型，以及分布式分类帐作为保护物联网解决方案的一种方式获得了动力。欲了解更多信息，请下载[完整结果](https://www.globenewswire.com/Tracker?data=UOj_Tp2IDJdTmUmchQxrt1wrBqvZ54sU2Y0HXgxIBhXjja8iANcGRXQexokhSPMAp0MELlCkPpJkMxP_EzA3r4wdh7MwXrjNZCH-No4g-5B6s4yQVHeYcXUde6-lsCTI)。
*   **npm 引入了一个公共路线图:**npm JavaScript package registry 已经[引入了](https://github.blog/2020-10-22-introducing-the-npm-public-roadmap-and-a-new-feedback-process/)一个[公共路线图报告](https://github.com/npm/roadmap/)和一个[新的公共反馈流程](https://github.com/npm/feedback/)，希望透明性将为 NPM 做它最近为 npm CLI 所做的事情，该 CLI 是上周[与 npm v7.0.0 一起](https://github.blog/2020-10-13-presenting-v7-0-0-of-the-npm-cli/)推出的。路线图将显示管道中的特性、它们的当前状态以及“每个部分”的预计到达日期与此同时，反馈回购将允许你[开启讨论](https://github.com/npm/feedback/discussions)分享建议，他们说 npm 团队将尽最大努力在七天内做出回应。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>