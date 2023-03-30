# 闭合反馈回路:自动化洞察系统

> 原文：<https://thenewstack.io/pentaho-easing-data-workflow-headaches/>

IBM Analytics 的 Jean-Fran ois Puget 去年 10 月在 T2 的 Spark 和机器学习会议上谈到一家公司建立了一个预测引擎来减少客户流失。

它列出了一份可能取消订单的客户名单，公司的客户关系部门给这些客户打电话，试图留住他们。然而，这些电话给了这些客户一个更容易取消的方法，只是加速了客户流失。

预测是准确的，尽管结果出乎意料，普吉特注意到房间里的笑声。

“我们需要一个反馈回路。我们需要衡量预测的商业后果，”他说。

他告诉与会者，随着模型的创建变得如此容易，试图有效利用分析的公司面临的许多棘手问题都来自内部。

在另一个案例中，数据科学团队构建了一个很棒的模型，然后将它交给开发人员，开发人员用不同的语言对其进行重新编码以便实现。几个月后，数据科学家提出了一个更好的模型，但开发人员已经被重新分配，无法重新编码，因此优化的模型从未实现。

“这必须是一个 [DevOps](/category/devops/) 的故事，”他说，并指出创建模型的工具可能与部署和操作模型所需的工具不同，但需要有一个持续的过程。

## 应用机器学习

大数据集成和分析供应商 [Pentaho](http://www.pentaho.com/) 最近宣布，它正在将[机器学习](https://community.hitachivantara.com/s/article/4-steps-to-machine-learning-with-pentaho)应用于这些工作流问题。

它旨在解决四个方面的瓶颈:

*   数据和特征工程。
*   模型训练、调整和测试。
*   部署和操作模型。
*   定期更新模型。

该公司宣传其 [Pentaho 数据集成](http://www.pentaho.com/product/data-integration)包，用于准备自动化数据加载、数据转换和数据验证，消除了手动数据准备过程的繁重工作。

Pentaho 全球企业数据科学总监 Wael Elrifai 说:“你不能只是将数据输入模型。“必须进行功能工程和数据工程……确保数据一致且有意义，并区分标量数据和矢量数据等。

“你不是用机器学习来做数据准备，而是用数据准备来做机器学习，”他说。

通过集成像 [R](https://www.r-project.org/) 和 Python 这样的语言，以及像 [Spark MLlib](http://spark.apache.org/mllib/) 和 [Weka](https://sourceforge.net/projects/weka/) 这样的机器学习包，数据科学家可以继续使用他们最喜欢的工具进行训练、调整和测试。但是在 Pentaho 数据分析平台内工作，不同的团队更容易合作，因为每个人都在使用一个公共平台，他们正在建立可用于不同目的的数据管道，Pentaho 产品营销高级总监 Arik Pelkey 说。

例如，在 Pentaho 的 Weka 知识流环境中，机器学习可以用来评估变量的重要性，找到关键变量的相互作用，并进行初步的预测评估。

拖放界面使得在具有可嵌入 API 的现有应用程序中部署和运行模型变得简单，并且可以定期更新模型。

“你不能有静态模型；模型必须进化，”Elrifai 说。

然而，更新是公司容易下滑的一个领域。根据 Ventana Research 的调查，只有 31%的组织使用自动化过程来更新他们的模型。

通过 Pentaho，数据工程师和科学家可以使用新的数据集重新训练现有模型，或者使用 R、Python、Spark MLlib 和 Weka 的自定义执行步骤更新功能。预构建的工作流可以自动更新模型和归档现有模型。

## 建立洞察团队

Forrester Research 分析师 Brian Hopkins 在二月份的 AnacondaCON 大会上对听众说，在未来的几年里，仅仅拥有大量关于你的业务的数据不会转化为竞争优势，因为每个人都将拥有大量数据。

那些获取更多更好数据并使用闭环系统迭代反馈的公司将会脱颖而出。他称这些为“洞察力系统”

“将进化的数据科学融入洞察系统的公司将会胜出，”他说。

洞察力驱动的公司正以约 27%的复合年增长率增长，而整体经济仅增长约 3%。创业公司的发展速度甚至更快。

诀窍是找到正确的数据，然后利用这些数据采取行动。

“每当你应用一种洞察力时，就会产生关于这种洞察力的结果的数据，而公司不会将这些数据捕捉回流程中，以便他们可以学习并优化它，”他说。

有效的公司从数据中创建洞察，然后测试洞察，并仔细检测软件和流程，以迭代洞察并为下一轮迭代捕获更多数据。

他指出电动汽车制造商[特斯拉](https://www.designnews.com/electronics-test/has-tesla-found-better-way-test-and-validate-vehicles/141623126256511)和在线个人购物服务 [Stitch Fix](https://www.designnews.com/electronics-test/has-tesla-found-better-way-test-and-validate-vehicles/141623126256511) 是那些有效迭代洞察系统的公司。

他描述了一个由 5 到 15 名数据科学家、开发人员、数据工程师和领域专家组成的跨职能团队，这是一个“insight-ops”类型的团队，由一名技术经理提供支持，他的工作是为团队获得正确的技术和正确的数据，他为一名拥有成果并有预算为该成果花费的业务领导工作。

他说，这必须是一项团队运动。

“[数据科学家]不是你可以把需求抛给他们的独立团队；他们嵌入到洞察力驱动的业务中，”他说。“他们是推动差异的团队，创造品牌和价值，推动企业估值。”

他们不会以“嗯”开头。我有很多数据，我能用它做什么？”他们首先确定他们认为会给他们带来竞争优势的结果和指标，有时是中期指标。

他们测试这种洞察力，如果不成功就放弃。他说，他们不断完善洞察力，在一个支持迭代、敏捷开发的单一平台上使用数据管理、分析和洞察力执行。

该平台具有大数据基础、由分析运行时组成的数据管道(运行所有模型的地方)和由工具或微服务组成的 insight 执行框架，允许您部署 insight 应用程序的组件，并将该流程与 insight 缓存、图形数据库等可以保存分析结果的东西相结合。他说，他们使用专门配备的应用程序和软件来收集 insight loop 所需的特定数据。

他说，人工或先进的机器学习可以增强这种努力，帮助你找出数据的重要之处，并为分析做好准备，使用更先进的算法进行特征工程，大大减少用于运行测试和选择最能推动结果的模型的抽象，并简化根据具体情况定制通用模型的过程。

特征图片: [dmytrok](https://www.flickr.com/photos/klimenko/) 的[弧](https://www.flickr.com/photos/klimenko/5093971521/in/photolist-8L8Wgc-6eeNM7-SdnGaA-buYRAF-9utVWm-chzskh-tD6K3-4VtCYV-aEzxg-9URwa8-7vjKZ1-8oGgyX-ahQFbF-bupiT8-5Mfypt-4J1wg-LPrKj-s7mCLa-drHPNZ-5KV7W2-fhKxHm-nF7Naj-rzM5io-b26hQR-pVsuNp-6q9zFs-8mJRjn-kCpMq-oKCdHQ-52R8Ly-8rZjgV-paHiwU-hXR55-qbZqDE-ddNWmg-PxD7o-d3Rj5A-rnrEec-681whb-bwZnp7-K68au-dXNm7d-dXNm8S-dXGEgZ-dXGEaB-3VknPD-xApv9-coq8sG-a4EweM-bJre7c)，授权于**的[CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/)T7。**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>