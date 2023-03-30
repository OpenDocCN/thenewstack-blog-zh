# 现成的黑客:在 Linux 上向 Wordpress 添加演示视频

> 原文：<https://thenewstack.io/off-the-shelf-hacker-add-demo-videos-to-wordpress-on-linux/>

展示正在进行的项目构建、结果和工作原型细节的短视频将出现在每周的现成黑客专栏中。例如，你可能真的想看[赫德利](https://thenewstack.io/off-the-shelf-hacker-hedley-the-robotic-skull-spooks-minneapolis/)，我的蒸汽朋克机器人头骨对话。我已经在文本中讲述了所有的努力，让他能够说出一些精选的预编程短语。是时候在故事中加入视频元素了。一个小视频演示总结了一切，并重点介绍了所有工作的成果。

[https://www.youtube.com/embed/oeDxbTSXBOY?feature=oembed](https://www.youtube.com/embed/oeDxbTSXBOY?feature=oembed)

视频

YouTube 是一种分享视频的便捷方式，而且很容易将它们放入文章中。今天，我们将看看如何将视频集成到 OTSH 专栏工作流中。读者可以使用这些信息在他们自己的网站和项目页面上做类似的事情。

## 设置一个 YouTube 帐户

你需要一个 YouTube 帐户才能发布视频。

去 youtube.com 的。单击页面右上角的“登录”按钮。在“选择帐户”页面上，选择“使用另一个帐户”菜单项。单击“创建帐户”链接。选择“为我自己”。输入您希望用于 YouTube 帐户的名字和姓氏。如果您还没有 Gmail 帐户，请单击“创建一个 Gmail 帐户”。输入您将用于 Gmail 地址的名称。输入您将用于该帐户的密码。确认密码。它应该至少包含八个字符，并使用特殊的符号、字母和数字。您将被要求提供恢复电话号码、恢复电子邮件地址和生日。填写这些内容以创建您的帐户。

## 添加并嵌入视频

使用您新创建的 Gmail 帐户名称和密码登录您的 YouTube 帐户。

点击页面右上方有小人的圆圈。将会打开一个包含您的姓名和 Gmail 地址的菜单。点击“我的频道”。您的 YouTube 频道页面将会出现。

接下来，选择“视频”选项卡，点击页面右上方带有“+”号的小摄像头图标。在下拉菜单中选择“上传视频”点击页面中间的大向上箭头图标，转到您想要上传的视频所在的目录。我们稍后将介绍如何创建一个新视频。

单击所需的视频，然后选择窗口底部的“打开”。视频应该开始从你的 Linux 笔记本上传到谷歌。顶部的标尺显示上传/处理的状态。处理完成后，您可以根据需要填写页面标题、描述和标签。单击“高级设置”选项卡，确保选中“分发选项”下的“允许嵌入”。

最后，点击页面右上角的“发布”按钮，将视频发布到您的频道。将出现一个带有视频 URL 的新页面。记下 URL 或复制/粘贴到您想要嵌入视频的位置。它看起来会像下面这样。

```
https://youtu . be/jnpro 4t qqs

```

在 WordPress 页面上，简单地将 URL 粘贴到文本中。作为一般规则，我坚持把它放在段落的末尾。在段落中间插入视频会破坏读者的语境。

如果你想链接到一个普通的旧网页上的视频，使用一个标准的 HTML 标签。例如:

```
<ahref=" https://youtu . be/jnpro 4 tqqs ">链接 到 我的 频道 视频</ 
```

## 用你的智能手机拍摄视频

目前，我会用 Galaxy 8+智能手机拍摄视频。我已经在专栏里用它来拍照片了，效果相当不错。

对于这个故事，我简单地使用了默认的 16:9 的全高清(FHD)拍摄模式，分辨率为 1920 x 1080。我使用了前置摄像头，手机水平放置。换句话说，手机的长边是水平的。我们将在以后的文章中更详细地研究如何拍摄视频。YouTube 会自动调整，使视频保持垂直。

这段 26 秒的赫德利讲话视频的大小为 54.7 MB。对我来说，把文件从我的手机传到我的 Linux 笔记本上最简单的方法就是通过电子邮件。没错，普通的旧邮件。我写给自己，并添加了一个快速的主题行来提醒我内容。好消息是，当我在家时，手机连接到 WiFi 网络，所以我不会使用手机计划中的数据。如果我绝对需要发送一些东西，当我在 5/4G 手机网络上时，它就在那里。一旦文件下载到我的 Linux 笔记本上的 Thunderbird 电子邮件客户端，我会将它保存到一个适当的目录，以便进一步处理或上传到 YouTube。

多年来，我一直用电子邮件传送我的文章照片。这项技术同样适用于视频，尽管在使用手机网络时，传输时间会稍长一些，并且会很快耗尽数据和资金。请记住，在无线网络上几乎不需要花费什么，包括在异地办公室，也就是 Panera Bread。登录你的手机和笔记本上的 WiFi 热点，然后你就一切就绪了。

最后一件事。确保你的电子邮件服务可以处理视频大小的文件。一些供应商对上传的大小有限制。

## 后续步骤

这是制作视频并将其用于文章的快速纲要。有很多可能的改进和附加功能，我们将随着时间的推移进行检查。我们还将探索使用视频和音频编辑器、灯光、演示设置等等，让现成的黑客故事和操作方法对读者更有用。

我们将视频制作流程与现代现成黑客可能在日常项目中使用的所有其他深入的物理计算、物联网(IoT)和技术推广主题相结合。

赶上【Torq 博士的 [现成的黑客专栏](https://thenewstack.io/tag/off-the-shelf-hacker/)，每周六，只在新栈！在 doc@drtorq.com[或 407-718-3274 直接联系他进行咨询和委托项目。](mailto:doc@drtorq.com)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>