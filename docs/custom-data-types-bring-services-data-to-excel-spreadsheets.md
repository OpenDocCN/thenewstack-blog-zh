# JSON 自定义数据类型来 Excel 电子表格

> 原文：<https://thenewstack.io/custom-data-types-bring-services-data-to-excel-spreadsheets/>

地球上大约有 7.5 亿人使用微软熟悉的电子表格应用程序 Excel 来存储和处理数据。

所以当增加新功能时，这是一件大事。

果不其然，在今年 11 月初举行的年度微软 Ignite 大会上，该公司宣布 Excel 正在升级其游戏，至少有一个科技网站称微软[将 JavaScript 引入 Excel](https://techcrunch.com/2021/11/02/microsoft-brings-javascript-to-excel/) 。

但事实要复杂得多:早在 2018 年，微软就已经增加了使用 JavaScript 插件[为 Excel 编写定制函数的能力。相反，Excel 现在也获得了面向对象编程中可定制数据类型的巨大能力和灵活性。也就是说，Excel 现在也将支持使用 JavaScript 对象符号(或 JSON)创建自己的数据类型。](https://github.com/OfficeDev/Excel-Custom-Functions)

这将最终带来将数据从您自己的内部服务公开到 [Excel 电子表格](https://thenewstack.io/spreadsheets-and-low-code-development-platforms/)的能力。

## 发送加载项

这项新功能是通过一个名为插件的 Excel 高级用户功能实现的(插件曾被称为“Office 应用程序”)。多年来，微软一直允许这些功能扩展应用程序集成到 Excel 中，允许它们添加自定义键盘快捷键、对话框，甚至在 Excel 菜单下添加自定义图标“丝带”。

插件可以通过 [Office 插件商店](https://support.microsoft.com/en-us/office/insert-office-add-ins-into-excel-for-the-web-3a19321c-182e-4cb7-9379-7f646fa2152c)分发(或者通过您的 IT 部门部署)。当然，一些用户甚至[创建了他们自己的](https://trumpexcel.com/excel-add-in/)(尽管微软的[文档](https://docs.microsoft.com/en-us/office/dev/add-ins/develop/develop-overview)描述了使用 Visual Studio 或用于 Office 插件的 Yeoman generator 来构建它们)。多亏了插件，Excel 已经变得越来越复杂；内容插件甚至允许在 Excel 电子表格中嵌入 YouTube 视频播放器。

但是现在 Excel 加载项也获得了创建自定义数据类型的强大新功能。在 11 月初的一篇博客文章，[中，微软 365 的总经理万圭·麦凯尔维](https://www.linkedin.com/in/wmckelvey/)写道，该功能将复杂的数据转化为“更灵活的结构”，“以更自然的方式向用户展示这些数据，同时仍然提供用户对其分析或报告所关心的全部信息的轻松访问。”

在她的博客文章中，McKelvey 强调这意味着现在你的 Excel 应用程序中的数据可以从你自己的定制数据源中提取。(在一个来自[Ignite conference skilling session](https://techcommunity.microsoft.com/t5/video-hub/excel-add-ins-and-data-types/ba-p/2909835)的例子中，一个内部数据库的列被无缝地聚集到单个对象中。)

对自定义数据类型的新支持“允许你将平面数据打包成一个逻辑[单一]值”， [Chris Gross](https://www.linkedin.com/in/chrisgross123) ，一位从事 Excel 工作的微软项目经理[在一篇博客文章](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-excel-add-ins-and-data-types/)中解释道。(这些对象甚至可以包括额外的属性，如说明正在定义的对象的图像。)

正如 skilling 会议所展示的，从内部数据库系统[创建的对象](https://thenewstack.io/category/data/)可以无缝地输入到每种对象类型的年度利润率计算中。是的，用户生成的“自定义函数”可以将这些用户创建的自定义数据类型作为它们的参数。

“我们构建这些 API 时考虑到了服务，”Gross 在技能会议上说。在他的博客帖子中，他写道“我们希望让您作为开发人员能够轻松地扩展任何服务，并通过您的加载项轻松地将您的数据公开给 Excel。它应该像采用我们的模式并传递模式化的值以便在 Excel 中显示和重用一样简单。”

或者，正如他在他的技能课程中所说，“这就像将你现有的服务连接到 Excel 一样简单。”

在某一点上，McKelvey 的帖子还特别强调了一个公司内部的场景，其中超级用户可以“创建可以将数据类型连接到您自己的服务或数据的插件或解决方案。”

Gross 在 skilling 会议的后期再次强调了他们与服务的兼容性，告诉他的观众微软正在“为开发者搭建一个平台”

## 多年的旅程

该功能是多年开发的结晶。

在过去，Excel 的单元格大多是用文本或数字填充的。(一些单元格也允许真-假布尔值——当然，也有像#REF！对于无效的引用。)但是现在微软“想让 Excel 超越数字和文本，”ZDNet 的一个标题宣称[(同时强调新功能“不是针对使用 Excel 的商业高管，而是针对需要在 Excel 单元格中争论元数据的开发人员。”)](https://www.zdnet.com/article/microsoft-wants-to-take-excel-beyond-numbers-and-text/)

展望文本和数字之外，在技能会议上，格罗斯描述了微软的道路:“我们已经走了多年的旅程，以提高您可以在 Excel 中处理的数据类型。”

从 2018 年的[开始，微软首次为地理名称增加了一种额外的数据类型(预先填充了人口等属性)以及一种股票类型，这两种类型都利用了微软的“知识图”数据集来获取最新信息。](https://techcommunity.microsoft.com/t5/excel-blog/preview-of-stocks-and-geography-new-data-types-in-excel/ba-p/176185)

微软称它们为“连接数据类型”，因为它们的值可以用新的在线信息来更新，去年微软宣布与 Wolfram 合作创造几百种新的数据类型。(“用化学、营养、邮政编码、历史事件甚至遗传学等相关数据类型来补充你的分析。”)

但是现在他们已经迈出了最后一步:创建自己的自定义数据类型的能力——以及使用它们的自定义函数。为了实现这一新功能，微软[为 Excel 开发者扩展了一个已经存在的特性](https://devblogs.microsoft.com/microsoft365dev/ignite-2021-excel-add-ins-and-data-types/)。微软的文档已经包含了一个高级的 Excel 特性，允许开发者[指定一系列单元格](https://docs.microsoft.com/en-us/office/vba/api/excel.range.value)，这些单元格的值都将被赋值或调整。这可能很简单:

`Worksheets("Sheet1").Range("A1").Value = 3.14159`

但是一个范围显然也可以跨多个单元格，更重要的是，这些值也可以通过一行代码来赋值。例如，如果数值低于某个阈值，则可以对该范围内的所有数字进行测试并向下舍入。

为了保持简单和直观，Range 使用了人们早已熟悉的对象语法，以及几个对象样式的[属性](https://en.wikipedia.org/wiki/Property_(programming))(比如`[Range.Value](https://docs.microsoft.com/en-us/office/vba/api/excel.range.value)`和`[Range.Count](https://docs.microsoft.com/en-us/office/vba/api/excel.range.count)` —范围内的单元格数量)。

因此，现在微软为 Range 添加了另一个对象样式的属性，名为 Range.valuesAsJson。这现在允许赋值代码使用熟悉的 JavaScript 对象符号语法。(尽管本周[的一个数据类型概述页面](https://docs.microsoft.com/en-us/office/dev/add-ins/excel/excel-data-types-overview)仍然警告说 Range.valuesAsJSON“正在开发中，还没有公开预览版。”)

## 一种指定数据组织的新模式

除此之外，微软还宣布了一个新的模式，指定如何在 Excel 中组织数据，其中包括一个新的类型属性(指定数据的类型)，它也可以与自定义数据类型一起工作。Gross 在他的博客文章中写道:“我们的重点是公开结构，这样你就可以使用我们的模式将数据导入 Excel。”

然而，微软的官方文档[包含了另一个免责声明](https://docs.microsoft.com/en-us/office/dev/add-ins/excel/excel-data-types-overview):“数据类型 API 目前仅在公共预览版中可用。预览版 API 可能会发生变化，并且不适合在生产环境中使用。不要在生产环境或关键业务文档中使用预览 API。

它还警告说，与数据类型集成的自定义功能“目前正在公开预览，只与 Windows 上的 Office 兼容。”

“要使用此功能，您需要[加入](https://insider.office.com/join/windows) [Office Insider 计划](https://insider.office.com/)，然后选择 Beta Channel Insider 级别。”

但微软最终对这一新功能寄予厚望。在上周的[博客文章](https://www.microsoft.com/en-us/microsoft-365/blog/2021/11/02/microsoft-office-transforming-for-the-hybrid-world/)中，McKelvey 将其描述为“给予开发者在 Excel 中构建的终极自由。”

她认为这是一个更大的过程的一部分，这个过程就是“让 Office 成为各种创作者的通用、交互式画布”

* * *

# WebReduce

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>