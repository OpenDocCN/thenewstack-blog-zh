# 英伟达 GPU 推动 HPE 超级计算机进入亿亿次级

> 原文：<https://thenewstack.io/nvidia-gpus-nudge-hpe-supercomputer-into-the-exascale/>

企业 IT 系统提供商[惠普企业](https://www.hpe.com/us/en/home.html)将开始交付和安装组成北极星的计算组件，北极星是一台大型超级计算机，将位于伊利诺伊州[阿贡国家实验室](https://www.anl.gov/)，作为[人工智能](https://thenewstack.io/what-is-real-artificial-intelligence/) (AI)和该实验室即将推出的 Aurora [exascale](https://en.wikipedia.org/wiki/Exascale_computing) 系统的其他项目的试验台。

一旦北极星在 2022 年初组装并上线，它将提供比目前在阿贡运行的超级计算机多四倍的性能，并以 44 petaFLOPS(每秒 44 万亿次浮点运算)的峰值性能，在每年两次的世界最快超级计算机 500 强名单中排名第九，这是基于 6 月发布的最新名单。

这台超级计算机将包括来自 Nvidia 的 2240 个 A100 张量核心 GPU 加速器，也将基于混合精度计算能力驱动近 1.4 万亿次理论人工智能性能。

Nvidia 技术营销负责人 Dion Harris 在一次关于超级计算机的新闻发布会上说，北极星“将允许(Argonne 的)开发者、他们的应用程序持有者、他们的工程师开始建立大规模加速计算的能力”。“这是一个非常高性能的系统，无论是在人工智能方面，还是在基于基本原理的模拟的经典 FP64 方面。因此，我们预计这将加速他们的核心应用程序，并为他们建立一个令人难以置信的人工智能系统，即使 Aurora 上线也是如此。”

## **即将到来的万亿亿亿次运算**

Aurora 是美国正在建造的三台亿亿亿次超级计算机之一，其他三台是劳伦斯利弗莫尔国家实验室的 El Capitan 和橡树岭国家实验室的 Frontier，预计将在未来一两年内上线。 [Exascale computing](https://www.lanl.gov/projects/exascale-computing-project/index.php) 承诺让研究人员能够运行当前系统无法处理的日益复杂的高性能计算(HPC)工作负载，并帮助被数据和人工智能和[数据分析](https://thenewstack.io/redefine-customer-data-analytics-using-an-open-source-stack/)等新兴工作负载淹没的企业。

包括中国、日本和欧盟在内的其他国家也在建造万亿次超级计算机，它们和美国竞争，看谁能成为万亿次和超级计算的领导者。那些成功的公司将在从科学研究、军事到医疗保健和经济等领域拥有优势。

2019 年年中，美国能源部(DOE)将建造 El Capitan 的 6 亿美元合同授予了长期超级计算机供应商 Cray。该公司已被命名为建设极光和前沿。2019 年 9 月，HPE 以 13 亿美元的价格收购了 Cray，成为系统供应商，此举大大扩展了其在 HPC 的业务。

## **北极星初具规模**

现在该公司正在建造北极星。它将基于 280 个阿波罗 Gen10 Plus 系统，这些系统是为高性能计算和人工智能环境而创建的，并以亿亿亿级时代为目标。这些系统将使用 AMD 的 560 2 ^(nd) 和 3 ^(rd) Gen Epyc 服务器处理器，用于改进建模、模拟和数据密集型工作流，GPU 将帮助推动超级计算机运行人工智能工作负载的能力。

与北极星一样，Aurora 将是一个加速系统，尽管使用英特尔的至强可扩展处理器和芯片制造商即将推出的 Xe-HPC“Ponte Vecchio”GPU。

Polaris 将运行 HPE 的 CrayOS 操作系统，将使用 HPE 为 HPC 和 AI 环境设计的 [Slingshot 以太网](https://www.hpe.com/us/en/compute/hpc/slingshot-interconnect.html)结构——该供应商在收购 Cray 时继承了这一结构——作为高速互联和 HPE 性能集群管理器来监控和管理超级计算机，以确保最佳性能。在存储方面，超级计算机将使用 Eagle 和 Grand，这两个都是 100 Pb 的 Lustre 系统，由能源部科学网站阿贡领导计算设施(ALCF)于去年开发，并由 HPE 的 Cray ClusterStor E1000 平台提供支持。根据 Argonne 的说法，Eagle 系统使科学界内部的数据共享成为可能。

北极星已经被谈论了大约一年，但是 8 月 25 日的公告带来了更多的细节。

“北极星已经做好准备，通过加速人工智能能力的应用，以满足我们用户日益增长的数据和模拟需求，帮助 ALCF 进入计算科学的艾亿级时代，”ALCF 主任迈克尔·帕普卡在一份声明中说。“除了让我们为 Aurora 做好准备之外，北极星还将进一步提供一个平台，对超级计算机和大规模实验设施的集成进行实验……让更多的科学界可以使用 HPC。北极星还将提供更广泛的机会，帮助原型设计和测试 HPC 与实时实验和传感器网络的集成。”

## **加速计算是关键**

英伟达的哈里斯表示，超级计算一直是推动技术在帮助解决一系列挑战方面的界限的驱动力，包括寻找癌症的治疗方法，探索聚变能源和应对气候变化。然而，近年来，在问题规模和数据量不断增长的情况下，摩尔定律的放缓阻碍了研究人员的工作。人工智能进入等式，并被用于许多互联网应用，引起了科学家对如何将该技术用于他们的研究的兴趣。

他说，利用像英伟达这样的 GPU 加速器将有助于提高 Polaris 上运行的此类工作负载的性能。

“当我们谈论这项技术将如何被使用时，看到科学家们现在就可以开始，真的很令人兴奋，”哈里斯说。“一旦我们在明年年初部署该系统，他们将能够开始开发这些应用程序，并将它们移植到加速模型中。他们可以开始利用人工智能来真正构建他们如何看待这种融合 HPC 人工智能模型的能力。然后，他们可以通过利用北极星来开始测试这些理论。”

一旦上线，Polaris 最初将被参与这些计划的研究人员使用，如[能源部的亿亿次计算项目](https://www.exascaleproject.org/)和 ALCF 的 Aurora 早期科学计划，该计划不仅使科学家、工程师和其他用户能够准备在 Aurora 架构和规模的系统上运行的关键应用程序，并为其他生产应用程序准备好库和基础设施，还可以解决当前超级计算机无法解决的项目。

这些项目包括从推进癌症治疗和解决美国能源安全同时减少对气候的影响，到在 [ATLAS 实验](https://en.wikipedia.org/wiki/ATLAS_experiment)中进行粒子碰撞研究，该实验使用了瑞士的[大型强子对撞机](https://home.cern/science/accelerators/large-hadron-collider)粒子加速器。

哈里斯说，在北极星上线的几个月内，它可能会向更广泛的研究社区开放。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>