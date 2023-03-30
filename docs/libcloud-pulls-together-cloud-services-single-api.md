# Libcloud 将云服务整合在一个 API 下

> 原文：<https://thenewstack.io/libcloud-pulls-together-cloud-services-single-api/>

云服务互操作性库 Apache Libcloud 已经准备就绪。开源包已经发布了 1.0 版本。

该库结合了来自 50 多家云提供商的信息，并使用单个 Python API 来管理多个云环境和自动化服务器部署。

系统管理软件提供商 [SaltStack 的首席技术官](https://saltstack.com/about/) [Thomas Hatch](https://twitter.com/thatch45) 表示:“Apache Libcloud 已经成功创建了一个最稳定、最可用的 API 来管理云环境，如果没有它，几乎不可能从 SaltStack Cloud 创建云业务流程。

LibCloud 最初创建于 2009 年的 Cloudkick，捐赠给了 Apache 孵化器，并于 2011 年成为 Apache 软件基金会的顶级项目。

它现在支持超过 50 家供应商，包括亚马逊网络服务、Apache CloudStack、谷歌云平台、微软 Azure、OpenStack 和 VMware。

“当我们第一次组建 Apache Libcloud 时，为云提供商创建标准 API 规范的尝试失败了很多，”该项目的原始贡献者之一 Apache Libcloud 的副总裁[tomamuraus](https://github.com/Kami)说。

他们从 IaaS 开始工作，支持托管 KVM、VMware 或 XenServer 虚拟机。该项目后来承担了 DNS、负载平衡、存储和备份等问题。

它现在有六个主要的 API，涵盖计算、存储、DNS、容器和备份，尽管它警告说容器 API 和备份驱动程序只是实验性的。支持 [Python 2.5、Python 2.6、Python 2.7、PyPy 和 Python 3](https://libcloud.apache.org/about.html#supported-python-versions) 。对 Python 2.4 的支持已经取消。

1.0 版本引入了两种新的驱动程序类型，容器即服务和备份即服务，并带有完整的[变更日志](https://libcloud.readthedocs.io/en/latest/changelog.html)。

它提供了一个简单的 API 抽象来跨私有云和公共云部署 Docker 容器。

它支持容器即服务(CaaS)提供商，包括 Docker 的、亚马逊 EC2 容器服务(ECS)、谷歌云容器引擎(GKE)以及 Kubernetes 和 Docker 的本地选项。

Muraus 表示，学术和非营利组织一直希望使用 Libcloud 来利用免费或低成本的云，但仍与公共云兼容，以供商业采用。

云提供商也使用 Libcloud 来实现多云集成，并支持直接集成到 API 中。

它是 [Rackspace 云监控 API](https://github.com/racker/rackspace-monitoring) 库的基础；[发电厂乐团](https://github.com/jokull/kraftwerk)服务管理工具将其作为命令行工具的一部分，用于部署和调试云服务器，基础设施管理平台 [mist.io](https://github.com/mistio/mist.io) 在其托管服务中使用，从任何 web 设备管理和监控跨多个云的服务器。

Linux 基金会合作项目[Cloud Native Computing Foundation](https://cncf.io/)(CNCF)，也在接受挑战[让各种云技术](https://thenewstack.io/cloud-native-computing-foundation-seeks-clarity-world-container-confusion/)协同工作。

[Cloudsoft](https://cloudsoft.io/) 和 [InContinuum](http://www.incontinuum.com/) 的高管最近也与新的堆栈谈论了他们试图减轻[管理多平台环境](https://thenewstack.io/cloudsoft-incontinuum-set-controller-fully-fungible-cloud/)的痛苦。

[云软](https://cloudsoft.io/)和 [Docker](https://www.mirantis.com/software/docker/kubernetes/) 是新栈的赞助商。

特征图片:[暴风雨奏鸣曲](https://www.flickr.com/photos/kansasphoto/9189952695/in/photolist-f15ULg-d6Mdzh-otFhQh-d6Me59-avtPQq-nLgYf8-4zfoaJ-d6Mex1-eAh3rs-7iQrkR-9yMcHL-9Lz3iv-o12dtU-ag8rub-bvSFVm-dkn7At-qjgdsk-cpG6Wb-5xFtH9-2EJ7MC-9yzGqf-ck3Th1-a477YA-uzC2e2-5PRf57-7Juw58-dNjxNt-dNjxZV-rAAUfR-dNjxFB-on3FaD-cRxDQf-dNjw52-dNjxX8-6EdbJf-aovATQ-6bBPSV-eQywMW-cNRNo1-5F1jYi-9q46AT-ekg8wQ-7GpK16-4XHdXb-a7n55M-4xXFcT-fFafEn-d2aojW-4TEu99-eQn916)作者[帕特里克爱默生](https://www.flickr.com/photos/kansasphoto/)，授权**CC BY-SA 2.0T27。**

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>