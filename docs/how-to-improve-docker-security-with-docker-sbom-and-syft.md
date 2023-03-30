# 如何利用“docker sbom”和 Syft 提高 Docker 安全性

> 原文：<https://thenewstack.io/how-to-improve-docker-security-with-docker-sbom-and-syft/>

Docker 推出了一个新的 [`docker sbom`命令](https://docs.docker.com/engine/sbom/)，它为 Docker Desktop 用户提供了一个强大的工具，可以在本机 Docker CLI 中快速生成集装箱图像的详细软件材料清单(即 SBOM)。该命令建立在由 Anchore 维护的[开源项目 Syft](https://anchore.com/opensource/) 之上。

 [丹尼尔·努尔米

Anchore 联合创始人兼 CTO Daniel Nurmi 在为企业部署设计和发布安全、生产级、大规模分布式和高性能计算系统、云基础架构和应用程序方面拥有丰富的经验。Anchore 是 Syft 和 Grype 开源项目的维护者。](https://www.linkedin.com/in/dannurmi/) 

SBOM 可以识别容器映像中的每一个工件，使您更容易查明软件供应链中的漏洞，并在软件开发生命周期的任何阶段快速修复这些漏洞。

有多种方法可以使用 SBOM 来提高 Docker 安全性:

*   为所有容器工件生成一个单一的真值来源。
*   聚合各个容器图像的 SBOMs 以获得应用程序级视图。
*   发现意外的依赖关系、恶意渗透构建的行为以及无意的错误。
*   跨所有生命周期阶段执行漏洞扫描。
*   基于丰富的 SBOM 数据创建和实施策略。
*   满足客户和联邦法规遵从性要求。

## **为什么码头保安从 SBOM 开始**

SBOM 在保护容器形象方面的作用是基础性的——它的作用就像是开发生命周期每个阶段的配料列表，因此您始终可以准确地知道容器形象中包含了什么，以及它是在什么时候、在什么地方推出的。

软件供应链是复杂的，每个应用程序都可能有数百甚至数千个依赖项，而这些依赖项对您来说可能并不明显或可见。SBOM 数据的真正价值在于实时了解软件供应链中的安全问题。

因为漏洞可以在开发周期的任何阶段引入，所以您需要为每个源、构建、阶段、部署和运行阶段生成一个 SBOM，以生成工件的完整记录。然后，您可以使用 SBOMs 检查容器映像随时间的异常情况，并在需要修复漏洞时启动取证分析。`docker sbom`命令在关键构建阶段发挥作用，并提供使您能够在本机 Docker 开发环境中生成 SBOMs 的功能。

## **SBOM 格式和使用案例**

作为开发和安全团队的基础数据源，SBOMs 在一系列使用情形中都很有价值，从基本的软件开发卫生到复杂的安全和法规遵从性管理，重点关注篡改和漂移检测、零日修复、取证分析等。

虽然您可以使用安全扫描工具来识别软件组件，但它们通常无法让您访问 SBOM，或者无法提供支持各种用例所需的详细信息。Docker 和 Anchore 之间的开源合作使您能够独立于漏洞扫描或许可证检测等操作来创建和存储 SBOM。

在底层，`docker sbom`命令利用 Syft 对 SPDX、CycloneDX、Syft-JSON 等行业标准格式的使用来创建和存储与不断发展的安全和 DevOps 基础设施工具互操作的 SBOMs。

您的用例将决定使用哪种 SBOM 格式。例如，如果与其他工具的互操作性很重要，可以选择 SPDX 或 CycloneDX 作为向下游客户分发 SBOMs 的标准格式。Syft 还提供了一种原生 SBOM 格式，用于与 [Grype](https://github.com/anchore/grype) 漏洞扫描器的无损互操作性。

## **动作中的`docker sbom`命令**

新的`docker sbom`命令易于使用，并利用 Syft 的功能以各种数据格式生成丰富的 SBOM 内容，其他工具可以接收这些内容来执行关键的安全操作，如漏洞扫描。

在本例中，`docker sbom`命令是针对一个测试映像执行的，该测试映像将标准发行版提供的包(我在这里使用的是 Alpine)与 Log4j 的几个易受攻击的版本结合在一起，这些版本以各种不同的形式打包，从顶层 jar 到压缩 Java 归档中的多级 jar:

```
%  docker  sbom  dnurmi/testrepo:jarjar

Syft v0.42.2

✔  Loaded image
✔  Parsed image
✔  Cataloged packages  [217  packages]

NAME              VERSION      TYPE

alpine-baselayout  3.2.0-r18    apk
alpine-keys 2.4-r1 apk

…
…
log4j-core        2.12.1 java-archive
log4j-core        2.11.0 java-archive
log4j-core        2.11.1 java-archive
log4j-core        2.13.2 java-archive
log4j-core        2.12.0 java-archive
…

```

“docker sbom”命令支持越来越多的输出格式，这些格式可以直接集成到分析 sbom 的其他系统和工具中，但默认输出是人类可读的格式:

```
%  docker  sbom  --help

Usage:  docker sbom  [OPTIONS]  COMMAND

…

 --  format string    report output format,  options=[syft-json cyclonedx-xml cyclonedx-json github-json spdx-tag-value spdx-json table text]

                                          (default  "table")

…

```

为了演示该命令是如何工作的，这里有一个简单的用例，其中“docker sbom”用于将其数据生成为 SPDX JSON，供 Anchore 的开源漏洞扫描器 [Grype](https://github.com/anchore/grype) 使用，以生成漏洞报告:

```
%  docker  sbom  --format  spdx-json  docker.io/dnurmi/testrepo:jarjar  |  grype

Syft v0.42.2

✔  Loaded image
✔  Parsed image
✔  Cataloged packages  [217  packages]

NAME        INSTALLED      FIXED-IN VULNERABILITY SEVERITY

…
log4j-core 2.12.1 CVE-2021-45046 Critical
log4j-core 2.11.0 CVE-2021-45105 Medium
log4j-core 2.13.2        2.16.0 GHSA-7rjr-3q55-vv33    Critical
log4j-core 2.12.1        2.12.4 GHSA-8489-44mv-ggj8    Medium
log4j-core 2.13.0 CVE-2020-9488          Low
log4j-core 2.12.1        2.12.3 GHSA-p6xc-xr62-6r2g    High
log4j-core 2.12.0        2.12.3 GHSA-p6xc-xr62-6r2g    High
log4j-core 2.12.0 CVE-2021-44832 Medium
…

```

正如您所看到的，新的“docker sbom”命令是一个强大的功能，可以快速生成可被您已经使用的安全工具吸收的 sbom。SBOMs 是容器安全性的基础，使您能够更快地查明和补救开发过程中任何阶段可能出现的安全风险。Docker 桌面的所有用户现在都可以使用 [`docker sbom`命令](https://docs.docker.com/engine/sbom/)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>