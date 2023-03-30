# JavaScript 库让开发者将人工智能功能添加到网络中

> 原文：<https://thenewstack.io/javascript-library-lets-devs-add-ai-capabilities-to-web/>

人工智能公司 Hugging Face 发布了一个新的开源 JavaScript 库,允许前端和 web 开发人员向网页和应用程序添加机器学习功能。

传统上，Python 笔记本是数据科学家的工具包，但对于大多数 web 和前端开发人员来说，它是 [JavaScript](https://thenewstack.io/javascript-developers-on-what-matters-and-whats-next/) 。这就是为什么 Hugging Face 创建了新的 HuggingFace.js 库，允许开发人员在网站和应用程序上利用初创公司的能力。

这家初创公司的产品和增长负责人杰夫·布迪尔说，到目前为止，添加这些功能意味着后端的 [Python](https://thenewstack.io/why-does-python-keep-getting-more-popular-github-knows-whats-up/) 应用程序可以完成这项工作。使用 JavaScript，浏览器可以请求机器学习模型为访问者提供预测和获得答案。

“我们提供一些[低代码/无代码工具](https://thenewstack.io/low-code-vs-no-code/)，但如果你想深入一点，你还得拿出一些 Python 笔记本等。这是数据科学家的传统工具箱，”Boudier 告诉 New Stack。"但是对于大多数开发者来说，JavaScript 是你构建应用程序的方式."

## 启用前端开发用例

Hugging Face 在其网站上有超过 150，000 个开源机器学习模型，但 Hugging Face.js 支持的一些用例包括:

*   语言翻译
*   情感分析
*   摘要
*   文本分类
*   图像中的目标检测
*   文本到图像的创建

“今天的公司使用我们的模型在其应用程序中构建的所有用例都将在网页上提供，”Boudier 说。"所有这些用例都可以直接在网页上实现."

[Jeremy Ellis](https://github.com/hpssjellis) 是一名开发人员，STEM 高中教师，他花时间与模型一起工作，为他的学生进行演示，这可以在网上[获得](https://hpssjellis.github.io/my-examples-of-huggingfacejs/public/index.html)。

“我在一周内能够完成的事情通常需要我花大约四个月的时间，”埃利斯通过乳齿象与新堆栈分享。“当我向他们展示我遇到的问题时，他们甚至改变了他们的模型演示。他们将 arrayBuffer 改为 blob，这使得向图像模型显示文本变得更加容易。”

埃利斯分享了一张他使用拥抱脸工具(他的演示页面上的 hug16 条目)创建的图像，该工具将文本“一只名叫 lowrain 的小狗在海滩上玩耍的高分辨率图像”转换为图像。

![A puppy on a beach](img/55142788de72eff3612a924313f21273.png)

人工智能图片由杰里米·埃利斯提供

显然，对于大型网站，利用这些模型将需要更多的基础设施支持，Boudier 解释说。在这些情况下，可以使用推理端点进行部署。它允许开发人员在完全托管的基础设施上部署机器学习模型。

Hugging Face.js 可以免费使用，连接它的 hub API 也没有任何成本，允许前端开发人员通过利用推理端点的 API 免费使用该功能。公司也欢迎社区对。js 库，Boudier 补充道。

“这就像你会直接使用我们的网站，但当你使用推理 API 时，你是通过拥抱脸. js 库来使用它，”Boudier 说。“还是那句话，没有成本。这与你在我们的网站上做的事情是一样的，但你是通过拥抱脸. js API 来做的。”

## 开源与闭源机器学习模型

除了它的产品，[humping Face 支持开源社区](https://thenewstack.io/machine-learning-is-as-easy-as-an-api-says-hugging-face/)，充当所有类型的人工智能模型的免费存储库。它还提供了一个沙盒来探索模型做什么，以及关于潜在偏见的信息。

今年 2 月，该公司宣布与 AWS 建立[合作伙伴关系，以便更容易使用和训练机器学习和人工智能模型。作为合作伙伴关系的一部分，AWS 开始提供 JumpStart 模板，允许 web、前端和其他软件开发人员快速部署模型，同时通过 API 访问它们。](https://thenewstack.io/hugging-face-aws-partner-to-help-devs-jump-start-ai-use/)

Boudier 强调说，与其他不太开放的人工智能 API 相比，拥抱脸的开源选项有一点不同，那就是开发者拥有更多关于潜在偏见和其他模型细节的信息。

“这一点非常重要，因为这意味着你可以了解内部发生了什么，你可以检查它，在它的基础上进行构建，等等。，”他说。“当然，我们有 150，000 种不同的模型来做你想做的事情。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>