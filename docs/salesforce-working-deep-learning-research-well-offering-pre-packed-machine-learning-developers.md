# Salesforce 加大深度学习研究，为开发人员提供预打包的机器学习

> 原文：<https://thenewstack.io/salesforce-working-deep-learning-research-well-offering-pre-packed-machine-learning-developers/>

企业软件云提供商[Salesforce.com](http://www.salesforce.com)正在建立一个人工智能驱动的服务连续体，从将智能引入日常工作的预打包解决方案，到支持公司建立自己的深度学习模型的平台。

Salesforce 在这一新兴领域的部分动力来自于今年早些时候[对 meta mind](https://techcrunch.com/2016/04/04/saleforce-acquires-metamind/)的收购。该公司任命 MetaMind 创始人兼首席执行官 [Richard Socher](http://www.socher.org/) 领导一个研究实验室，该实验室将调查人工智能(AI)和[机器学习](/category/machine-learning/) (ML)如何在企业中使用。

现任 Salesforce 首席科学家的 Socher 上周在 Salesforce 的年度[dream force](https://www.salesforce.com/dreamforce/DF16/)用户大会上告诉我们，实验室将公布其研究结果，而不是发布另一个深度学习工具包。

Socher 带着他创办的一家初创公司来到 Salesforce，从事机器学习的动态记忆方法。这是他在斯坦福大学研究的一个课题。

Socher 的方法为神经网络增加了更多的内存，以帮助它在解析信息时存储和更新细节，帮助它处理一系列事实或来自不同来源的信息。他展示了该系统检测复杂句子的情绪，并回答关于照片中正在发生的事情的问题；任务[机器学习](/category/machine-learning/)系统经常出现问题。

他的实验室将致力于深度学习、自然语言处理和计算机视觉的基础研究，而不是产品功能，尽管它们将作为[爱因斯坦](https://www.salesforce.com/blog/2016/09/introducing-salesforce-einstein.html)的一部分出现，这是 Salesforce 最近添加到其云服务中的一套机器学习功能。

“我们覆盖的范围很广，从我们知道如何解决的问题，如领先得分，但我们可以用最新最棒的技术做得更好，到我们不知道如何做的问题，”Socher 说。“我们不知道如何对大量文本进行推理，我们无法做完美的翻译。我们正在做一些基础的，基础性的研究，改进神经网络，真正困难的任务，没有人能做得很好，比如回答问题。我们非常兴奋的是计算机视觉和多任务学习，而不是单一模型方法。”

不过，不要指望像谷歌、微软、亚马逊、英特尔和百度那样推出自己的深度学习框架。

“我们将发表学术的、同行评议的论文；我们将把它们向前推进，我们将发表我们的见解，”Socher 告诉我们；“我们不必重新发明框架。我们认为已经有足够多的框架了。问题是你如何使用这些框架，你用它们做什么。在某种意义上，它们是一种商品，就像编程语言和操作系统是商品一样；我们不需要回到汇编语言，我们可以使用更高级的语言。”

该研究实验室正在研究的技术超越了内置于 Salesforce 工具中的爱因斯坦机器学习功能，如[销售云](https://www.salesforce.com/products/sales-cloud/overview/)和[营销云](https://www.salesforce.com/products/marketing-cloud/channels/)，这些工具基于使用 Salesforce 的每个企业定制的机器学习模型提供预测、建议和警报。

“我们可以学习模式并对客户数据做出预测，”Salesforce 数据科学负责人 Shubha Nabar 解释道。“您的客户流失的可能性有多大？你应该如何接触他们，甚至你的沟通文本应该是什么？”

这可能是对销售线索评分，向高级销售人员发送优先机会，建议一天中发送消息的最佳时间，以便快速阅读，发现你试图与公司的错误人员达成交易，并建议其他人应该参与对话，或者使用实体识别检测电子邮件中提到的竞争对手。

“我们可以确定哪些公司在其他公司的背景下被提及，谁是首席执行官，那里的个人网络是什么样的，”Socher 声称。

爱因斯坦可以根据消费者的购物习惯对他们进行细分，比如你可以争取回有特定兴趣的选择性订户的休眠客户，或者打开很多页面但不点击很多东西的橱窗购物者。爱因斯坦可以用来改变购物网站上产品的排序顺序，通过使用以前的销售来预测特定的客户会对什么感兴趣。它可以帮助将客户支持案例发送给最合格的代理，或者将未回答的客户问题自动升级为案例。

图像识别功能可以查看客户照片，并允许组织深入了解他们感兴趣的功能。性别、头发颜色和长度数据可以用来给短发男人提供帽子，给长发的黑发女人提供发带。

Salesforce 还在为其物联网服务开发预测分析和预测设备评分。

这些都是开发人员在使用其用于 web 和移动开发的 Lightning 工具构建基于 Salesforce 的应用程序时可以使用的拖放选项——后者基于 [Cordova](https://cordova.apache.org/) mobile framework，基于 Salesforce [Lightning](http://www.salesforce.com/campaigns/lightning/) 的应用程序也可以在 Microsoft Outlook 中工作。

但 Metamind 的两个更高级的选项也进入了 Salesforce 通过上传训练集，您可以为预测视觉和情感服务训练自己的深度学习模型，这就像在浏览器中选择要上传的文件一样简单。

如果没有预先训练的分类器适合您需要处理的图像，您可以训练自己的模型来检测徽标，处理医学图像或区分平屋顶和斜屋顶。你可以使用自然语言处理服务在文本中寻找积极和消极的情绪。你还可以以互动的方式询问图像中正在发生的事情，这样你就可以将其构建成一个聊天机器人，为客户服务。预测服务是您可以从任何应用程序调用的 API。

您还可以更进一步，在 Salesforce 提供的 [Heroku Private Spaces](https://developer.salesforce.com/blogs/developer-relations/2016/01/introducing-heroku-private-spaces-applying-network-access-controls-salesforce-integration-apps.html) 中使用正在开发的 [Apache PredictionIO](http://predictionio.incubator.apache.org/) 开源机器学习服务器，该服务器提供专用实例，为您提供您自己版本的 Heroku，因此您可以添加限制哪些 IP 范围可以访问该实例或选择它在哪个地理位置运行。PredictionIO 让你可以使用像 Spark [MLlib](http://spark.apache.org/mllib/) 和 [OpenNLP](https://opennlp.apache.org/) 这样的机器学习库，或者构建你自己定制的机器学习模型。

简而言之，Salesforce 现在提供连续的 ML 服务，从将 ML 添加到常见销售和支持流程的固定 Einstein 服务，到新兴的和更具实验性的图像和自然语言预测服务，到您可以用 Java、PHP、Python 和 Ruby 设置、定制和编程的完整机器学习环境。

在这些不同级别的工具之间移动是一个相当大的跳跃，但如果您的企业正在使用 Salesforce，您可以选择如何使用机器学习，这取决于您可用的技能和资源。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>