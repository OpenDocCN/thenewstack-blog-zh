# 时间序列数据如何使电信公司保持竞争力

> 原文：<https://thenewstack.io/how-time-series-data-empowers-telcos-to-stay-competitive/>

随着一些新技术和政府行为改变了潜在的商业格局，并为新公司创造了创新和颠覆现有公司的空间，电信行业正在经历快速变化。

在本文中，我们将看看现代[电信](https://www.influxdata.com/solutions/by-industries/telecommunications/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-09_spnsr-ctn_time-series-telco_tns)公司面临的一些最大问题，看看这些问题的一些潜在解决方案，以及这些解决方案在现实世界中是如何被大公司使用的。

## 不断变化的电信格局

企业面临的问题取决于它们处于生命周期的哪个阶段。对于电信领域的老牌公司来说，最大的挑战是必须维护他们的传统基础设施，同时实现现代化并迈向未来。

由于世界各地的许多政府[推动法规](https://www.whitehouse.gov/briefing-room/statements-releases/2021/07/09/fact-sheet-executive-order-on-promoting-competition-in-the-american-economy/)以增加电信行业的竞争，从而为客户提供更好的服务，这一现代化进程变得更加重要。老牌电信公司未来将无法依靠专属客户来获得稳定的收入。他们将需要与新的竞争者正面竞争。

让我们来看看这些公司需要应对的一些最大挑战:

*   **可靠性比以往任何时候都重要**:大量的人仍然远程工作，需要可靠的互联网来提高工作效率。这种可靠性将需要更智能的网络，通过更好的监控来快速发现问题，并通过自动化来解决这些问题。
*   越来越多的设备产生越来越多的数据:需要更多的硬件来应对越来越多的人接入互联网。这意味着会产生更多的数据来监控所有这些设备，这可能会对存储和分析数据的传统工具构成挑战。
*   **边缘计算的兴起**:消费者想要更低的延迟和更好的性能。不同形式的边缘计算正在兴起，以帮助实现这一目标。但是边缘计算给网络和软件架构带来了更大的复杂性，需要考虑这一点以保持可靠性。
*   **支持传统硬件**:处理通过不同协议通信的不同硬件，在某些情况下使用特定于供应商的工具会降低公司的速度。
*   颠覆性技术:像 Starlink 这样的新技术让公司更容易否定老牌公司的基础设施优势。[例如，T-Mobile](https://www.t-mobile.com/news/un-carrier/t-mobile-takes-coverage-above-and-beyond-with-spacex) 最近与 Starlink 合作，为以前由于成本原因无法接入的地区的人们提供蜂窝网络接入。5G 是另一项新技术，由于推出和管理所有新的必需硬件的复杂性，它将对电信公司产生重大影响。
*   **安全**:保护这些网络比以往任何时候都更加重要。似乎每周我们都会了解到新的重大安全漏洞。能够实时可靠地监控网络以检测潜在的安全漏洞至关重要。

## 时间序列数据库如何帮助解决这些问题

上面讨论的许多问题构成了与[时间序列数据](https://www.influxdata.com/what-is-time-series-data/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-09_spnsr-ctn_time-series-telco_tns)相关的问题。监控应用、异常检测、网络安全和跟踪网络可靠性——所有这些都依赖于不同形式的时间序列数据。拥有一个专门的工具来存储和分析这些数据是让电信公司更容易面对挑战的一种方式。让我们看看其中的一些问题，以及现实世界中的公司是如何使用时间序列数据库来解决这些问题的。

### 性能、可扩展性和可靠性

对于电信公司来说，[时间序列数据库](https://www.influxdata.com/time-series-database/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-09_spnsr-ctn_time-series-telco_tns) (TSDB)最基本的好处是能够更有效地存储和查询他们的数据。随着生成数据的设备数量的快速增加，为了提供更可靠的服务，公司需要更精细的粒度，例如能够每秒而不是每分钟收集[指标](https://thenewstack.io/what-is-the-difference-between-metrics-and-events/)。

[例如，思科](https://www.influxdata.com/customer/cisco/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-09_spnsr-ctn_time-series-telco_tns)使用 InfluxDB 监控其内部 SaaS 解决方案，并通过根据正常运行时间、加载速度和可用性等提供警报，为最终用户提供实时监控。思科还使用 InfluxDB 来监控其年度思科直播会议的网络基础设施，以确保现场用户能够稳定地访问互联网，虚拟与会者能够获得可靠的视频流。

Vonage 是另一家使用时间序列数据库提供可靠服务的公司。Vonage 为企业客户提供呼叫中心解决方案，保证 99.999%的正常运行时间。为了确保达到这个数字，它依赖 InfluxDB 来确保对其基础架构的实时可见性和对其指标的毫秒级解析。如果没有专门设计的数据库来处理这种类型的数据，这种类型的分析将非常具有挑战性。

### 数据集成

[Network to Code](https://www.influxdata.com/customer/network-to-code/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-09_spnsr-ctn_time-series-telco_tns) 与试图实现网络基础设施现代化的企业客户合作。其中很大一部分是获得对基础设施的可见性，这在处理许多不同的特定于供应商的硬件和网络协议时是一个挑战。它严重依赖 Telegraf 以最小的努力转换和存储这些数据。许多时间序列数据库还将提供额外的[本地集成](https://www.influxdata.com/products/data-collection/cloud-native/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-09_spnsr-ctn_time-series-telco_tns)，用于获取数据，而无需处理外部服务或编写定制代码。

### 自动化

为了维护客户的高服务级别协议(SLA)，自动化是强制性的。在许多情况下，人类根本无法足够快速地做出反应，尤其是当问题在巨大的网络中变得复杂时。

[Comcast](https://www.influxdata.com/customer/comcast/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-09_spnsr-ctn_time-series-telco_tns) 使用时间序列数据库来分析其基础设施中的大量性能指标，不仅可以提高其软件的可靠性，还可以根据收集的指标预测硬件需求，从而确定潜在的成本节约。

Red Hat 还能够自动化许多事情，变得更加高效和可靠。Red Hat 的硬件分布在 60 个不同的位置，有超过 1，600 个设备和 14，000 个网络接口。Red Hat 利用时间序列数据库的优势，实现了合规报告、异常检测和容量规划等工作的自动化。

### 安全性

时间序列数据库通常用于网络安全，通过比较近期数据和历史数据来跟踪事件和寻找异常。如果您的时间序列数据库是开源的，您可以通过在本地存储数据来进一步降低安全漏洞的风险，从而避免将敏感数据暴露给潜在的网络风险。对于不太敏感的数据，一些 TSDBs 为您提供了将数据复制到其他存储位置的选项。这为您带来了边缘低延迟处理的优势以及云的可扩展性和可靠性。

## 结论

从技术、业务和监管的角度来看，电信行业正在发生许多变化。至少从技术的角度来看，一些主要问题可以通过使用像时间序列数据库这样的新技术来解决，以使公司更加可靠、高效和多产。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>