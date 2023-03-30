# 为什么格拉夫纳会给赏金猎人一大笔钱

> 原文：<https://thenewstack.io/why-grafana-will-pay-good-money-for-bounty-hunters/>

Grafana 凭借其广受欢迎的 Grafana 面板和开源工具走过了羽翼未丰的创业阶段，开始失去其天真无邪的一面，以承担一家价值数十亿美元的科技公司的问题。它的首要担忧当然是安全性，因为攻击者和数据窃贼在 1，000 万且不断增长的用户群中发现了一个越来越有吸引力的目标。Grafana 在安全方面不断增加的投资提供了其作为更大参与者的新地位的最重要证据，以及其在真正的损害发生之前急于发现和修补漏洞的行为。一个典型的例子是它的 9.1.2 和图像渲染器 3.6.1 版本如何包括针对使用 Grafana 图像渲染器插件( [CVE-2022-31176](https://nvd.nist.gov/vuln/detail/CVE-2022-31176) )的 [Grafana](https://thenewstack.io/will-grafana-become-easier-to-use-in-2022/) 实例的高严重性安全修复。

这一重大安全修复也恰逢 Grafana 决定加大对安全工程师的投资，并在未来几个月内通过直接向 bug 赏金猎人支付奖金，为那些成功找到重大安全漏洞的人提供一笔可观的资金(赏金的金额尚未披露)。

Grafana Labs 的首席信息安全官 Thomas Owen 告诉 New Stack 说:“作为一个组织，我们正在经历正常的成长烦恼。”。“但在我看来，我实际上被要求做出更少的取舍，”因为 Grafana 不仅仅在安全方面进行了足够的投资。

事实上，欧文说他惊喜地发现格拉夫纳不仅仅是作为一名安全官员为欧文的计划提供必要的支持。“我们正在发布一项奖金计划，该计划将转向奖金的高端，”欧文说。“我们正在做一些有点不寻常的事情，我们将自己运营，不会外包。我们将尝试利用这样一个事实，即我们是一个如此不可思议的社区驱动的机器，我们将尝试按照同样的原则运行 bug bounty。”

## 错误修复时间表

想法是找到并修复漏洞，并尽可能大声地公布更新。Grafana 或任何公司想要的是让一个被遗漏的漏洞成为头条新闻，该漏洞在未被发现的猖獗利用后导致重大数据攻击和暴露。一名内部安全研究人员于 8 月 11 日发现，Grafana 图像渲染器插件的 Grafana 实例的高严重性安全修补程序随最新的 Grafana 版本一起发布。

Grafana 说，Grafana 安装和图像渲染器插件应该在使用带有 HTTP remoting 的 Grafana 图像渲染器插件的用户中升级。Grafana 传达了以下升级说明:

升级您的 Grafana 实例。

使用 Docker Image Grafana/graf ana-Image-Renderer:3 . 6 . 1 升级 graf ana 图像渲染器。

在 Grafana 配置文件的 rendering 部分，在 renderer_token 中定义一个强密码。

通过名为 AUTH_TOKEN 的环境变量或通过在 Grafana config 的[plugin . Grafana-Image-Renderer]部分添加 auth_token 配置密钥，为图像渲染器配置相同的密码。

重新启动 Grafana 实例。

重新启动您的 Grafana 图像渲染器 Docker 图像。

如果你不能升级，作为一个解决办法，可以禁用 HTTP 远程渲染或完全停止使用 Grafana 图像渲染器插件。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>