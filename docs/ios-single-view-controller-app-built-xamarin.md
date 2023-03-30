# Xamarin 内置的 iOS 单视图控制器应用程序

> 原文：<https://thenewstack.io/ios-single-view-controller-app-built-xamarin/>

创建 iOS 应用程序时，通常会使用许多视图控制器。这些是管理屏幕和控制屏幕间导航的 iOS 对象。不过，只用一个视图控制器创建一个多表单也是可能的，在本文中，我将向您展示如何实现。

完整的源代码，包括 thi sapp 的所有项目文件，都在新的 Stack GitHub 账户上。

## 这个应用程序是做什么的？

它显示一个带有几个按钮的屏幕。这些是木制按钮，一个写着“软木”，另一个写着“钙”。点击“软木”会切换到两个垂直排列的按钮，标题分别为“木材”和“Calc ”,两个按钮的背景都是软木。单击“Calc”按钮会显示一个简单的数字键盘，包括 0-9、一个小数点以及 Del 和 Send 按钮。点击这些按钮输入一个带小数点的五位数。DEL 键删除最后按下的数字或字符，SEND 弹出一个显示输入值的框，并切换回双按钮显示。

所有三个不同的屏幕都是通过重用一个视图控制器实现的。

## 该应用的架构

最小的 iOS 应用程序只需要一个 AppDelegate 和一个 UIViewController。在这个应用程序的 AppDelegate 中，它创建并设置 SingleViewController 作为根控制器，即启动事物的控制器。这是一个非常简单的类，它继承自 UIViewController 基类，并覆盖 ViewDidLoad 方法来调用 StartUp()方法。当 ViewController 第一次变为活动状态时，将调用 ViewDidLoad()方法。这里，它创建了 MainView 类的一个实例，将其分配给视图控制器的 View 属性，然后调用 MainView 实例 Start()方法。

视图控制器是应用程序的关键，如果你使用 iOS 故事板功能，你可以创建一个应用程序，为你完成大部分(如果不是全部)管理视图控制器的工作。我选择让这个应用程序 100%代码，所以没有笔尖或故事板使用。对于一个简单的应用程序来说，这是可以的，但是当你开发一些更复杂的东西时，你会感激故事板和笔尖能为你做什么。

## 景色

每个视图控制器都有一个视图，它是 UIView 的一个实例，在屏幕的矩形部分显示内容，并让用户与该内容进行交互。你可以有一个由多个视图控制器组成的屏幕，每个控制器处理它的一部分，或者你可以有一个视图控制器用于整个屏幕，就像我做的那样，有多个控件。

每个 iOS 控件都是一个视图，因为控件的类继承自 UIView。要用控件填充视图，只需创建所需的控件，并使用 view 将每个控件添加到视图中。AddSubview(控件)。这将视图添加到视图中。这个数组管理视图中的控件以及它们的显示方式。创建按钮等的所有代码都放在 lib.cs 文件中，例如 lib.GetTextureButton。

为了保持应用程序相对简单，我将所有视图代码放在 MainView.cs 中。它本来可以放在 ViewController 文件中，但最好是将视图和视图控制器分开。MainView 类是控件，继承自 UIView。在从 SingleViewController StartUp()方法调用的构造函数中，iPhone 的 UIScreen。主屏幕。传入边界；这些是屏幕的尺寸。因此，主视图控件可以访问所有屏幕，包括顶部的电池状态行、3G 信号强度等。

```
View  =  new MainView(UIScreen.MainScreen.Bounds);

```

main view 构造函数在 lib 类中缓存了一些值，特别是 FrameWidth 和 FrameHeight。这些用于计算按钮大小。因为有两个方形按钮，所以计算出的按钮大小存储在 lib 中。来自 iPhone 屏幕宽度的 ButtonWidth，用于计算水平坐标 col1 和 col2，并在放置按钮时使用它们。

## 什么是统一 API？

苹果要求所有应用程序在 2015 年 6 月前转换成统一的应用程序，即它们可以运行在 64 位或 32 位架构上。Xamarin 现在支持这一点，这个应用程序已经开发为一个。您会注意到，它使用 nint 和 nfloat 等变量类型，其中 n 代表本机，因此 nint 在 32 位架构上是 32 位，在 64 位架构上是 64 位，而 int 在两种架构上都是 32 位。iPhone 5 和更早版本使用 32 位架构，而 iPhone 5S 和更早版本使用 64 位架构。

## 撕掉它，重新开始

TidyViews()方法清除屏幕，并从三个方法 Start()、Calc()和 Cork()中调用。它删除了视图中的所有控件(更准确地说是子视图中的视图),因此可以添加新的控件。这是仅用一个视图控制器实现多个屏幕的关键机制。

```
  // Removes all controls (views) from the View
  private void TidyViews()
  {
  foreach  (var view in Subviews)
  {
  view.RemoveFromSuperview();
  }
  }

```

主视图方法 Start、Cork 和 Calc 都有一个与。NET 事件处理程序。这是一个带有两个参数的方法:object sender 和 EventArgs e。我已经在 lib.cs 中用这一行将其显式定义为委托类型 Anaction。

```
  internal delegate void Anaction(object sender,  EventArgs args);

```

lib 的参数之一。GetTextureButton 是一个操作，它使用 lambda 表达式连接到 TouchUpInside 事件。你可以在 GetTextureButton 中看到这一行。如果你不知道 C#委托或者 Lambda 表达式也不用太担心，基本都是匿名函数。下面的语法可能很难理解，但它所做的只是将传入的函数 d 添加到按钮 TouchUpInside 事件处理程序中。

```
 button.TouchUpInside  +=  (o,  e)  =&gt;  d(o,  e);

```

作为动作参数 d 传入的任何内容都成为点击的目标。在下面的代码中，在坐标(Col1，bottomy)处添加了一个带有文本“Cork”的按钮，当单击该按钮时，它会调用 Cork()方法。

```
 AddSubview(_lib.GetTextureButton("Cork",  col1,  bottomy,  Cork));

```

键盘按键使用 UIButton。标记属性来标识在 ClickButton()事件处理程序中按下了哪个键。按钮标记值被转换为 lib 中的字符串。TranslateButtonIndexToString()。如果单击了 SEND 按钮，并且有一个字符串，那么它调用 ShowValue()来使用 UIAlertController 显示该值。

## 不要混淆 iOS 委托和 C#委托

在 iOS 中，当你看到 delegate 这个词时，它意味着一个类为另一个类做一些事情，这是整个 iOS 中非常常见的模式。在 C#中，虽然委托意味着匿名函数。

## 结论

这是 ponyish 的一个小技巧，但对于创建简单的应用程序来说可能是有用的。

真实图像[通过](https://www.flickr.com/photos/75001512@N00/7864614878/in/photolist-bBnC2S-bBoAow-9KJbGj-gHeEMT-3SzWn9-9Kj3a6-5WoGuJ-5WoGqW-nLKXZ6-9gzLnQ-6pEMeU-7iEFwq-9KJaUC-5WjpVt-5WjqpK-7z6BZD-7zas45-5WoGws-e49PUQ-7zapQ3-7zapcQ-9KHMS7-ecdhVE-earsT3-eakLze-eakMEF-5WoFZS-8sPtGD-cYYd1f-cdjyHJ-cdjxhs-9isYYY-dtgma-cdjRmQ-cdjouh-bVX7uZ-bVXvMX-9gwFon-8g9fo6-9bW3Cu-9GjoHr-ebEpkH-64GBfU-61MDuv-ccqggh-7Uq6YD-5WoGo7-5Mux8Y-6bcDJ8-5WjqfX) Flickr 知识共享。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>