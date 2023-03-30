# Netlify 通过 Quirrel 采集增加了预定功能

> 原文：<https://thenewstack.io/netlify-adds-scheduled-functions-with-quirrel-acquisition/>

Netlify，这个给世界带来了 [JAMstack](https://jamstack.org/) 的公司，已经迈出了向其用户提供[预定功能](https://ntl.fyi/sched-func)的第一步，本周收购了[奇洛](https://quirrel.dev/)——一个用于管理和调度无服务器功能和作业执行的开源解决方案。Netlify 不仅买下了这家公司，还聘请了奇洛的创造者[西蒙·克诺特](https://twitter.com/skn0tt)，他也是 [Blitz.js](https://blitzjs.com/) 的维护者，并将加入 Netlify，进一步开发这一功能。

Netlify 首席执行官兼联合创始人马特·比尔曼(Matt Biilmann)说，他们是在不久前介绍认识的，他立即发现克诺特是“一个非常善于让日程安排、工作流程和工作体验变得非常直观、非常棒的人。”

在收购的同时，Netlify 还推出了[预定功能](https://ntl.fyi/sched-func)的测试版，比尔曼表示，自从该公司[在 2018 年](https://thenewstack.io/netlify-embeds-serverless-functionality-web-app-development-platform/)首次推出 Netlify 功能以来，这项功能一直是近年来最受欢迎的功能之一。通过函数，Netlify 为其用户提供了一种无需运行专用服务器即可运行动态应用程序的按需服务器端代码的方式。但是它们需要被触发——它们不会按计划运行。

Biilmann 说:“我们一直围绕着这样一个想法，即网络的架构将真正开始从一个每个网站都是一个整体应用程序的世界，一个所有东西都生活在该应用程序中的世界，变成一个你可以真正将网络用户界面分离成自己的东西，后端将分裂成所有这些不同的 API 和服务的世界。“当你构建一个 web UI 时，你有很多任务不能在浏览器中运行。它们需要在服务器端运行，它们需要与你不同的 API 和服务对话，它们需要成为 web UI 的后端。我们一直收到的一个请求是安排和管理重复的任务，或者删除作业，或者与您的 Web UI 相关的工作流。”

Biilmann 说，到目前为止，他们已经看到了各种不同的方法来运行预定的功能，从用 Zapier 设置预定的 webhooks，到在 AWS 或其他云提供商的基础上缝合服务，甚至到运行服务器来执行传统的 cron 任务。然而，这使得开发人员将代码放在了不同的地方。他说，现在预定的功能使它成为“真理的主要来源，不仅是我们希望发生的事情，也是我们希望它发生的时间”。

克诺特指出，这些安排功能的复杂尝试是创作奇洛的灵感来源之一。

“我从 Blitz 社区的某个成员那里读到了这篇文章，他解释了如何构建这个作业队列桥，将您的亚马逊 SQS 队列连接到您的应用程序运行的任何地方，例如 Netlify，这非常复杂，而且非常重复。这是构建奇洛背后的动机之一，因为很多东西在应用程序中是非常重复的。克诺特说:“有一种服务可以满足所有需求，这很好。”。

Biilmann 指出，预定功能可以用于各种任务，例如为每周报告收集数据或执行数据备份，甚至用于执行网络代码的构建。使用 crontab 及其[扩展](https://man7.org/linux/man-pages/man5/crontab.5.html#EXTENSIONS)等工具使用的[“cron 表达式”格式来调度函数，这些扩展提供了简化的调度，如“每日”或“每小时”](https://man7.org/linux/man-pages/man5/crontab.5.html)

目前处于测试阶段，该公司警告说功能可能会改变，并建议不要在“任何生产和/或关键工作流程”中使用它比尔曼说，它将至少在几个月内保持测试状态，“只是为了让人们经历一个周期，实际上拿起它，用它构建东西，并让我们知道核心原语是否正确。”

Biilmann 说，除了推动普遍可用性和巩固功能，他们还想超越作为同步进程运行预定功能。

“最终，我们希望确保这些程序可以作为后台功能运行，并运行更长时间的任务，”他说。“我们还想找出最好的方法，为这些任务的进度提供更多的反馈工具，并运行一个工作流，而不仅仅是一个作业。”

对于托管的奇洛服务的现有用户，克诺特在他自己的[博客帖子中提供了关于收购](https://dev.to/quirrel/quirrel-is-acquired-and-i-am-joining-netlify-dha)的更多细节，其中他指出，尽管在 2022 年 7 月底关闭了服务，奇洛“是(并将继续)开源的，现有客户将能够转向自托管的实例，我们(Netlify +我)将尽最大努力帮助你平稳过渡。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>