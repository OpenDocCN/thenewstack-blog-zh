# 关于滚动发布，Linux 发行版可以教你什么

> 原文：<https://thenewstack.io/linux-distributions-can-teach-rolling-releases/>

开源中的编程实践发生得很快——通常，似乎比其他地方的编程更快。不受经济动机的影响和替代项目的数量使得开源成为几乎任何可以想象的替代方案的试验场。

这一点在软件的发布方式上表现得最为明显，尤其是在 Linux 发行版中，传统的单点发布在某些情况下已经被滚动发布所取代，滚动发布是一种不太正式的策略，它更关注单个包或特性的发布而不是整体。

从 2000 年发布的 Gentoo Linux 开始，其他 Linux 发行版已经采用了滚动发布，最突出的是 T2 的 Arch Linux 和 T4 的 openSUSE。这些发行版所展示的集体经验对于任何软件项目都是值得研究的。

在 Linux 发行版中，滚动发行版已经成为点发行版的替代品。正如您可能知道的，在一个点版本中——也称为标准或通用版本——所有的组件都是同时发布的。主要版本被赋予一个整数(2.0)，小数点后的数字表示次要版本(2.3)。通常，一个点版本有一个粗略的 alpha 版本，然后是一个更完整的 beta 版本。然后，宣布功能冻结，发布候选版本，然后发布正式版本。

在一些开发项目中，比如 Ubuntu 或 Fedora Linux 发行版，点发布会定期进行，通常是每六个月一次，尽管一些项目，比如 Debian，时间间隔会有所不同，甚至长达几年。

相比之下，在滚动发布中，当一个新版本被测试并准备好时，每个包都会被发布。有时，为了稳定起见，核心功能(如操作系统的核心)仍然作为点版本，少数项目(如 openSUSE)同时保持滚动和点版本。其他的，比如 Arch Linux，完全是滚动发布。

## 对速度的需求

