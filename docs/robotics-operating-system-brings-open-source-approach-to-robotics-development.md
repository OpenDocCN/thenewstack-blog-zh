# 机器人操作系统为机器人开发带来开源方法

> 原文：<https://thenewstack.io/robotics-operating-system-brings-open-source-approach-to-robotics-development/>

编者按:TNS 出版社

[Alex Williams](https://thenewstack.io/author/alex/)

促成了这个故事。

人类的未来很可能真的是一个完全机器人化的未来，充满了智能机器人，它们可以在办公室里和你一起工作，比如 T2 喂老人，T4 做精密手术。然而，正如人们可能想象的那样，设计和制造这些机器人的过程并不简单，也不尽如人意。毕竟，不久前，许多在机器人领域工作的人在着手一个新项目时，经常发现自己从零开始，重新实现复杂机器人算法所基于的软件基础设施。结果是太多的时间被浪费在“重新发明轮子”上，而不是开发创新的机器人软件。

进入一些[开源](/tag/open-source/)解决方案，比如由[开放机器人](https://www.openrobotics.org/)提供的解决方案，这是一个植根于[斯坦福大学](https://www.stanford.edu/)和[柳树车库](https://en.wikipedia.org/wiki/Willow_Garage)的组织，一个著名的科技产业孵化器。在最近的亚马逊网络服务 Re:Invent 用户大会上，AWS 开发者倡导者阿莱杭德娜·奥尔韦拉-诺维克讨论了开放机器人软件的可能用途。一个这样的例子是运行一只机器服务狗。一只机器狗，虽然不像拥抱，需要更少的维护，并能在紧急情况下提供更多有用的信息。

Open Robotics 于 2012 年作为非营利组织推出，现在与学术界、行业、政府和企业合作，在从研究和教育到产品开发和部署的多个阶段创建和支持开源机器人软件和硬件。为了更好地了解这个开源平台是如何工作的，我们与开发人员 Katherine Scott 讨论了 Open Robotics 的两个主要项目，[机器人操作系统](https://www.ros.org/) (ROS)和 [Gazebo](http://gazebosim.org/) ，一个 3D 多机器人模拟框架。

![](img/626d622805373201aea54c4a9d0df123.png)

凯瑟琳·斯科特，开放机器人的开发者倡导者

**什么是机器人操作系统，它是如何工作的？**

尽管名字如此，ROS 实际上并不是一个操作系统。它运行在各种操作系统之上，通常是 Linux。

向新的技术受众描述 ROS 的最佳方式是说 ROS 之于机器人，就像 Ruby on Rails 或 Node 之于 web 开发一样。也就是说，ROS 是一套用于创建、配置、构建、调试和管理复杂机器人系统的工具。在其核心，ROS 是一个发布/订阅系统，可用于在组成更大机器人系统的小型计算机程序之间共享数据和信号。例如，如果你有一台相机，你想把它连接到一个大型工业手臂上，ROS 允许你连接到这些组件，向它们发送和接收数据，并编写代码将行为粘合在一起。

**它与业内其他类似工具相比如何，它的重要之处是什么？**

行业内根本没有任何类似的工具——或者至少没有你可以买到的商业工具。由于它的历史、联邦开发模型和全球用户基础，ROS 拥有几乎所有机器人应用程序的工具。虽然有些供应商可能有针对特定垂直市场的特定应用解决方案，但没有一家是面向通用机器人开发的。

**开源方法在机器人领域有哪些优势？**

开源软件运行在世界的大部分地方，从云端一直到你家中的嵌入式设备。出现这种情况的原因是开放源码的上市时间大大缩短了；也就是说，更小的团队可以更快地创造更多的价值。开源还使得培训开发人员、进行研发和促进供应商之间的合作变得更加容易。使用我们上面的例子，ROS 将允许你在你的机械臂上使用任何相机，你需要做的就是创建一个界面，可能有人已经在过去这样做了。

开源技术的使用也使企业摆脱了对单一供应商或来源的依赖。Open Robotics 从 Willow Garage 分离出来的主要原因之一是为了确保该组织不局限于一家公司。

在 ROS 之前，每个机器人专家都必须从头开始他们的研究。几乎没有共享的工具或资源。迄今为止，使用 ROS 的最大优势是它是成熟的机器人软件，在大多数情况下已经被证明可以在机器人上工作。

**ROS 开源有什么缺点吗？**

ROS 的缺点与任何其他开源项目一样:虽然软件可以免费使用，但这并不意味着使用该软件进行开发或扩展是免费的。虽然事情通常运行良好，但验证软件是否适合其应用程序的性能需求是由开发人员决定的。包括开放机器人在内的许多组织都可以为 ROS 用户提供帮助、建议和支持。

**开发和实现开源机器人工具有哪些挑战？**

我们最大的挑战在于平衡全球多元化利益主体群体的需求和优先事项。ROS 和 Gazebo 的用户群包括爱好者、学生、研究人员、企业家和经验丰富的开发人员——他们为汽车、船只、飞机、人形机器人和玩具以及无数其他应用程序编写代码。迄今为止，我们的软件平台已经被证明足够通用和灵活，可以满足这些群体中的许多人，也许是大多数人。但是我们必须不断地工作来平衡和优先考虑我们想要支持的用例。

**最近有哪些 ROS 帮助机器人开发者的例子？**

使用 ROS 的一个很好的案例是 [Simbe Robotics](https://www.simberobotics.com/) 。Simbe 创造了[理货](https://www.simberobotics.com/platform/tally/)机器人，零售机构使用它来完成库存跟踪、缺货管理、促销执行和货架图合规等任务。我们目前正与 Simbe 合作发布一份白皮书，介绍他们使用 ROS 的体验。他们相信 ROS 在创造计数机器人方面为他们节省了 22 年的开发时间。Simbe 成立于 2015 年，在产品开发阶段保持相对精简，他们能够取得的成就令人惊叹。

Simbe 只是 ROS 如何帮助机器人公司的一个例子，还有很多其他的例子。2019 年 9 月，在其物流机器人中使用 ROS 的公司 [6 River Systems](https://6river.com/) 被以 4.5 亿美元收购。此外，四家基于 ROS 的机器人初创公司在近一个月的时间里筹集了近 1.44 亿美元的风险资本。简而言之，ROS 是一种开源技术，推动了机器人技术的大部分进步。

**ROS 和 Gazebo 的最新更新和改进是什么，它们解决了什么问题？**

Open Robotics 目前正在从最初的 ROS(或“ROS 1”)过渡到 [ROS 2](https://index.ros.org/doc/ros2/) 。目前，我们正在努力推动 ROS 2 的采用和发展，已经有了很好的 ROS 1 用户基础。我们正在开发 ROS 1 的第 13 个也是最后一个版本，它已经保持了相当稳定的 API 大约十年了。ROS 2 是我们解决过去可能限制 ROS 1 的问题的机会，并为未来二十年的机器人技术发展创造一个成熟和开放的平台。我们刚刚发布了 ROS 2 的第五个版本，雄辩的 Elusor，我们认为现在是社区开始转变的时候了。Open Robotics 是一个依靠反馈和协作蓬勃发展的组织，我们需要我们的用户社区将他们的代码库转换到 ROS 2，并开始就如何改进它提出建议。

ROS 2 解决了 ROS 1 在安全性和可靠性方面的很多缺点。ROS 2 还使得创建 ROS 硬件接口变得容易得多，这为硬件制造商打开了一个全新的世界。对于 ROS 2，我们正在做一些更大的事情。我们不只是在开发一套软件包——我们正在为未来的机器人系统开发一个强大的通用界面。

我们也对 Gazebo 进行了类似的过渡。Gazebo 的下一个版本目前正在进行中，叫做[点火](https://ignitionrobotics.org/)。Ignition 允许你“模拟”创建一个机器人，并在真实的虚拟环境中测试它，在某些方面类似于视频游戏。这项技术非常强大，因为它允许开发人员构建和测试代码，而不必坐在机器人面前，乏味地等待它运行他们的命令。当与云计算结合时，模拟成为在复杂环境中测试机器人行为的不可思议的工具。使用云，你可以在一个模拟环境中运行一个机器人，对环境或机器人的行为进行微小的改变；您可以并行重复这个过程数千次。这使得机器人开发人员的工作效率大大提高，也让我们能够更好地测试我们制造的机器人的性能。这也意味着多个开发人员可以同时在同一个机器人上工作。

Ignition 的模拟能力使得机器人开发变得更加容易；你不需要造一个机器人，你只需要一台笔记本电脑和一个想法。通过将硬件开发从软件开发中分离出来，我们已经向全球更多的受众开放了机器人技术，组织也开始注意到这一点。

*如果你有兴趣学习 ROS，或者测试你的技能，试试虚拟的 [DARPA 地下挑战赛](https://www.subtchallenge.com/)，或者 NASA 喷气推进实验室的开源漫游者太空挑战赛。*

[https://www.youtube.com/embed/kZ66pI_d5WE?feature=oembed](https://www.youtube.com/embed/kZ66pI_d5WE?feature=oembed)

视频

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>