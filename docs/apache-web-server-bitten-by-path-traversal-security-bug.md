# Apache Web 服务器被路径遍历安全漏洞咬了一口

> 原文：<https://thenewstack.io/apache-web-server-bitten-by-path-traversal-security-bug/>

回到 20 世纪 90 年代[国家超级计算应用中心](http://www.ncsa.illinois.edu/) httpd 服务器是早期最流行的 web 服务器。虽然它需要很多补丁才能真正有效。因此，布莱恩·贝伦多夫和克里夫·斯科尔尼克整理了一份邮件列表，以开发一个基于原始 httpd 服务器的新服务器，他们称之为[阿帕奇](https://httpd.apache.org/)。它很快变得非常流行。

今天，在 Apache 和 [NGINX](https://www.nginx.com/) 之间，谁是使用最广泛的 web 服务器是一场难分胜负的比赛。当然，随着流行而来的是攻击。最新的是 Apache HTTP Server 2.4.49 中的[路径遍历和文件泄露漏洞，这是一个令人讨厌的漏洞。](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-42013)

当然，任何时候你在网络服务器上看到一个[路径遍历安全漏洞](https://owasp.org/www-community/attacks/Path_Traversal)，你就知道你有麻烦了。它使攻击者能够访问存储在 webroot 文件夹之外的文件和目录。通过使用引用带有“点-点-斜线(../)"序列和变体，或者通过使用绝对文件路径，黑客可以访问任意文件和目录。这可能包括应用程序源代码或配置和关键系统文件。

你能说坏消息吗？当然可以。

尤其令人痛苦的是，在 Apache HTTP Server 2.4.50 中推出的第一个针对 [CVE-2021-41773](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-41773) 的修复不够好。总是有事！

事实证明，攻击者仍然可以使用路径遍历攻击将 URL 映射到由类似别名的指令配置的目录之外的文件。如果这些目录之外的文件没有受到通常的默认配置“拒绝所有请求”的保护，这些请求可能会成功。如果也为这些别名路径启用了 CGI 脚本，这些脚本可以用于远程代码执行。

好消息是，这个问题只影响 Apache 2.4.49 和 Apache 2.4.50，不影响更早的版本。此外，根据互联网服务器和设备搜索引擎 Shodan 的说法，只有少数 Apache 安装在运行 2.4.49 或 2.4.50。在整个 Apache 安装群中，只有不到 1%的人容易受到攻击。

请注意，如果使用 Netcraft 的网络服务器数量(T1)，可能还不到 300 万台服务器。这意味着很多服务器可能会受到攻击。您还应该记住，您根据需要自动启动的所有容器化 Apache 服务器也可能容易受到攻击。

顺便说一下，这不是什么理论上的攻击。[思科](https://www.cisco.com/)正在报告攻击。这些[攻击大多是通过访问凭证或直接访问外壳来尝试系统访问](https://blog.talosintelligence.com/2021/10/apache-vuln-threat-advisory.html)。大多数情况下，这些敲服务器门的行为是由作为用户代理的 [cURL](https://curl.se/) 完成的，但是[思科的 Talos](https://talosintelligence.com/) 团队已经看到了使用其他普通用户代理的其他活动。

显然，既然现在已经有了合适的补丁，为了安全起见，你必须[升级到](https://httpd.apache.org/download.cgi) [Apache 2.4.51](https://httpd.apache.org/download.cgi) 。这也意味着您的云原生容器的 Apache 源代码也必须更新。

完成后，你就安全了…直到下一次袭击来临。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>