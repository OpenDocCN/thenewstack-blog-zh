# 物理计算类型对 GitHub 的看法略有不同

> 原文：<https://thenewstack.io/physical-computing-types-see-github-a-little-differently/>

软件人员通常将 GitHub 视为一个易于访问的存储设备，用于保存源代码。您可以将文件上传到云，管理您的版本，共享项目并与其他人协作。

对于不经意的观察者来说，GitHub 上有各种各样的项目并不完全明显。不足为奇的是，很多人倾向于软件方面。

GitHub 不仅仅是为纯软件爱好者准备的。我们混合软件/硬件物理计算极客、小玩意、工程师和发明家也有一席之地。

如果你稍微探索一下，物理计算、硬件开发人员、创客运动和 DIYer 类型的人会发现成千上万的 GitHub 仓库，它们迎合了 3D 打印、ESP32 微控制器、Arduino 社区、Raspberry Pi 和许多其他“物理”主题。你甚至会遇到像“计算流体力学”或“软件无线电”这样的新奇事物的可行项目

进入 [GitHub 主页](https://github.com/)，在搜索框中键入一两个关键词，然后坐下来，惊叹于屏幕上出现的雪崩式的回复。在我写这篇文章的时候，“3D 打印”向我展示了 8552 个仓库。“Arduino”有超过 241，000 个。有些只是一个半打左右文件的列表，而其他的则包含了他们主题的全面覆盖，包括项目代码、图表、照片、原理图、打印文件、零件列表、配置、文档、教程等等。

今天，我们将看看几个与 3D 打印、微控制器、机械装置、零件、工具和 CAD 相关的 GitHub 知识库。我将指出您在优化自己的 GitHub 项目集合时可能会看到的优点和挑战。GitHub 上到处都是有趣的有价值的信息，发现它们可能会帮助你完成下一个令人敬畏的项目。

## 三维打印

[Octoprint 3D 打印显示器项目](https://github.com/Qrome/printer-monitor)是 GitHub 物理计算回购的一个经过深思熟虑和执行的好例子。

这是网页内容的简要概述。

*   设备的特点
*   微控制器部分的设计细节
*   接线图
*   打印硬件外壳的文件
*   设备的图片
*   零件目录表
*   微控制器的代码
*   Web 界面设置
*   贡献者
*   许可和捐赠

我注意到缺少的一个小东西是关于项目或代码的目的的描述性的第一段，它是用来做什么的，它是如何被使用的，以及要使它全部工作还需要什么。这发生在很多仓库中，这对回购的所有者来说是好事。

他们知道代码和项目发生了什么，尽管页面对面发生的陌生人可能需要四处戳来回答上述问题。尽管如此，这个回购检查了许多“好”的盒子。

[Prusa](https://www.prusa3d.com/) 3D 打印机部件[仓库](https://github.com/prusa3d/Original-Prusa-i3)在描述部门稍微好一点。它指出，回购房屋的 SCAD 和 STL 文件打印备件。文件包括可下载的部分，您可以将其导入到 FreeCAD 等程序中，或者直接放在 SD 卡上，然后在 MK3S 打印机上制作。在页面底部有一个 Prusa 网站、产品页面、构建手册等相关链接的列表。请注意，有些链接连接到其他 Prusa GitHub 页面。

[FreeCAD](https://www.freecadweb.org/) 是我 2D/3D 计算机辅助设计的选择。它稳定、快速、强大，运行在 Linux 上。虽然有其他好的 CAD 软件包，有付费的也有免费的，但是 FreeCAD 提供了我需要的一切，并且在网上有一个很大的支持社区。因为是免费的，你肯定会期待一个体面的 [FreeCAD GitHub 页面](https://github.com/FreeCAD/FreeCAD)。

如果你打算制作自己的小工具，特别是 3D 打印，你需要学习 CAD。FreeCAD 在开始时有点难，所以看看 YouTube 上丰富的教程视频来获得帮助，了解一些基础知识。能够设计自己的零件，然后在办公桌上打印出来，这是有史以来最伟大的工程飞跃。

FreeCAD repo 是有组织的，专注于软件，包括截图、代码和有用的链接。请访问主页，获取详细的手册、教程和用户信息。这里有一个 GitHub 页面的快速列表。

*   概观
*   装置
*   构建状态
*   问题
*   使用
*   相关网站的链接

当你学习 FreeCAD 时，一定要利用任何新的 [CAD 库](https://github.com/FreeCAD/FreeCAD-library)和[附加组件](https://github.com/FreeCAD/FreeCAD-addons)，也在 GitHub repos 中。

## 机械的

我用“机械”这个关键词找到了 7727 个回购。

例如，“[Awesome Mechanical Engineering Resources”项目](https://github.com/m2n037/awesome-mecheng)使用 GitHub 的方式有所不同。没有多少代码或打印文件。它所拥有的是一个巨大的页面，里面充满了各种机械工程和设计网页的链接。

这些链接包括你可以选修的课程、数据库、教程、编程语言和各种工程相关的应用。你还可以找到关于机械设计、控制工程、热力学、微积分和许多其他主题的链接。底部是博客、社团和竞赛的链接。对于后院和专业工程师来说，这是许多有趣和有价值的信息。

## 微控制器

也许你的 Arduino 项目需要一些灵感。我找到的 241，086 个 GitHub 回购可能有你需要的。

一个很好的起点是 Arduino 官方回购。在这里，您可以找到 Arduino IDE(集成开发环境)上的所有代码和信息。这包括下载、安装、发布、构建和测试的资源。非常典型的以“软件”为中心的 GitHub 库，它当然与物理 Arduino 微控制器世界联系在一起。有关实际 Arduino 板的详细信息，请访问 Arduino 主页。

虽然官方 Arduino repos 主要包含代码，但其他页面突出显示了实际项目，包括硬件、提示和技巧、一次性库、ESP8266/ESP32 主题(34250 个 repos)等等。一个家伙正在通过 GitHub 推广他的 [ESP32 开发培训课程](https://github.com/RuiSantosdotme/ESP32-Course)。好主意，尽管你应该在做“商业”类的事情之前检查平台(GitHub)的使用条款。

## 外来植物

我将给你留下更多的“在那里”的回复来探索。

首先是 [Jevois 机器视觉](https://github.com/jevois/jevois)回购。我使用我的机器人头骨[赫德利](https://thenewstack.io/off-the-shelf-hacker-conversations-with-hedley-the-robotic-skull/)中的 Jevois 传感器来识别人和物体。Jevois 背后的主要人物 Laurent Itti 是南加州大学的机器视觉专家。他和他的团队已经为探索机器视觉建立了一个令人敬畏的装置，包括软件和硬件。谈谈物理计算。这个理论很深奥，需要消化的信息非常多。另一方面，任何人都可以花 50 多美元买一个 Jevois 传感器来完成机器视觉任务。

请务必转到 FreeCAD 资源库的[计算流体动力学工作台。在我卑微的蒸汽朋克机械小工具项目中，我对数学的深度还不太感兴趣……也许有一天。如果你做那种工作，我向你致敬。](https://github.com/jaheyns/CfdOF)

在“特别提款权”下，出现了 6028 个回购。

描述性 GitHub 页面的一个广泛的例子是 [GNSS-SDR 项目](https://gnss-sdr.org/)。GNSS 代表“全球导航卫星系统”基本上，它告诉你如何在软件定义无线电上处理全球定位卫星信号。我包含了这个库，因为它绝对是巨大的。主页会一直持续下去，而且有很多信息。我认为这是一个很好的例子，说明你可以如何设计一个大型描述性回购。

哦，对了，别忘了在 GitHub 搜索框里输入“树莓派”。你会得到超过 92，000 的点击率。当然有一些很酷的项目，你可以在那个类别下使用。

*在[doc@drtorq.com](mailto:doc@drtorq.com)或 407-718-3274 联系 [Rob "drtorq" Reilly](/author/rob-reilly/) 咨询、演讲约定和委托项目。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>