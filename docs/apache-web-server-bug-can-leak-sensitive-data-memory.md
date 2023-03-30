# Apache Web 服务器漏洞使得攻击者能够利用内存数据

> 原文：<https://thenewstack.io/apache-web-server-bug-can-leak-sensitive-data-memory/>

Apache web 服务器中存在一个漏洞，使得攻击者能够获取存储在服务器内存中的敏感数据。该漏洞可通过以下方式触发。htaccess 配置文件，因此它对允许用户创建此类文件的共享主机环境构成了最大的风险。

“如果您在一个允许用户创建的共享托管环境中运行 Apache web 服务器。发现该漏洞的安全研究员[Hanno bck](https://hboeck.de/)说:“你应该放弃你现在正在做的一切，立即更新，并确保之后重启服务器。他将其命名为 Optionsbleed，因为它在概念上类似于 [Heartbleed](http://heartbleed.com/) ，这是三年前在 OpenSSL 中发现的一个漏洞，允许攻击者从支持 HTTPS 的 web 服务器中提取内存内容。

虽然与 Heartbleed 相似，但 Optionsbleed 的范围更有限，因为它需要特殊的条件才能被利用。当服务器收到 HTTP OPTIONS 请求，并在其配置文件中为非标准 HTTP 方法设置了一个[限制指令](https://httpd.apache.org/docs/2.4/mod/core.html#limit)时，就会触发该漏洞。

大多数人都熟悉 HTTP GET 和 POST，但这只是 HTTP 协议中定义的两种请求“方法”。另一种方法叫做 [OPTIONS](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html) ，接收这种请求的服务器用一个列出它们支持的 HTTP 方法的头来响应。

管理员可以通过使用名为 Limit 的配置指令来限制对某些 HTTP 方法的访问。

中的任何无效 HTTP 方法设置限制指令。在构造 Allow 头时，htaccess 文件导致了一个使用 after free 错误，”bck 在他的报告中说。

如果确定了易受攻击的服务器，攻击者可以反复向其发送 OPTIONS 请求，以便从 web 服务器进程的内存中获取数据。这些内存块可能包含服务器当时正在处理的敏感信息。

乍一看，web 服务器的管理员没有理由为非标准的 HTTP 方法设置限制指令，因此风险应该不大。然而，在共享主机环境中，多个用户共享同一个 web 服务器，并且可以创建他们自己的服务器。htaccess 文件，可以故意触发该错误。

“这种破坏不仅限于单个虚拟主机，”博克说。“共享主机提供商的一个客户可能会故意创建一个。希望能够从同一系统上的其他主机提取机密数据。

博克对 Alexa 排名前 100 万的网站进行了一次扫描，发现 466 台主机的 Allow 标题被破坏。

该漏洞被跟踪为 [CVE-2017-9798](https://nvd.nist.gov/vuln/detail/CVE-2017-9798) ，将在 Apache httpd 版本 2.4.28 中修复，该版本尚未发布，但有一个[手动补丁](https://svn.apache.org/viewvc/httpd/httpd/branches/2.4.x/server/core.c?r1=1805223&r2=1807754&pathrev=1807754&view=patch)。多个 Linux 发行版已经发布了补丁包，所以你应该和你的发行版维护者核实一下。

值得注意的是，该漏洞也影响到 Apache 2.2，该版本已经到了生命周期的尽头，不会得到官方的修复。然而，开发者 Thomas Deutschmann 为其反向移植了补丁。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>