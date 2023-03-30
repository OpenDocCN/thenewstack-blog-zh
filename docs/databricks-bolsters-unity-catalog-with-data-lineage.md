# Databricks 通过数据沿袭支持 Unity 目录

> 原文：<https://thenewstack.io/databricks-bolsters-unity-catalog-with-data-lineage/>

[Data lakehouse](https://thenewstack.io/5-ways-to-make-the-most-of-your-new-data-lakehouse/) 先锋 [Databricks](https://databricks.com/) 宣布在其 [Unity 目录](https://databricks.com/product/unity-catalog)中支持数据血统。[数据谱系](https://en.wikipedia.org/wiki/Data_lineage)对于采用 Databricks 平台进行机器学习、统计人工智能和数据治理的组织来说，具有重要的意义。

在构建和部署机器学习模型的整个过程中，无缝跟踪数据行程的能力会影响从成功运营到法规合规性的方方面面。

“你应该能够看到一个模型是如何工作的，”Databricks 营销副总裁 Joel Minnick 坚持说。“无论该模型是通过手动开发生成的，还是使用 AutoML 带您走一部分路或全部路，该模型的工作方式都不应该是不透明的。”

数据血统在很大程度上帮助数据科学家理解机器学习模型为什么会产生它们特定的输出。它使用户能够跟踪用于特定模型的数据的一切，从训练中涉及的数据到数据是如何操作或转换的。此外，数据沿袭为部署期间遇到的操作数据模型提供了同样的好处。

Unity 目录中的数据起源功能实时促进了这些优势，因此，正如 Minnick 所指出的那样，实际上“我在目录中看到的这些数据的沿袭和历史，与目前的真实情况没有任何区别。”

这种元数据的上游和下游方面在理解机器学习模型为什么会产生特定结果方面都起着关键作用。传统上，收集这些信息从来都不容易。

## **下游影响**

数据在整个企业中的移动的详细知识适用于各种用户，包括数据管理员、数据分析师、数据工程师等。然而，这种可追溯性对于寻求训练和部署[机器学习](https://blogs.gartner.com/sanjeev-mohan/2020/09/14/48/)模型的数据科学家来说尤其有用。Unity 目录被 Minnick 称为“基于 API 的”因此，它“通过 Databricks 平台捕获所有这些 API 调用和数据操作，以提供对数据发生的所有实时洞察，”Minnick 说。

这些信息对于数据科学家来说是非常宝贵的，他们需要确定模型使用了什么数据，数据来自哪里，以及数据是如何配置的。此外，Unity catalog 的主要区别之一是它为当今一些最流行的数据科学平台提供了这种可见性。Minnick 解释说:“我们为目录和数据谱系考虑的一件事是，它不仅仅局限于 SQL，许多目录产品都是如此。“但当我们开始谈论笔记本电脑时，人们越来越多地使用 Python、R 和 Scala。”

## **上游影响**

Databricks 的 Unity Catalog 促进的数据传承不仅扩展到数据科学笔记本，还扩展到仪表板和其他来源，如数据湖库、数据仓库和数据湖。正如可追溯性对数据科学家的帮助一样，它对专门的[数据治理](https://blogs.gartner.com/andrew_white/2020/08/26/stop-your-data-quality-project-and-start-your-outcome-based-data-governance-program/)人员也同样有用，比如数据管家，尤其是考虑到 Minnick 所说的“上游影响”仔细检查这些元数据可以让数据管理员在非常详细的层次上对整个企业进行影响分析。

例如，他们可以看到更改数据类型、删除列或更改行名的影响。对于特定的数据，管理员不仅可以了解它在哪些表格中使用过，现在还可以了解它在哪些笔记本中使用过；明尼克透露:“这种技术已经在哪些仪表板上使用了。“所以现在，我真的知道如果我对数据进行这种改变，可能会产生什么样的业务连续性问题。”

## **法规合规及更多**

数据来源的效用是无止境的，特别是对于 Databricks 等数据仓库解决方案和机器学习的部署。虽然 Unity Catalog 现在支持的详细谱系并不是解释能力的灵丹妙药，但它确实给了数据科学家相当多的可视性，让他们了解模型是如何创建他们的结果的。该知识随后提供了如何重新校准模型及其训练数据输入的蓝图，以产生公平、透明和更准确的输出。

“最近媒体上有一些例子，人们不得不回答这个问题:这个模型训练的数据来自哪里？”明尼克说。“如果你无法回答这个问题，或者你可以回答这个问题，但很难将有问题的数据与没有问题的数据分开，那么你必须停止使用这个模型。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>