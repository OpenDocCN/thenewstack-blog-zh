# 英特尔 SGX 公司:毕竟不太安全，PIC 泄露

> 原文：<https://thenewstack.io/intel-sgx-not-so-safe-after-all-aepic-leak/>

[英特尔软件保护扩展(SGX)](https://www.intel.com/content/www/us/en/developer/tools/software-guard-extensions/overview.html) 内存加密技术在 2015 年听起来是个不错的主意。这组安全指令将使程序员能够建立受保护的私有内存区域，称为飞地。在其中，数据和代码将根据需要被解密。哦，好吧，这是个不错的主意。六个漏洞，包括一个[幽灵](https://github.com/lsds/spectre-attack-sgx)变异，很快就出现了。而现在，在 [2022 黑帽安全大会](https://www.blackhat.com/us-22/)上，又一个基于 CPU 的安全漏洞被揭开:[？PIC 泄露](https://aepicleak.com/)。

这个由欧洲研究生和一名 [AWS](https://aws.amazon.com/?utm_content=inline-mention) 研究员挖出的是一个[新的英特尔架构 CPU bug，它可以在不使用侧通道的情况下泄漏数据](https://blackhat.com/us-22/briefings/schedule/#architecturally-leaking-data-from-the-microarchitecture-26559)。就一个字，“坏！”

## 受影响的 CPU

根据研究人员的说法，利用他们的发现，[机密可以从大多数第 10、11 和 12 代英特尔 CPU 上的处理器中泄露](https://regmedia.co.uk/2022/08/08/aepicleak_paper.pdf)。这包括 [Sunny Cove 微架构](https://en.wikichip.org/wiki/intel/microarchitectures/sunny_cove)设计，如英特尔第十代 Ice Lake CPUs 其目前的第三代至强可扩展服务器 CPU(Ice Lake SP)；以及新的第 12 代 Alder Lake CPU(Golden Cove)。然而，英特尔声称阿尔德湖 CPU 没有受到影响。

？PIC 泄漏的工作原理是对 L2 与末级缓存之间传输的数据进行采样。这包括来自[超级队列](https://www.intel.com/content/www/us/en/homepage.html?ref=https://www.intel.com/content/www/us/en/develop/documentation/vtune-help/top/reference/cpu-metrics-reference/l3-bound/sq-full.html)的 SGX 飞地数据。攻击者可以锁定使用中的数据，如寄存器值和内存负载，以及静止的数据，如 SGX 飞地数据页。因此，这种端到端攻击可以在几秒钟内从飞地中提取 AES-NI、RSA，甚至 SGX 认证密钥。

与臭名昭著的瞬时执行攻击 [Meltdown 和 Spectre](https://spectreattack.com/) 不同，PIC Leak 是一个架构错误。攻击者可以在不依赖嘈杂的侧信道的情况下获取敏感数据。这使得攻击可能更容易实施。

## 好消息

好消息是，完成这样的攻击需要管理员或 root 权限。此外，在具有虚拟机(VM)的云上，虚拟机管理程序不允许直接访问本地硬件的高级可编程中断控制器(APIC)。因此，基于云的虚拟机被破解的噩梦般的安全案例不会发生。

对于在安全、隔离的环境中使用基于 SGX 的内存加密的系统来说，情况就不同了。至少有两种技术，高速缓存行冻结和飞地震动，可以从[英特尔的 IPP 库](https://www.intel.com/content/www/us/en/developer/tools/oneapi/ipp.html)中抓取 AES-NI 密钥和 RSA 密钥，以及英特尔的 SGX 密封和远程证明密钥。

## 修复问题

英特尔正在努力解决这个问题。首先是[英特尔创建了一个更新的英特尔 SGX 软件开发套件(SDK)](https://www.intel.com/content/www/us/en/developer/articles/technical/software-security-guidance/advisory-guidance/stale-data-read-from-xapic.html) ，帮助降低潜在的风险。[英特尔还建议用户更新至最新固件](https://www.intel.com/content/www/us/en/security-center/advisory/intel-sa-00657.html)。[解决该问题的微码已经可用于 Linux。](https://github.com/intel/Intel-Linux-Processor-Microcode-Data-Files)然而，[可信计算基础(TCB)对？PIC 泄漏](https://www.intel.com/content/www/us/en/developer/articles/technical/software-security-guidance/resources/intel-sgx-software-and-tcb-recovery-guidance.html#intel-sgx-tcb-recovery)的恢复要到 2023 年 3 月 7 日才可用。

这都是好事，但我同意研究人员的观点。“唯一短期缓解 PIC 泄露’的方法是让 APIC·MMIO 失去能力，或者不依赖 SGX。”

虽然它的通用漏洞评分系统(CVSS)得分仅为 6.0，但对于依赖 SGX 来获得安全的人来说，这要糟糕得多。

同样值得指出的是，英特尔已经降低了某些处理器家族的 SGX。这种贬值已经导致了一个意想不到的副作用。英特尔第 11 代和第 12 代 CPU 的消费者用户[无法在 4K 观看 UHD 蓝光内容](https://www.techspot.com/news/93006-intel-sgx-deprecation-impacts-drm-ultra-hd-blu.html)，因为没有 SGX，其数字版权管理(DRM)“保护”将无法工作。没有 SGX，企业软件程序也可能遇到麻烦。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>