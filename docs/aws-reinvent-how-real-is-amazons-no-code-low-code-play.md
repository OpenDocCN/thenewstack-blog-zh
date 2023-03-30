# AWS Re:发明:亚马逊的无代码/低代码游戏有多真实？

> 原文：<https://thenewstack.io/aws-reinvent-how-real-is-amazons-no-code-low-code-play/>

在拉斯维加斯举行的年度 Re:Invent 用户大会上，低代码/无代码成为亚马逊网络服务(AWS)一些关键公告的基础，包括无代码平台(T2)的可用性和机器学习(ML)的适应性。AWS 还引入了用于 web 应用程序开发的[amplife Studio](https://aws.amazon.com/amplify/studio/)，这是一种减少(但不是消除)为[AWS amplife](https://aws.amazon.com/amplify/)web 开发堆栈编写的代码量的工具。

低代码/无代码的确切含义通常仍然不清楚，因为定义会根据来源而变化。但就 AWS 而言，云服务提供商巨头正在吹捧其亚马逊 SageMaker Canvas 的发布，特别是作为 ML 的无代码版本。AWS 表示，它允许业务分析师构建用于预测的 ML 模型，而无需知道如何编写代码或具有 ML 专业知识。例如，借助图形用户界面，业务用户可以简单地合并云中或内部数据源中的文件，以便生成货物交付预测。

SageMaker Canvas 的设计很简单，尽管这可能会限制它的使用范围。尽管如此，它确实为模型预测提供了 ML 功能，其界面像 Excel 电子表格一样易于管理。

亚马逊网络服务(AWS)首席执行官亚当·塞利普斯基(Adam Selipsky)在活动开始前的主旨发言中表示:“现在，业务用户和分析师可以使用 SageMaker Canvas，使用直观易用的界面生成高度准确的预测，无需编写代码，也无需任何 ML 体验。”。“重点是分析师已经熟悉的术语和可视化，它们补充了他们已经在使用的数据分析工具。这是一种强大的自动机器学习技术，可用来创建模型，使业务用户和分析师能够以与数据科学家相同的高质量创建预测。”

在一篇博文中，[AWS 的开发者支持者 Alex Casalboni](https://twitter.com/alex_casalboni) 展示了如何使用 SageMaker Canvas 接口来合并两者。csv 文件，包含 120 种产品和 10，000 条运输记录的相应产品和运输数据(ProductData.csv 和 ShippingData.csv ),只需选择导入和上传即可。他展示了如何通过在 Models 部分选择 New model 来创建一个新的 ML 模型。

“这种快速的反馈循环和直观的 UI 允许我使用 ML 模型，而不必编写定制代码，”Casalboni 写道。“如果我决定将模型集成到自动化生产系统中，Amazon SageMaker Studio 集成让我可以轻松地与团队中的其他数据科学家共享模型。”

然而，正如 TNS 记者兼分析师贾纳基拉姆·MSV 敏锐地注意到的那样，SageMaker Canvas 似乎仅限于使用 CVS 文件。

AWS 的无代码画布是亚马逊现有 SageMaker AutoML 功能的简单 GUI，[企业管理协会(EMA)](https://www.linkedin.com/in/torstenvolk/) 的分析师 Torsten Volk 告诉新堆栈。Volk 说，这些功能并不是新的，因为有十几个供应商提供 AutoML，有时更加灵活、透明和强大。“但真正的问题是，Canvas 为那些乐于上传大量数据、定义因变量和目标变量并期望从这一过程中获得准确的统包预测模型的商业用户提供了多大程度的指导:这就是 Canvas 似乎失败的地方，因为模型生成器没有警告用户诸如类不平衡、模型过度拟合和功能之间的相互依赖性等问题，”Volk 说。“SageMaker Canvas 似乎也没有弥补这些问题，也没有指出最终模型的缺点。”

## 机器学习平台

许多其他 AutoML 平台，如 Dataiku、H2O AI、DataRobot 和 IBM Watson“在这方面走得更远，就数据源的哪些部分应该排除以及成功的模型训练需要额外的数据或预处理提出了明确的建议，”Volk 说。“Canvas 似乎让用户犯自己的错误，如果他们不小心，他们甚至可能将由此产生的错误模型投入生产供他人欣赏，”Volk 说。

AWS Amplify Studio 可以说属于公民开发人员的低代码类别，通过使用可视化开发界面，允许开发人员使用“最少的代码”创建 web 应用程序用户界面(ui)，从而减轻了 web 应用程序开发的许多中间和繁琐的过程然而，它也允许开发者使用熟悉的编程语言定制他们的应用程序的设计和行为，例如 JavaScript 和 TypeScript，AWS 说。

“Amplify studio 帮助开发人员和 UX 设计师更好地合作。除了开发人员需要花费大量时间来完成 pixel 完美的设计之外，这些 UX 设计经常没有得到正确实施，这让 UX 的设计人员感到沮丧，并使最终用户体验不如预期的好，”AWS 开发人员宣传经理阿里·斯皮特尔在主题演讲中说道。"有了 Amplify Studio，开发者可以从他们的设计者那里导入定制的 UI 代码."

AWS 表示，Amplify Studio 实际上不仅仅是一个低代码工具，因为它旨在为开发人员提供自己编写代码的精度，但具有低代码工具的速度。

在一次演示中，Spittel 展示了 Amplify Studio 开发人员如何从 React 组件中进行选择，而不必“编写成千上万行自定义代码来生成人类可读、可信的 React 代码，”Spittel 说。“以后，如果我需要，我可以自己扩展这些代码，对我的组件进行额外的控制，或者添加更多我需要的数据属性，”Spittel 说。

然而，Volk 说，Amplify Studio 将属于低代码工具类别，因为开发人员和业务分析师是如何工作的。Volk 说:“对于开发团队来说，将他们当前的 ide 换成包含潜在的省时模板的低代码工具将需要很多，甚至是部分。“这是一个有趣的想法，但它需要被打包为流行的开发人员 ide 的扩展，以潜在地吸引他们作为观众。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>