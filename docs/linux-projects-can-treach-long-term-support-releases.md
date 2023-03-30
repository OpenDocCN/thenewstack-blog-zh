# 关于 Linux 长期支持版本的所有事实

> 原文：<https://thenewstack.io/linux-projects-can-treach-long-term-support-releases/>

长期支持(LTS) [版本](https://www.kernel.org/category/releases.html)和软件一样古老。然而，Ubuntu 背后的公司 Canonical 是第一个使用术语 T3 的 T2，现在其他开源项目，包括 Linux 内核和许多发行版，区分了 LTS、常规和 T4 滚动版本 T5，每一个都有不同的优势，吸引不同类别的用户。

许多用户满足于每 6 到 18 个月发布一次。其他需要最新版本的人更喜欢滚动发布，即每个包在准备好的时候都会更新。相比之下，顾名思义，LTS 版本的支持时间更长，通常为 2 到 5 年，尽管 Canonical 也提供两年的扩展安全维护付费服务。

LTS 版本在指定的支持期限内得到安全更新、错误修复、反向端口和新设备驱动程序的支持，就像常规版本一样，尽管在 Debian 等一些项目中，它们没有点版本，这意味着应用修复的方式和时间可能与常规版本不同。同样，LTS 版本可能只支持常规版本支持的最流行的硬件架构。

LTS 版本尤其适合商业产品，因为它们的生命周期通常更短。Debian LTS 发布版的工作人员 Roberto C. Sánchez 给出了 LTS 发布版可能更好的其他场景:“可能需要继续使用旧版本的关键软件包，以便有时间移植依赖于旧底层组件的关键任务系统。或者在一个特定的环境中需要升级的系统的数量和规模可能非常大，以至于需要额外的时间来计划和完全部署一个更新，就像从一个 Debian 版本转移到下一个版本一样。”

此外，LTS 发行版通常是 Ubuntu 衍生的发行版的基础，如 Trisquel GNU/Linux，因为它们使得维护量对于一小部分贡献者来说是可管理的。Linux Mint[的 Clément Lefèbvre 说:“通过迁移到 LTS，我认为我们使 Linux Mint 作为一个操作系统更加稳定，这使我们能够生产更好的质量，并且比以前更加专注于开发。如果我们没有做出那样的选择，我不确定我们在开发方面会不会如此雄心勃勃或要求苛刻。”](https://www.linuxmint.com/)

在 Debian 的例子中，两个版本之间的长时间间隔和旧版本被替换后一年的支持可能会使 LTS 版本显得多余。然而出于实际原因，赞助商的兴趣导致了 Debian LTS 的出现。在查看 Debian LTS 赞助商的名单时，raphal Hertzog 注意到“其中至少有三家在嵌入式环境中使用 Debian，在这样的设备上进行重大升级确实非常昂贵，而提供向后兼容的安全更新则不成问题。其他人是托管者，他们希望为不想在工作服务器上进行重大更新的用户提供安全更新。”

并非所有项目都包括 LTS 支持。OpenSUSE 保持了一个定期和滚动版本，而 Fedora 对 LTS 版本的需求由 Red Hat Enterprise Linux 和由其衍生的 CentOS 来满足。即便如此，Fedora 负责人马修·米勒(Matthew Miller)指出，一些用户要求发布既 LTS 又滚动的版本，尽管这两种策略是相反的。

事实上，如果你自己不是 LTS 的用户，你可能会对这么多人使用这些版本感到惊讶。根据 Canonical Ubuntu 产品和战略主管 Dustin Kirkland 的说法，94%的 Ubuntu 桌面和服务器使用 LTS 版本。同样，维护 [LTS Linux 内核](https://www.kernel.org/category/releases.html)的 Greg Kroah-Hartman 指出，这些内核被用在数百万的 Android 设备上。在其他地方，用户数量更少，当一个版本到达生命周期的终点时，用户数量甚至会下降，然而 Debian 开发者[raphal Hertzog](https://twitter.com/raphaelhertzog)估计至少有 25%的用户会一直使用 Debian LTS 版本，直到生命周期的终点。

## LTS 的代价

LTS 版本的生命周期与常规版本的生命周期只是松散地同步。同样重要的是，重点不同。正如 Kirkland 指出的，“在构建 Ubuntu LTS 版本的过程中，我们将注意力转移到更高质量、额外测试、稳定的版本上。我们在开发和集成新功能方面稍微不那么积极，以获得额外的稳定性和质量。”

这种优先级的差异会导致不同的技术决策，以及不同的工作关系。

例如，在一个常规版本中，一个 bug-fix 可能被简单地添加到下一个单点版本或者甚至下一个通用版本中。然而，由于 LTS 版本通常没有点版本，LTS 的维护者必须决定是否发布一个补丁，或者将其作为安全补丁或反向移植。类似地，当前版本的上游包也不能在 LTS 版本中工作。这样的问题以及如何解决它们需要主流和 LTS 维护者之间的协调。

对于一个小的或重点突出的项目，这些额外的考虑可能很容易管理，只需要在不同的优先级上进行快速培训。Kroah-Hartman 说，在 Linux 内核的情况下，额外的努力可能只不过是开发者愿意维护 LTS 版本，以及开发者对贡献包或测试结果感兴趣。

在这些情况下，LTS 支持可能只是维护人员日常工作的一部分。然而，在更大的项目中，LTS 可能会变得更专业。例如，Debian LTS 目前有 18 名时间贡献者，正在为一个全职职位寻找赞助。同样，Kirkland 报告说“我们在 Canonical 有许多专门的工程师维护 Ubuntu LTS 版本——内核、用户空间、错误修复程序和安全修复程序。我们还有一个专门的支持团队，与 Canonical 的商业客户合作。”

对 LTS 版本的一个特别关注是安全补丁。Kirkland 指出了其他 LTS 开发商也提到的几个问题:

*   安全漏洞通常在头部或主干的上游被修复。发行版有责任将这些修补程序反向移植到该软件受支持的旧版本。
*   随着软件的老化，旧版本和头/主干之间的偏差增加了。这使得反向移植修复和测试结果变得更加危险和困难。
*   最终，该软件将寿终正寝，发行版将停止发布安全更新。这些日期已经清楚地公开传达了很多次。

当不再维护 LTS Linux 内核时，用户应该为自己升级，就像他们为任何其他内核升级一样。然而，在其他项目中，升级可以像普通版本一样精细，用垫片来简化过渡，特别是当涉及到技术的重大转变时，例如转移到 [systemd](https://thenewstack.io/systemd-vs-linux-kernel/) 。一旦过渡完成，循环就重新开始。

## 利弊

LTS 版本的一些特征是模糊的。正如 Sánchez 指出的，一些人可能会认为过时的标准可能会在 LTS 继续存在这一事实是一个错误，其他人则认为旧标准的延续意味着 LTS 发布的版本为无论如何都会被使用的软件提供了某种形式的官方支持。

然而，一般来说，LTS 版本的缺点和优点是显而易见的。一方面，“缺点是显而易见的，”勒菲弗尔说。"在一个 LTS 周期的末尾，你基本上距离被认为是新的东西还有好几年."

另一方面，勒菲弗尔说，“非 LTS 周期太快了。每六个月就有一个新的包库，我们不断地追踪 bug，修复新的回归，使软件适应库的变化，基本上产生大量的工作，只是为了保持相同的质量水平，而剩下的时间很少，无法真正改进。通过转移到 LTS，我们在整整两年的时间里专注于相同的开发平台、相同的目标、相同的软件包基础，因此在我们适应它之后，我们有大量的时间投入到开发新功能和改进对用户来说很重要的操作系统方面。

有些人可能会认为，随着集装箱和通用包装等技术的不断发展，LTS 版本可能会变得过时。然而，正如赫佐格所说，“对 LTS 的需求不会消失。它甚至可以被培养。运行仅在特定旧环境中测试的旧软件的愿望不会消失。我们可以把它藏在一个容器里，但旧的基础系统必须保持安全。”从这个角度来看，在未来的几年里，LTS 版本似乎仍将是软件开发的一个主要领域。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>