为什么要考虑滚动发布？就自由软件而言，答案很简单，需求是存在的。例如，openSUSE 主席 [Richard Brown](https://rootco.de/) 解释说，openSUSE 的 Tumbleweed rolling 版本开始是因为内核开发者 [Greg Kroah-Hartman](http://www.kroah.com/log/) “希望它成为自己的发行版”，并且该版本吸引了其他开发者。

然而，更常见的是，滚动发布的主要原因是一些用户希望最新的上游版本越快越好。“这尤其适用于 GNOME 或 Python 这样的复杂项目，与发行版提供的东西一起使用可能会很棘手，”Linux 开发大师 bartomiej Piotrowski 说。Piotrowski 还指出，“维护负担更轻，因为一周或两周升级一次系统就足够了，而不是每六个月或两年进行一次潜在的麻烦巨大的升级，”这往往意味着随着功能的发展和变化，定制设置的丢失。

Brown 指出，相比之下，一个点发布通常很难与上游项目协调，因为上游项目通常有自己的发布时间表。人们偶尔会努力消除这种缺乏协调的情况，比如 2008 年[马克·舒托沃尔斯](http://www.markshuttleworth.com/) [呼吁上游项目将它们的时间表与下游项目(如 Linux 发行版)相匹配，但这些努力都没有成功。](http://www.markshuttleworth.com/archives/146)

布朗说，这种情况意味着开发项目经常不得不“做出艰难的决定，保留一个[依赖]来促进其他的。”因此，单点版本的用户可能需要等待数月甚至数年才能获得最新的功能，或者最多只能依赖安全性和稳定性不如其他软件全面的更新和第三方来源。

对于私人用户来说，这样的情况是不耐烦的原因，尤其是 Linux 和其他开源软件的用户。然而，正如 openSUSE 的 Douglas DeMaio 指出的，“开发者需要他们的系统尽可能地靠近相关的上游项目。”通常，随着一个点的发布，满足这个需求会“以稳定性为代价”

此外，DeMaio 说，商业开发商可能会发现上游和下游发布时间表的差异会严重影响他们的上市时间。在越来越多的产品依赖于开源项目的时候，这种关注变得越来越重要。

当然，滚动发布并不是满足这些需求的唯一解决方案。所谓的通用包装系统，如 [Flatpak](http://flatpak.org/) 和 [Snaps](https://snapcraft.io/) 正在开发中，以帮助解决这种缺乏协调的问题。然而，这些替代方案仍在开发中，根据布朗的说法，可能需要将测试转移到上游项目和[项目间更大的标准化](https://thenewstack.io/expect-not-expect-linux-universal-packages/)。此外，滚动发布具有已经在使用的优势，有许多模型可供那些希望实现自己的模型的人使用。

## 滚动释放的安全坑洞

然而，如果滚动发布令开发者和高级用户满意，它们可能并不适合所有人。对于运行网络和服务器的系统管理员，或者主要关心生产力的普通用户来说，新版本不如安全性和稳定性重要——传统观点认为点版本最适合同时提供这两者。

[CoreOS](https://github.com/robszumski)的构造产品经理 Rob Szumski 为传统观点辩护说，point 发布了“电力可再生基础设施”。

例如，以 CoreOS 自己的产品为例，Szumski 说，“用户可以在一百台机器上部署[Container Linux](https://coreos.com/os/docs/latest)v 1451 . 2 . 0，并确信每台机器将以相同的方式启动，并且内核、init 系统和容器运行时的版本将相互兼容。”

Szumski 说，因为有了点版本，Container Linux 有了“一个更小的测试矩阵，更容易自动化，并允许在一个整体环境中进行测试”。Chef 或 Puppet 等基础架构管理工具可以通过帮助管理升级和补丁来增强这种控制。

然而，并不是每个人都同意传统的智慧。例如，Piotrowski 认为点发布更安全的想法是“经常重复的错误”。事实上，一个“稳定”的发行版本越老，从新的项目发布版本中反向移植任何安全或常规修复所花费的工作就越多，因为代码可能会从冰点改变很多。滚动发行版只需将包更新到最新版本或轻松应用 Git 的补丁；通常，它们比传统发布的要快。”

尽管如此，即使 Piotrowski 是正确的，滚动发布仍然需要安全措施。在 2016 年 openSUSE 大会上，Brown [做了一个演讲](https://speakerdeck.com/sysrich/opensuse-conference-2017-tumbleweed-a-story-of-love-and-worry)，他在演讲中承认，由于他们对单个包的重视，Linux 发行版作为一个整体可以被忽略，因为包不仅需要工作，还需要与其他包兼容。

作为滚动发布的原则，Brown 提出，“为了快速移动任何东西，你需要快速移动所有东西。”他还警告不要进行他所谓的“被动测试”:将一个包留在版本库的测试分支中，然后如果没有问题就发布它。

正如单点发布使用错误修复和补丁一样，openSUSE 的 Tumbleweed 也使用了许多安全措施。首先，测试 Tumbleweed 的部分过程是通过 [openQA](http://open.qa/) 和[开放构建版本实现自动化的。](http://openbuildservice.org/)同样重要的是，Tumbleweed 默认使用 [Btrfs](https://en.wikipedia.org/wiki/Btrfs) ，这是一个支持快照和回滚到安装的早期版本的文件系统，因此用户可以退出有问题的升级，并继续以他们习惯的方式使用他们的系统。最近，Tumbleweed 还包括了安全位置独立可执行文件(PIE)，它在随机内存地址加载可执行文件，[使它们更难破解](https://lists.opensuse.org/opensuse-project/2017-06/msg00008.html)。

这种保护措施可能有其自身的成本。布朗指出，例如，太多的快照会增加在线存储库的大小，并且在某一点上，支持旧快照可能会限制安装新软件包的能力。

尽管如此，也许除了它们的新颖性，这些安全措施似乎并不比 Debian 或 Ubuntu 等发行版中出现的安全更新和新软件的反向移植更令人担忧。

## 选择滚动释放或点释放

更重要的是，Linux 发行版的例子表明滚动发布是点发布的一个有用的替代品——但是它们并不适合每个用户。不管使用什么样的发布策略，测试和更新仍然需要在开发过程中的某个地方进行。区别在于完成的时间、协调整个发行版的策略以及目标用户。

单个 Linux 发行版通常可以选择一种发布方法而不是另一种，因为替代方法是由一个相关的发布方法提供的。例如，Debian 发布之间的长时间间隔弥补了 Ubuntu 这样的衍生点发布更频繁、更有规律的事实，而且像 [Siduction](http://forum.siduction.org/) 这样的滚动发布也是可用的。

在其他软件项目中，可能需要在一个点和一个滚动发布之间做出选择，特别是如果项目很大的话。然而，即使选择了主要策略，也可能需要其他策略来获得其他策略的一些好处，无论是点发布的回退还是滚动发布的回退。这些经验应该像适用于 Linux 发行版和自由软件一样适用于其他软件。

[CoreOS](https://coreos.com/) 是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>