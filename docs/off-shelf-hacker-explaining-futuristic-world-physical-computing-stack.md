# 现成的黑客:解释物理计算堆栈的未来世界

> 原文：<https://thenewstack.io/off-shelf-hacker-explaining-futuristic-world-physical-computing-stack/>

我们听说过“全栈开发人员”或 LAMP 栈这样的术语。前者指的是能够对独立或 web 软件应用程序的前端和后端部分进行编程的人。例如，有人可以构建 web 应用程序的用户界面，还可以编写财务引擎，让 web 应用程序实际处理客户的在线订单。后者指的是 Linux、Apache、MySQL 和 PHP 等软件基础设施，这些都是互联网上的网站。

几年前， [TechCrunch](https://techcrunch.com/2014/11/08/the-rise-and-fall-of-the-full-stack-developer/) 表示，全栈开发即将过时。今天的热门产品是全栈集成器。好吧…

硬件人员也有他们的堆栈。

我创造了自己的“堆栈”，即物理计算堆栈。

回到我开始使用微控制器的时候，从[基本印记](https://en.wikipedia.org/wiki/BASIC_Stamp)开始，汤姆·伊戈伊、[《物理计算:用计算机感知和控制物理世界》](https://www.amazon.com/Physical-Computing-Sensing-Controlling-Computers/dp/159200346X)和《让事物说话:连接物理对象的实用方法》这两本书向我介绍了物理计算的未来世界。

我的物理计算栈在 Igoe 的模型上扩展，与时俱进。

## 物理计算堆栈示例

可以把物理计算栈想象成“计算和与之相关的一切与现实世界相遇的地方。”最简单的形式是，像 Arduino 一样，你有一台小型计算机和它的固件，以及它控制的输入传感器和执行器。Arduino 读取输入，进行一些计算，并可能改变一些输出。同样的程序非常快速地重复发生，直到设备断电。

要构建一个实际运行的原型项目，您必须考虑以下许多物理计算堆栈元素(排名不分先后):

```
Software
Hardware
Firmware
Operating System
Networking
Sensors
Actuators  -  Hydraulics,  Pneumatic,  Magnetic,  Electric
Mechanisms
Product Packaging
Aesthetics
Databases
Web/Internet
Mobile Components
Radios
Servers
Protocols
Interfaces
Electronics
Security
Big Data and Artificial Intelligence

```

最近关于电动汽车的 [TNS 文章](https://thenewstack.io/off-shelf-hacker-much-torque-never-enough/)有一个物理计算的旋转，它使用计算技术来控制大型电动机，输入来自轴速度传感器和油门踏板下的电位计。在这种情况下，电机控制器很像一个工业级 Arduino，感应输入，进行一些计算并改变一些输出。你可以把疯狂的僵尸 222 野马的车身、车架、传动装置想象成“美学”和堆栈的“产品包装”元素。

机器人将物理计算栈的概念又向前推进了一点。机器人有一个计算机大脑，让它移动的马达，检测它何时会撞到什么东西的传感器，以及使它以富有成效的方式运行的软件。

添加网络硬件(以及相关的软件或固件)，以及亚马逊 Alexa 这样的后端服务，用于向机器人发出命令，一些 led 灯，动画眼球和某种声音，你就会开始了解一个真实世界的物理计算堆栈。

## 从机器人到机械

我们对机器人的传统概念是有轮子在地板上移动的东西。物理计算堆栈当然包括机器人。它也可能偏离机制的非传统方向。

我的[蒸汽朋克眼球](https://thenewstack.io/off-shelf-hacker-behold-steampunk-eyeball-complete-part-5/)融合了物理计算栈“机制”层的元素。它不是真正的机器人。这款完全独立的设备使用专门的像素图像传感器来跟踪彩色斑点，通过几个 X-Y 伺服系统平移和倾斜眼球。我认为黄铜眼球框架，眼球本身，基地和潘枢纽作为所有的“机制”层的一部分。所有的元素都必须协同工作，否则，它就不是一个可以向观众或赞助商演示的功能原型。

工业控制，另一个物理计算堆栈，包含一个沉重的“机制”层组件。当然，移动手臂、启动泵和监控通过滑槽的部件数量都与工业机制密切相关。

## 要么做大，要么回家

如果你将轮式库存处理机器人与生产线上的工业控制结合起来，并将其全部连接到中央控制服务器(或云中的容器)，从而将状态更新发送到你的 Android 超级手机上的一个小移动应用程序，会怎么样？这可能包括软件、硬件、固件、网络、无线电、网络/互联网、数据库、机制、接口、协议等等。

这开始成为一个更加复杂的物理计算堆栈，你说呢？

最酷的是，作为一名现成的黑客，你可以从小处着手，迅速积累你在每个方面的专业知识。从一个 Arduino、几个 led 和几个传感器开始。启动一个基本项目。然后把 Arduino 换成树莓派。之后，通过从另一台机器远程修改您的 Raspberry Pi 程序来加快联网速度。接下来，把你的项目改造成一个旧玩具或者一些疯狂的临时设备。

今天在这里，我只讨论了其中的几层。

就在今天，Hackaday.io 上有一篇关于使用[电动线性电位计](http://hackaday.com/2017/04/26/wherein-the-mechanical-keyboard-community-discovers-motorized-linear-potentiometers/)的文章。这绝对是“传感器”层的一个独特组成部分。你如何在项目中使用它？

或者，将几个物理计算层合并到一个魔术表演中不是很有趣吗？也许[安静的一半佩恩和柜员](http://www.smithsonianmag.com/arts-culture/teller-reveals-his-secrets-100744801/?all&no-ist)能给你一些思路。

有上百万的新发明在那里，只是等待现成的黑客，他们可以用物理计算栈来构建项目。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>