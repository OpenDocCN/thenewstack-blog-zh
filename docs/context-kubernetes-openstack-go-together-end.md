# 背景:Kubernetes、OpenStack 以及 SAP 如何构建自己的容器化平台

> 原文：<https://thenewstack.io/context-kubernetes-openstack-go-together-end/>

去年八月，[SAP 的云架构师 Markus Riedinger](https://www.linkedin.com/in/markus-riedinger-2615aa83) ，向[展示了他和他的团队如何在他们自己的企业中生产出](https://www.youtube.com/watch?v=4gyeixJLabo)自动化、容器化、CI/CD 兼容的 OpenStack。

在这一集的新堆栈内容中，我们将探讨 Kubernetes、OpenStack 以及企业在使用开源软件构建自己的基础设施时所扮演的角色。

[秀 6: Kubernetes 和 OpenStack:谁先上？](https://thenewstack.simplecast.com/episodes/show-6-kubernetes-and-openstack-whos-on-first)

SAP 是如何做到这一点的，并不是通过 OpenStack 组件来部署 Kubernetes，或者将 OpenStack 塞进一个容器。相反，该团队重新设计了 OpenStack 在多个容器之间的分工，就好像它一开始就是这样创建的一样。它有意将控制层和数据层的操作分开，以保持这种划分。作为完成不可变操作的一种方式，它在两个平面上都产生了冗余。

“为了明确区分控制和数据，”Riedinger 告诉与会者，“与控制[路径]相比，允许数据路径有一个独立的服务级别目标，控制[路径]还实施独立的流程和程序来分别扩展控制和数据的每个方面，从而扩展、修复和改进现有模型来运营供应商设备。SAP 是非常典型的组织…没有自主开发的硬件。而且现有的运营模式应该坚持下去，只是修正和扩展。”

非常聪明的是，Riedinger 的团队利用解耦服务的概念，沿着 SDN 风格的控制和数据线路，解开典型企业中所有 OpenStack 组件。这样，基础架构的底层就不再需要考虑应用程序的服务级别是否得到满足。相反，好像 OpenStack 从一开始就被设计为一个 SDN 系统。

SAP 的项目可能不是第一个成功容器化 OpenStack 的项目，但它很可能是第一个完全移植到生产中的项目。

专题图片: [Leslie Hawley](https://www.flickr.com/photos/lah1971/) 的 [Red](https://www.flickr.com/photos/lah1971/7264847926/in/photolist-c4YfbJ-dE41Rf-arUQwV-c6dzyL-cwDWC3-c6dAHm-c6dAh9-cwDY6A-cwE2bd-cwEaw3-cwE175-cwE5CU-cwDZyo-tx3pFQ-sVQZ2P-rZ2Fzk-sDfpNb-rZgjFZ-rZ2Kck-rZ2yMn-tx3ckY-5tFwKC-5B652D-oLUi5t-49qUG-4rMvha-cwEc6f-4CviPC-cwEa5C-6NeZM3-93r3Zv-6C2fEC-ouFvAw-38G8MR-aPrzzD-cpy9sj-38Q9ow-38LGod-cwEeho-cwE37m-7vmtiV-cwE2D1-6buvaL-cwE1Bf-cwEdLW-cwDUMd-cwDTME-cwDX6N-cwDUf5-cwDVmm) 在 [CC BY-ND 2.0](https://creativecommons.org/licenses/by-nd/2.0/) 下获得授权。

播客中提到的 CoreOS 是新堆栈的赞助商。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>