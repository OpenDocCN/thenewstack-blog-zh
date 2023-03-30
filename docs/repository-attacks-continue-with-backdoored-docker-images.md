# 存储库攻击继续利用后门 Docker 映像

> 原文：<https://thenewstack.io/repository-attacks-continue-with-backdoored-docker-images/>

最近几个月，在 NPM 和 PyPI 知识库上发现了后门组件[之后，研究人员警告说，另一个公共知识库](https://thenewstack.io/npm-attackers-sneak-a-backdoor-into-node-js-deployments-through-dependencies/) [Docker Hub](https://hub.docker.com/) 即将分发恶意的 Docker 图像。

在过去的一年中，至少有 17 张被批量上传的流氓图片被发现存放在一个名为 docker123321 的公共 Docker Hub 注册表下。尽管用户和安全公司自 9 月份以来多次报告，但直到今年 5 月，注册表才被删除，当时这些图像已经被删除了 500 多万次。

根据[Krom tech 研究人员最近的分析](https://kromtech.com/blog/security-center/cryptojacking-invades-cloud-how-modern-containerization-trend-is-exploited-by-attackers)，最初的三张图片是由 docker123321 在 2017 年 5 月发布的，被命名为 tomcat、tomcat11 和 tomcat22。它们包含 shell 脚本，试图在用户的主机系统上安装反向 shell 或添加授权的 SSH 密钥。

tomcat 映像包含的脚本试图将/etc/从主机文件系统挂载到容器内的/mnt/etc/

tomcat11 映像有一个类似的基于 crontab 的有效负载交付机制，但是它创建的 cronjob 设置了一个基于 Bash 的反向 shell。最后，tomcat22 试图挂载/root/。然后试图将攻击者控制的 ssh 密钥添加到/root/。ssh/authorized _ key。

第二批恶意图片于 2017 年 10 月至 12 月期间被推送到 Docker Hub 上 docker123321 的注册表中，名称为 kk、mysql、data 和 mysql0。虽然有效载荷的交付也依赖于 cronjobs，但有效载荷本身包括加密硬币挖掘软件，特别是 Monero 加密货币。

在 1 月和 2 月，继续上传 docker123321 注册表下的流氓图像。这些图片展示了类似的恶意行为:执行反向外壳或加密货币挖掘。

来自攻击者使用的矿池的统计数据显示，他们的一个钱包收到了 544.74 XMR(Monero coins)——约 89，000 美元——很可能是使用其他人的云基础设施挖掘的。

> Kromtech 的研究人员说:“对于普通用户来说，只是从 DockerHub 中取出一个 Docker 图像就像从某个地方取出任意二进制数据，执行它，并希望得到最好的结果，而不知道里面有什么。”

Docker Hub 上的 Docker12331 并不是唯一一个发现[拥有 Monero miners 操纵的恶意图像](https://github.com/docker/hub-feedback/issues/1121)的公共注册表。更令人担忧的问题是，直到最近，Docker Hub 上几乎没有针对这个问题进行监管。

包括安全公司 Fortinet 在内的多方[在过去一年中公开报告 Docker12331 的图像是恶意的，](https://www.fortinet.com/blog/threat-research/yet-another-crypto-mining-botnet.html)[第一次是在 2017 年 9 月](https://github.com/docker/hub-feedback/issues/1121#issuecomment-326664651)，然而他们一直持续到 5 月。从那以后，其他人[发现了托管在其他注册表下的类似中毒图像](https://github.com/docker/hub-feedback/issues/1549)。

一位名叫 [Jamin Wong](https://github.com/jmwong) “我们已经删除了报告的存储库。我们的团队正在努力改善 Docker Hub 上的用户体验。”

“就像任何公共存储库一样，Docker Hub 是为社区服务的，”Wong 说。“在处理开放公共存储库和开放源代码时，我们建议您遵循一些最佳实践。我们建议用户尽可能使用 Docker Hub 中的精选官方图片和 Docker Store 中的认证内容。对于社区图像，请在运行之前验证内容作者并检查图像的内容。

“Docker 通常不会监管社区图片，除非它们包含非法内容，”Wong 补充道。“但是，我们确实雇佣了专门的团队来管理 Docker Hub 上的官方图像和 Docker Store 上的认证图像。”

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>