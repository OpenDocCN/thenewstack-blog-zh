# 重新思考 Web 应用防火墙

> 原文：<https://thenewstack.io/rethinking-web-application-firewalls/>

随着 Web 服务器攻击变得越来越普遍，web 应用程序防火墙(WAF)在 20 世纪 90 年代末首次出现。今天，在云原生技术的背景下，人们正在重新思考 WAF 应该如何应用。

Tigera 首席执行官 [Ratan Tipirneni](https://www.linkedin.com/in/ratantipirneni/) 、 [Tigera](https://tigera.io/?utm_content=inline-mention) 总裁兼首席执行官在本期《新堆栈制造商》中表示，不再仅仅是 WAF 背后的静态应用。

[https://www.youtube.com/embed/5d-b1lZYPSo](https://www.youtube.com/embed/5d-b1lZYPSo)

视频

“对于云原生应用程序和微服务分布式架构，你必须假设集群内部的某些东西已经受到威胁，”Tipirneni 说。“所以仅仅坐在晶片后面并不能给你足够的保护；打个比方，你必须假设每一个微服务容器几乎都对互联网开放。

那么接下来的问题是如何应用 WAF 控制？

蒂珀涅尼说，今天 WAF 必须以工作负载为中心。在他看来，每个工作负载都必须有自己 WAF。当一个容器启动时，WAF 控制自动启动。

因此，这样一来，即使集群内部的某些东西遭到破坏或者将一些服务暴露给互联网，也没有关系，因为工作负载受到保护，Tiperneni 说。

那么，如何应用这种级别的安全性呢？您必须考虑以工作负载为中心 WAF。

## **场景**

Tiperneni 解释说，现在漏洞如此之多，云原生应用程序具有更大的攻击面，无法使用传统方法来缓解漏洞。

“抛出一份报告告诉你系统中的所有漏洞已经不够了，”蒂珀涅尼说。“因为那份报告不具有可操作性。运营服务的人发现，修复所有这些漏洞所花费的时间和精力是惊人的，对吗？因此，他们在寻找从哪里开始的某种优先级别。”

用户有责任减轻这个问题，蒂珀涅尼说。这些客户必须考虑漏洞的爆炸半径及其在系统中的背景。第二部分:如何管理攻击面。

蒂珀涅尼说，在这个云原生应用的世界里，客户很快发现，当所有东西都可以访问其他东西时，试图保护每个东西几乎是一项不可能的任务。

用户需要一种方法来控制微服务如何与每个微服务进行通信，并为相互通信设置权限。在某些情况下，特定的微服务根本不应该相互对话。

“因此，这是一种高度杠杆化的活动和安全控制，可以阻止许多这样的攻击，”蒂珀涅尼说。

即使在所有这些之后，用户仍然不得不假设攻击会发生，主要是因为总是存在内部攻击的威胁。

在这种情况下，搜索是在进程级、文件系统级或系统调用级寻找异常行为模式，以确定标准行为的基线，然后告诉用户如何识别偏差，Tiperneni 说。接下来的问题是试图梳理出一些信号，这些信号要么是攻击的指标，要么是妥协的指标。

“也许一个更简单的用例是能够在运行时不断监控已知的坏哈希或文件或二进制文件，这些都是已知的坏，”Tipirneni 说。

公司面临的真正挑战是建立架构来确保微服务的安全性。市场可能会采取多种方式。在录音中，Tipirneni 谈到了 WAF 的发展，可观察性的重要性，以及如何更好地与公司已部署的服务和公司已构建的整体系统建立联系。

“没有单一的灵丹妙药，”蒂皮涅尼说。“你必须能够做多件事来保证你的应用在云原生架构中的安全。”

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>