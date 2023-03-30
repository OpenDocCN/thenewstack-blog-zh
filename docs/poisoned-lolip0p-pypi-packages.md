# 中毒的 Lolip0p PyPI 包

> 原文：<https://thenewstack.io/poisoned-lolip0p-pypi-packages/>

我以为他们只在万圣节给糖果下毒。在 [Python 包索引](https://thenewstack.io/python-package-repository-struggles-deal-typosquatting/)上，已经出现了三个新的假冒包，colorslib、httpslib、libhttps，都带有恶意软件。

难道不是就在几天前，某个卑鄙的笨蛋把一个[恶意软件中毒的文件放在 Python 包索引上，伪装成一个真正的程序](https://thenewstack.io/pytorch-poisoned-in-software-supply-chain-attack/)？为什么，是的，是的，它是！又来了！

## 不是真正的程序

这次 [FortiGuard](https://www.fortinet.com/fortiguard/labs?utm_source=blog&utm_campaign=fortiguardlabs) 团队在名为“ [colorslib](https://www.fortinet.com/blog/threat-research/supply-chain-attack-using-identical-pypi-packages-colorslib-httpslib-libhttps) [”、“](https://www.fortinet.com/blog/threat-research/supply-chain-attack-using-identical-pypi-packages-colorslib-httpslib-libhttps) [httpslib、](https://www.fortinet.com/blog/threat-research/supply-chain-attack-using-identical-pypi-packages-colorslib-httpslib-libhttps) [”和“libhttps”的三个 PyPI 包(Python 包索引)中发现了类似的零日](https://www.fortinet.com/blog/threat-research/supply-chain-attack-using-identical-pypi-packages-colorslib-httpslib-libhttps)[攻击这些听起来很熟悉，但是，这些都不是真正的 Python 程序。](https://www.fortinet.com/blog/threat-research/supply-chain-attack-using-identical-pypi-packages-colorslib-httpslib-libhttps)

那么，为什么有人会为它们费心呢？因为，与类似的 PyPI 攻击不同，发布它们的攻击者编写了描述和元文本，使它们看起来像是合法的程序。

通常情况下，攻击者甚至都不会费心。正如 PyTorch 团队对早期实例的解释，“因为 PyPI 索引优先于 T21，所以这个恶意的包被安装了，而不是我们官方仓库的版本。这种设计允许某人用与第三方索引中存在的相同名称注册一个包，pip 将默认安装他们的版本。”

谁认为这是个好主意？我想和他们谈谈。

也就是说，一旦就位，他们就试图用一个可疑的 URL 运行一个 [PowerShell](https://thenewstack.io/microsoft-open-sources-powershell-ports-cli-linux/) 命令。这会将程序发送到另一个站点。在那里，它下载一个名为“Oxyz.exe”的不可信可执行文件。然后，它删除另一个可执行文件“update.exe”，该文件在以下文件夹中运行:

%USER%\AppData\Local\Temp\ '

在这个目录中，当运行 update.exe 时，它会将许多文件放到这个文件夹中

% USER % \ AppData \ Local \ Temp \ one file _ % PID _ % TIME % '。

其中，你会发现 SearchProtocolHost.exe，这是真正的恶意软件。还有一个收集[不和谐令牌](https://www.online-tech-tips.com/computer-tips/what-is-a-discord-token-and-how-to-get-one/#:~:text=A%20Discord%20token%20is%20a,you%20are%20the%20account%20holder.)的过程，所以也有一些信息窃取。

## 还有更多的事情要做

尽管《奸诈三人组》总共只有几百次下载，但还是太多了。

你可能会问——我知道我问了——为什么这种事总是发生在 PyPI 身上？ [Python 软件基金会](https://www.python.org/psf-landing/)正试图[修复 PyPI 的安全性](https://www.activestate.com/blog/pypi-security-pitfalls-and-steps-towards-a-secure-python-ecosystem/)。显然，需要做更多、更多的工作。

目前，您所能做的就是仔细地——我是说仔细地——检查任何新的 Python 代码，然后再让它接近您的生产系统。就个人而言，我不认为我会添加任何在我的系统上至少一个月没有出现的 Python 代码。让其他人去发现是否有什么问题。我没有时间。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>