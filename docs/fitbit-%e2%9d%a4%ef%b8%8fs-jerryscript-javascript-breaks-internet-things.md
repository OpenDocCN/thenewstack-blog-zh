# fitbit ❤️'s Jerry script:JavaScript 闯入物联网

> 原文：<https://thenewstack.io/fitbit-%e2%9d%a4%ef%b8%8fs-jerryscript-javascript-breaks-internet-things/>

最近发布的 Fitbit Ionic 标志着 Fitbit 的第一款真正的智能手表。然而，对 [JavaScript](/tag/javascript/) 开发者社区来说，更重要的是，Ionic 是使用 [JerryScript](https://github.com/jerryscript-project/jerryscript) 生产和运输的，这是一种为物联网(IoT)提供动力的轻量级 JavaScript 引擎。

Ionic 代表了 JerryScript 在生产中使用的第一个实例之一，更不用说是迄今为止最雄心勃勃的实例了。仅此一点就标志着 JavaScript 社区在物联网生产环境中获得 JavaScript 的工作取得了重大胜利。同样令人兴奋的是，在发布的同时，Fitbit 也发布了它的 SDK。因此，开发人员不仅可以创建基于 JavaScript 的定制钟面，还可以为 Fitbit OS 创建应用程序，然后将这些应用程序提交到 Fitbit 应用程序库与其他人共享。这是 Fitbit 首次向外部开发者开放开发平台。

JerryScript 在微控制器等资源受限的设备上表现出色，因为它能够在 RAM 小于 64KB 的设备上运行，引擎代码所需的 ROM 空间小于 200KB。用 [C99](https://en.wikipedia.org/wiki/C99) 编写为了最大化可移植性，并为将 JavaScript 源代码预编译成字节码提供快照支持，JerryScript 支持在设备上编译、执行和从 JavaScript 访问外设。一个成熟的 C API 也使得 JerryScript 很容易嵌入到应用程序中。

JerryScript 也是 JS 基金会最早赞助的项目之一。New Stack 采访了该基金会的执行董事 Kris Borchers，以了解更多关于物联网市场这一令人兴奋的发展的信息——它将开源技术融入到智能设备中，然后首次邀请开发人员构建软件并贡献应用程序。

**能给个 JerryScript 的简史吗？**

JerryScript 本身是由三星创建的，他们在所有设备(从手机到电视)的物联网方面做了很多工作，所以我的假设是他们希望将 JavaScript 引入这些设备，以进入开发生态系统。我在 2016 年初与三星合作，作为重新启动 jQuery Foundation 的一部分，他们提出他们已经创建了 JerryScript，希望它不只是三星的努力。这就是基础所在——我们获得知识产权的所有权，但三星开发人员继续运营它，因为我们引入了新的开发人员来扩大长期的可持续基础。我们现在有来自许多不同组织的贡献者:Fitbit、 [Intel](https://www.intel.com/content/www/us/en/homepage.html) 、 [Arm](https://www.arm.com/) 。

JerryScript 无论是在使用上还是作为一个社区，都在不断发展壮大。人们对它所代表的可能性非常感兴趣。

【JerryScript 突破智能设备生产环境的障碍是什么，现在仍然是什么？

缺少的部分是在这样一个资源受限的环境中，将 JavaScript 转换到设备固件的需要，以及实现 JavaScript APIs 的需要。

JerryScript 首次搭载在 Pebble 智能手表上。后来 Pebble 被 Fitbit 收购，Fitbit 立即开始利用它来制造自己的手表。Pebble 已经构建了 [Rocky.js](https://github.com/pebble/rockyjs) ，这是一个框架，用作 JerryScript 和实际设备 API 之间的绑定，Fitbit 仍然使用它的一个版本来将 JerryScript 绑定到 Ionic。Rocky.js 目前没有开源，部分原因是不清楚开源它对项目或 JerryScript 生态系统有多大好处，因为它非常适合 Fitbit。也就是说，JerryScript 从 Fitbit 的积极参与中受益匪浅——任何新的功能和内容，只要与它们的绑定一起运行得更好，他们都会将其贡献给 JerryScript。

其他项目正在填补这一空白。在三星，有一个类似于 JerryScript 的项目，叫做 [IoT.js](https://github.com/Samsung/iotjs) ，他们只是开始加速发展。IoT.js 旨在以比 Rocky.js 更通用的方式成为一个可互操作的服务平台，因此你可以在不同的设备上使用它。英特尔一直致力于为资源受限的设备开发可扩展的实时操作系统[泽法](https://www.zephyrproject.org/)，以及为泽法操作系统开发 JavaScript 运行时。

因此，这些新的运行时不仅为 JavaScript 进入物联网领域打开了大门，而且是以完全开源的方式？

泽法运行在 JavaScript 之上，拥有许多微控制器和开发板。它是开源的，构建在同样是开源的 JerryScript 上。

从操作系统到 JavaScript 的整个堆栈现在都可以开源了——泽法本身就是一个 RTOS 和一个开源 Linux 基金会项目。英特尔是泽法的主要贡献者和消费者，所以他们构建了 Zephyr.js 作为泽法的开源 JavaScript 运行时。而 Zephy.js 下的底层引擎是 JerryScript。

我和泽法一直在我的办公室里做一些东西，试图建立某种实际上的[无服务器钻机](/category/serverless/)。你可能会看到有人用[覆盆子酱](https://www.raspberrypi.org/)这样做，但在我看来这是欺骗。它基本上是一个服务器，对吗？尝试使用最大 1MB ROM 和 256K RAM 的微控制器——我正在使用一堆这样的微控制器。很好玩因为都是 JavaScript！

**告诉我们更多关于 Ionic 软件开发套件(SDK)的信息？**

SDK 是该项目的面向应用开发者的部分，它将 JavaScript 链接到设备；因此，SDK 是您与该层交互的方式。老实说，就目前而言，Fitbit 开源他们的 SDK，除了 Fitbit 之外，我不能说会有多少直接的好处。但简单地拥有一个 JavaScript 驱动的 SDK 将有望让开发者使用 Fitbit 设备，获得更多关于开发者希望看到什么的反馈。我最终的希望是，这是一个让中间层更多地参与物联网 JavaScript 领域的门户。这对两个方向都有好处:选择用 JavaScript 构建物联网的公司会发现更多的开发人员已经有所了解并做出了贡献。然后，如果在幕后使用 JavaScript，他们开始为已经存在的开源项目做贡献，而不是构建一些专有的东西。

这是一把双刃剑。我们的生态系统中有如此多的快速创新，都是由人们创造驱动的，这很棒，但同时也是上周 100 个最佳日期选择器 jQuery 插件的最终结果。每个人都做着同样的事情，重复着自己。我们不想扼杀创造力，因为不时会出现一些真正新的有用的东西，但这让人们很难弄清楚‘我现在应该用什么？’因此，如果有地方，特别是在像这样的新兴领域，您可以用开源中已经存在的东西来替代封闭源代码，这是值得探索的。

**那么:JavaScript 扩大其在物联网领域的存在的合理的下一步是什么？**

物联网中的 JavaScript 无疑是一个增长趋势，但谈论所有物联网中的 JavaScript 有点困难，因为它现在是一个通用术语，物联网实际上无处不在。JavaScript 在边缘已经被很好地采用了。你可以在 [Node-RED](https://nodered.org/) 中看到这一点，node.js 的轻量级运行时已经存在了一段时间，是一个被广泛采用的将硬件、API 和 web 服务连接在一起的工具。它已经相当成熟，并且集成到了许多东西中。

我们现在看到的是，人们正以一种严肃的方式深入到微控制器小型器件层面。物联网中的 JavaScript 真正开始于业余爱好者和创客空间，建造机器人和有趣的灯光秀。但现在我们看到它进入了物联网的更多工业应用。 [Opto 22](http://www.opto22.com/) 是一家工业机器和过程控制器制造商，他们有一个微控制器边缘设备，使用 NodeRED 来聚合和引导来自该设备的数据流。

从创客世界到企业应用，我们开始看到人们更加认真地对待 JavaScript。Pebble 要小得多(就市场覆盖面而言)；有了 Fitbit，我们现在看到在个人设备层面上，JavaScript 在广泛的生产规模上受到了重视。随着开源工具的不断发展和跨越所有用例，机会是无穷无尽的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>