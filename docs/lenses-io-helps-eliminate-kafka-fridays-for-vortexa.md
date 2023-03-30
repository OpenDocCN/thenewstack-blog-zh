# Lenses.io 有助于消除 Vortexa 的“卡夫卡星期五”

> 原文：<https://thenewstack.io/lenses-io-helps-eliminate-kafka-fridays-for-vortexa/>

能源分析初创公司 [Vortexa](https://www.vortexa.com/) 曾有过它所谓的“卡夫卡星期五”卡夫卡在周五会出问题，这意味着要花一个周末的时间来解决问题，并试图修复它。

“我们完全理解创业公司可以获得竞争优势，因为他们正在使用这些新的尖端技术，对吗？这是促成因素之一，也是这家初创公司的独特之处之一。因此，我们渴望以某种方式让它工作，以某种方式，[但它]到了我的许多人都没有睡觉的地步。他们把时间花在不断排除与卡夫卡相关的呼叫上，”Vortexa 首席技术官 [Maksym Schipka](https://www.linkedin.com/in/mschipka/?originalSubdomain=uk) 说。

总部位于伦敦的 Vortexa 公司提供了全球海运燃料的实时可见性。它随时跟踪 10，000 多艘船只，并提供数据的分析汇总，供能源交易商、对冲基金、船舶经纪人和租船主用来优化运营和达成交易。

很大一部分数据来自[自动识别系统](https://www.navcen.uscg.gov/?pageName=aismain) (AIS)，它提供每艘船的位置、方向、速度等信息。它每秒钟收到大约 500 条 AIS 信息。而且还将地面、卫星和操作数据源结合到机器学习应用中。

它使用机器学习模型和人机反馈回路来填补数据空白，并帮助进行预测。Schipka 说，处理和分析实时数据是其业务的核心，但 Kafka 的开源摄取技术存在许多问题。

每当数据流出现问题时，首席执行官都会问这是不是卡夫卡的问题。“在 99%的情况下，答案是肯定的，”斯基普卡说。

“让实时 Kafka 基础设施正常工作，并让其上的所有模型可靠地工作，这绝对至关重要。我们根本无法获得任何稳定，”他说。“我们不得不编写许多内部工具来尝试和理解实际发生的事情，因为我们从来没有获得任何合理的可见性。”

它运行两个生产集群集群，一个充当或多或少的哑元—某种缓存或同步解决方案—但另一个是繁重处理发生的地方。

这家 53 人的公司的数据科学家比软件工程师还多。它在一个站点可靠性工程团队中有五个人，其中一个被斯基普卡描述为对卡夫卡有敏锐的直觉，但总的来说，员工对它几乎没有经验。

所以它开始寻找各种选择。一家是附近的托管服务提供商，但斯基普卡称其成本“绝对令人眼馋”

“现在我们有良好的七位数收入，但(在 2019 年初)我们才刚刚开始出售这种东西，数据被延迟很多很多小时甚至很多天，实际上可能会在公司开始以任何合理的方式产生之前破坏公司的声誉，”他说。

他在一次会议上遇到了 Lenses.io 团队，当时这个团队还被称为 [Landoop](https://thenewstack.io/landoop-lenses-promises-ease-application-development-kafka-streams/) 。夫妻团队 [Antonios Chalkiopoulos](https://www.linkedin.com/in/antwnis/) 和 [Christina Daskalaki](https://www.linkedin.com/in/chdask/) 与联合创始人、现首席技术官 [Andrew Stevenson](https://www.linkedin.com/in/datamountaineer/?originalSubdomain=nl) 一起围绕 Kafka 编写了大约 35 个开源工具，并决定将它们整合到一个[流数据管理平台](https://github.com/lenses)中，以使开发者和分析师更容易使用 [Kafka Streams](https://kafka.apache.org/documentation/streams/) 进行实时数据分析。

他们的工具范围包括提取、转换和加载(ETL)参考架构[流反应器](https://github.com/Landoop/stream-reactor)到[快速数据开发](https://github.com/Landoop/fast-data-dev)，这是一个包括 Zookeeper、Kafka、模式注册表和平台的 20 多个连接器的项目。

“当我们第一次使用晶状体时，这是我们第一次真正开始看到隧道尽头的光明，”斯基普卡说。“Lenses 立即发现了我们试图用 Kafka 做的事情的复杂性，只是通过…可视化所有数据流，可视化我们主题的拓扑结构，并[向我们]展示它有多复杂。

“我们一点也没有意识到。我们在黑暗中工作，试图部署我们认为正确的事情。只有当我们使用镜头时，我们才意识到我们试图用卡夫卡作品做的事情是多么复杂和不寻常。”

它还选择了[亚马逊 MSK](https://aws.amazon.com/msk/) ，Kafka 的管理解决方案，Schipka 将其描述为“不是没有自己的问题，但仍然很好，价格也更合理”，并决定将两者一起部署。

Lenses 在迁移中很有帮助，因为团队可以看到主题是如何被填充的，并帮助公司识别不必要占用资源的陈旧主题，并优化其基础架构。

自从与 Lenses 和亚马逊 MSK 合作以来，该公司已经开始在 Kubernetes 上部署——声称是第一个将三者结合使用的公司。

它还减少了调试和故障排除的开发时间。Schipka 估计节省的时间相当于一半到一个全职。

“如今，我的[团队]绝对无法想象没有镜头的工作，因为你知道，当他们遇到任何问题，当应用程序不符合他们的预期时，他们的第一个想法是连接到镜头，检查数据流，并使用 SQL 实时查询数据，以了解实际情况。”

它还为公司更广泛的部门带来了更广泛的数据可见性。

“自 2019 年 6 月以来，我们已经将我们与 Kafka 相关的基础设施和受控部署、受控数据流带到了一个人们可以开始睡得更多的状态。尤其是数据科学家，他们不怕接触卡夫卡，敢于尝试新的方法来解决我们面临的难题，”他说。

“最终，我们花在解决业务问题上的时间比管理成本和数据流的时间要多得多。”

特征图片:“[马士基 _ 埃德加。里加 2017 年 10 月 20 日](https://www.flickr.com/photos/142171772@N06/25691270798/in/photolist-F9ftJN-2gb7QS1-fo9LzZ-RF7w6W-2h6Egr5-2hHvQjN-UeAJeo-MJs4E3-npzi8K-JW1Pyy-g8ch6N-HJhS57-4RNyjz-28NFucm-HaT6E7-6RAb6B-6UHnM2-b4kqXH-b4kr9F-b4krdc-b4kqTV-b4krgD-b4kr2F-2gNK6gx-5y2Rru-2hNDYMt-2iwXKwH-nvSubP-2gdmuNg-pnAnJB-eeQq9Y-2hNGBt8-6oeTQw-8qaEjV-2gWNgDw-fm9a8H-8qdTnh-SZ8ugW-8qdNxA-bdD3NP-HhhneC-KMWQUs-2coTU7k-2hAz9am-cBc19m-GLcsLo-b4kr6p-b4kqW6-9fEJ22-b4kqPZ)”作者[егоржуравлёв](https://www.flickr.com/photos/142171772@N06/)。根据 [CC BY-SA 2.0](https://creativecommons.org/licenses/by/2.0/) 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>