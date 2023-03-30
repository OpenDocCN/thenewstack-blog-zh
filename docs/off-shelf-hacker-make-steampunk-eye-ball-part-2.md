# Off-The-Shelf Hacker: How to Make A Steampunk Eyeball - Part 2

> 原文：<https://thenewstack.io/off-shelf-hacker-make-steampunk-eye-ball-part-2/>

Building a new project is a lot of fun, but it can also be daunting.

Even a small project, like my new [Steampunk Eyeball](https://thenewstack.io/off-shelf-hacker-make-steampunk-eyeball/) endeavor, offers many options and a fair number of “moving” parts. In this sense, think of “moving parts” as the different subsystems, firmware/software, and processes needed to turn the pile of parts into a working device.

Here, the moving parts include the eyeball sphere itself, the eyeball pivoting and tilt servo mechanisms, the Pixy camera and it’s mounting inside the sphere, the base, and pan servo parts, plus a whole host of other incidental bits and pieces. There’s also the software used on a Linux notebook to setup and run firmware on the Pixy, monitoring software, electronic connections and power. When you think about it, the Eyeball has most of the elements of the physical computing stack.

Yup, there’s a lot to it. If it were that easy, a fifth grader could do it.

Before we get too deep, let’s review the homework assignment from [last week’s Off-The-Shelf Hacker column](https://thenewstack.io/off-shelf-hacker-make-steampunk-eyeball/). Did you pick a cool part for your project? Did you start a little project notebook and jot down your ideas? What about your theme? Great. Keep up the good work.

With that out of the way, I want to cover how I arrived at the major design decisions for the Steampunk Eyeball. We’ll also look at a few fabrication issues and solutions, that surfaced, as I started the build.

No fifth graders here.

## **Perspective Vision**

My steampunk eyeball “want” list is pretty straightforward.

*   Use the Pixy camera
*   Make it unique so it attracts attention at conferences
*   Make it fun for the readers and audiences
*   Build something cool
*   Make it move
*   Give it a strong steampunk look

Notice anything missing? How about the main driver for having a steampunk eyeball with a Pixy camera inside, in the first place?

Purpose: I’d like the audience to be impressed with a physical computing device that tracks me as I walk around during one of my tech talks.

Having a vested interest in your ideas sometimes causes you to assume that everybody else understands the big picture, without you coming right out and saying it. Clearly expressing your project vision, is important. Yes…I wasn’t clear.

A great way to keep perspective and not gloss over important points is to write out your “want list” in one sentence, which is what I did. Here’s what I want the thing to do: Build a moving steampunk device, that’s fun, attracts attention at conferences and tracks me as I move around the stage, using the Pixy camera video processing capability.

## **Deciding How To Get There**

You could plan everything out in minute detail, then fab.

我更喜欢“构建、破解、修改、重复”的方法，基于我最终想要什么的总体愿景，就像一句话的总结。我对自己的 fab 技能有足够的信心，知道自己可以修复、适应或纠正任何问题。我通常对小项目进行快速的心理风险/收益测试，而不是冗长的分析。

更大的项目需要更多的计划、分析和设计讨论，特别是如果是团队工作的话。我也倾向于过多考虑选项，很难做出“纸上决策”，因此拖慢了项目的进度。对我来说，在我的小型快速原型项目中使用“构建、破解、修改、重复”的方法效果更好。

不管 fab 和开发方法如何，做出设计决策和设置优先级仍然很重要。

对于这个项目来说，除了眼球可以在某种支架上旋转之外，其他什么都不重要。为了获得逼真的效果，Pixy 还需要安装在眼球球体内部，这样当我在设备前面走动时，固件可以正确计算如何移动伺服系统来跟踪我。让它发挥作用是当务之急。

到目前为止，这些是主要的设计决策和推理:

## **进入下一步**

下周，我们将讨论制造半环和伺服装置的细节。我们甚至可以测试小精灵是如何追踪一个彩色斑点的。我很期待看到眼球动起来。

不要忘记在笔记本上记录您的项目风险/收益分析和设计决策。想想看，你可能想把你的项目放在 [Instructables](http://www.instructables.com/) 或者其他创客网站上。有笔记会让写你的故事(或者在会议上告诉每个人……提示……提示)变得容易。

下周见。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>