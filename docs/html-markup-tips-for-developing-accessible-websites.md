# 开发可访问网站的 HTML 标记技巧

> 原文：<https://thenewstack.io/html-markup-tips-for-developing-accessible-websites/>

如果你想知道你的网站到底有多容易访问，使用屏幕阅读器访问它，JavaScript 和 React 开发者和独立承包商 Cory House 建议道。

豪斯在肯塔基州路易斯维尔举办的地区开发者大会 [CodepaLOU](http://www.codepalousa.com/) 上展示了“构建可访问的网络应用”。上个月。

“有视觉障碍的人经常使用屏幕阅读器，所以如果我们真的要这么做，我们体验一下整个情况怎么样？”豪斯说。

他部署了内置于 MAC 电脑的屏幕阅读器 [VoiceOver](https://www.apple.com/voiceover/info/guide/_1124.html) ，来阅读他设计的一个简单网站。尽管它很简单，但是很难辨别页面上的图像或者用户应该在文本字段中输入什么。

House 共享的 HTML 标记，当插入到页面中时，将大大有助于使用户更容易访问它。他在网站中发现的第一个问题是什么？HTML 标签本身缺失，将其标记为英语网站。

## 转子友好体验

为了展示他的样本网站在辅助技术方面的表现有多糟糕，House 介绍了 VoiceOver 的转子。转子用于通过在链接、按钮、标题和其他导航工具之间来回移动来快速导航应用程序和网络。

“一旦我发现了 rotor，它终于让我认识到了这样一个事实，即浏览一个网站实际上可以非常快速地完成。使用辅助工具，”豪斯说。

他说，这就像用眼睛扫描标题或可点击的图像。转子内置在 VoiceOver 和其他辅助技术中，允许用户以不同的方式查看站点。为了帮助转子，请确保所有链接、标题和按钮都已命名。如果标题被适当地嵌套也是有帮助的，只有一个 H1 标题，后面跟着几个 H2 标题，如果需要的话以此类推。

## 创建地标

他说，想象一下，你被丢进华盛顿特区，那里没有地标——没有白宫，没有华盛顿纪念碑，没有任何东西可以证明它是国会大厦。

地标在转子中以同样的方式发挥作用，并识别导航和网站的其他部分。这些部分必须使用语义标记来标识。

“现在，我还想指出的是，还有一个通常会出现在转子中的部分，称为界标，”他说。“地标现在没有显示出来，因为我的网站建得太差了，没有地标。”

开发人员经常使用 *< div >* 标签，但这对辅助技术没有帮助——它基本上没有告诉用户关于页面的任何信息。相反，应该使用一个 *<导航>* 标签来定义一组导航。然后，VoiceOver 可以识别该导航，并将其识别为站点的地标之一。

另一个有用的 HTLM 标签是 *< main >* ，他说，这样用户就可以识别页面的主要内容。

> 标记越好，可访问性就越好。

<main>“When I jump onto a page, yeah, maybe I’m looking for navigation, but often I’m just looking for the main content,” House said. “When I say main content, that’s a big hint to what HTML tag is missing in our markup right now, which is *<main>*.” 

<main>

<main>Identifying what constitutes the main content might require a conversation with UX, he added.</main>

<main>
“Main content is the thing that changes on every page, and the stuff that stays the same is not main content, your header and your footer,” he said. Now, landmarks shows two items: Navigation and Main, he noted.</main>

<main>
”Notice how it highlights the navigation main, or it highlights main, if I hit enter, it’s going to take me right into that section,” he said. “So already, life has gotten better here; somebody using assistive technologies can quickly jump to the section that they’re looking forward.”

## 何时使用 ARIA

网站通常会使用放大镜来显示可用于搜索的文本框。从视觉上看，这是一个搜索框的明显标志。

这是 House 建议使用可访问的富互联网应用程序(ARIA)标签的少数情况之一。他说，虽然他可以去掉放大镜，或者在里面加上“搜索”这个词，但这可能会引起 UX 团队的抱怨。输入 ARIA 标签。

“ARIA 标签是我在没有其他方法解决问题时使用的一种东西，”House 说。

放大镜现在变成了一个标签，被辅助技术作为搜索按钮读取。

“我鼓励你，如果你还没怎么用过 ARIA，你可以出去看看所有不同的 ARIA 标签，那里有一堆标签，”他说。

## 快乐的标记，快乐的开发者

他指出，通常有更精确的 HTML 代码，开发人员可以用来提高可访问性和代码。例如，除了插入文本字段本身，开发时更好的方法是使用更具体类型的文本字段。通过在 Visual Studio 代码中点击 command，他调出了许多可以使用的其他类型的字段，包括 search。VoiceOver 会将其作为搜索文本字段读取。

他说，标记越好，可访问性就越好，但是编写更好的标记还有额外的好处。首先，其他开发人员可以通过简单地阅读标记来了解更多关于代码的信息。第二，如果开发者使用自动化测试，标记越好，编写自动化测试就越容易，因为标记为测试提供了很好的目标，他说。

“你作为一名开发人员的生活变得更容易，因为你通过编写更易访问的代码来为其他人创造更好的生活，”他说。"所以这是一个很好的良性循环."

为了获得更多关于编写可访问代码的信息，House 在 Github 上维护了一个可访问性提示列表和一个 [A11y 审计清单。](https://github.com/coryhouse/a11y)

</main>

</main>

</main>

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>