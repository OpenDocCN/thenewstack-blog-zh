# 利用 SPDX 提高开源供应链的透明度

> 原文：<https://thenewstack.io/improving-open-source-supply-chain-transparency-with-spdx/>

针对[软件物料清单](https://www.ntia.gov/SBOM) (SBOM)的 [ISO/IEC 5962:2021 标准](https://www.linux.com/audience/iso-establishes-sbom-standard-for-open-source-development-with-spdx/)的发布更多的是开始而不是结束。至少，这是我在去年夏天那篇文章发表前后采访[大卫·a·惠勒博士](https://dwheeler.com/dwheeler.html)时了解到的。

要理解这种区别及其对整个计算世界的影响，需要一点标准化背景知识、软件的逻辑观点以及 [Linux 基金会](http://linuxfoundation.org)，Wheeler 在该基金会担任开源供应链总监。以下是这些部分如何组合在一起的总结:

## 安全在中心

SBOM 是一个严肃的话题，从这个意义上来说，它不仅被政治活动家和理论家所讨论，还被总统幕僚和军事决策者所讨论。

 [卡梅伦·莱尔德

Cameron 是 Phaseit，Inc .的副总裁，在那里他实施软件项目并发表关于结果的文章。作为一名长期的开发人员、经理和作家，他最近专注于“持续一切”的架构挑战:持续集成、持续测试等等。](https://github.com/claird) 

最明显的是，美国总统拜登关于改善网络安全的第 14028 号行政命令(EO14028)承认 SBOM 管理是一个紧迫的国家安全问题。

计算机领域的一个神秘角落——这就是 SBOM——是如何成为全球关注的焦点的？

拜登政府的行政命令无疑是由 2020 年 3 月的网络安全管理软件产品袭击和各种高度公开的对能源供应商的基础设施袭击引起的，如 2021 年的 Colonial Pipeline。然而，最近一个值得注意的例子是 [Apache 软件基金会的 Log4j](https://logging.apache.org/log4j/2.x/) 软件中的一个漏洞。该漏洞 [CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-44228) 又名 Log4Shell，可允许攻击者完全控制未打补丁的系统。

就像 10 年前影响 OpenSSL 库的 [Heartbleed 事件](https://www.vox.com/2014/6/19/18076318/heartbleed)一样，Log4Shell 是一个影响许多系统的严重漏洞。在 Log4j 的情况下，这可能是数十亿个系统。

对漏洞的反应是迅速的。维修人员迅速行动起来。补丁开发得很快。高管们命令 24 小时工作人员更换 Log4j 的易受攻击版本，并将互联网恢复到足够安全的基线。

但是，正如 2012 年的 HeartBleed 和 Log4j 一样，组织不一定知道受影响的组件在应用程序中的位置。

听起来很简单。软件组件损坏了，所以专家需要更新软件组件，对吗？

但并不是每个修复都像更换一个软件组件那么简单。然而，现代软件是建立在许多许多组件之上的。正如一辆汽车可能在田纳西州由世界上一千个其他工厂生产的零件组装而成，软件是建立在其他软件之上的，而软件又是建立在其他零件之上的，如此类推。

2012 年的 Heartbleed 响应者很快发现，无论他们多么想替换和修复漏洞，仅仅定位 SSL 的所有使用都是一项庞大且可能不可行的工作。特定的软件依赖于容易受到攻击的特定 SSL 库吗？2012 年令人震惊的部分原因是发现“是/否”问题的答案往往是“我们不知道”。

2022 年，“Log4j 的所有用途都在哪里？”看起来惊人的相似。

业界通过更多的技术共同解决了这个问题:使用[软件包数据交换](https://spdx.dev/)(SPDX)[开放链规范](https://www.openchainproject.org/news/2019/04/26/openchain-specification-2-0-out-now)和其他标准描述的 SBOMs，软件帮助将组件问题减少到更易于管理的水平。

与其他领域一样，基于标准的解决方案只有在遵守标准的情况下才能解决问题。EO14028 的大部分影响与政府运作中对 SBOMs 的要求有关。

惠勒指出，在一个层面上，将 SPDX 作为 SBOM 标准发布是“完全不相关的”:希望遵守的个人和组织早在像发布这样的官方里程碑之前就已经知道该标准，而选择忽略该标准的组织可以继续忽略它，无论它变得多么“官方”。真正重要的是标准的使用，而不仅仅是正式出版。

然而，让人们同意使用 SBOMs 的格式是一个艰难的挑战。现在，SPDX 格式[已经被 ISO 完全认可为 SBOM 文档](https://www.iso.org/standard/81870.html)的格式，这赋予了它在这个领域更大的可信度，所以 Wheeler 和其他人认为应该庆祝一下。

Linux 基金会已经在它的一些项目中使用 SPDX，例如 T2 泽法 T3 实时操作系统，SPDX T4 SBOM T5 现在已经内置到它的 T6 西方 T7 元命令行工具中。此外， [Yocto 项目](https://www.yoctoproject.org/)，一个来自用于定制系统实现的源代码 Linux 发行版的构建，正在生成 SPDX，作为其整个构建过程的一部分。

## 标准流程

理解标准化是一个艰难的、持续的挑战。接受像 ISO/IEC 5962:2021 这样的严格标准通常需要至少三年的时间。

标准组织最初关注的是基本的材料要求，如螺栓的尺寸和安全设备的材料。最终，包括药品、电子元件和化学原料在内的高价值商品需要正式的标准化。现在该轮到软件了:软件在日常生活中扮演着如此重要的角色，以至于标准化它是值得的。

从某种意义上说，ISO/IEC 5962:2021 更多的是开始而不是结束:许多其他软件技术可能会遵循正式的标准化道路。

此外，这个出版物有一个战略性的方面，至少对于支持 SPDX 的 SBOM 一代的 LF 来说是这样:Linux 基金会希望建立在 ISO/IEC 5962:2021 经验的基础上。标准化本身可以变得更容易复制和管理。

从计算的角度来看，SPDX 是另一种有趣的专用语言，旨在表达依赖关系、许可证继承和其他特定于领域的细节。

与此同时，最终更重要的是，SPDX 只是谈判法律制度的热身，这使得强大的软件成为可能。从这个角度来看，SPDX 与其说是一个语言和计算的构造，不如说是一个不同形式的人类协作的故事，至少在与软件开发相关的三个层次上:

*   认识到软件存在于其他软件的独特丰富的环境中，并且有无数的依赖关系。据广泛估计，一个新产品中只有 10%的软件是该产品独有的或专有的；任何应用程序的绝大多数功能都存在于现有产品之外的公共库中。创建一个伟大的应用程序不像是在一个孤立的阁楼里进行英勇的艺术创作，而更像是一项宏大的后勤工作。
*   标准化本身是一种独特的人类活动，具有强大的影响力。
*   SPDX 故事的聪明观察者正在吸取教训，以应用于 SVG、5G、笔记本和 NoSQL 等其他需要标准化的软件技术的治理和管理。

LF 和[开源安全基金会](https://openssf.org/) (OpenSSF)对网络安全和软件供应链问题的关注非常及时。这些组织最近参加了在白宫举行的[跨行业虚拟会议，并分享了他们与公共和私营部门政府合作的意图，所有技术和软件项目都由他们支配。](https://www.linuxfoundation.org/press-release/the-openssf-and-the-linux-foundation-address-software-supply-chain-security-challenges-at-white-house-summit/)

SPDX 只是 LF 和 OpenSSF 赞助的几十个项目中的一个，包括最佳实践和培训项目，但是 SPDX 将是一个重要的工具，组织可以使用它来更好地了解他们环境中安装的组件。

为了了解更多关于 SPDX 的信息，Linux 基金会鼓励组织参加其 [SPDX 社区 SBOM 文档节](https://www.linuxfoundation.org/blog/please-join-us-in-the-january-2022-spdx-community-sbom-docfest/)，该活动将于 1 月 27 日虚拟举行。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>