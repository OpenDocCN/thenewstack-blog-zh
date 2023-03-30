# Apache 服务器中有一个严重的安全漏洞

> 原文：<https://thenewstack.io/theres-a-nasty-security-hole-in-the-apache-webserver/>

这里有一个安全漏洞，那里有一个安全漏洞，到处都有安全漏洞。最新的一个是一个令人讨厌的标签为 [CVE-2022-30522](https://nvd.nist.gov/vuln/detail/CVE-2022-30522) 的。这是在 [Apache HTTP 服务器](https://httpd.apache.org/)的 [mod_sed 模块](https://httpd.apache.org/docs/2.4/mod/mod_sed.html)中的拒绝服务(DoS)攻击。

那是微弱的铃声吗？如果是这样，那是因为我们以前来过这里。2022 年 3 月，[mod _ sed 中的一个 Apache 内存崩溃漏洞 CVE-2022-23943](https://nvd.nist.gov/vuln/detail/CVE-2022-23943) 被揭露。这是一个越界写入漏洞，使得攻击者能够覆盖堆内存。当你说“覆盖堆内存”时，你知道这是个坏消息。这影响了 Apache HTTP Server 2.4 版本 2.4.52 和更早的版本。

## 新问题

很快就修好了。但是， [JFrog](https://jfrog.com/) 安全研究团队的安全研究技术负责人 [Brian Moussalli](https://www.linkedin.com/in/brianmoussalli/?originalSubdomain=il) 担心，虽然 [Apache 代码“修复解决了问题](https://jfrog.com/blog/cve-2022-30522-denial-of-service-dos-vulnerability-in-apache-httpd-mod_sed-filter/)，但它产生了一种新的有害行为。”穆萨利是对的。

原来这个补丁打开了一个新的 mod_sed 漏洞。好消息是它只影响阿帕奇 HTTPD 2.4.5。当一个 mod_sed 过滤器用于请求或响应编辑时，它被调用。

在深入研究这个 bug 之前，让我们快速回顾一下 mod_sed 是做什么的。本质上，mod_sed 使您能够使用 steam 编辑器，是的，经典的 Unix [sed](https://www.gnu.org/software/sed/manual/sed.html) ，来操作服务器请求的输入和输出流。作为输入过滤器，它可以用在 HTTP POST 请求的主体上，作为输出过滤器，它使您能够修改服务器的响应。总之 [mod_sed 可以很有用](https://business-asset.com/eng/wiki-blog/useful/using-mod-sed-to-filter-web-content-in-apache-731.html)。

但是，在这种情况下，最新的漏洞在处理流缓冲区时错误地处理了内存分配。当缓冲区达到一定大小时，它们会成倍增加，以避免多次调用内存分配函数。听起来不错，但是当攻击迫使太多数据进入缓冲区时，缓冲区就会超过 Apache 的内存限制。结果呢？进程中止，然后——砰！—你得到一个 DoS。

虽然 Apache 认为这个 bug 没什么大不了的。他们将其严重性评为“低”国家漏洞数据库( [NVD](https://nvd.nist.gov/vuln/detail/CVE-2022-30522) )不同意。NVD 给它的通用漏洞评分系统(CVSS)评分为 7.5 分(高)。JFrog 把它放在了中间，这是因为它一方面平衡了它的影响，另一方面也平衡了相对稀少的安装基数。

## 立即更新

我吗？任何有可能成为一个真正的麻烦，同时也是一个容易解决的问题都会尽快得到修补。只需[更新到阿帕奇 HTTPD 2.4.54](https://downloads.apache.org/httpd/Announcement2.4.html) 或以上。那你就再也不用担心了。

如果出于某种原因，您不能修补它，您也可以通过限制 POST 方法的主体大小来阻止利用它的外部攻击，这样它就永远不会被触发。为此，在 Apache HTTPD 配置文件(/etc/httpd/conf/httpd)中输入一个 [LimitRequestBody](https://httpd.apache.org/docs/2.0/mod/core.html#limitrequestbody) 配置语句。conf)到 2gb 或更少。

例如:

LimitRequestBody 107374182

这将阻止任何大于 1 GB 的身体大小的数据被接受。不过，这并不完美。JFrog 指出，这种“缓解措施只能防止客户端请求导致的拒绝服务攻击，但如果使用 mod_sed 修改 web 响应，并且向客户端发送大于 2GB 的响应，服务器仍然容易受到拒绝服务攻击。”

所以，最好的办法是将你的网络服务器升级到 2.4.54 或更高版本。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>