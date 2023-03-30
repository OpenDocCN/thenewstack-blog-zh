# 来自 2022 OSSRA 报告的开源新闻

> 原文：<https://thenewstack.io/open-source-news-from-the-2022-ossra-report/>

当开源 Apache 日志库 [Log4j](https://www.synopsys.com/blogs/software-security/mitigating-impact-of-log4j-log4shell/?cmp=pr-sig&utm_medium=referral) 中的一组[漏洞](https://armerding.medium.com/get-your-vaccine-for-the-log4shell-software-pandemic-ae445b771be8)被公开时，世界在 2022 年之交得到了另一个关于开源软件无处不在的提醒。这些 Log4Shell 远程代码执行缺陷影响了运行 Java 应用程序的计算机，Java 是世界上最流行的编程语言之一。

 [泰勒·阿梅尔丁

泰勒是一名屡获殊荣的记者，他在 2011 年离开了主流报纸的衰落领域，前往爆炸式扩张的信息安全领域写作。Taylor 目前是 Synopsys 软件完整性小组的高级信息安全作家，之前曾为 CSO Online 和 Sophos 博客 Naked Security 写过文章。当他不写作的时候，他会去远足、骑自行车、打高尔夫球和播放蓝草音乐。在 Twitter @tarmerding2 上关注他。](https://www.linkedin.com/in/taylor-armerding-b6b2b03b) 

利用 Log4Shell 很容易。新思软件完整性小组的技术总监兼首席架构师迈克尔·怀特在[的博客文章](https://www.synopsys.com/blogs/software-security/mitigating-impact-of-log4j-log4shell/?cmp=pr-sig&utm_medium=referral)中写道，这些漏洞“执行起来微不足道”这意味着安全团队要加班很多时间，因为他们正期待着假期休息。

开源漏洞问题并不新鲜，Synopsys [网络安全研究中心(CyRC)](https://www.synopsys.com/software-integrity/cybersecurity-research-center.html?cmp=pr-sig&utm_medium=referral) 最近发布的[开源安全和风险分析](https://www.synopsys.com/software-integrity/resources/analyst-reports/open-source-security-risk-analysis.html?cmp=pr-sig&utm_medium=referral) (OSSRA)报告提供了有关如何查找、跟踪、维护和管理开源代码的指导，以便组织可以避免任何软件带来的不可避免的风险。

OSSRA 报告基于对 2021 年 17 个行业超过 2400 个商业代码库的分析。根据该报告的第七次年度迭代 2022 OSSRA，“开源无处不在，正如正确管理其使用的需求一样。识别、跟踪和管理开源对于有效的软件安全至关重要。”

今年发现的一些趋势令人鼓舞。至少有一个开源漏洞的代码库百分比略有下降，从 2020 年的 84%降至 81%。具有至少一个高风险开源漏洞的代码库的百分比下降更为显著，从 60%下降到 49%。

一些趋势不那么令人鼓舞。航空航天、航空、汽车、运输和物流类别以及物联网类别—60%或更多的代码库存在漏洞。另外八个行业(互联网和移动 appsed tech 营销技术；能源和清洁技术；金融服务和金融科技；零售和电子商务；制造业、工业、机器人；和企业软件/SaaS)50%或更多的代码库存在漏洞。另一个长期存在的问题是未打补丁的组件:“88%包含开源组件的过时版本，”根据该报告。也就是说，有可用的更新或修补程序，但尚未应用

## **log 4 shell 唤醒呼叫**

Log4Shell 是一个严重的漏洞——它耗费了组织大量的金钱和资源。OSSRA 报告指出，它还促使组织重新审视开源组件固有的挑战以及如何管理它们。

由于开源项目是由志愿者创建和维护的，补丁和安全更新通常不会“推”给用户；他们必须被“拉”

流行的开源项目可能有大量的志愿者来帮助维护代码，但是有数百万不太流行的项目只有不到 10 个人来维护它们。在某些情况下，项目多年没有更新或维护。

此外，太多的开发人员采取了一种“信任并且不用费心去验证”的方法。CyRC 的首席安全策略师 Tim Mackey 是 OSSRA 报告撰写团队的一员，他称之为“WooHoo！”接近。开发人员可能会被开源软件组件所能做的事情弄得眼花缭乱，以至于他们不会执行商业或专有软件所需的安全审查。

开源组件并不比商业或专有代码更安全或更不安全，但是对它们的管理不当会产生重大的商业风险。组织应该如何应对这些现实？

最好的方法是从[软件材料清单(SBOM)](https://www.synopsys.com/blogs/software-security/software-bill-of-materials-bom/?cmp=pr-sig&utm_medium=referral) 开始，这是一个代码库中每个组件的详细清单，加上制作它的志愿者的信息，许可限制，已知的漏洞和它正常工作所需的软件组件(依赖)。它本质上是软件供应链中的一个成分列表。

SBOM 可以帮助完成手动不可能完成的任务——探测依赖链的深度。Mackey 使用了一个简单应用程序的例子，它有八个“声明的”依赖项。虽然这看起来是一个可管理的数字，但其中每一个都有自己的依赖关系。一个多了八个，而另一个多了十五个。最终，该应用程序有 130 多个依赖项，这些依赖项有几个层次。

根据 OSSRA 的报告，“这些依赖性是软件供应链中存在最大风险的地方。最大限度降低这种风险的唯一方法是使用全面、详尽的 SBOM 来跟踪依赖关系及其相关风险，从而使您能够在需要时采取有针对性的明智措施。”

事实上，当漏洞被披露时，SBOM 可能是一项重要资产。在 Log4j 的例子中，一个拥有最新 SBOM 的组织只需进行简单的数据库搜索，就可以发现该库是否在其软件供应链中。如果是这样，它知道它需要获取并应用补丁。

好消息是，在过去的一年里，SBOM 已经成为网络安全领域最热门的缩略语之一。乔·拜登总统在 2021 年 5 月 12 日发布的关于[“改善国家网络安全”](https://www.nist.gov/itl/executive-order-improving-nations-cybersecurity) (EO 14028)的行政命令中明确呼吁这样做。该命令禁止联邦机构购买任何不包含 SBOM 的软件产品。

## **没有银子弹**

需要注意的是，SBOM 的“SB”并不代表“银弹”SBOM 是必要的，但这还不够。在 Synopsys 视频博客 AppSec Decoded 的最近一集[中，麦基指出，“SBOM 会告诉你软件中有什么，但不会告诉你如何修补它，不会告诉你它是否已被修补，如果你不小心，它可能会给你误导性的信息。”](https://www.synopsys.com/blogs/software-security/appsec-decoded-sbom-silver-bullet-supply-chain-security/?cmp=pr-sig&utm_medium=referral)

尽管如此，SBOM 本可以消除围绕 Log4Shell 的大部分恐慌——更不用说圣诞节前数千个开发和安全团队的不眠之夜了。正如 OSSRA 报告所述，“这种全天候的补救工作通常是由于组织不知道 Log4j 在他们的系统和应用程序中的位置，或者事实上，如果它在那里的话。”

“正如我们以前说过的，重要的是要区分缺乏开源管理和开源本身不是问题的事实，”报告总结道。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>