# 基于 Rust 的云虚拟机管理程序走向 Linux 基础

> 原文：<https://thenewstack.io/rust-based-cloud-hypervisor-heads-to-linux-foundation/>

[云虚拟机管理程序](https://www.cloudhypervisor.org/)项目已经在 [Linux 基金会](https://training.linuxfoundation.org/training/course-catalog/?utm_content=inline-mention)找到了一个家，将它对基于云的工作负载的虚拟机监控的模块化方法带到了供应商中立的基金会。

云虚拟机管理程序是在虚拟机管理程序创建浪潮中[首次创建的](https://thenewstack.io/intel-releases-cloud-hypervisor-based-on-same-components-as-amazons-firecracker/)，英特尔研究员兼该项目的创始技术发起人[阿尔扬·范·德·Ven](https://www.linkedin.com/in/arjan-van-de-ven-015834)解释道，它与其他类似项目有着共同的根源，但它通过模块化提供了一种既能提供安全性和性能又能提供灵活性的方法。

“在一次会议上，我们一群人坐在一起，我们说，‘看，我们每个人都在做自己的事情，这没有意义。’但是很明显，不会有一个放之四海而皆准的方法——适用于 Lambda 的方法不适用于容器。“这是一个需求的连续统一体，”范德 Ven 说我们必须弄清楚如何共享公共代码，因为你不想重新发明轮子，同时，要灵活，这样你就可以准确地拨入你想要的问题，你的解决方案。这就是我们现在的云虚拟机管理程序。"

## 传统和模块化

云虚拟机管理程序的一个关键原则是其模块化。通过提供最少的组件并让用户选择它们所包含的组件，不仅提供了更好的性能，还提高了安全性。范德 Ven 解释说，不是专门为云计算开发的传统虚拟机管理程序可能会模仿传统硬件，甚至是软盘驱动器之类的东西。默认情况下，云虚拟机管理程序在假设您不需要传统硬件的情况下运行，他说这极大地简化了事情。

“当我们与一些大型云公司交谈时，他们对现有解决方案的最大担忧是这是一个巨大的整体。安全团队很难证明某些部件不是意外使用的。范德 Ven 说:“你可以证明一些东西没有被正常使用，但你不能证明一些东西没有被黑客使用。”。"最安全的代码是甚至不在二进制文件中的代码，对吗？"

虽然模块化减少了攻击面，但这也意味着云虚拟机管理程序速度很快，能够通过直接内核引导在不到 100 毫秒的时间内引导到用户空间，并且在内存方面是轻量级的。这种性能的一部分也可以归功于用来构建它的编程语言:Rust。

云虚拟机管理程序基于 Rust virtual machine manager，或 [rust-vmm](https://github.com/rust-vmm) ，这是一组开源的虚拟机管理程序组件，亚马逊的[鞭炮微型虚拟机就是基于这些组件构建的](https://opensource.com/article/19/3/rust-virtual-machine)。在语言选择方面，范德 Ven 说没有竞争。

## 拉斯特朗

“如果你今天想在这一层寻求安全，Rust 是一种可以使用的语言。就是这样，”范德 Ven 说。“我们研究了 Go，我们研究了 C，Go 级别太高，因为所有这些垃圾收集元素对软件堆栈的这一层都没有吸引力。在这一层，你想离金属更近一点，铁锈具有所有的安全属性。如果你重新开始，正如我们所做的，你会从生锈开始。”

在推进该项目时，范德 Ven 表示，重点将是通过强化和添加[可信域扩展(TDX)](https://www.intel.com/content/www/us/en/developer/articles/technical/intel-trust-domain-extensions.html) ，让云虚拟机管理程序为在生产环境中运行做好准备。除此之外，他说他预计随着更多模块的出现，产品会自然发展，例如人工智能加速器或数据库。

“我可以想象每一个进来的人。这就是它的目标。一旦你进入真正的生产使用，这些东西几乎会自己冒出来，”他说，并指出这就是加入 Linux 基金会的原因。“这就是我们现在去找 Linux 基金会的原因，因为我们正处在一个很明显这正在起作用的阶段。我们希望开始进入更多采用阶段。与供应商驱动相比，保持 Linux 基础中立更有意义。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>