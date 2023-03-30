# Docker 用户是否正在向 Ansible 迁移，远离木偶和厨师？

> 原文：<https://thenewstack.io/are-docker-users-migrating-to-ansible-and-away-from-puppet-and-chef/>

Docker 是 DevOps 工具运动的自然补充，与 Chef 和 Puppet 等编排技术一起占据了人们的注意力。访问 [Docker 注册表](https://registry.hub.docker.com)并搜索“Chef”图像:在撰写本文时，有 57 个用户创建了 80 个存储库。搜索“Puppet”会得到几乎同样多的结果:41 个用户上传了 57 个存储库。投资界相信这些技术的长期潜力，风投对 Puppet Labs 的投资超过 8500 万美元(最近在 6 月份投资了 4000 万美元)，对 Chef(以前的 OpsCode)的投资接近 6500 万美元。

还有另一个流行的编排工具: [Ansible](http://ansible.com) 。Ansible 自动化技术不同于厨师和木偶。它严格通过 SSH 运行，不需要服务器端守护进程。作为一项技术，Ansible 并不像其他公司那样拥有巨大的支持(Ansible 迄今只筹集了 600 万美元)。但是，根据我对新堆栈的研究，在 DevOps 工具集中，Ansible 是 Docker 贡献者的首选工具。与我们从 Docker 注册表中提取的数字相比，这可以说是未来成功和 Docker 用户相关性的更强有力的指标。

## Docker 社区的新堆栈分析

我带着以下问题开始分析 GitHub 上托管的 Docker 存储库:

1.  Docker 贡献者还对哪些存储库感兴趣？
2.  谁是 Docker 贡献者？

本文详细介绍了第一个问题最有趣的答案:Docker 贡献者还对哪些东西感兴趣？本系列的另一篇文章试图回答第二个问题。

## 利益？

为了回答第一个问题，我们查看了 Docker 存储库的贡献者。成为一名贡献者会让你成为 Docker 社区中一个特别的人。向像 Docker 这样受欢迎的项目贡献代码需要深厚的技术知识，但也需要坚持不懈地坚持过程。一个变更作为一个“拉”请求被提交，然后被审查，评论，可能被接受，但也可能被拒绝，重新开始整个过程。提交不能破坏测试套件。当贡献发生在一个由创业公司管理的开源项目中时，与核心设计原则(可能没有清楚地陈述或像陈述的那样静态)的一致可能是棘手的。最后，对于围绕 Docker 的所有活动和宣传，获得认可仍然需要社区内的一些影响力和认可，并且在像 Docker 这样一个动态和快速增长的社区中，现在建立这种信任更具挑战性。在 Docker 这样的项目中获得代码贡献有很多障碍；设法做出贡献的人是罕见的。

我们查看了 Docker 存储库的贡献者，并问:这些编码人员还在做什么？看待这个问题的一种方法是列出他们曾经工作过的所有其他库，看看它们之间是否有共同点。如果两个存储库都是同一个源存储库的“分支”,则共性可以表明两个开发人员正在为同一个中央存储库做出贡献。要对 GitHub 上的存储库做出贡献，您需要“分叉”该存储库，在您的帐户中创建一个同名的新存储库。这个新的存储库是原始存储库的派生，并与原始存储库联系在一起。一旦您的更改完成并添加到您的存储库中，您就可以将您的更改合并到原始的源存储库中。我们分析了这些开发人员在同一个源代码库中协同工作的情况。

## Ansible 和 Docker:绝配？

我们发现的最有趣的趋势与像 Ansible 这样的 DevOps 工具有关，它被分叉了 26 次。我们证实至少有 23 名开发人员对 Ansible 库做出了贡献。相比之下，有八个开发人员使用 Chef 存储库的分叉；而 Puppet 并没有进入我们共享餐叉的前 15 名。我们还查看了 stargazers:Docker 贡献者列表中的 27 名开发人员“主演”了 Ansible，5 名主演了 Chef repository，Docker 贡献者列表中有 14 人主演了 Puppet。

当您看到 GitHub stargazer 对包含这些技术的代码的每个存储库的计数时，这并不特别令人惊讶。有 6612 个人“主演”这个库(相当于一个书签)。对于[主厨](https://github.com/opscode/chef/stargazers)，只有 2798 个观星者，而[傀儡](https://github.com/puppetlabs/puppet/stargazers)仓库有 2320 个观星者。

> 从 Docker 存储库中加入所有这些数据告诉我们，对于 Docker 超级用户(DevOps 社区的引领者)来说，Ansible 是受欢迎的，并且在不断增长。

## 为什么是 Ansible？

我们想知道 Ansible 为什么受开发人员欢迎。我们询问了来自 ModernRepo.com 的约翰·明尼汉，他对 Ansible 和 Docker 赞不绝口。

使用 Ansible 构建容器是如此的快速、简单+可靠，以至于我无法想象用其他方式来做这件事。这也许是已知的，但是我不能夸大一个过程的价值，不管我在哪里或什么时候运行它，它都会产生相同的结果。我对 Ansible 的最高评价是，它已经消失在背景中——它很好地完成了编排 Docker 的工作，以至于看不见它。

来自 Flux7 的 ater Suleman 在 DockerCon 向我证实了这一点。他说他可以在 Ansible 上放一个新的工程师，几个小时内就能得到结果。使用其他 DevOps 工具，入职可能需要几天时间。

我们就这些问题采访了[大厨](http://getchef.com)(前 OpsCode)。大厨的科林·坎贝尔指出，大厨履行的职责和 Ansible 提供的职责之间有着重要的区别。他说这些工具处理两种责任:创建容器和配置容器。他说 Ansible 在第一点上做得很好，但在第二点上就不行了。据坎贝尔说，厨师擅长配置容器；例如，凭证交换，它应该保持在容器映像之外。Ansible 使用 SSH 来编排映像，SSH 守护进程通常不在容器上运行。Chef 服务器在容器内部运行，并将配置拉入容器，根据 Campbell 的说法，这是处理配置的一种更好的方式。

## 其他观察:不仅仅是针对运营人员

另一个值得注意的趋势是 Mac 开发者有很多活动:其他 Docker 贡献者贡献的下一个最受欢迎的库(除了 Docker 本身和 Docker-registry 库)是 [Homebrew，](http://brew.sh/)Mac OSX 包管理系统。在我们抽样调查的 375 名开发者中，共有 21 人对自制软件做出了贡献。boot2docker 有 13 个分支，boot 2 docker 是使用 VirtualBox 运行 Docker 主机的 OSX 工具。同样，这意味着许多开发人员已经积极地对这些项目进行了代码更改；这些工具在 Docker 社区中的实际使用量可能要大一个数量级。

Docker 的主要承诺之一是，它有助于将复杂的 ops 任务迁移为开发人员可以完成的任务。事实上，许多运行 OSX 的 alpha 开发人员都在使用 Docker，而不仅仅是运行 Linux 的操作人员，这表明 Docker 正在解决开发人员的一个痛点。

## 计算机编程语言

我们也看到了对 Python 使用的明显偏好。docker-py 存储库(用 Python: 14 forks 编写的 docker 的 API 客户端)、django 存储库(用 Python: 11 forks 编写的 web 应用程序框架)和 boto 存储库(与 Amazon Web Services 的 Python 接口:8 forks)是前 15 个共享 forks 列表中的其他存储库。令人惊讶的是，在 top 15 列表中没有看到任何 Go 项目，因为 Docker 是用 Go 编写的，但与 Python 相比，Go 是一种相对较新的语言，而且基于 Python 的项目比基于 Go 的项目更加成熟和活跃。

最有趣也最难量化的趋势之一是 Docker 社区的变化率。当我们在四月份开始做这个分析时，贡献者的数量是 373。在撰写本文时，有 500 个。我认为，随着一个项目越来越受欢迎，贡献的障碍应该会增加，几乎没有新技术比 Docker 现在更受关注。贡献者的快速增加显示了 Docker 的发展速度。它还显示了代码库的质量，因为一个可以扩展并且仍然保持质量水平的项目必须有一个强大的测试套件和持续的集成故事，就像 Docker 一样。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>