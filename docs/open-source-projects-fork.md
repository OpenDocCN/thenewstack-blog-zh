# 为什么开源项目会分叉？

> 原文：<https://thenewstack.io/open-source-projects-fork/>

[](https://www.cumulusnetworks.com/)

 [皮特·布拉塔克

皮特·布拉塔克管理积云网络的文档和社区工作。在此之前，他帮助编写了开放计算项目的第一份技术规范，并为脸书开发者平台编写了文档和一些博客文章。一个开放网络和社交网络的粉丝，也喜欢好喝的啤酒和饼干，你可以在 Twitter 和 Instagram @desertmonkey 上关注他。](https://www.cumulusnetworks.com/) [](https://www.cumulusnetworks.com/)

开源软件(OSS)项目的初衷是创造技术，用于技术或全球社区的更大利益。随着项目的成长和成熟，项目的目标或观点可能会出现分歧。在这种时候，项目参与者开始考虑叉子。

分叉一个 OSS 项目通常开始于一个利他的努力，其中一个社区的成员寻找一个不同的路径来改进这个项目。但具有讽刺意味的是，分叉有点像 OSS 中的地铁第三轨:如果你能帮助它，你真的不想碰它。

开源软件开发人员 David A. Wheeler 将分叉比作议会的不信任投票或劳工罢工。这会给相关人员带来很多痛苦。它甚至可以撕裂一个社区。

这里我们也不是在谈论 GitHub 风格的分支，它们实际上是短暂的分支，当有人完成开发一个新功能时，它们要么被拉回上游，要么被简单地删除。我们所说的分叉是指 OSS 社区中的大量开发人员决定从原始项目中分支出来，试图改进它并最终取代它。

那么为什么 OSS 项目会分叉呢？最简单的答案是因为观点不同，这可能是技术性的或个人的，但也有其他原因。研究人员格雷戈里奥·罗伯斯和 T2 赫苏斯·m·冈萨雷斯-巴拉霍纳[在 2012 年发表了一篇名为“软件分叉的综合研究:日期、原因和结果](http://link.springer.com/chapter/10.1007%2F978-3-642-33442-9_1)”的论文，确定了项目分叉的一些关键原因:

*   一些贡献者希望将项目引向一个不同的技术方向。
*   一些原始项目的贡献者觉得他们的反馈没有被听到，维护者在接受补丁方面进展太慢，甚至他们发布得太快——想想去年关于 Docker 和[项目分叉](https://thenewstack.io/docker-fork-talk-split-now-table/)的传言。
*   原来的项目已经放弃了。回到 20 世纪 90 年代，Apache web 服务器项目接管了被放弃的 NCSA HTTPd 项目。
*   商业原因出现了。这种情况发生在公司参与其中，并且想要创建原始软件的付费版本时，反之亦然。
*   法律原因扰乱了社区。一个项目可能会脱离 GPL (GNU 公共许可证)，可能会出现商标纠纷，或者有人可能会改变程序使用加密的方式。
*   个人原因碍事。非技术性质的不可调和的分歧导致各方之间的裂痕，因此项目分叉。

## 一个项目如何分叉？

分叉是如何进行的，有一个非常有序的过程。其他人已经写了文章和学术论文，讨论如何、[为什么](https://www.techrepublic.com/article/why-you-should-fork-your-next-open-source-project/)和[什么时候](https://jamesdixon.wordpress.com/forking-protocol-why-when-and-how-to-fork-an-open-source-project/)你应该分叉一个项目，所以这里我们就不赘述了。然而，应该注意的是，即使它被视为所有其他选项都用尽时的最后手段，分叉通常会产生积极的结果。

## 分叉的最终结果是什么？

那么当一个 OSS 项目分叉时可能会有什么结果呢？Wheeler 和 [Robles 和 gonzález-巴拉霍纳](http://link.springer.com/chapter/10.1007%2F978-3-642-33442-9_1)深入研究了大约 220 个“重大”分叉，确定了这些潜在的结果:

*   原始项目和 fork 都成功。一个显著的例子是 Android 操作系统，亚马逊和其他公司已经从谷歌的原始操作系统中分取了一部分，开发了自己的操作系统。另一个是 BSD 及其衍生项目，如 FreeBSD、NetBSD 和 OpenBSD。这是最常见的结果。
*   分叉合并回原始项目。这种情况很少发生，但并非不可能。你可能还记得 EGCS 从 GCC，GNU 编译器集合中分离出来的时候。分叉是成功的，但是为了避免用户集成新软件的问题，这些变化被合并到原始的 GCC 代码中，并作为新的 GCC 发布。
*   叉子枯萎死亡。当 libc 从 g libc 中分离出来时，glibc 的贡献者深入改进 glibc，以至于它超越了 fork，最终大多数用户停止使用 libc 而支持 glibc。
*   原始项目失败。XFree86 脱离了 GPL 兼容的许可，所以项目分叉，产生了 X.org，它很快被大多数开发者和用户采用。不久之后，XFree86 核心团队解散了，项目开发也停止了。
*   两人都失败了。罗伯斯和冈萨雷斯-巴拉霍纳指出，在他们研究的 220 个重要叉子中，这种情况不到 10%。

## 恰当的例子

以网络路由软件 [Quagga](http://www.nongnu.org/quagga/) 最近的一个分支 [FRRouting 项目](https://frrouting.org/)为例。分叉源于原始 Quagga 项目方向上的典型技术差异，加上等待上游合并的大量且不断增长的补丁。

“我们的工程师已经在上游项目上开发了几十年的改进，”首席技术官、 [Cumulus Networks](https://www.cumulusnetworks.com/) 的联合创始人 [JR Rivers](https://twitter.com/jrcumulus) 说。“我们花了数年时间试图整合这项工作，但由于各种情况，进展缓慢。其他人要么希望获得我们的成果，要么希望在此基础上进行建设，因此我们发现自己陷入了两难境地。”

当团队开始分叉时，他们从一开始就开始以不同的方式做事。据 Cumulus Networks 的工程师和 FRRouting 项目的维护者 Donald Sharp 所说，他们“更关注社区建设，而不是代码工作。”这有助于他们已经有许多新代码等待发布。

因此，随着[代码在](https://github.com/FRRouting/frr)中被检入，社区被组织，新项目[被启动](https://www.linux.com/news/2017/4/welcoming-frrouting-linux-foundation)，团队踏上了一条很少有人走过的路，就像他们之前的所有分叉一样，他们这样做是为了同一个目的:获得一个他们非常了解并充满热情的好产品，并努力把它做得更好。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>