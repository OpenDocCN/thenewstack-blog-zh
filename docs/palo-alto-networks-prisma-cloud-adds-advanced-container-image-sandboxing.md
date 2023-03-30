# Palo Alto Networks 的 Prisma Cloud 增加了高级容器映像沙箱

> 原文：<https://thenewstack.io/palo-alto-networks-prisma-cloud-adds-advanced-container-image-sandboxing/>

高速的喜悦[持续集成/持续交付(CI/CD)](https://www.hpe.com/us/en/insights/articles/continuous-integration-and-delivery-tool-basics-1807.html) 在形容词里:高速。但是，与此同时，如果你经常从第三方注册表中提取图片来加速你的开发，你也在为骗子和卑鄙小人敞开大门。怎么办，怎么办！[帕洛阿尔托网络](https://www.paloaltonetworks.com/cloud-security?utm_content=inline-mention) (PANW)最新答案是给 [Prisma Cloud](https://www.paloaltonetworks.com/prisma/cloud) 添加高级容器映像沙箱。

这使您能够在预部署沙箱中进行连续测试，也就是[左移测试](https://thenewstack.io/what-does-shift-left-mean-if-every-process-is-a-circle/)。在这个沙盒中，Prisma Cloud 使用[机器学习(ML)](https://thenewstack.io/category/machine-learning/) 来检查您在交付物中使用的图像。ML 程序自动分析实际运行时的动态威胁，了解所有正在运行的进程、映像的网络活动和所有文件系统访问，以构建映像在生产中的深入模型。

分析结果会发送到 CLI 和控制台 UI。有了它，您可以在将图像带入真实环境之前就获得对图像的洞察力和控制权。

Prisma Cloud 命令行界面(CLI)， [twistcli](https://docs.paloaltonetworks.com/prisma/prisma-cloud/prisma-cloud-admin-compute/tools/twistcli.html) ，使您能够直接从开发人员的笔记本电脑上扫描图像，查找漏洞、合规性问题、恶意软件和机密。

此外，Prisma Cloud 还扩展了 AWS 独立虚拟机的自动检测和自动保护功能，将 Azure 和 Google Cloud 也包括在内。借助自动防护，Prisma Cloud 大大减少了手动配置、部署和更新主机安全代理所需的工作量。

该计划的网络应用和 API 安全(WAAS)网络应用防火墙(WAFs)也得到了改善。诚然， [WAFs 并不全是他们所吹捧的](https://thenewstack.io/the-web-app-firewall-is-dead-and-we-know-who-killed-it/)，但 PANW 的 WAFs 也涵盖了 [OWASP](https://owasp.org/) 十大，并带有 API 安全功能、高级 DoS 保护和 bot 风险管理。

在最新的更新中，这些功能还扩展到保护 Windows 主机，包括 Windows Server 2019 LTSC。此外，WAAS 现在自动支持在服务网格上安装，如 [Istio](https://istio.io/) 或 [Linkerd](https://linkerd.io/) 。简而言之，Prisma 的 WAAS 功能适用于 DevOps 一代，而不是云时代之前的原生技术世界。

此外，WAAS 功能现在还提供了关于 API 运行状况和吞吐量的详细信息，包括应用程序响应代码、流量和性能详情、 [TLS 证书](https://protonmail.com/blog/tls-ssl-certificate/)状态以及可定制的日志清理。基础？是的，但是你更有可能通过基本攻击面被攻击，而不是被最新的热门但不为人知的安全漏洞攻击。

除此之外，Prisma Cloud 现在还包括:

*   针对新工作负载类型的应用嵌入式 Defender Forensics，例如 [AWS Fargate](https://aws.amazon.com/fargate/) 、 [Azure 容器实例](https://azure.microsoft.com/en-us/services/container-instances/)、 [Google Cloud Run](https://cloud.google.com/run) 和 [Google Kubernetes 引擎自动驾驶](https://cloud.google.com/blog/products/containers-kubernetes/introducing-gke-autopilot)。此功能将客户运行时规则和我们广泛的取证数据收集带到所有这些计算堆栈中。
*   亚马逊机器映像(AMI)扫描改进:现在，主机安全能力扩展到涵盖定制 AWS 虚拟私有云(VPCs)，甚至加密的 AMI。
*   无服务器安全:最新版本包括无服务器自动保护 v2 和无服务器防御中对 Ruby 2.5 和 2.7 的支持。

如果你已经是 Prisma Cloud 的用户，你应该认真考虑升级。此外，如果您还不是客户，请考虑将它添加到您的云保护外套中。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>