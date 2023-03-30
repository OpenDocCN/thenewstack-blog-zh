# Ansible 进驻 Red Hat，推出无等待调度

> 原文：<https://thenewstack.io/ansible-settles-red-hat-debuts-no-wait-scheduling/>

按照它的时间表，红帽周二发布了一个重新制作的 Ansible 2.0，为 Docker、OpenStack 和 Windows 提供了改进的异常处理和更新的模块。

红帽公司负责工程的高级主管[蒂姆·克莱姆](https://twitter.com/tjcramer)说:“这个版本已经等了很久了。“我们基本上重写了一堆核心引擎。清理 Ansible 并让它赶上人们使用它的目的，从而使它更易于维护和扩展，这涉及到大量的技术债务。”

红帽[在 10 月份以大约 1.5 亿美元收购了自动化和配置框架](https://thenewstack.io/red-hat-ansible-staying-better-together/)。它当时表示，2.0 版本将如期发布。

“我们一直非常小心，也非常清楚我们正在重写核心引擎，所以在 2.0 版本推出时，我们会继续修复 1.9 版本的错误，”Cramer 说。“当人们转换时，我们将保持这两种方式，因为我们不希望每个人一开始就转换。”

最显著的改进之一是，软件现在解除了对如何在系统中推广更新的一些限制。

**"** 传统的执行策略是一种线性策略，因此您需要等待所有主机完成所有任务，然后再继续，因此您需要更新所有这些服务器，然后在它们上面安装一个 web 服务器传统的方法是更新服务器——假设有 10 台服务器，其中 9 台已经更新，第 10 台需要进行一系列更新——您需要等待第 10 台主机完成其任务，然后才能继续下一项任务，”Cramer 解释道。

“我们现在有一种称为自由策略的东西，它允许每个主机尽可能快地处理任务，而不必等待其他主机。因此，现在这 9 台服务器可以立即安装 Web 服务器，第 10 台服务器将按照自己的速度安装。他说:“如果您的数据中心很乱，或者您想在组合中添加一台服务器，而您正等着那台服务器跟上，那么这真的会有助于提高速度。”。

其他改进包括:

*   **改进的错误消息:**“有时候使用剧本，你会以一个错误结束，你不知道发生了什么。他说:“我们已经改进了错误信息，它会显示错误发生的行或列，只是为了在你写的剧本有问题时更容易调试它。”。
*   **任务块:**“这是一种你可以从剧本中分离出一个任务块的方法，你可以用它来捕捉错误并执行一组任务，不管异常是否发生。它有一个 try/except/finally 结构[来自 Python]。这是一种让你非常简洁地尝试一些东西，然后发现其中错误的方式。”
*   **OpenStack、Docker、Windows 的模块** : Ansible 2.0 a 有 200 多个新模块，包括 open stack、Amazon Web Services 和 VMware 环境的新模块或扩展模块。它还对 Docker 模块和新的 Docker 连接插件进行了实质性的改进。大多数新模块都是社区贡献的，然而，Cramer 说，“我们在 Windows 模块上做了大量工作。现在在 Ansible 上有专门的资源。我们看到 Windows 方面有如此多的推动，我们已经投入自己的资源来加快这些模块的速度。”

“我们已经对 2.0 进行了大量的社区测试，所以我们对它非常有信心，”他说。“我们几乎 100%向后兼容——有几件小事，比如 Ansible 中的变量引用直到现在还没有定义。所以我们对它进行了定义和标注。它只是在 1.x 的时间范围内有所变化。如果他们从 1.7 升级到 2.0，他们可能会看到一些细微的差别。”

Ansible 2.0 可以通过 [GitHub](https://github.com/ansible/ansible) 、 [PyPi](https://pypi.python.org/pypi/ansible) 和大多数主流 Linux 发行版的包管理器获得。

Cramer 曾在 Sun Microsystems 和 Hewlett-Packard 经历过收购，他说红帽收购 Ansible 是“令人难以置信的好”

“我们与业务的其他部分没有太多重叠，所以没有争斗。我们来了，这是一个伟大的契合，它填补了他们真正的需要，”他说。“Red Hat 已经加入进来，并试图加速产品的开发。我们正在寻找各种各样的集成，我们正在寻找开源塔，但我们没有任何改变我们做事方式的大任务。在工程方面，他们基本上是将团队扩大了一倍。”

[VMware 和 Docker 集成](http://sdtimes.com/ansible-2-0-adds-better-exception-error-handling/)在未来版本的路线图上。Red Hat 的 Ansible 社区主管 Greg DeKoenigsberg 说，因为有积压，它将重新审查提交模块的审查过程。

已经雇用了一名全职人员来处理网络问题。

DeKoenigsberg 告诉 SDTimes 说:“2.0 出来后不久，我们将讨论网络功能，那里将存在什么模块，以及我们如何认为这可以改变该领域中许多没有机会在网络世界中创建 DevOps-y 进程的人的游戏规则。”

Docker、Red Hat 和 VMware 是新堆栈的赞助商。

专题图片:[马克·钱德勒](https://www.flickr.com/photos/grow_love/)创作的[大理石鲁布·戈德堡](https://www.flickr.com/photos/grow_love/8359280369/in/photolist-dJFuPB-5Aumn-3HruEk-6sjCuP-thSTC9-ukRJR1-3zC5V5-qrz39L-86656v-6agzR3-emeHx4-8aVwbz-8ogC32-sogdHX-s4Yhb6-dEDTg3-7H3xJd-5Xws7b-dovrrt-6n7kLQ-9BBwUY-yJxFX-7H3ycb-byqQ26-4Gu5LM-7TqRQU-7TqRNN-91otqR-64qK1D-64qQqZ-64qNox-64qL6K-64ux4U-64kFk8-64v3bh-64qu4h-64mb4M-4uiXe5-4ueUy2-oPqgd-7H3y4J-WtWcK-LUHvw-LUS7x-7GYCor-aNVUat-e26FZb-7H3x7A-7H3xCh-4fXXtd)，获得 **CC BY-SA 2.0** 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>