# 测试版解决方案帮助前端开发者开发本地移动应用

> 原文：<https://thenewstack.io/beta-solution-helps-frontend-developers-make-native-mobile-apps/>

帮助企业构建内部应用的 Retool 正在提供一种新的低代码解决方案的测试版，该解决方案可以帮助开发人员仅使用 SQL 和 JavaScript 创建定制的原生移动应用。

Retool 的产品经理 [Sean Ren](https://www.linkedin.com/in/shawiz/) 解释说，这个名为 [Retool Mobile](https://retool.com/products/mobile) 的解决方案针对的是前端和 web 开发人员，他们希望利用本地移动功能，但不想为此学习一门新语言。通常，前端开发人员可以部署为单个网页应用程序，但这种方法不允许访问原生手机功能，例如相机。

“我们提供了一个非常独特的角度来挖掘原生应用程序，以及低代码，这给了你大量的灵活性，以及你的应用程序上的所有原生功能，”任说。“市场上也有类似的产品，但其中大多数要么是无代码的——因此它们不会给你提供代码访问或与你自己的数据库的连接——要么是一款网络应用。”

Retool 发言人 [Michael Selvidge](https://www.linkedin.com/in/michaelselvidge/) 强调，尽管代码很低，但该工具是为专业开发人员而非普通开发人员设计的。Retool 最近被列在 Gartner 低代码魔力象限中，作为专业开发人员的利基解决方案。

一般来说，移动应用程序要么以苹果语言部署，如 [Objective C](https://thenewstack.io/objective-cs-roots-in-the-life-of-brad-cox/) 或 [Swift](https://thenewstack.io/apple-highlights-swift-enhancements-at-wwdc22/) ，要么以安卓语言部署，如 [Java](https://thenewstack.io/javas-history-could-point-the-way-for-webassembly/) 或 [Kotlin](https://thenewstack.io/kotlin-multiplatform-mobile-from-jetbrains-takes-on-flutter/) 。这意味着如果可能的话，经常需要雇佣一个对两个平台都非常熟悉的移动开发者，否则就雇佣两个开发者。Ren 说，通过支持更常见的语言 JavaScript 和 SQL，更多的开发者将能够开发移动应用。

他说:“我们真正支持的是(为)大多数能写一点 JavaScript 和 SQL 的开发人员，这对大多数开发人员来说是非常基础的。”。

## 为什么对开发者来说代码低？

像 [Flutter](https://thenewstack.io/google-roadmap-flutter-to-integrate-with-javascript-wasm/) 这样可以用于部署到移动设备上的替代品，需要开发者学习 [Dart](https://thenewstack.io/dart-frog-a-frontend-language-moves-to-the-backend/) ，它越来越受欢迎，但仍然不如 JavaScript 那样广为人知。Ren 说，Retool 的低代码方法为开发者提供了一个拖放的起点，然后可以用代码进行调整，从而使开发变得更加容易。他补充说，这将提高程序员的生产率。

Retool Mobile 没有在 [IDE](https://thenewstack.io/2023-hotness-cloud-ides-web-assembly-and-sboms/) 中编写所有代码，而是提供了一个可视化编辑器，组件可以通过拖放来组装，然后通过一些事件处理程序连接到数据库。

“我们提供了 UI Builder，这是一个拖放式的构建器，您可以在屏幕上快速组装一系列预构建的组件。因此，这进一步减少了你开发应用程序的时间，”任说。“这是更高层次的抽象。它将 UI 和组件打包在一起。你所要做的就是组装用户界面，并将数据连接到可视化界面上。”

## 预先构建的集成

Retool Mobile 内置了对几十个原生移动组件的支持，以及预构建的布局。它还连接到大多数数据库，包括 PostgreSQL、MySQL、MS SQL 和 MongoDB。

他说，“你可以连接到你的产品上已经有的任何现有数据库，所以你不必在你自己的数据库和你的应用程序上的这些数据之间保持同步。”“如果你没有数据库，你可以随时使用 Retool dB 创建一个全新的数据库，它在幕后是一个 Postgres 数据库，你可以在用户界面上直接编辑数据库，类似于 [Airtable](https://www.airtable.com/) 或 [Google Sheets](https://thenewstack.io/how-to-use-google-sheets-as-a-database-with-react-and-ssr/) 。”

Retool Mobile 还支持第三方 API 集成，如 Firebase 或 Twilio。他补充说，它还包括一些 JavaScript 实用程序库，如 Lodash，Moment 和 numbro，并支持原生 JavaScript APIs。该解决方案允许开发人员部署到 web、Android 和 iOS。

该公司还在开发一个白色标签功能，允许开发人员以公司名称推出自己的应用程序，并附上公司的标志。如果需要，这个白标产品将允许开发者添加额外的库。

重新设计的应用程序也可以支持移动硬件功能，如地理定位、相机、NFC 和 QR 码/条形码扫描仪。Retool Mobile 提供了预建的 Zebra 集成，这是一项测试功能，允许工作人员在 Zebra 设备上安装应用程序，并使用内置的 Zebra 扫描仪和传感器。

## 支持远程离线应用

另一个重要的支持功能是离线能力，任说。

“在这些远程工作环境中，离线是一个非常普遍的要求，当他们在现场时，有时互联网非常不稳定，”任说。“它允许你缓存当你有互联网时获取的信息，这样当你远程访问时，你仍然可以读取相同的权限。我们还允许您在设备离线时在本地缓存编辑内容。您编辑的信息将被同步回服务器，以便您可以在远程进行读写操作；当您回到互联网时，这些信息将能够返回到服务器并进行同步更新。”

它支持的一些用例是库存管理、站点检查和文件销售更新，这在一定程度上要归功于内置的 Salesforce 集成和过滤。Retool 表示，迄今为止，其测试版移动解决方案已被用于部署超过 10，000 个应用程序，亚马逊、T2、DoorDash、NBC 和 T4 Stripe 等公司使用它来部署解决内部工作流程的应用程序。测试版可供最多五人的团队免费使用。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>