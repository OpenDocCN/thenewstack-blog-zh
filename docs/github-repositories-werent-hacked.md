# GitHub 仓库没有被黑客攻击

> 原文：<https://thenewstack.io/github-repositories-werent-hacked/>

好消息是成千上万的 GitHub 库没有被黑客攻击。我重复一遍，“不是被黑。”但是许多存储库已经被克隆，然后掺入了有毒的恶意软件内容。

在这种情况下，软件程序员 [Stephen Lacy](https://twitter.com/stephenlacy) 在 Twitter 上报告说，他发现“似乎是一个[对@github](https://twitter.com/stephenlacy/status/1554697077430505473?t=pUIQZ0Ss0cCWh4GmOFeRvw&s=19) 的大规模广泛恶意软件攻击。

*   目前超过 35000 个存储库被感染
*   到目前为止发现的项目包括:crypto，golang，python，js，bash，docker，k8s
*   它被添加到 npm 脚本、docker 映像和安装文档中”

## 没有看上去那么糟

然而，仔细观察后，发现它远没有莱西说的那么糟糕。他自己也承认，“[更正一下，github 上的 35k+‘代码点击数’，不是被感染的库。](https://twitter.com/stephenlacy/status/1554718086657282049)

其中，超过 13，000 个恶意文件来自同一个存储库。红帽-运营商-生态系统。该存储库已被删除。

莱西还发现原始文件没有被破坏或感染。相反，他们是用听起来合法的名字克隆出来的。这是一种非常常见的攻击媒介。始终确保您为您的项目使用准确、正确的回购。记住，你只是一个妥协项目中的一个小错误。

结果还表明，主要的存储库，如 bash、crypto、docker、golang、python 和 k8s，都没有受到影响。但不要认为这意味着你不需要担心这个。正如 [Javascript 库“colors.js”和“faker.js”的惨败所显示的那样](https://www.zdnet.com/article/when-open-source-developers-go-bad/)，即使是小的、模糊的、损坏的代码文件也会造成大的损害。

对于这种特殊情况，恶意软件感染的文件既渗透了用户的环境变量，又包含一行后门程序。前者已经够糟了——通过它，攻击者可以获得您的 API 密钥、凭证和加密密钥——但是通过后者，攻击者可以在您的系统上运行任意代码。你一直想要的，对吧？

## 烟比火多

尽管如此，这是一个烟多于火的例子。正如 GitHub Security 在查看报告后所说:

* [没有存储库遭到破坏](https://twitter.com/GitHubSecurity/status/1554843443200806913?)

*恶意代码被发布到克隆的存储库，而不是存储库本身

*克隆已被隔离，GitHub 或维护者帐户没有明显受损

所以，这不是一个无足轻重的汉堡，但也没什么大不了的。

这个故事的寓意是，虽然你应该睁大眼睛注意安全问题，但你不应该把网络上每一个关于新安全问题的随机报告都视为灾难。不幸的是，这些天来，随着一个接一个的安全漏洞，我们都有点紧张是可以理解的。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>