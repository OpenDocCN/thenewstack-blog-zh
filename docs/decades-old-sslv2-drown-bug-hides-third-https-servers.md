# 几十年前的 SSLv2 淹没漏洞隐藏在三分之一的 HTTPS 服务器中

> 原文：<https://thenewstack.io/decades-old-sslv2-drown-bug-hides-third-https-servers/>

OpenSSL 项目背后的人[宣布](https://www.openssl.org/news/secadv/20160301.txt)一个新发现的错误，该错误存在于运行 TLS(传输安全层)的服务器中，用于安全通信。

DROWN(使用过时和弱化的加密解密 RSA)使用中间人( [MITM](http://www.veracode.com/security/man-middle-attack) )攻击，“允许攻击者破解加密，读取或窃取敏感通信，包括密码、信用卡号、商业秘密或财务数据。”

[红帽安全博客](https://securityblog.redhat.com/2016/03/01/go-home-sslv2-youre-drowning/)将该漏洞评定为重要的安全严重性，并“建议 SSLv2 是一种不再被认为是安全的协议，不应在现代环境中使用。”

根据 OpenSSL 主导的 Drownattack 网站，33%的安全 HTTPS 服务器容易受到攻击。除了提供一份完整的技术论文之外，该网站还提供了一个方便的工具来检查你的服务器是否有漏洞。

[![https://drownattack.com/](img/c0b73b49d1b122843606629a0474d560.png)](https://drownattack.com/)

在 drownattack.com 检查你的域名漏洞

Qualys 工程总监 Ivan Ristic 在 Qualys 安全博客中写道，[DROWN 的核心代码是 SSL v2，于 1995 年首次发布，“不到一年后宣告死亡”。“尽管这个旧版本的 SSL 目前使用得不多，但它继续得到许多服务器的支持。”](https://blog.qualys.com/securitylabs/2016/03/01/drown-abuses-ssl-v2-to-attack-rsa-keys-and-tls)

Ristic 解释说，尽管这种代码是计算机时代的古老代码，而不是现在使用的代码，但它“可以被用来利用 TLS，即使在客户端设备不支持 SSL v2 的情况下，有时甚至在服务器不支持 SSL v2 的情况下(但使用与其他支持 SSL v2 的服务器相同的 RSA 密钥)。Ristic 在这里提供了更多关于这个 bug [的历史。](https://blog.qualys.com/securitylabs/2016/03/01/drown-abuses-ssl-v2-to-attack-rsa-keys-and-tls)

## **什么处于危险之中？**

根据 Drownattack 网站的说法，该漏洞可以影响“用户和服务器之间的任何通信”。这通常包括但不限于用户名和密码、信用卡号、电子邮件、即时消息和敏感文档。在一些常见的情况下，攻击者还可以冒充安全网站，拦截或更改用户看到的内容。”

Red Hat Security 博客解释说，“这意味着如果攻击者能够拦截并修改客户端和主机之间的网络流量，攻击者就可以在预期的安全连接上冒充服务器。然后，当重要信息在服务器和客户端之间传输时，攻击者可能会窃听或修改这些信息。”该公司还发布了一篇[漏洞文章](https://access.redhat.com/security/vulnerabilities/drown)，提供了进一步的细节。

据 Ristic 称，修复很容易。“禁用你系统中所有服务器上的 SSL v2，”他写道。

红帽已经为 OpenSSL 提供了一个[更新](https://access.redhat.com/security/cve/cve-2016-0800)，禁用 SSLv2。这是一个好的开始，但是 SSLv2 协议需要在整个服务器系统中禁用。

Ristic 解释说:“如果你一直在重复使用私有 RSA 密钥(即使使用不同的证书)，如果有其他服务器(可能使用不同的主机名、端口，甚至协议)继续支持这个旧的、非常容易受到攻击的协议版本，那么在一台服务器上禁用 SSL v2 不会有任何帮助。”

红帽是新堆栈的赞助商。

来自 Drownattack.com[的特写图片](https://drownattack.com/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>