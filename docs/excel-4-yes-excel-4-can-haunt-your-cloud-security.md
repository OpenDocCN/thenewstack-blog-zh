# Excel 4，是的，Excel 4，会困扰您的云安全

> 原文：<https://thenewstack.io/excel-4-yes-excel-4-can-haunt-your-cloud-security/>

如果你认为现在的 Windows 软件安全性很差，那么你就错过了动态数据交换(DDE)、对象链接和嵌入(OLE)以及 Office 宏安全漏洞的“好时光”。虽然 DDE 和 OLE 现在只不过是头发花白的 Windows 开发人员的噩梦之源，但 Windows 软件宏的安全漏洞仍然存在。

真的吗？说真的。

[Giovanni Vigna，](https://www.linkedin.com/in/giovanni-vigna-7881542/) [VMware](https://www.vmware.com/) 网络和安全业务部门(NSBU)的威胁情报高级主管，在[黑帽 2021](https://www.blackhat.com/us-21/) 的一场展示 Excel 4 宏如何继续造成今天的浩劫的演讲中指出了这一可悲的事实。

这不仅仅是理论上的攻击。乌克兰最近指控俄罗斯间谍将带有恶意宏的文件上传到乌克兰政府文件共享网站。2020 年，微软[警告带有恶意宏](https://www.zdnet.com/article/microsoft-beware-this-massive-phishing-campaign-using-malicious-excel-macros-to-hack-pcs/)的 Excel 4 文件的钓鱼邮件。

一个可以追溯到 1992 年的电子表格程序怎么可能在 2021 年造成大混乱？简单。虽然微软已经通过调用 Office 365 的[反恶意软件扫描接口(AMSI)](https://docs.microsoft.com/en-us/windows/win32/amsi/antimalware-scan-interface-portal) 阻止了 Azure 云上的 Visual Basic for Applications (VBA)宏恶意软件，但直到最近，它还没有对用 Excel 的古董 XLM 宏语言编写的攻击采取任何措施。

技术债务有各种有趣的方式回来踢你的安全屁股。

虽然你可能没有听说过 XLM，但自从 VBA 在 1993 年取代了它，一些用户仍然使用它，所以它在当代版本的 Excel 中仍然受支持。

因此，正如微软解释的那样，“虽然比 VBA 更初级，但 XLM 足够强大，可以提供与操作系统的互操作性，许多组织和用户继续出于合法目的使用它的功能。网络罪犯知道这一点，他们越来越频繁地滥用 XLM 宏来调用 Win32 APIs 和运行 shell 命令。”你会在今天的程序中发现它被用于攻击，如 [Gozi](https://www.secureworks.com/research/gozi) 、 [Trickbot](https://www.cisecurity.org/blog/trickbot-not-your-average-hat-trick-a-malware-with-multiple-hats/) 、 [Ursnif](https://success.trendmicro.com/solution/000283513) 和 [Zloader](https://www.proofpoint.com/us/blog/threat-insight/zloader-loads-again-new-zloader-variant-returns) 。

你看，当 XLM 第一次被用于攻击时，微软最初没有说的是，XLM 实际上远比 VBA 宏更危险。后者只能影响电子表格中发生的事情。然而，XLM 写于一个更天真的时代，拥有对操作系统的完全访问权。而且，一旦它到达 Windows 虚拟机或容器，就可能对操作系统实例造成严重破坏，可以想象，托管它们的云也会受到严重破坏。正如 Vigna 所说，“他们可以启动程序，可以使用 PowerShell 执行命令，可以访问 Windows API。”

或者，正如他们可能会说的，如果这是 60 年代科幻/恐怖节目的一集，外部界限，“我们将控制水平。我们将控制垂直。”

吓人？当然，但是发现宏观攻击有多难？这比你想象的要难。Vigna 解释说，XLM 使创建危险但混乱的代码变得容易。

它始于琐碎的混淆方法。例如，代码被写在各处，用白色字体写在白色背景上。孩子的东西。但是，后来的版本开始使用更复杂的方法，比如通过使用 VeryHidden 标志而不是 Hidden 来隐藏。用户不能从 Excel 中取消隐藏一个非常隐藏的标志。你必须用 VBA 脚本发现隐藏的数据，甚至求助于十六进制编辑器。有多少 Excel 用户会知道什么是十六进制编辑器，更不用说使用它了？

雪上加霜的是，Excel 4 没有区分代码和数据。所以，是的，看起来像数据的东西可以作为代码来执行。情况变得更糟。Vigna 补充道“攻击者可以一次一个字符地构建真正的有效载荷。他们可能会添加一个时间相关性，使当前日期成为代码的解密密钥。在错误的日子里，你只会看到胡言乱语。”正如 VMware 安全研究员 [Stefano Ortolani](https://www.linkedin.com/in/stefanoortolani/?originalSubdomain=uk) 所补充的，Excel 4.0 宏“易于使用，但也易于复杂化。”

你觉得呢？

所以，用传统的静态扫描方法寻找这些漏洞就到此为止了。为了打击利用这些安全漏洞的黑客，VMware 现在提供了 AMSI Excel 4.0 宏预防的[炭黑云支持。这使您可以针对典型的 Excel 4.0 宏技术测试您的 Excel 保护。](https://github.com/carbonblack/excel4-tests#carbon-black-tau-excel-4-macro-analysis)

然而，这还不够。因此，VMware 使我们能够使用[符号执行](https://link.springer.com/chapter/10.1007%2F978-3-540-78800-3_28)来检测 Excel 4 宏。符号执行是一种程序分析技术，其中抽象，也称为符号输入值，被提供给程序。它不是运行 XLS 文件，而是分析并解释所有指令，然后执行 Excel 采用的所有不同路径，作为对输入值的一组约束。这使得自动获得到达特定点所需的输入成为可能。换句话说，它消除了可疑 Excel 文件中的数据和函数的模糊性。

幸运的是，这比使用[sym excel](https://www.blackhat.com/us-21/briefings/schedule/#symbexcel-bringing-the-power-of-symbolic-execution-to-the-fight-against-malicious-excel-4-macros-22893)解释起来容易。这是 VMware 的 Excel 4 宏的符号执行器。这个 Python 程序仍在开发中，它可以展示高度混乱和难以理解的代码背后的东西。

然而，这不会是灵丹妙药。正如 VMware 所解释的那样，Excel 4 宏是一种持续发展的威胁，仍然难以准确分析和检测。虽然 Symbexcel 允许 VMware 分析否则无法具体消除混淆的样本，但仍有许多工作要做。

那么，你能做什么？好吧，和你的安全人员谈谈，改进他们对你的员工的网络钓鱼培训。不管一个 Excel 文件可能多么无害，除非你确切地知道是谁发送的，他们为什么发送它，以及它有什么作用，把所有这样的文件当作带有炭疽热的文件来处理。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>