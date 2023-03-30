# Uno 将代码移植到多个平台，包括 WebAssembly

> 原文：<https://thenewstack.io/uno-ports-code-to-multiple-platforms-including-webassembly/>

更多的工具正在上线，以支持将一个代码库移植到多个平台。上周，新的堆栈分享了最新的:。网毛伊岛。

但是[。NET MAUI 是新的](https://thenewstack.io/what-net-maui-can-do-for-frontend-and-web-developers/)，带有所有潜在的问题，它不支持 Linux 或 WebAssembly。对这些问题不耐烦的开发者还有另一个选择: [Uno](https://platform.uno/) ，一个. NET 的开源 UI 平台

“从单一代码库开始，使用 C#，我们能够为所有平台创建本机应用程序。网络今天开始运行，”Uno 公司首席执行官弗朗索瓦·坦瓜伊(Francois Tanguay)说。“我们在用户界面方面的一些最大优势是，我们能够通过 WebAssembly 在 web 上运行，也可以在 Linux 上运行，例如，在 IoT(物联网)设备上运行。”

## 来自一个代码库的原生应用

Tanguay 解释说，Uno 的工作原理是基于每个平台的本地框架。他说，它将 Windows UI 作为一个 API 连接到所有的本地平台。但是它仍然使用。NET 运行时。

“我们正在利用他们正在做的所有运行时工作，包括运行时工作。Tanguay 说:“你可以在 web assembly 上为你的网络浏览器安装. NET。“我们正在利用他们正在开发的所有工具。因此，我们实际上只是另一种选择，采用不同的方法来实现跨平台 UI 框架。”

它也运行在与微软相同的[IDE 上，所以开发者可以使用 Visual Studio。](https://thenewstack.io/microsoft-launches-dev-box-preview/)

Uno 方法的一个优势是应用程序作为本地应用程序部署到每个平台。他补充说，这允许开发者将第三方供应商的特定原生组件引入每个平台的原生应用程序。

“如果您真正需要的东西不符合跨平台的模式，您可以将它纳入您针对该特定平台的跨平台解决方案中；因为你毕竟是一个本地应用，”他说。“你可以在每个平台的基础上，从第三方供应商或任何其他地方引入特定的本地组件到你的本地应用中。”

他说，基于 HTML 的转换工具将代码封装到外壳中，并在网络浏览器上运行用户界面，这是不可能的。

与单页框架应用相比，原生应用的另一个优势是原生应用可以通过应用商店部署。Twitch 上的网络开发秀，告诉 TNS。

他补充说，Uno 还提供“像素完美”的结果。这是 Uno 和的另一个区别。净毛伊岛，他说。

他说:“他们没有像 [Flutter](https://thenewstack.io/12-ways-flutter-streamlines-app-development/) 那样，试图创造一种在任何地方看起来都一样的像素级完美体验，而是采取了一种不同的方式，他们说，‘让我们保持一切都是原生的，让我们尝试将 iOS、Android、Windows 和 Mac OS 的共同点抽象出来’，让我们尝试将其抽象为一个单一的概念。”我们已经实现了它，所以它看起来像素完美，在每个本机平台上的外观和行为完全相同。"

## WebAssembly 支持

。NET 可以运行在 WebAssembly 之上。然后 Uno 可以作为 UI 框架，并使用。他解释道。基本上，它的工作方式和其他平台一样。

“这项技术让我们能够瞄准网络，但通过提供丰富的用户界面框架，而不是仅仅迎合今天的 HTML 开发者和 [JavaScript](https://thenewstack.io/javascript-build-objects-and-eliminate-looping-with-reduce/) 开发者，”他说。“它允许 C#。NET 开发者可以瞄准 Web，而不必满足于 HTML 和 JavaScript。”

这是一个很大的变化，Uno 首席营销官 Sasha Krsmanovic 补充道。

Krsmanovic 说:“WebAssembly 为大众所做的是，它使发展民主化。“在 WebAssembly 出现之前，即使你看看 W3C，看看他们的建议是什么，基本上，为了进行 web 开发，你必须使用 JavaScript。这是前进的方向，但是随着 W3C 宣布 WebAssembly 是 web 的第四种语言，这真的为所有其他编程语言的参与打开了大门。”

## 支持 Figma

Uno 还提供对流行的 Figma 设计工具的支持。Krsmanovic 说，Uno Figma 通过编写 XAML UI 代码，帮助开发人员和设计人员合作。

“对一个开发者来说，只要按钮在，就足够好了。对于设计师来说，向左两个像素和向右一个像素真的很重要，因为按钮的确切位置需要很多思考，”Krsmanovic 说。他说，有了 Uno 制作的代码，“就没有摆弄[和]没有谈判，它成为按钮[将]在哪里的唯一事实来源”。

Tanguay 补充说，这为部署应用程序的团队节省了时间。

“普通的移动应用程序需要 2500 个小时才能升级，现在我们可以把它降低到每小时 250，260 个小时，”他说。“当我们可以拥有 10 倍的工具时，我们不需要 10 倍的开发人员。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>