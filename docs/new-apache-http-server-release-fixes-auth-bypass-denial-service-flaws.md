# 新的 Apache HTTP Server 版本修复了身份验证绕过、拒绝服务缺陷

> 原文：<https://thenewstack.io/new-apache-http-server-release-fixes-auth-bypass-denial-service-flaws/>

Apache HTTP Server 项目发布了世界上最广泛使用的 web 服务器软件的 2.4.x 和 2.2.x 版本的安全补丁。

周一发布的 Apache HTTPd 2.4.26 是一个安全版本，其中包含针对被评为重要的[五个漏洞](https://httpd.apache.org/security/vulnerabilities_24.html)的补丁。这些缺陷可能允许攻击者绕过身份验证要求，使服务器进程崩溃，或触发缓冲区溢出。

其中四个漏洞也会影响 Apache HTTPd 2.2.x，并将在尚未发布的 2.2.33 版本中得到解决。在那之前，服务器开发者[发布了可以手动应用的补丁](https://httpd.apache.org/security/vulnerabilities_22.html)。

认证旁路漏洞 [CVE-2017-3167](https://access.redhat.com/security/cve/CVE-2017-3167) 是最严重的一个，在红帽的通用漏洞评分系统(CVSS)中获得了 7.4 的初步评级。

该问题源于 ap_get_basic_auth_pw()函数的使用，可能导致请求被错误地验证。Apache HTTP Server 项目建议第三方模块开发人员改用 ap_get_basic_auth_components()函数。

当第三方模块在对 HTTPS 端口的 HTTP 请求期间调用 ap_hook_process_connection()时，mod_ssl 中可能会出现空指针取消引用。这个问题被跟踪为 [CVE-2017-3169](https://access.redhat.com/security/cve/CVE-2017-3169) ，可能导致拒绝服务(DoS)情况。

在 mod_http2 中发现并修复了另一个可能导致服务器崩溃的空指针取消引用问题( [CVE-2017-7659](https://access.redhat.com/security/cve/CVE-2017-7659) )。此漏洞仅影响 2.4.x HTTPd 分支，通过向服务器发送恶意创建的 HTTP/2 请求，可以利用此漏洞。

另外两个打了补丁的漏洞， [CVE-2017-7668](https://access.redhat.com/security/cve/CVE-2017-7668) 和 [CVE-2017-7679](https://access.redhat.com/security/cve/CVE-2017-7679) ，分别是 ap_find_token()和 mod_mime 中的缓冲区溢出。攻击者可以利用这些问题，通过向服务器发送恶意的请求标头序列或发送特制的内容类型响应标头来导致分段错误。

Web 服务器管理员应该监视来自他们的 Linux 发行版的更新的 HTTPd 包，并且应该尽快应用补丁以避免潜在的攻击。

红帽是新堆栈的赞助商。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>