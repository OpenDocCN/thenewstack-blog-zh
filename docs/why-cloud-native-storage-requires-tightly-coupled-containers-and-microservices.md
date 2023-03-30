# 为什么云原生存储需要紧密耦合的容器和微服务

> 原文：<https://thenewstack.io/why-cloud-native-storage-requires-tightly-coupled-containers-and-microservices/>

云本地计算基金会赞助了这篇文章。

 [尼尔·皮莱格

Nir 创立了 Reduxio，作为首席技术官，他设计了其突破性的核心技术。作为一名有着 30 多年经验的高技术行业高管和梦想家，他在计算机系统、分布式存储、重复数据删除和加密领域拥有 20 多项美国专利和正在申请的专利。](https://www.linuxfoundation.org/) 

许多研究已经证实了基于云的开发和服务部署在采用容器方面的显著增长。

例如，根据[云本地计算基金会(CNCF)的客户研究](https://www.cncf.io/blog/2018/08/29/cncf-survey-use-of-cloud-native-technologies-in-production-has-grown-over-200-percent/)，73%的被调查客户在生产中运行容器化的应用程序，剩下的 27%计划在未来使用容器。

除了调查数据，以及新闻报道的激增(虽然有些人可能认为 Kubernetes 也产生了相当多的宣传)，因此毫无疑问，容器代表了基础设施虚拟化的下一波浪潮。这是因为容器化的好处是显著的:应用程序的可移植性、易于部署和配置、更好的可伸缩性、基础设施的弹性、更高的生产率、持续的集成和更有效的资源利用。

与此同时，应用架构也在不断发展，从几十年前的面向服务架构(SOA)发展到微服务架构。借助微服务架构，应用程序被构建为服务套件，这些服务套件使用定义明确的接口相互通信。每个微服务都可以独立部署和扩展。基于微服务的应用程序在设计时考虑了分散治理、分散数据管理、基础设施自动化、故障设计和可扩展性。

微服务架构和容器紧密联系在一起也不是巧合，因为容器化在不同的微服务之间提供了明显的自然界限。同时，使用容器并不意味着一个应用有微服务架构；单片应用程序*可以*容器化，容器变成单片*——或者单个逻辑可执行文件。*

 *整体式容器化方法的一个缺点是改变应用程序组件的周期——对应用程序的一小部分进行更改需要重新构建和重新部署整个整体。随着时间的推移，通常很难在整体模型中保持良好的模块化结构，如果应用程序的一部分需要扩展，整个应用程序必须扩展，这是低效的。

换句话说，这是不祥之兆:许多企业和开发人员现在已经得出结论，如果不采用微服务架构，就不可能完全实现迁移到容器的好处。采用基于容器化和微服务的应用程序现代化方法的优势是相辅相成的，因此不能满足于折衷的方法，任何支持这种现代化工作的方法都应该是全面的。

## 存储和数据管理

无状态应用程序主要推动了容器的最初采用，通常由微服务组成，这些微服务充当没有容器化的有状态后端的前端。要完全迁移到基于容器的基础设施，需要将无状态和有状态应用程序都实现为容器。为了实现这一点，需要克服容器环境中存储和数据管理的挑战，以便更有效地将有状态应用程序引入容器化的世界。

今天，我们正处于如何存储和管理容器化生产部署中的有状态应用程序的过渡状态。许多企业依赖外部、*孤岛式*存储*设备*，这些设备不是云/容器环境的组成部分，但已经成熟，可提供丰富的数据管理功能，如灾难恢复、数据减少、擦除编码(与镜像相反)和实时分层。

要真正实现容器化的优势，存储基础架构必须与容器化应用的计算端共存于同一环境中。这将大大简化管理，降低成本，提高资源利用率。达到这一点需要一种新的方法。

## 重新思考存储架构

存储架构的圣杯一直是数据和控制平面的分离，以允许数据(数据平面)和元数据(控制平面)流的独立扩展。此外，分隔平面允许控制平面驱动分层、数据移动或快照等数据管理操作，而不会干扰数据路径活动。

迄今为止，存储实施尚未有效分离控制平面和数据平面，繁琐的标准、附加的增量功能和非优化的数据流经常成为障碍。然而，容器和微服务的出现给了存储世界一个抛弃这些并重新开始的机会。

## 进入微服务

微服务架构原则可以很自然地应用于容器本地存储系统设计。例如，控制和数据路径分离非常符合“智能端点，哑管道”微服务设计原则。

基于微服务的设计可能会是什么样子，它可能带来什么好处？

通过分离控制平面和数据平面，基于微服务的容器原生存储解决方案将拥有不同的控制实体(元数据)和数据服务，它们可以独立扩展，并以高度可扩展的分布式方式共同提供服务(IO 和数据管理),非常类似于基于微服务的应用程序。有人可能会说，使用微服务实现存储系统不仅使*能够实现*，而且实际上*迫使*分离控制和数据平面。

*   **容量和性能扩展:**一个基于微服务的容器原生存储系统可以有效地分离数据和控制路径，在多个轴(容量、带宽、IOPs)上提供扩展，从而允许容量和性能根据需要进行扩展。不应低估缩减资源的影响，因为这种水平的基础设施资源灵活性可以允许跨应用程序高效地共享资源；
*   **弹性:**由于微服务可以独立地失效和重启，弹性在这种类型的设计中也得到了提高；
*   **数据管理:**很多数据管理操作都可以由元数据微服务单独进行，不会影响数据平面。在需要操纵数据的其他情况下，元数据和数据上的操作可以分离，以最小化性能问题并提高效率；
*   **存储介质支持:**由于微服务是独立的，并且使用明确定义的协议进行通信，因此这样的系统可以实现多种风格的数据平面微服务，从而驱动多种介质类型；
*   **分层:**元数据微服务可以通过控制这些媒体类型之间的分层操作来提供进一步的功能，从而实现更好的成本结构和最佳的数据布局；
*   **数据移动:**一旦数据和元数据存储由离散的微服务单独维护，多个元数据项可能引用一个公共数据块，文件或卷等对象就可以虚拟化为轻量级的纯元数据对象，这些对象引用一个公共数据池，该公共数据池可能跨越不同的介质类型甚至地理位置。这带来了有趣的数据移动能力，增加了混合云和多云部署的能力；
*   **存储协议和应用支持:**通过将应用前端作为微服务，它也可以以多种方式实施，支持不同的存储访问协议甚至特定于应用的访问，从而提供更大的灵活性。

虽然基于微服务的容器原生存储系统可以提供其支持的应用程序和容器所需的灵活性、可扩展性和可移植性，但还有其他问题需要考虑。例如，对于需要提供性能的分布式系统来说，保持强一致性是非常困难的，而最终的一致性对于许多应用程序来说是不可选择的。虽然这是一个困难的挑战，但与其他问题一起解决并非不可能，这不应阻碍对基于微服务的架构的追求。

## **结论**

微服务和容器已经发展到为当今的企业提供重要价值，随着越来越多的应用程序作为云原生实现，支持这些应用程序的基础架构也需要发展。基于微服务的容器原生存储方法的灵活性和可扩展性有助于创建满足现代应用需求的解决方案，同时还消除了基础架构的约束和限制。为了真正实现容器带来的应用程序现代化的潜力，我们需要消除存储解决方案的限制，采用微服务方法。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>*