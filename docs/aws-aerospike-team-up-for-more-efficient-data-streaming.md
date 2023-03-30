# AWS 和 Aerospike 携手实现更高效的数据流

> 原文：<https://thenewstack.io/aws-aerospike-team-up-for-more-efficient-data-streaming/>

在三大公共云提供商中，亚马逊[在碳中和目标和进展方面一直落后于微软和谷歌](https://thenewstack.io/the-state-of-sustainable-architecture-practices-in-2022/)。但该公司最近努力在可持续性方面赶上竞争对手。

在数据平台公司的用户大会[Aerospike’s Summit 2022](https://aerospike.com/summit/summit22/)上，[亚马逊网络服务(AWS)](https://aws.amazon.com/?utm_content=inline-mention) 和 [Aerospike](https://aerospike.com?utm_content=inline-mention) 宣布即将在 Graviton 上发布 Aerospike，这是两家公司之间的合作，声称它可以帮助亚马逊实现其环境目标。

Aerospike 的创始人兼首席技术官[Srini Srinivasan](https://www.youtube.com/watch?v=zf26H24-3tM&feature=emb_imp_woyt)上周三在 2022 年 Aerospike 峰会的合作伙伴会议上表示:“Aerospike 带来的[服务器占用空间的大幅减少](https://thenewstack.io/latest-aerospike-update-supports-large-scale-data-models/)进一步得到了运行在 Graviton 上的 Aerospike 的推动。

据 Srinivasan 称，Aerospike 计划在 Graviton 上制造 Aerospike，这是其实时数据流平台的集成，运行在 AWS 最新版本的处理器上，将于今年下半年与 AWS 合作上市。

当亚马逊在 2019 年与环境倡导组织[全球乐观主义](https://www.globaloptimism.com)共同创立[气候承诺](https://sustainability.aboutamazon.com/about/the-climate-pledge)时，它将自己定位为应对气候变化的领导者。第二年，该公司报告称，它已成为全球最大的可再生能源企业购买者。

AWS EC2 首席产品管理官[阿米特·沙阿](https://www.linkedin.com/in/amit-shah-4326986/)在 [Aerospike Summit 2022](https://aerospike.com/summit/summit22/) 的合作伙伴会议上表示:“我们有一个长期承诺，即到 2040 年我们的业务实现净零碳，这比巴黎协议提前了 10 年。

Srinivasan 说，随着 Graviton 上的 Aerospike 在今年晚些时候广泛上市，“你将获得可持续性，这将有助于我们继续取得进展，以达到净零目标。”

根据环保组织新气候研究所和碳市场观察的一份报告，亚马逊减少用电排放的努力似乎是全面的，[。但该报告警告称，亚马逊的净零碳承诺仍然缺乏证据，因为该公司没有明确的减排目标。](https://newclimate.org/2022/02/07/corporate-climate-responsibility-monitor-2022/)

[亚马逊自己报告称，2019 年至 2020 年，其碳排放量增加了 19%](https://sustainability.aboutamazon.com/environment/sustainable-operations/carbon-footprint),但该公司也表示，其碳强度，即每赚一美元所排放的碳量，在 2020 年提高了 16%。

## Graviton3:提高了效率和性能

根据 Shah 的说法，AWS Graviton2 处理器的性能功耗比是 AWS 中其他处理器的 3.5 倍，新的 AWS Graviton3 处理器的能效比上一版本高 60%。

Srinivasan 说，Aerospike 在实验室测试中发现，在 Graviton 上运行的 Aerospike 的性价比比在其他处理器上运行的 Aerospike 高 40%至 60%。

根据软件公司 Cribl 的一项研究，当 CPU 利用率达到最大值时，[AWS 的 Graviton2 处理器比英特尔 m5zn 和 AMD c5a 实例类型具有更好的性价比，但这种优势只有在 CPU 利用率超过 70%时才显而易见。](https://cribl.io/blog/comparing-intel-amd-and-graviton2/)

## 降低服务器使用率

Srinivasan 说，Aerospike 去年与 AWS 和英特尔合作，展示了他们在云上的效率。

“我们能够显示仅在 20 个节点上每秒运行数百万个事务，”他说。“从那时起，有更多的新实例正在酝酿或已经发布，所有这些都将增加 Aerospike 在 AWS 上的可持续性。”

他说，Aerospike 降低的服务器需求将有助于 AWS 实现其碳排放目标。

根据 Aerospike 委托 Forrester 进行的一项研究，使用 Aerospike 平台时，一家公司的服务器需求[可以在三年内减少 80%。更少的服务器意味着更少的电力需求和更少的碳排放。](https://thenewstack.io/latest-aerospike-update-supports-large-scale-data-models/)

## 处理任务关键型工作负载

Srinivasan 说，当你有很多服务器时，就很难产生可预测的延迟，他的公司的客户包括 PayPal 和 Nielsen。

“Aerospike 的重要之处之一是实时访问更多数据，”他说。

据 Srinivasan 称，由于 Aerospike 的混合内存架构，一家未透露姓名的欺诈检测公司能够将其服务器数量从 360 台服务器减少到仅 20 台。

“在这种特殊的使用情况下，它能够提供更可预测的服务级别协议，因此他们可以更有效地实时防止欺诈，”他说。

任务关键型工作负载依赖于即时可访问性，任何停机都会严重影响企业运营。AWS 的 Shah 说，与工作负载相关的所有数据都需要全天候可用，否则会对用户产生重大影响。

“当我谈到实质性影响时，这意味着要么我们无法满足我们已经提供的客户服务水平协议，要么存在重大的业务影响，导致每分钟数千美元的损失，”他说。

Shah 说，AWS 与 Aerospike 的合作有助于两家公司更好地服务于需要最快性能的客户，并对 AWS 的最新存储产品产生了影响。

“由于与 Aerospike 的更紧密合作，我们定制了我们的 [AWS Nitro SSD](https://thenewstack.io/aws-pushes-forward-its-custom-chip-efforts-with-graviton3/) ，以提供 60%的低延迟和高达 75%的低延迟可变性，”他说。

您可以在此观看 Aerospike Summit 2022 的完整合作伙伴演示:

[https://www.youtube.com/embed/zf26H24-3tM](https://www.youtube.com/embed/zf26H24-3tM)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>