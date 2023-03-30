# 工具包允许 JavaScript 开发者对嵌入式设备进行编程

> 原文：<https://thenewstack.io/toolkit-allows-javascript-devs-to-program-embedded-devices/>

一个新的工具包使 JavaScript 开发人员能够为嵌入式和桌面应用程序创建本地用户界面。叫做 Slint，也支持 C++或者 Rust 的编程。

Slint 是一家名为 [SixtyFPS GmbH](https://slint-ui.com/imprint.html) 的初创公司的创建。基于 Rust 的 UI 工具包最近在 2023 年嵌入式世界大会上获得了工具类的第一名。虽然这个工具是用 Rust 编写的，但是对开发人员来说是模糊的。相反，开发人员与 [JavaScript](https://thenewstack.io/javascript-library-lets-devs-add-ai-capabilities-to-web/) 、 [Rust](https://thenewstack.io/what-rust-brings-to-frontend-and-web-development/) 或 [C++](https://thenewstack.io/c-on-the-move/) 库交互来构建 UI 界面，但 Rust 的底层为工具提供了基础，SixtyFPS GmbH 的联合创始人 [Olivier Goffart](https://github.com/ogoffart) 说。

“我们从一开始就说，我们希望这能得到几种编程语言的支持，因为在 10 年或 20 年后，当 Rust 不再好用时，我们希望能够为用户提供这种支持，以便他们可以用自己的语言编写，”Goffart 告诉新的 Stack。“Rust 本身并不是一种编写应用程序逻辑的好语言，因为应用程序逻辑通常不需要这么高的性能。”

但是在应用程序中支持 Rust 很容易，因为它是实现语言。支持 C++也很容易，因为它是编译过的，团队来自那个生态系统。最后，他们想要支持 JavaScript，因为它是一种动态语言。如果他们最初可以支持这三种语言，那么他们认为他们最终将能够支持所有语言。

尽管 Slint 的创造者对 C++很有经验，但他们认为 Rust 比 C++有更好的工具，感觉更现代，同时仍有 C++的潜力。戈法特补充说，它还有更安全的额外好处。

“我们想要一个真正快速的东西，因为当你运行嵌入式[应用]时，CPU 的每个周期都很重要——所以我们负担不起垃圾收集器，”Goffart 说。

[垃圾收集器语言](https://thenewstack.io/google-cloud-engineer-kathryn-s-mckinley-on-leadership-mentoring-garbage-collection-and-rust/)监控内存分配并回收不再需要的已分配内存块。JavaScript、C#和 Java 都是垃圾收集器语言的例子。

Slint 编译应用程序，使其在嵌入式设备或 [Linux](https://thenewstack.io/rust-in-the-linux-kernel/) 、 [Mac](https://thenewstack.io/apple-disposing-traces-of-intel-in-mac-with-new-chip-os/) 和 [Windows](https://thenewstack.io/kubernetes-for-windows/) 桌面上运行。

## Slint 如何工作以及为什么要嵌入它

Slint 是用 Rust 实现的，但是它的 API 是用一种特定领域的语言编写的，叫做 Slint 语言。然后有一个 API 连接到支持的语言库。

“如果你只懂 C++，就不需要关心 Rust。如果你只懂 JavaScript，你就不需要关心 Rust，”他说。

SixtyFPS GmbH 选择进入嵌入式领域，因为这里的竞争比 web UI 领域要少。他们认为，这无疑也更有利可图。Goffart 解释说，该工具旨在工作在[嵌入式设备](https://thenewstack.io/an-introduction-to-using-linux-in-embedded-systems/)的“真正低端”，这些设备往往具有较低的计算能力。

“嵌入式有不同的层次——有一种非常便宜的微处理器，只能运行编译好的代码，没有太多内存，然后是高端嵌入式，有时甚至比个人电脑更强大，”他说。“随着我们规模的扩大，我们也可以支持越来越多的计算机，这些计算机要么根本不完美，要么甚至有硬件加速器——因此，任何可以显示用户界面的东西。”

他说，在高端嵌入式方面，该工具“可以轻松支持 JavaScript”。事实上，业内一些人已经通过在嵌入式系统上安装浏览器来使用 JavaScript 了，他补充道。所以对于 Slint 团队来说，使用 JavaScript 是有意义的，但没有浏览器的额外负担。

## 为什么是台式机？

Goffart 说，现在有一种趋势，即使用浏览器作为基础来创建像桌面应用程序一样运行的网页。对于 Slint，该团队希望在桌面上启用一个看起来像本地人的用户界面。

“我们想提供一种方法来制作一个不在浏览器中的用户界面，所以它是原生的，看起来像一个真正的计算机应用程序，而不是一个网站，”Goffart 说。“我们认为原生样式很重要，这样所有的控件看起来都像操作系统的控件。”

现在，工具团队专注于开发人员创建 UI 所需的东西。

SixtyFPS GmbH 的联合创始人西蒙·豪斯曼(Simon Hausmann)说:“如果你让显示面板成为某个工厂里弯曲金属的工业机器的控制面板，你不会雇佣一个机构来为它创造一个漂亮的设计。“你要让自己或(你的)开发人员尽可能容易、尽可能快地实现这些功能。当然，它应该是可用的，而且应该看起来很体面，但你不会太关注设计方面。”

在未来，这可能会改变——他们的计划是让 Slint 成为一个设计者和开发者一起使用的工具。

“我们不仅要瞄准软件开发人员，还要瞄准设计人员；这样设计人员和软件开发人员就可以更容易地合作，把重点放在嵌入式设备或笔记本电脑上运行的应用程序等产品上。

Slint 是双重许可的，这意味着开发人员可以根据 GPL 版本 3(一种开源许可)或专有许可(允许在所有者不希望其源代码可用的产品中使用 Slint)对其进行许可。通过购买副本或参加 Slint 的大使计划，开发者可以获得免费的专有许可证，用于标记使用 Slint 构建的应用程序。竞争对手包括自由产品公司和豪斯曼之前工作过的 [QT](https://www.qt.io/) 。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>