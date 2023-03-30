# 什么？NET MAUI 可以为前端和 Web 开发人员做些什么

> 原文：<https://thenewstack.io/what-net-maui-can-do-for-frontend-and-web-developers/>

假设您有一个很棒的 web 应用程序，它在浏览器中运行良好，但出于某种原因，客户想要一个移动原生或桌面原生的应用程序。

输入[。NET MAUI](https://thenewstack.io/facing-the-challenges-in-building-cross-platform-apps/) ，代表。NET 多平台应用程序用户界面。这是一个跨平台的框架，用 C#和 [XAML](https://thenewstack.io/microsoft-hones-visual-studio-cross-platform-open-source-development/) 创建本地移动和桌面应用。

微软称其为“微软 [Xamarin](https://thenewstack.io/ios-single-view-controller-app-built-xamarin/) 的下一次进化”它与 [Flutter](https://thenewstack.io/google-flutter-now-rivals-facebooks-react-in-developer-use/) 有许多共同之处，后者是由 [Google](https://thenewstack.io/tina-huang-curating-for-sre-through-lessons-learned-at-google-news/) 创建的跨平台、开源 UI 软件开发套件，它从单一代码库支持用于 [Android](https://thenewstack.io/this-week-in-programming-windows-opens-up-to-android-developers/) 、 [iOS](https://thenewstack.io/wwdc21-ios-platform-upgraded-but-what-about-the-web/) 、Linux、macOS、Windows、 [Google Fuchsia](https://thenewstack.io/this-week-in-programming-less-than-random/) 和 web 的应用程序。

微软指定[。NET MAUI 是为那些想要:](https://learn.microsoft.com/en-us/dotnet/maui/what-is-maui)

*   从 Visual Studio 中的单个共享代码库，用 XAML 和 C#编写跨平台应用程序。
*   跨平台共享 UI 布局和设计。
*   跨平台共享代码、测试和业务逻辑。

但这忽略了一点。NET MAUI 将允许前端和网络开发人员将他们的网络应用程序变成一个接近金属的移动或桌面应用程序，可以在 Windows 或 Mac 上运行。 [NET Dev 显示](https://www.youtube.com/playlist?list=PLvmaC-XMqeBaqRbDn0cY9dVZEIt-Yu7HB)在[上抽动](http://www.twitch.tv/codeitlive)。还不支持 Linux。网毛伊岛。

进步已经与。NET 毛伊岛和微软从“零日”巴苏说，并已使用。NET MAUI 来构建 iOS 和 Android 应用商店中的应用程序。进步提供了什么。NET MAUI 是一个完美的性能 UI，因此开发人员不必硬编码所有的 UI。它的 [Telerik DevCraft](https://www.telerik.com/devcraft?_ga=2.236844418.245467704.1663598760-389870001.1661174558) 包括用于。网毛伊岛。

“如果您的客户希望在桌面或移动设备上看到相同的体验，那么这是一个简单的方法；同时也是为了开发者不要重新发明轮子，想出一个全新的 UI 和全新的体验，”Basu 上周在 Progress Software 的开发者大会 [Progress 360](https://thenewstack.io/progress-360-how-panera-fixed-its-application-validation-gap/) 上告诉 TNS。

他说，原生应用具有原生用户界面、确保速度的原生性能，以及对所有设备 API 的原生访问。对于苹果产品来说，原生意味着应用在 [Swift](https://thenewstack.io/lessons-swift-designer-chris-lattner-has-learned-about-leadership/) 或[Objective C](https://developer.apple.com/library/archive/documentation/Cocoa/Conceptual/ProgrammingWithObjectiveC/Introduction/Introduction.html)；对于 Android 来说，意味着 Java 或者 Kotlin。当然，对于 Windows，这意味着。网，他解释道。

“对于企业来说，这很难，因为你现在必须为一个应用程序维护三个不同的代码库，”他说。“所以，理想情况下，现在我们正在寻找跨平台的解决方案，我可以拥有一个可以在任何地方运行的单一东西。”

除了为 Windows 转换应用程序之外，NET MAUI 利用 [Mac Catalyst](https://developer.apple.com/mac-catalyst/) 将应用程序转换到 iOS 的能力。

## 带来了。NET 和 JavaScript 世界越来越近

什么？网毛伊岛确实带来了。他补充道，NET 和 JavaScript 的结合更加紧密了。

“它使用了一个叫做网络视图的小东西，本质上是一个浏览器组件，”他说。“如果你投资了 JavaScript 或任何你正在用 [Angular](https://thenewstack.io/google-launches-organization-to-protect-trademarks-for-istio-angular-and-other-open-source-projects/) 或 [React](https://thenewstack.io/typescript-vs-react-js/) 或 [Vue](https://thenewstack.io/meet-vue-js-flexible-javascript-framework/) 做的现代网络，它们现在都可以在桌面和移动设备上运行。”

虽然已经有了将 web 应用程序转换为移动应用程序的单页面框架，但这些选项不允许开发人员利用移动平台的一些原生功能，例如手机上的摄像头或加速度计。此外，单页框架应用并不总是被允许出现在应用商店中，他补充说，这可能会限制应用的曝光率。

“你不在应用商店里，你不能访问所有的设备，比如你知道的相机、地理位置、加速度计，以及我们所有的设备 API，”他说。“那是你从哪里得到的东西。网毛伊岛，差不多免费。”

他补充道: [JavaScript](https://thenewstack.io/javascript-hydration-is-a-workaround-not-a-solution/) 仍然在网络外壳中。。NET MAIU 允许开发人员将 Angular 或 React 应用程序与针对性能优化的运行时捆绑到桌面或移动应用程序中，因为它允许开发人员挑选应用程序需要的内容，并仅将其与应用程序捆绑在一起。

“运行时真正迎合了应用程序和具体的事情。所以它只给你你需要的东西。所以这就是他们保持小规模的方法，”巴苏说。

通过使用。NET MAUI，代码将捆绑 web 应用程序所需的本质，但代码是成对的，以便运行得更快。他解释说，相比之下，Electron 将所有的东西——HTML、CSS、JavaScript——所有的网络资产打包到一个 shell 中，以 Node.js 作为运行时。他提到了 Slack 和其他电子应用程序，并补充说，电子是经过战斗考验的，但它可能会很重。

“电子让你可以在桌面上做你可能不需要的事情。移动设备上的电子设备并不真的工作得很好，因为它是一个很大的应用程序包。他说:“电子产品主要是用于桌面。”。

与。NET MAUI，转换不会使应用程序依赖于 Node.js，允许它以更小的占用空间创建更原生的体验。

“我们只能依靠。NET 来引导我们的应用程序，”巴苏解释道。“因为我们不支持浏览器组件，因为我们不支持运行时，所以它的重量更轻，加载速度更快。只要你的设备上有通过移动或桌面的浏览器，你就应该是好的。”

## 怎么会。净毛伊岛不同于替代品

他补充说，其他选择包括使用 React Native 和 NativeScript。

“这些平台将让开发者编写 web 内容，然后最终转而编写原生移动应用，”他说。“对于。NET 开发者，这就容易多了。”

正如开发人员中介公司 Protovate 的技术项目经理 Vince Giacoppo 所详述的，它在一些方面也与 Flutter 有所不同。贾科波指出。NET MAUI 不支持 web，但是“开发者可以利用 Blazor 框架来提供使用 MAUI 资源的桥梁。”

现在还为时尚早。网毛伊岛，巴苏提醒道。

他说:“我们有企业和公司开始使用它，并把它作为编写下一个跨平台应用程序的一种方式。”

*披露:Progress Software 支付了 Loraine Lawson 参加其在波斯顿的会议的费用。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>