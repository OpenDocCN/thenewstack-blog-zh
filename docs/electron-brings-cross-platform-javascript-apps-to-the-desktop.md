# Electron 将跨平台的 JavaScript 应用程序带到了桌面上

> 原文：<https://thenewstack.io/electron-brings-cross-platform-javascript-apps-to-the-desktop/>

JavaScript 作为一种脚本语言，已经走过了漫长的道路。最初， [JavaScript](/tag/javascript/) 只在网络浏览器中使用——有点勉强——因为 JavaScript 是浏览器唯一本地支持的选项，可以用于简单的任务，比如创建幻灯片。

从那时起，这门语言已经走过了漫长的道路。这种变化的第一个主要催化剂是大量强大的基于浏览器的 JavaScript 库和框架，如 Angular、 [Ember](http://emberjs.com/) 、 [d3](https://thenewstack.io/visualizing-data-web-d3-js/) 和 React。JavaScript 的另一个重大转折点是 [Node.js](/tag/node.js/) 的引入，它允许 JavaScript 除了在客户端运行之外，还可以用作服务器端语言。此外， [es6/es2015](https://thenewstack.io/ecmascript-6-biggest-update-javascript-yet-start-rolling-annual-improvements/) 让这种语言对许多开发者来说更加舒适。

没有人能确切地说出它是如何发生的，但是现在 JavaScript 比以往任何时候都更接近成为“统治一切的一种语言”或者，不那么夸张地说，是一种可以在每个平台上运行的语言。除了 Node 带来的上述服务器端功能，JavaScript 也是移动场景中的一个活跃参与者，无论是通过基于 web 的解决方案，如 [PhoneGap](http://phonegap.com/) ，还是越来越受欢迎的原生解决方案 [React Native](https://thenewstack.io/react-native-learn-write-anywhere/) 。即使在物联网和微控制器领域，JavaScript 也通过一个名为 [Johnny-Five](http://johnny-five.io/api/) 的项目存在。

有点讽刺的是，JavaScript 覆盖的最后一个领域是传统的桌面应用程序。

直到电子出现。 [Electron](http://electron.atom.io/) 项目实际上是开源 Github 的温床，它使你能够使用 JavaScript 和 Node 编写桌面应用程序。

## 为什么是电子？

在看电子背后的“如何”之前，让我们先来探究“为什么”像电子这样的东西是可取的。尽管 web 和移动应用变得越来越强大和普及，桌面应用仍然有许多优点和使用案例。从增强的离线支持，到较低级别的 API，再到在 windows 菜单或 MacOs dock 中有一个插槽，能够通过桌面上的应用程序“alt-tab”的魔力是基于 web 的应用程序无法模仿的。

electronic 的另一个强大用例是能够利用现有的开发人员技能集。如今，制作桌面应用程序已经是一门失传的艺术了；与桌面编程 API 的知识相比，现在有更多的开发人员对 web 栈有很深的了解。

虽然拥有“最适合工作的工具”是有价值的，但是简单地拥有“任何”适合工作的工具也是有价值的。电子不仅将 JavaScript 这种语言带到了桌面，还带来了 HTML、CSS，以及整个 JavaScript 生态系统。不仅所有的浏览器都在你的支配之下，而且强大而广泛的 [NPM 模块](https://thenewstack.io/the-kik-kerfuffle/)集合也在你的支配之下。最终的结果是，web 开发人员只需要很少的额外培训，就可以创建出非常漂亮的桌面应用程序。

## 跨平台优势

即使你有一些具备桌面编程知识的开发人员。Windows 的原生编程与 Linux 和 MacOs 的编程完全不同。有了 electronic，你可以编写相同的应用程序，并让它在所有三个平台上运行。

尽管编写桌面 GUI 的跨操作系统解决方案已经存在了一段时间(Java、Python 等)，但是电子化方法还有另一个好处。如今，许多应用程序都是从 web 应用程序开始的，桌面应用程序紧随其后。即使你获得了与 Java 的跨平台兼容性，你也不能重用你的 webapp 前端代码。有了 electronic，您可以在很大程度上重用所有 web 前端代码！就代码重用和生产率而言，这是一个巨大的胜利；潜在地，人们可以为 Web、Android、iOS、MacOs、Windows 和 Linux 重用相同的代码库。

[https://www.youtube.com/embed/8YP_nOCO-4Q?feature=oembed](https://www.youtube.com/embed/8YP_nOCO-4Q?feature=oembed)

视频

## 它是如何实现的

Electron 基于 Node.js，在看 Electron 之前对 Node 如何工作有一个基本的概念是有帮助的。

JavaScript 最初只适用于浏览器。不仅没有任何方法可以从浏览器外部调用 Javascript，而且即使你可以，它也不会非常有用。这是因为 JavaScript 不是通用编程语言；它的输入输出能力与浏览器紧密耦合，不可能做简单的事情，比如读写文件系统。

在浏览器环境中，这可能是最好的——我不希望任意的网站能够访问我的整个文件系统——但是对于使用 JavaScript 作为独立语言来说，这无疑是一个障碍。Node.js 所做的就是从 Chrome 浏览器中获取超级快速的动态语言 V8 运行时，并用一个全新的标准库包装它。

这个库为 JavaScript 提供了大量的底层功能，比如联网、流，当然还有对文件系统的读写。然后，电子项目采用了这个增强的 JavaScript 节点版本，并通过 Chromium content 模块将它嵌入到了 Chromium 中。

现在，乍一看，我们似乎又回到了起点:一个使用 JavaScript 编写脚本的 web 浏览器。这还不是故事的全部。实际上，这一次的最终结果是一个使用 JavaScript one 的高特权版本的 web 浏览器，它可以在浏览器中完全访问客户机。这基本上结合了传统前端 JavaScript 的所有功能，并将其与服务器端节点 JavaScript 功能相结合。Examples Electron 不仅仅是 Github 的一个附带项目。

电子为许多流行的生产就绪软件提供动力。一些流行的包括 Slack 的桌面版本，Visual Studio Code，以及另一个流行的 Github 项目——那个 [Visual Studio Code](https://thenewstack.io/microsoft-releases-cross-platform-code-editor/) 是一个名为 Atom 的分支。Atom 是一个现代的文本编辑器，它有一个非常模块化的基于插件系统的包。Atom 受欢迎的部分原因是，使用 JavaScript 或 Coffeescript(一种受 Ruby/Rails 社区欢迎的 JavaScript 语言编译器)为 Atom 编写插件非常简单。这很快为一个相对年轻的文本编辑器带来了大量的插件。下一次你在寻找一个桌面应用程序来配合你的网络展示时，一定要去看看 electronic。

即使你最终选择了真正的本土体验，电子产品快速上市的潜力也不应该被掩盖！

[https://www.youtube.com/embed/ojX5yz35v4M?feature=oembed](https://www.youtube.com/embed/ojX5yz35v4M?feature=oembed)

视频

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>