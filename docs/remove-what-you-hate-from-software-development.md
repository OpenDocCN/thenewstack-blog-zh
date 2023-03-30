# 从软件开发中去除你讨厌的东西

> 原文：<https://thenewstack.io/remove-what-you-hate-from-software-development/>

[从软件开发中去除你讨厌的东西](https://thenewstack.simplecast.com/episodes/removing-what-you-hate-from-software-development)

作为当今热爱编程和编码的开发人员，您会发现您所做的一些工作(如果不是很多的话)可能与应用您的技能和创造力来解决代码问题无关。相反，您可能会发现自己在与更普通的工具和实践作斗争，这些工具和实践可能需要部署到例如云原生平台。

不幸的是，大部分工作都与使用 [YAML](https://yaml.org/) 和 shell 脚本、创建空间和文件名等有关。将时间和精力投入到“所有那些与让你的代码运行有关但实际上与代码无关的事情”上， [Gene Kim](https://www.linkedin.com/in/realgenekim) ，开创性且仍非常及时的书籍[、【凤凰计划】、](https://www.barnesandnoble.com/w/the-phoenix-project-gene-kim/1115141434)[、【DevOps 手册】](https://www.barnesandnoble.com/w/the-devops-handbook-gene-kim/1121371901#/)的合著者，以及为云原生平台提供软件交付平台的 [Atomist](https://atomist.com/) 的顾问。

“在过去的一年里，这件事让我意识到我是多么厌恶作为一名开发者的那些部分，”Kim 说。“这离真正解决问题还很远，而这正是我喜欢做的事情。”

这就是今天开发人员和软件交付的生活，但是在未来，新的工具将会越来越多地为软件开发和部署提供更加纯粹的可编程方法。这是 New Stack 创始人兼主编亚历克斯·威廉姆斯(Alex Williams)主持的播客的主题，首席执行官[罗德·约翰逊](https://www.linkedin.com/in/johnsonroda/)、原子主义者和 [Spring 框架](https://spring.io/)的创始人与金(Kim)分享了嘉宾位置。

Kim 描述了他典型的工作日是如何由写作、编程和“与游戏中的佼佼者共度时光”组成的。然而，他也注意到现在配置和代码之间的界限是多么模糊。“我，觉得总的来说，我是偏向配置的。我的意思是为什么要学习另一种语言或另一种 DSL？”金说。“但后来我发现自己在努力编写 Kubernetes YAML 或部署 YAML 文件等等——这令人抓狂。因此，从很多方面来说，你宁愿将它们组合成代码，而不是将它们视为配置。”

然而，转向存储库并采用事件驱动的方法进行软件交付是消除当今软件开发和交付中一些更普通、更低效和更笨拙的缺陷的一种方法。“当我们转向细粒度服务时，我们可能会发现我们有数百甚至数千个不同的存储库，”Johnson 说。“为每一项都建立一个管道是不可扩展的，而且会产生大量重复。你说的不是一份 YAML 档案，而是 500 份或更多。”

相反，Atomist 提供了一种事件驱动的方法，Johnson 说。“因此，不是对这些进行建模，以便每个存储库都有一个管道，而是有一个事件中心，并创建一个作为事件的推送，”Johnson 说。“因此，从本质上讲，Atomist 将开发团队中发生的所有事情都视为一个推送或一个现场结果或一个部署事件，并将其视为一个事件。”

原子主义者的平台也作为解释事件的模型。“每个存储库有一个管道的好处是有一个隐含的上下文，”Johnson 说。通过这种方式，可以深入了解代码和单个项目，看到所做的更改以及谁做了更改。

Johnson 说，Atomist 提供的另一个关键要素是“如何实现事件处理，我们认为应该用代码来实现”。“所以对于(批处理和 YAML 文件)或类似的东西，你使用一种成熟的现代编程语言。'

约翰逊说，在许多方面，今天，我们正站在巨人的肩膀上，包括艾伦·图灵和其他人，并且有机会“使用这些通过极其聪明的人的工作建立起来的概念来操纵事物”。

有了合适的平台，软件创建和交付应该纯粹是为了增加知识库，而不是花费过多的时间和精力用工具来填补空白，这些工具可能只是用来引导代码以部署到云原生平台。

“这实际上是关于，你能做什么的范围，哪些代码已经大大增加了，”约翰逊说。“我们都应该充分利用它。”

### 在这个版本中:

[1:13:](https://thenewstack.simplecast.com/episodes/removing-what-you-hate-from-software-development?t=1:13) 原子论者简介。
[10:21:](https://thenewstack.simplecast.com/episodes/removing-what-you-hate-from-software-development?t=10:21) 你如何让他们通过那座桥，进入并超越 YAML？
[14:10:](https://thenewstack.simplecast.com/episodes/removing-what-you-hate-from-software-development?t=14:10) 你如何利用这些平台来帮助开发人员，而不是强迫他们学习所有这些东西？
[15:17:](https://thenewstack.simplecast.com/episodes/removing-what-you-hate-from-software-development?t=15:17) 交付的复杂性是什么，你向日常工作中与你交谈的人推荐的基于事件的方法是什么？
[18:07:](https://thenewstack.simplecast.com/episodes/removing-what-you-hate-from-software-development?t=18:07) Gene，这种方法对你来说有什么重要的？
[23:24:](https://thenewstack.simplecast.com/episodes/removing-what-you-hate-from-software-development?t=23:24) 根据其他人证明有效的方法，开发人员发现自己正朝着什么方向发展，这告诉了你什么？

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>