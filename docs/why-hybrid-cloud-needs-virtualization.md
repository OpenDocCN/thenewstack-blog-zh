# 为什么混合云需要虚拟化

> 原文：<https://thenewstack.io/why-hybrid-cloud-needs-virtualization/>

[](https://www.linkedin.com/in/charlesschulz/)

 [查尔斯-亨利·舒尔茨

查尔斯-亨利·舒尔茨是战略创新的负责人。他是一名技术专家、网络安全专家、自由软件倡导者，并在开源项目和网络安全政策方面工作了多年。](https://www.linkedin.com/in/charlesschulz/) [](https://www.linkedin.com/in/charlesschulz/)

一切都在向云移动，或者已经向云移动了。说到云，我们指的是科技巨头的数据中心，如 AWS、Azure、Google、Equinix、Oracle 等。更具体地说，云计算最明显的一面是其主要的公共云参与者，也就是所谓的“公共云”虽然这些大型云服务提供商及其大部分云竞争对手的业务量和规模都在增长，但他们的客户依赖这些服务来推动自身业务的方式发生了明显的转变。

随着越来越多的工作负载和数据集被上传到云平台上，从公共云的转移也在发生，并且从[到现在大约四年](https://www.fortinet.com/blog/industry-trends/ihs-markit-fortinet-cloud-report-insights)以来一直引人注目。以下是目前正在发生的事情…

公共云有几个好处，第一个是外包 IT 运营的便利性和随之而来的复杂性。然而，公共云的本质迫使组织适应他们所依赖的云平台，并将他们自己的部分或全部应用程序重写为云原生的。虽然这本身并不是一个坏主意，但它并不能真正解决组织的问题，也不能降低成本。通过将其所有或部分基础架构从公共云移回私有云或内部，甚至选择在几个公共云服务提供商之间分担工作负载，组织能够利用两个世界的优势，同时有效应对每个选项的缺点。这种趋势通常被称为混合云。

为了利用所有这些选项，有必要了解有一些关键工具能够使组织运行并将其系统和应用程序从一种类型的基础架构迁移到另一种类型。

## 基层

跨平台和基础架构移动数据、应用程序和整个系统需要能够对硬件和运行它们的任何软件环境进行抽象。这种能力在虚拟机中很容易找到。通过虚拟机管理程序在裸机基础架构上运行，虚拟机成为完整的虚拟环境，嵌入了从应用程序及其数据到操作系统和网络层的整个系统和平台。

虚拟化可能会被视为过时的技术。然而，虚拟化无处不在，从运行在组织内部服务器上的服务器，一直到公共云。事实上，没有管理程序和虚拟机，云计算就无法运行。

通过在虚拟机中嵌入完整且通常复杂的环境，可以安全地充分利用各种平台，包括公共云和私有云、单个数据中心和本地系统。

## 复杂环境的可移植性

虚拟机的一个主要好处是它们的可移植性。加上适当的管理工具，虚拟机可以非常容易地复制和备份，从而防止数据丢失或系统停机。虚拟化是跨整个基础架构管理整个系统和环境的实用而有效的工具。使这些系统具有可移植性使得它们能够在数据中心和基础设施之间迁移、转移、复制和备份。它使混合云成为可能和理想。

混合云之所以可行，是因为内部基础架构和云之间的二分法不再适用。它之所以有效，还因为它有很多好处。

## 混合云的优势

虽然与更广为人知的术语“云计算”相比，“混合云”这一术语意味着更多的复杂性，但混合云背后的现实表明了许多实际的好处。

已经完全过渡到公共云以满足其全部或大部分 IT 需求的组织通常会指出，一旦迁移完成，各种促销入门费和“宽限期”结束，这种选择的成本就会飙升。通常情况下，公共云并不意味着只为使用的资源付费。定价通常没有那么精确，除了软件许可证和支持合同之外，组织通常不真正了解其实际的 IT 资源消耗。因此，公共云通常会带来隐性成本，尽管其优势显而易见。另一方面，混合云不会抑制隐性成本，因为它允许组织更好地确定其需求和想要在云中使用的实际资源。混合云允许组织将它能够负担得起的工作负载外包到公共云，同时依靠各种其他选项和方案，具体取决于其需求和要求。至少，混合云提供了更清晰的支出内容和支出方式。这最终转化为更好的控制和更低的成本。

转向云服务提供商的组织面临的另一个问题是，他们最终将不得不依赖提供商自己的应用程序和软件堆栈。其原因是，除非他们仅使用一些公共云基础设施来满足相当原始的需求，否则组织将不得不重写自己的应用程序堆栈，或者迁移到适合云服务提供商自己的技术要求的应用程序堆栈。虽然这有时可能是最好的，但如果堆栈被重写或专门适合一个云服务提供商，它可能会促进供应商锁定。在这种情况下，应该问的问题是，旧解决方案退出新应用程序堆栈的成本是多少，退出新应用程序堆栈的成本是多少(如果将来需要的话)？答案可能并不漂亮。

混合云并不排除向新应用程序堆栈的迁移。但它允许组织保持其遗留或当前的应用程序在它希望它们运行的地方运行，而不必以任何方式改变或重写它们。混合云提供了一种有效的方式来控制软件供应商和云服务提供商。

混合云的最后一个但同样重要的好处是更好的安全性。这并不是说公共云本质上不安全，无论如何都不是。但混合云本质上提供的是一个减少的攻击面，通过运行一组不同的托管功能:公共云、私有云、内部。它还使组织能够对其基础架构的敏感部分进行优先级排序，这些部分通常以更严格控制的方式托管(在内部或在私有云基础架构中)，并根据基础架构中发生安全事件的位置来管理不同的防御措施和对策。在网络攻击的数量和严重性都在上升的时代，这是一个至关重要的优势。

混合云不是公共云的对立面，也不是内部运行的 IT 基础架构的对立面。它试图利用所有可能的场景，而虚拟化是实现这一点的一个关键工具。因此，从虚拟机管理程序到管理和备份工具，选择正确的虚拟化体系是一个非常重要的选择。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>