# 开源构建者:为什么数据科学家喜欢 Matplotlib

> 原文：<https://thenewstack.io/open-source-builders-why-data-scientists-love-matplotlib/>

这是关于开放源码构建者系列的一部分。要获得本系列的其他文章列表，请查看

[the introductory post](https://thenewstack.io/open-source-builders-an-inside-look/)

.

亚马逊网络服务(AWS) 赞助了这篇文章。

 [马特·阿萨伊

Matt 是 AWS 的负责人，参与了开源及其支持的所有领域(云、机器学习、数据基础设施、移动等。)近二十年来，为各种开源公司工作，并定期为 InfoWorld 和 TechRepublic 撰写文章。你可以在推特上关注他(@mjasay)。](https://www.linkedin.com/in/mjasay/) 

无论您使用 TensorFlow 处理多少成千上万的大型数据集，或者您使用 PyTorch 使用 GPU 加速张量计算，在某些时候您都会希望使用跨平台的图表和数字来表示您的结果。为此，您几乎肯定会想要了解 [Matplotlib](https://matplotlib.org/) ，这是一个用于数据可视化的基本 Python 2D 绘图库。尽管 Matplotlib 深受数据科学家的喜爱，但它的根基却是物理科学、海洋学和气候学。数据科学人员后来来了，借用了核心库，并将它们应用于更多的企业用途。

尽管如今基于 Python 的数据科学工具和库不断增多，但多年来，Matplotlib 是用 Python 绘图的唯一方法；并且它仍然是默认的。Matplotlib 开发社区的核心是项目负责人 [Thomas Caswell](https://twitter.com/tacaswell?lang=en) ，他从回答 Matplotlib 关于堆栈溢出的问题，到提交错误修复，再到创作补丁，几乎是偶然找到了领导的道路。

在最近的一次网络会议上，Caswell 向我讲述了他的 Matplotlib 领导之旅，以及他做出贡献的原因。

## 贡献进化

卡斯维尔并不是 Matplotlib 的创始人——这一荣誉属于约翰·亨特，他是 21 世纪初芝加哥大学医学中心的癫痫研究员。亨特厌倦了为获得硬件密钥加密狗而斗争，这种硬件密钥加密狗允许他使用专有软件程序进行皮层脑电图分析。Hunter 首先尝试用 MATLAB 代替这个程序，但发现它不适合他的需要，所以他开始构建后来的 Matplotlib。

在此期间，Caswell 自己也在努力学习与内存管理相关的 MATLAB，并在芝加哥大学寻找继续其学术工作的选择。当他一头扎进 Python 时，他很自然地遇到了 Matplotlib，如前所述，他首先贡献了洞察力，最终贡献了代码。在 2012 年亨特不幸去世后，Mike Droettboom 担任项目领导，在他的指导下，这些代码变得更好。正如卡斯韦尔回忆的那样，“Droettboom 教会了我几乎所有关于编程的知识。”Caswell 与 Droettboom 密切合作，随着时间的推移，成为 Matplotlib 的主要维护者。

*cas well 的 Matplotlib 贡献是如何发展的值得一提，因为这种发展对于那些想要开始为开源项目做贡献的人来说是一个有用的指南。*

Caswell 指出，回答堆栈溢出问题被证明是学习库的一种特殊方式，因为它将你置于一个遇到其他用例的位置。这也是在不接触代码的情况下开始“修复”代码中的错误的理想方法。Caswell 说，最终他获得了提交权，这样他就可以从另一个方向对 bug backlog 施加压力。

同时，Caswell 的经历暴露了社区驱动的开源项目的另一面:你不能强迫它。Caswell 说，在过去的几年里，Matplotlib 的开发完全是由志愿者驱动的——由工业界的一些人以及一些教授和学生共同完成，这些人要么在工作中自由支配的时间，要么在晚上和周末完成这项工作。他说这导致了一个有趣的管理问题，因为你不能告诉任何人去做任何事情。这个社区“没有强迫”——只有说服。

他说，除此之外，当来自不同文化背景的人之间主要进行文本交流时，会出现有趣的冲突，管理一个开源社区最终会给那些可能对 MBA 毫无兴趣的人提供 MBA 水平的体验。

## 熟悉但不同

多年来，Matplotlib 的指导原则之一是在创新的同时保留与 MATLAB 的一些联系。这种与 MATLAB 的联系非常重要，因为历史上很多潜在用户社区都是在大学的科学和工程课上开始使用 MATLAB 的。

这是 Matplotlib 的一大优势，也是一个基本的矛盾:如何平衡熟悉和创新。

随着 Python 已经成为数据科学事实上的语言，并在大学中广泛教授，越来越多的 Matplotlib 用户从未使用过 MATLAB。这使得 Matplotlib 社区不再需要遵循 MATLAB 标准。卡斯韦尔说，熟悉 MATLAB 的好处开始减弱。然而，他很快补充道，“Python 世界并没有杀死 MATLAB。他们也在疯狂地成长。我们只是发展得更快了。”

但是，建设什么来刺激未来的增长呢？

“如果你做了一个改变，花费了你所有用户两个小时的时间，这对全球生产力是一个巨大的打击，”Caswell 说，这促使项目社区注意引入 API 的改变。与此同时，他说，你必须发展和增加新的功能，以跟上不断发展的用户需求。“如果你不跟上，你就会被取代，”他说。这种平衡是 Caswell 和其他项目维护者必须持续处理的关键问题。

## 让 Matplotlib 赚钱

考虑到这个工具对许多其他人的效用，我问卡斯维尔 Matplotlib 对他在布鲁克海文国家实验室(BNL)的工作贡献了多少，这个工具在 BNL 的“任何地方”都被使用。Caswell 花费 5%到 10%的工作时间为 Matplotlib 做上游贡献。这一比例可能会上升，这要归功于来自 Chan Zuckerberg Initiative 的 25 万美元[资助，以帮助 Matplotlib 开发者解决其维护积压等问题。](https://chanzuckerberg.com/eoss/proposals/matplotlib-foundation-of-scientific-visualization-in-python/)

Caswell 可能不再为 Matplotlib 做那么多实际的编码工作，但作为项目负责人，这仍然是一个重要的时间承诺——大部分工作没有报酬。他为什么这么做？

在他读研的几年里，他很快意识到他不想成为一名教授。“那看起来一点也不好玩，”他说。相反，他发现他喜欢制造工具，并且真的想为科学家制造更好的工具。“这是让我坚持下去的动力，”他总结道。“周六晚上 11 点，独自在地下两层楼的实验室里，想着那个研究生。支持那个人是我前进的动力。这就是我的激情所在。”

有很多方法可以为 Matplotlib 做贡献，欢迎所有的方法。如果您或您的组织使用 Matplotlib，社区会很乐意在 Matplotlib 博客上展示您的用例。访问他们的 [How to Contribute](https://matplotlib.org/matplotblog/posts/how-to-contribute/) 页面以了解更多信息，并查看 [Matplotlib 开发人员指南](https://matplotlib.org/3.1.1/devel/contributing.html)以了解如何贡献文档、错误报告/修复或其他代码。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>