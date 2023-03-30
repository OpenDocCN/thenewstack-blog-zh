# 反应本土和“一次学习，随处写作”的新梦想

> 原文：<https://thenewstack.io/react-native-learn-write-anywhere/>

由脸书创建，目前被网飞、Airbnb、Dropbox、[以及许多其他公司](https://github.com/facebook/react/wiki/Sites-Using-React)使用的 [React](https://thenewstack.io/javascripts-history-and-how-it-led-to-reactjs/) JavaScript 框架提供了一种创建用户界面的新方法，是最热门的新 web 前端技术之一。现在，有了[的 React Native](https://facebook.github.io/react-native/)——现在可用于 iOs 和 Android——好奇的移动开发者可以开始了解 React 为何如此特别。此外， [React Native](https://facebook.github.io/react-native/) 可以被经验丰富的 web 开发人员用来开发快速移动应用程序，现在他们有了另一个方便的工具来实现这一点，同时可以保留他们当前的大部分技能。

## **写一次就到处跑的梦想**

从 Java 到 C# Xamerian，编写跨多个平台工作的单一代码库的能力一直是移动开发的圣杯。此外，许多开发人员在 web 开发工具链方面比在移动开发工具链方面更有经验，他们不愿意花费大量的时间和精力去学习“另一个框架”

但许多人发现，“一次编写，随处运行”的模式充其量更接近于“一次正确，随处调试”，而在最坏的情况下，只能在系统之间传递很少的应用程序逻辑和代码。

一些现有解决方案的另一个主要限制是缺乏对底层硬件 API 的适当访问，如 GPS、倾斜和多点触摸功能。最后，许多当前的跨平台移动框架遭受了巨大的性能损失。

即使在最好的情况下，普通的 web 开发人员在转向移动开发时也会经历大量的摩擦，最终往往会开发出不合格的移动应用程序。

## **重新定义梦想**

虽然任何开发人员都希望他们的代码可以在任何地方运行，但这是一个很难解决的问题。这在某种程度上是对实际潜在问题的变通解决方案:大多数开发人员希望能够将他们的技能集从一个环境带到另一个环境，而不希望从头开始学习一切，只是为了针对另一个平台。

虽然这仍然是一个困难的问题——也许不像简单地让一个代码库在任何地方运行那样理想——但这是一个容易解决的问题。有了 React Native，新的模式就是“一次学习，随处编写”有了这种方法，一个有经验的 web React 开发人员可以开始运行，并以更快的速度编写 Android 或 iOS 应用程序。

目前，React web 应用、Android 和 iOS React 应用之间几乎没有代码共享。随着时间的推移，脸书希望允许目标平台之间的代码共享。为了理解这是如何实现的，我们可以看看 React for web 是如何被分成两个包的:React 和 React DOM。

## **不是关于 DOM**

从本质上讲，React 与文档对象模型( [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) )无关，它是浏览器解释网页的标准 HTML APIDOM 只是 React 如何为 web 创建的一个实现细节。

在 React 中编程时，理想情况下不需要对实际的底层 DOM 做任何工作；相反，人们呆在 [React 的虚拟世界](https://facebook.github.io/react/docs/glossary.html)中，让它弄清楚如何将其转化为真实的世界。

对于那些不熟悉 React 的虚拟 dom 的人来说，虚拟 dom 是 DOM 的轻量级抽象描述。实际的 dom 很重，是一个资源猪，而 React 的虚拟 DOM 是由轻量级的 JavaScript 对象组成的。应用程序 dom 中的每一个变化都会生成一个新的虚拟 DOM，并与之前的迭代进行比较，而不是直接进入 DOM。这种差异然后被应用于实际的 DOM。

这种方法是有效的，因为 React 只需要最少量的实际 DOM 操作就可以将我们带到这种新状态，即使从概念上来说，我们可以将它看作是随着应用程序的每次更改而重新生成整个 DOM。这允许开发人员以一种不可变的方式轻松地推理应用程序状态，同时获得对可变文档结构进行小的更改所带来的所有性能优势。

## **但是 iOS 和 Android 呢？**

考虑到这一点，这与 React 与 DOM 无关的大背景有什么关系呢？想象一下，代替 DOM，我们正在编写一个由 iOS 组件组成的应用程序，或者更抽象地说，一个平台的任何一组 UI 小部件。我们仍然可以将应用程序描述为一系列嵌套的组件，我们将在其中定义我们的“伪”组件，这些组件最终解析为实际的 UI 小部件或 DOM 元素。例如，假设我们有一个相当典型的导航应用程序。官方 [React Native](https://facebook.github.io/react-native/) 站点为此提供了一个 iOs 代码示例:

```
import React<span class="token punctuation">,</span>  <span class="token punctuation">{</span>  
  Component<span class="token punctuation">,</span>  
  TabBarIOS<span class="token punctuation">,</span>  
  NavigatorIOS  <span class="token punctuation">}</span>  from  <span class="token string">'react-native'</span><span class="token punctuation">;</span>  

class  <span class="token class-name">App</span>  extends  <span class="token class-name">Component</span>  <span class="token punctuation">{</span>  
  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span>  <span class="token punctuation">{</span>  
    <span class="token keyword">return</span>  <span class="token punctuation">(</span>  
      &lt;TabBarIOS<span class="token operator">&gt;</span>  
        &lt;TabBarIOS<span class="token punctuation">.</span>Item title<span class="token operator">=</span><span class="token string">"React Native"</span>  selected<span class="token operator">=</span><span class="token punctuation">{</span><span class="token boolean">true</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>  
          &lt;NavigatorIOS initialRoute<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">{</span>  title<span class="token punctuation">:</span>  <span class="token string">'React Native'</span>  <span class="token punctuation">}</span><span class="token punctuation">}</span>  <span class="token operator">/</span><span class="token operator">&gt;</span>  
        &lt;<span class="token operator">/</span>TabBarIOS<span class="token punctuation">.</span>Item<span class="token operator">&gt;</span>  
      &lt;<span class="token operator">/</span>TabBarIOS<span class="token operator">&gt;</span>  
    <span class="token punctuation">)</span><span class="token punctuation">;</span>  
  <span class="token punctuation">}</span>  
<span class="token punctuation">}</span>

```

和“对等”的 Android 版本:

```
import React<span class="token punctuation">,</span>  <span class="token punctuation">{</span>  
  Component<span class="token punctuation">,</span>  
  DrawerLayoutAndroid<span class="token punctuation">,</span>  
  ProgressBarAndroid<span class="token punctuation">,</span>  
  Text  <span class="token punctuation">}</span>  from  <span class="token string">'react-native'</span><span class="token punctuation">;</span>  

class  <span class="token class-name">App</span>  extends  <span class="token class-name">Component</span>  <span class="token punctuation">{</span>  
  <span class="token function">render<span class="token punctuation">(</span></span><span class="token punctuation">)</span>  <span class="token punctuation">{</span>  
    <span class="token keyword">return</span>  <span class="token punctuation">(</span>  
      &lt;DrawerLayoutAndroid renderNavigationView<span class="token operator">=</span><span class="token punctuation">{</span><span class="token punctuation">(</span><span class="token punctuation">)</span>  <span class="token operator">=</span><span class="token operator">&gt;</span>  &lt;Text<span class="token operator">&gt;</span>React Native&lt;<span class="token operator">/</span>Text<span class="token operator">&gt;</span><span class="token punctuation">}</span><span class="token operator">&gt;</span>  &lt;ProgressBarAndroid  <span class="token operator">/</span><span class="token operator">&gt;</span>  
      &lt;<span class="token operator">/</span>DrawerLayoutAndroid<span class="token operator">&gt;</span>  
    <span class="token punctuation">)</span><span class="token punctuation">;</span>  
  <span class="token punctuation">}</span>  
<span class="token punctuation">}</span>

```

虽然这些应用程序有不同的底层组件，Android 有 DrawerLayout，iOs 有 TabBarIos，但这两个应用程序的总体结构看起来非常相似，即使对不熟悉 React 或移动开发的开发人员来说也是如此！这是一个重大的胜利，因为它不仅允许开发人员利用两个应用程序大致相同的技能，而且使从一个平台移植到另一个平台变得更加简单。移植过程主要是将一个组件的一个版本换成另一个版本，而不是可能(很有可能)从头开始重新设计应用程序。但是，总体组件层次结构设计将基本保持不变。

左右两边的公司都在他们的应用程序中采用 React Native 。React Native 是一种潮流还是我们许多人一直在等待的跨平台解决方案还有待观察，但 React Native 迄今为止已经有了一个良好的开端！

通过 Pixabay 的特征图像，根据 cc0 授权。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>