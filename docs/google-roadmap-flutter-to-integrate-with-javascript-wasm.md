# 谷歌路线图:奋力整合 JavaScript，Wasm

> 原文：<https://thenewstack.io/google-roadmap-flutter-to-integrate-with-javascript-wasm/>

在肯尼亚内罗毕举行的 Flutter Forward 大会上，谷歌为其 Dart 框架 Flutter 制定了一个雄心勃勃的路线图，包括支持 WebAssembly (Wasm)的计划。这个互联网巨头正期待着它的开发者社区来帮助制定这个计划。还发布了 Dart 3.0 和 Flutter 3.7。

[Flutter](https://flutter.dev/) 是 Google 开源的移动 UI 框架。计划中的 Flutter 升级包括编译到 WebAssembly 的能力、改进的图形性能、JavaScript 和 Dart 之间的互操作性，以及将 Flutter 组件添加到 web 应用程序中的能力。目前它也支持 Android、iOS、Windows、macOS、Linux 和 web 同时也支持嵌入式平台使用 Flutter。

“我们真的试图展示方向，我们这样做是因为我们希望其他人做出贡献，而且这是一个开源项目，” [Tim Sneath](https://www.linkedin.com/in/timsneath/) ，Flutter and Dart 的产品和 UX 总监告诉新堆栈。“我们希望人们加入我们的旅程，Flutter 上几乎一半的贡献者不为谷歌工作，他们为其他公司或社区工作。通过制定我们的路线图，他们有机会加入我们的行列。”

Sneath 说， [Flutter 已经发展到大约 70 万个在商店上发布的应用，从初创公司到宝马和丰田这样的大公司，以及在谷歌内部用于大约 30 个不同的项目(包括 Classroom 和 Google Pay)。](https://thenewstack.io/industry-observer-sees-growing-interest-in-dart-flutter/)

谷歌还发布了 Flutter 3.7，这是一个稳定的版本，在 [iOS](https://thenewstack.io/wwdc21-ios-platform-upgraded-but-what-about-the-web/) 上添加了一个新的渲染引擎，增强了对 Material 3 和 iOS 风格小部件的支持，改进了对国际化的支持，后台处理的改进，以及对开发人员工具的更新。

然而，Sneath 说，会议和公告的主要焦点是下一年的道路。以下是 Flutter 希望在未来一年进行创新的领域:

## 将 Flutter 与 Web、JavaScript、Wasm

“我们正在投资使 Flutter 与其他代码的集成变得更容易，无论它是一个拥有系统 API 的移动应用程序，还是你想获得一些 Flutter 代码并将其放入你已经编写的网络体验中，”Sneath 说。“我们在这里做的所有工作都是为了让 Flutter 更容易与其他可能在那里编写的东西进行交流，因为世界上并不是每一行代码都是 Flutter 应用程序。”

他说，这意味着现在可以将 Flutter 组件放入网站，开发者可以将 [CSS](https://thenewstack.io/html-css-and-the-path-to-accessible-web-design/) 转换(如反射)应用于 Flutter 组件。

Flutter 现在与 [JavaScript](https://thenewstack.io/2022-a-golden-year-as-javascript-moves-to-the-edge/) 也有了更好的互操作性。

“你可以用 JavaScript 驱动 Flutter 小部件，反之亦然，”他说。“你可以从 JavaScript 方面读出 flutter 的数据，这是一个新的机会。”

谷歌也在研究一种与系统[API](https://thenewstack.io/key-concepts/apis/)集成的新方法，以减少与 Android 和 iOS 集成时的一些定制代码需求。例如，如果开发人员想要集成新的 Android jetpack 库或新的 Apple 库，他们可以调用新的 Dart 命令，它会自动生成所有绑定，以“用很少的仪式或代码”直接与这些 API 对话，Sneath 说。

然后是 WebAssembly。Sneath 说，WebAssembly 最初不支持像 Dart 这样的垃圾收集语言，所以谷歌与 WebAssembly 和 Chrome 团队合作来支持这些语言。还不是所有浏览器都支持它，但它可以在谷歌为开发者开发的浏览器 Chrome Canary 上运行。

他补充说，可能要到今年晚些时候，它才会得到全面支持。

“Dart 是最先采用这种方法的公司之一，”他说。“我们能够利用这一点，让 Flutter 应用程序现在可以编译成 WebAssembly。这意味着它们将启动得更快，更容易与用其他语言编写的其他代码集成，我们很高兴看到人们会这样做。

最后，Flutter 现在支持开源[架构标准，RISC-V](https://thenewstack.io/risc-v-the-next-revolution-in-the-open-hardware-movement/) 。

“基于 RISC-V 的硬件还不多，但我们认为这是未来一代工艺的一部分，”Sneath 说。

## 改进的移动图形性能，支持 3D

从历史上看，跨平台框架需要在视觉上做出妥协，因为创建抽象层存在挑战，Sneath 在周二的博客文章中说。

“Flutter 采取了与大多数不同的方法，它有自己的渲染层，可以在每台设备上提供硬件加速的图形和一致的视觉外观，”他写道。“展望未来，我们将投资突破性的图形性能，扩展 Flutter 在该领域的现有优势。”

“我们正在挑战那里的界限，”他告诉 TNS。“在过去的几个月里，我们用一个叫做叶轮的项目重新设计了整个图形渲染管道。叶轮旨在提升性能，并提供铸铁-始终保证没有下降的框架和真正高品质，如丝般光滑的体验。”

谷歌在大会上发布了对叶轮的早期支持。此[演示视频在左侧显示了传统的颤振渲染引擎](https://www.youtube.com/watch?v=Z7v-YRdHusM&t=6s)，右侧是新的叶轮渲染引擎。iOS 版 Flutter 3.7 上的叶轮有一个选择加入标志。

[叶轮](https://github.com/flutter/flutter/wiki/Impeller)针对颤振进行了优化，为开发人员提供了更多的灵活性和对图形管道的控制。Sneath 在博客中解释说，叶轮通过使用预编译的着色器来减少运行时由着色器编译导致的丢帧，从而提供了更可预测的性能。它使用 Metal 和 Vulkan 中的原语，这些原语是 iOS 和 [Android](https://thenewstack.io/this-week-in-programming-windows-opens-up-to-android-developers/) 中的现代低级 API。他补充说，它还“有效地利用了并发性，在线程间分配单帧工作负载”。

“在某些情况下，叶轮给我们带来了六到九倍于我们以前的图形引擎的性能提升，”他说。“但除了性能或如丝般顺滑的品质之外，它还为我们认为人们想要建立的一些新体验打开了大门。”

现在支持像素着色器，这是一种编写低级图形 GPU 函数的能力，可以在屏幕上的每个像素上执行，跨网络和移动。他补充说，它可以实现模糊效果和其他图形处理体验。

他补充说，谷歌也已经开始用 Flutter 支持 3D 的早期工作。他说，会议演示了如何导入用 Blender 创建的模型，以及如何使用 hot reload 实时迭代 Blender，并在运行的应用程序上查看结果。

![Improved Mobile Graphics Performance, Support for 3D](img/33b248fc6d17346063f035ab925e1a2e.png)

图片由谷歌提供

“我们正在进入 3D 世界，现在通过 Flutter 支持 3D 图形。对我们来说，这真的就像是下一代——一个全新的维度，”他说。“这意味着你可以用传统的 3D 工具工作，如 [Blender](https://www.blender.org/) ，你可以创建模型、 [3D 网格](https://link.springer.com/referenceworkentry/10.1007/0-387-30038-4_126#:~:text=Definition%3AMesh%20is%20a%203D,in%203D%20(Figure%201).)。你可以将它们导入到 Flutter 中，然后你就可以像编写任何其他代码一样编写和使用它们。”

他解释说，这是通过编程 Flutter 的 Dart 代码实现的。它可以在低至 2014 年发布的 iPhone 的设备上运行。

“看到 2D 和 3D 图形的结合真的很有趣，而且，从历史上看，这些都是不同的领域，不同的技术，不同的语言，”他说。“现在，我们将所有这些整合在一起，我们很高兴看到当您可以将这些东西结合在一起时会发生什么。”

## 改善开发人员在 Dart、Flutter

Sneath 补充说，谷歌本周还发布了 [Dart 3](https://dart.dev/get-dart/archive#dart-3-alpha) ，其中包括新的语言功能，以改善开发者的体验。Dart 3 完成了走向零安全性的旅程，他说这是编写无 bug 代码的关键要素。

“Dart 3 还删除了其他长期被否决的功能，以进一步使语言现代化，”Sneath 解释道。“我们已经开始发布 Dart 3 的 alpha 质量版本，以及匹配的 Flutter 版本，使开发人员能够测试软件包和应用程序。”

令人不安的是，谷歌正在提供其新闻工具包的第一个版本，针对的是那些希望提供移动应用程序但缺乏资源开发的地区新闻出版商。白标解决方案提供模板来帮助构建移动应用。谷歌与三家非洲新闻机构合作推出了这项服务——包括摩洛哥最大的出版商和肯尼亚的报纸《标准报》。

斯内思强调，并非所有的工作都已完成，但都是可行的。

“我们将在这里展示一些非常早期的演示，但这对我们作为一个团队来说基本上是通往未来方向的大门，”他说。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>