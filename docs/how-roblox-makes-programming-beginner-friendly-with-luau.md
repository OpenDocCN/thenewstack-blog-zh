# Roblox 如何让编程初学者对 Luau 更友好

> 原文：<https://thenewstack.io/how-roblox-makes-programming-beginner-friendly-with-luau/>

自 2006 年以来，超受欢迎的在线游戏平台 [Roblox](https://www.roblox.com/) 及其游戏创作系统 Roblox Studio 已经被儿童和所有年龄段的人使用。Roblox Studio 是由初学者常用的轻量级多范例编程语言 [Lua](https://en.wikipedia.org/wiki/Lua_(programming_language)) 的修改版本实现的。Lua 主要是为嵌入到其他应用程序中而设计的，与广泛使用但更好地用于 web 开发的 JavaScript 相比，它是游戏玩家学习脚本的好选择。

Roblox 开始在其平台中使用 Lua 5.1，使玩家能够在安全的环境中开发和分享自己的游戏。但随着 Roblox 内部代码库的增长以及用户需求的日益复杂，该公司决定对 Lua 进行升级。Roblox 没有重写和改变主语言，而是推出了一个继任者: [Luau](https://luau-lang.org/) 。2021 年 11 月，为了促进协作和鼓励其他社区参与，Roblox 选择开源 Luau。

由于 Roblox 的市场面向儿童，人们自然会认为它的编程语言 Luau 很容易学。然而，对一个人来说很容易的事，对另一个人来说可能出奇的棘手。对于刚开始接触编程的人来说，Luau 是个好选择吗？Roblox 的高级教学设计师 Genevieve Johnson 向新堆栈展示了 Roblox 的教育游戏风格。

## **Lua 与 Python 的对比**

“Roblox Studio 和 Lua 是一个很好的基础语言，适合初学编码或寻找比可视化编码环境(如 MIT Scratch)更大挑战的学生，”Johnson 说。“Lua 与 Python 非常相似，它非常轻量级，可读性很强，但 Lua 比 Python 更宽容。空白，或缩进，通常是新程序员的克星。Python 中出现一个缩进错误，你的脚本就无法运行。有了 Lua，你仍然希望对你的代码使用良好的组织，但是你不会因为错过一个缩进而受到惩罚。”

Roblox 从 Lua 5.1 开始是有原因的。它宽容、简单、直接。但是夏威夷宴会呢？

“对于初学者来说，学习 Luau 语言很容易，”Johnson 说。“我们对 Lua 5.1 进行了小规模的生活质量扩展，但总体体验是相似的。对于已经学习了这门语言的程序员来说，差别更大。对于更有经验的程序员来说，Luau 提供了额外的功能，让他们更容易写出正确的代码。”

“也就是说，”她继续说道，“让初学者和有经验的程序员都更容易的一个重要因素是，我们拥有丰富的工具，可以在编写代码时自动标记常见错误。这是集成到 Roblox Studio 中的，但也可以集成到其他编辑器中。因此，即使这种语言很容易学习，拥有一个帮助您编写正确代码的强大集成环境也会让它变得更容易。”

## **rob lox 的 Luau 与竞争对手有何不同**

一款可以与 Roblox 相媲美的产品是《我的世界》，这是另一款允许玩家编写游戏脚本的多人游戏构建平台。使用 JavaScript，《我的世界》脚本引擎让用户修改他们游戏的内部运作。

Roblox 和《我的世界》中脚本的关键区别在于两个游戏的构造方式。有了 Roblox，你可以分享你的创作，访问其他玩家的游戏。《《我的世界》》更像是一款单人游戏，你可以在其中编写模块，为游戏环境增加更多的维度。

即使《我的世界》看起来更简单，Roblox 仍然被广泛认为是初学者学习编码最容易的游戏。Lua 比 JavaScript 容易学得多，Roblox 基于社区的游戏平台让玩家有机会向其他创作者学习。

## **边玩边学**

对于初学者来说，创建和分享游戏不仅有趣，还能帮助他们学习。Roblox 致力于[教孩子和新手学习编码](https://www.techradar.com/news/teaching-children-to-code-and-program-with-roblox)并不令人惊讶，因为它的创始人[戴夫·巴斯祖基](https://www.linkedin.com/in/davidbaszucki/)曾经有一个面向儿童的教育编码平台业务，名为*知识革命*。知识革命在 1998 年被 MSC Software 收购，但这对于被 Roblox 用户称为“builderman”的 Baszucki 来说只是一个开始。

> “Roblox 的使命是到 2030 年支持 1 亿学生在我们的平台上学习。”

-Genevieve Johnson，Roblox 高级教学设计师

2006 年，Roblox 诞生了。有无数的研究表明，通过玩耍学习对孩子来说有多重要，可以肯定地说，成人也可以从同样的学习模式中受益。

关于寓教于乐的话题，Genevieve Johnson 告诉我们，这一直是 Roblox 的首要目标。“Roblox 的使命是到 2030 年支持 1 亿学生在我们的平台上学习，”她说。她也有一些想法，为什么 Roblox 对学习编码的孩子如此有益。

“我真的认为这是通过代码看到一个静止的、没有生命的世界瞬间变得有生命的视觉因果。只需几行代码，一个无聊的灰色部分就变成了一个五彩纸屑炸弹，或者一个可以呼叫电梯的按钮，或者一个跳跃垫。这些事情让初学者看到，编码可以成为他们创造力的一个出口，也是一项激发实验的活动。”

约翰逊补充说，有了 Roblox Studio，“任何人都可以跳进去开始创作，你可以邀请你的朋友在一个协作的实时环境中加入你。”

Roblox 受到初学编码的人的喜爱也就不足为奇了。毕竟，当你积极参与时，更容易记住信息。此外，说到编码，你永远不能太早开始。高达 77%的美国父母希望他们在上学的时候就学会编程。

Lua 通常被认为是孩子们的[完美编程语言](https://medium.com/turing-ninjas/the-double-edged-programming-language-lua-easy-for-kids-to-learn-and-also-powerful-enough-for-ca772e24a32b)，简单而强大。Roblox 的 Luau 只是一种已经对初学者友好且易于使用的脚本语言的延续，具有更高的安全性和复杂性。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>