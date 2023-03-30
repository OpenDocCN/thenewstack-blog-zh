# 利用 InfluxData 和 OPC-UA 服务器引领工业 4.0 时代

> 原文：<https://thenewstack.io/ushering-in-the-industry-4-0-age-with-influxdata-and-an-opc-ua-server/>

[InfluxData](https://www.influxdata.com/) 赞助了这个播客。

在本期《新堆栈制造商》节目中，TNS 创始人兼主编亚历克斯·威廉姆斯与 Factry 联合创始人兼首席执行官[耶鲁安·库塞蒙特](https://www.linkedin.com/in/coussej)坐在一起，重点讨论 OPC 统一架构(OPC UA)和 InfluxDB 在工业环境中的应用。

Coussement 建立了一个开源的 [OPC-UA 服务器](https://www.factry.io/blog/exposing-influxdb-data-opcua/)，用于将数据引入过程控制系统，并通过从工业控制系统收集数据、添加更多数据(并直观地解释结果)来展示时间序列数据库的价值，并以此作为优化的基础。

当在工业物联网(IIoT)环境中工作时，在整个软件开发过程中，有许多问题必须牢记在心。当 Coussement 构建 OPC-UA 服务器和[节点 OPC-UA 记录器](https://github.com/coussej/node-opcua-logger)时，他在构建服务器时强调“扁平化”模式，并在开发记录器时选择 Node 语言。

“您只需对其进行配置，它就会将您流程中的数据记录到 InfluxDB 中。简而言之，基本上就是这样。它还提供缓冲，因为通常您不希望任何数据丢失，所以您将收集器安装在您的自动化服务器之一上，在那里它尽可能靠近源。在那里，它将开始收集数据，如果出现某种网络问题，它将缓冲数据，以便当网络恢复在线时，它将发送它同时收集的数据，”Coussement 说。

[凭借 InfluxData 和 OPC-UA 服务器](https://thenewstack.simplecast.com/episodes/ushering-in-the-the-industry-4-0-age-with-influxdata-and-the-opc-ua-server) 迎来工业 4.0 时代

在工业环境中，许多设备和工具通过 IIoT 连接。因此，这需要一种新的方法来透明地管理数据库和信息，以及云计算和人工智能(AI)。Coussement 以开源项目的形式构建了 OPC-UA 服务器，允许制造组织在迁移到工业 4.0 标准时快速做出最能支持其业务的决策。

Coussement 对采用这些现代技术和多种数据源的观察结果各不相同，“首先，在技术方面，它们比我们在行业中使用的速度快得多，在我们知道和使用的旧应用程序中也是如此。第二，他们是用户友好的，他们是现代的。它向人们开放数据。因此，如果我们有这些限制，并且您需要使用特定工具查看您的数据，这些工具是该供应商特定堆栈的一部分，现在您有了 Grafana 这样的工具，您可以打开它，公司的每个人都可以使用它。”

在讨论的后期，当谈到人工智能和机器学习(ML)的问题是对这些技术的未来有所帮助的跨越时，Coussement 避免本末倒置。“我相信人工智能在未来会有所帮助，只是我们看到的现实是，大多数环境还没有为这一巨大的飞跃做好准备。

“工业 4.0 是一个很好的目标，但你必须把基础做好，”他说。“有了 InfluxDB 这样的技术，这就是我们现在试图做的事情，让工厂和工业环境达到这样一个点，一旦他们想开始做像人工智能这样的事情，他们就有数据来做，因为数据是算法和机器学习的燃料，所以没有数据，你就没有地方。”

### 在这个版本中:

[2:23:](https://thenewstack.simplecast.com/episodes/ushering-in-the-the-industry-4-0-age-with-influxdata-and-the-opc-ua-server?t=2:23) 你说的工业 4.0 是什么意思？
[6:27:](https://thenewstack.simplecast.com/episodes/ushering-in-the-the-industry-4-0-age-with-influxdata-and-the-opc-ua-server?t=6:27) 在开源方面，你一直在开发什么？也许你可以谈谈 OPC-UA 服务器？
[12:12:](https://thenewstack.simplecast.com/episodes/ushering-in-the-the-industry-4-0-age-with-influxdata-and-the-opc-ua-server?t=12:12) 什么是 OPC-UA 记录器？
[13:43:](https://thenewstack.simplecast.com/episodes/ushering-in-the-the-industry-4-0-age-with-influxdata-and-the-opc-ua-server?t=13:43) 你学到了什么，观察到了什么，我们看到这些现代技术被采用了，公司如何使用这些多种来源的数据？
[21:03:](https://thenewstack.simplecast.com/episodes/ushering-in-the-the-industry-4-0-age-with-influxdata-and-the-opc-ua-server?t=21:03)AI&ML 蛙跳将如何发生？
[26:07:](https://thenewstack.simplecast.com/episodes/ushering-in-the-the-industry-4-0-age-with-influxdata-and-the-opc-ua-server?t=26:07) 那么，你需要哪些人来帮助这些现代公司发挥潜力呢？

图片来自 Pixabay 的 Thomas B。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>