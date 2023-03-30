# Darktrace 通过机器学习实现网络安全自动化

> 原文：<https://thenewstack.io/darktrace-applies-math-unsupervised-machine-learning-automate-network-security/>

Darktrace 联合创始人 Poppy Gustafsson 最近在 [TechCrunch Disrupt London](https://techcrunch.com/event-info/disrupt-london-2016/) 上预测，[的恶意行为者将越来越多地使用人工智能](https://techcrunch.com/2016/12/05/darktrace-2/)来创建更复杂的鱼叉式网络钓鱼攻击。

根据安全供应商 [ESET](https://www.eset.com/us/) 的 [2017 年趋势报告](http://www.welivesecurity.com/wp-content/uploads/2016/12/ESET-Trends-2017-security-held-ransom.pdf)，犯罪分子与试图阻挠他们的人一样有能力使用人工智能，其中“下一代”安全营销人员抛出了“机器学习”、“行为分析”等流行词汇。这使得潜在客户更难甄别所有的炒作。

它预测了“杰克软件”或物联网勒索软件的兴起，例如将软件锁在汽车里，直到支付赎金。

[Darktrace](https://www.darktrace.com/) 在一些意想不到的地方注意到了物联网安全问题:

*   一家奢侈品制造商仓库的指纹扫描仪被攻破了。不仅所有员工的指纹被盗，黑客还上传了他们自己的指纹以进入仓库。

*   一家律师事务所将员工徽章与其联网的自动售货机相连，使员工能够建立账户，这样他们就不必去找零钱买零食了。他们可以刷卡。但是有许多与徽章相关的个人信息，并且该自动售货公司被发现向一家营销公司出售员工数据。

总部位于英国的安全供应商 Darktrace 认为，有决心的黑客会进入你的网络，所以基于边界的策略是行不通的。相反，它专注于在最早阶段检测和减轻攻击。它把它的检测部分称为[企业免疫系统](https://darktrace.com/technology/#enterprise-immune-system)，模仿人体的防御系统。使用无监督的机器学习——它不寻找恶意软件的签名或已知示例——在不知道要寻找什么的情况下，它为网络开发一种“正常”模式，然后寻找异常。

“我的身体就像一个网络——它与你的不同，它在不断变化，”Darktrace 的网络情报和分析主管贾斯汀·费里(Justin Fier)解释道。“我们不仅要寻找恶意行为，还要寻找异常情况。异常可能会转化为恶意活动，但也可能是配置错误或员工不守规矩。我们不想只关注恶意领域，因为除了恶意软件之外，还有很多其他事情也可能非常糟糕。”

他将企业免疫系统比作身体的免疫系统，能够检测到细微的变化，例如可能预示流感的温度升高。

“如果你看看网络活动，它真的只是一个大数据集。真正的问题是我如何以有效的方式操作和读取这些数据？这就是无监督机器学习的用武之地。这一切都是为了查看那些每秒都在变化的数据。它寻找趋势；它可以群集并找到哪些对象的行为与其他对象相似，并找到明显的偏差，通常是非常细微的偏差，”他说。

“我们正在研究一个设备如何与其他内部设备对话，以及它如何与外界对话，”Fier 补充道。“它的行为方式是否不同于正常的生活方式？然后我们会说，‘给我看所有和这个设备相似的设备。’它的行为方式对那些人来说是异常的吗？"

## 间谍机构和数学怪才

Darktrace 成立于 2013 年，由英国情报机构和剑桥大学数学家合作成立。其支持者包括 [Autonomy](https://www.ft.com/content/e657857a-7113-11e6-a0c9-1365ce54b926) 创始人迈克·林奇。它已经筹集了^(1.045 亿美元，包括 7 月份的[6400 万美元的 C 轮](https://techcrunch.com/2016/07/05/cyber-security-startup-darktrace-intercepts-64m-in-fresh-funding-at-a-valuation-of-over-400m/)。)

Darktrace 拥有 1500 个部署，包括丰田、捷步达康、普华永道和 T-Mobile 等客户，拥有大约 300 名员工。

其技术基于[贝叶斯概率数学](https://www.inverse.com/article/14403-make-better-decisions-with-bayesian-probability-the-smart-way-to-consider-risk)，侧重于积累知识而非历史频率，来估算风险。它使用连接到网络的设备，分析每个用户、设备和网络元素的行为，以建立常态模型。Fier 说，安装该设备大约需要一个小时，尽管用户可以使用数百种包含的模型中的任何一种，但它完全可以根据自己的网络进行配置。

该系统不依赖于代理，节省了安装和维护所需的时间。Fier 说，它通常比网络管理员预期的多检测 20%到 30%的设备。

除了提供网络可见性，网络团队还使用它来跟踪网络上的所有硬件，一些人力资源团队还使用它来监控被解雇员工的活动，以防止内部恶意活动。

Fier 说，可视化是一个关键的区别。例如，使用其威胁可视化界面，用户可以观察一个勒索软件的横向移动。它使网络完全可搜索。您可以深入查看特定设备的活动，观察诸如呼叫可疑区域或发送数据等行为。

“Darktrace 中的一切都是可配置的。你可以说，‘给我看看[特定时间范围内的]所有违规行为。费里说:“你还可以说，‘按型号排序’、‘按设备排序’或者‘给我看看表现古怪的用户账户。’”。

滑块还允许用户微调警报的数量。例如，您可以将其设置为只显示前 55%最罕见的异常。

除了向安全人员发出异常警报，它最近还推出了 [Antigena](https://darktrace.com/products/) ，可以实时对威胁采取自动行动。

它可以:

*   停止或减缓与特定威胁相关的活动。
*   隔离或半隔离人员、系统或设备。
*   标记特定的内容，如电子邮件，以便进一步调查或跟踪。

[Gartner](https://www.gartner.com/doc/3019619/cool-vendors-energy-utilities-) 将 Darktrace 评为“2015 年能源和公用事业领域的优秀供应商”，指出其能够实时识别攻击，但在发布 Antigena 之前撰写的报告中，强调了对检测到的威胁进行自动响应的必要性。

“这不是你的标准入侵检测系统，大多数管理员会告诉你，破坏比修复更多——关闭整个子网，影响很多业务连续性，”Fier 说。“Antigena 采取了非常外科手术式的方法。它只会阻止特定端口上的源和目的地之间非常特定的通信，甚至可能不会无限期地阻止它。我们可以告诉它只在一段特定的时间内阻止(通讯)。十有八九，用户甚至永远不会知道 Antigena 已经启动了。”

[451 Research](http://cstor.com/wp-content/uploads/2016/10/Darktrace_451-Research-Darktrace-Immune_Industry-Report.pdf) 对 Antigena 的加入大加赞赏，指出它“可以阻止攻击，将损害限制在几个文件内。我们相信这代表着行为分析向传统系统无法比拟的主动防御发展的重要一步。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>