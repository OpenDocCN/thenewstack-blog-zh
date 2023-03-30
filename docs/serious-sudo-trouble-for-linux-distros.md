# Linux 发行版的严重 Sudo 问题

> 原文：<https://thenewstack.io/serious-sudo-trouble-for-linux-distros/>

我们都知道这些笑话。Linux 管理员:“给我做个三明治！”奴才:“不行！”Linux 管理员:“ [`sudo`](https://www.sudo.ws/) 给我做个三明治！”奴才:“好吧。”但是，当一个[古 sudo 安全漏洞被揭开](https://blog.qualys.com/vulnerabilities-research/2021/01/26/cve-2021-3156-heap-based-buffer-overflow-in-sudo-baron-samedit)时，这可不是闹着玩的。

对于那些不熟悉 Unix 命令行的人来说，`sudo`是一个序言，它授予普通用户管理权限，可以执行他们希望执行的任何命令。这是一个避免使用根帐户的便利工具，根帐户总是一个危险的提议。

许多所谓的 Linux 漏洞，在更仔细的检查后，被证明没什么大不了的。但是，接下来，还有像[须藤的 CVE-2021-3156](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-3156) ，又名“巴隆·萨梅迪特”

有了这个，如果你懒于更新你的电脑，你就有麻烦了。任何本地用户都可以利用此 [sudo 基于堆的缓冲区溢出](https://www.sudo.ws/alerts/unescape_overflow.html)。更糟糕的是，任何 Joe 或 Jane 用户都可以利用它将权限提升到 root，即使他们没有在 sudoers 文件中列出。

正如 [sudo 程序员解释的那样](https://www.sudo.ws/alerts/unescape_overflow.html):通常，当你在 shell 模式下运行一个`sudo`命令时，你用一个反斜杠来转义命令参数中的任何特殊字符。然后，在评估 sudoers 策略之前，sudoers 策略插件从参数中删除转义字符。但是，如果该代码以非转义反斜杠字符结尾，那么它将读取字符串的最后一个字符以外的内容。

通常，这并不重要。但是，由于另一个错误，这次是在 shell 解析代码中，攻击者可以使用-s 或-i 选项运行 [sudoedit](http://www.wingtiplabs.com/blog/posts/2013/03/13/sudoedit/) 。这有什么不好？因为它启用了 shell 模式，而且实际上没有命令在运行，`sudo`不会对特殊字符进行转义。最后，但同样重要的是，决定是否删除转义字符的代码不会检查命令是否正在运行。

因此，当命令行到达`sudoers_policy_main()`程序时，`set_cmnd()`将命令行参数连接到一个基于堆的缓冲区中。在不知道命令有多长的情况下，`set_cmnd()`容易受到使用“user_args”缓冲区中越界字符的基于堆的缓冲区溢出的攻击。

这个理论听起来可能很复杂，但在实践中，利用它是微不足道的。要开始乱搞，您需要做的就是输入命令“`sudoedit -s`”，任何命令行参数都以一个反斜杠字符结尾。

是的，最近还有其他的`sudo`安全问题，但与这个相比，它们都是小巫见大巫。为了让那些人揍你，你必须有一个不寻常的`sudo`设置。这个可以在所有安装了 sudo 的 Linux 系统上运行。正如安全公司 [Qualys 研究团队](https://www.qualys.com/research/security-advisories/)的 [Animesh Jain](https://www.linkedin.com/in/animesh-jain-0b96996/) 所说，漏洞签名产品经理写道，“Qualys 建议用户立即为该漏洞应用补丁。”她是对的。

现在就给你的 Linux 系统的`sudo`命令打补丁吧。你要尽快升级到`sudo`版本 1.9.5p2 或更高版本。

不觉得能发生在自己身上？求你了。现在有许多针对 Linux 系统的僵尸网络使用暴力方法，这个漏洞非常适合自动利用。

你还在等什么？动手吧。现在就做。补丁已经可以在所有主要的 Linux 发行版上获得。

由 [Max Bender](https://unsplash.com/@maxwbender?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 在 [Unsplash](https://unsplash.com/s/photos/mask?utm_source=unsplash&utm_medium=referral&utm_content=creditCopyText) 上拍摄的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>