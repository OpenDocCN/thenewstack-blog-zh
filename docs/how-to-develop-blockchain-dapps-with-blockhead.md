# 如何用 Blockhead 开发区块链‘Dapps’

> 原文：<https://thenewstack.io/how-to-develop-blockchain-dapps-with-blockhead/>

*以下是 Cloud Foundry Foundation 关于数字化转型系列文章的一部分，旨在为即将在 T2 举行的 [Cloud Foundry 峰会做准备。](https://www.cloudfoundry.org/event/eusummit2018/)*

在过去的几年里，新的[区块链](https://en.wikipedia.org/wiki/Blockchain)技术的出现促使应用程序制造商——被称为[去中心化应用程序(dapp)](https://github.com/ethereum/wiki/wiki/Decentralized-apps-(dapps)) 开发者——为用户提供利用被大肆宣传的分布式账本的新方式。

然而，dapp 开发需要深入了解智能合约和区块链网络。Dapps 本质上是分散的，因为应用的每个实例可以与网络的不同节点通信。因此，dapp 开发人员必须在许多技术上有坚实的基础。他们必须能够:

1.  选择网络
2.  创建一个节点并将其连接到网络
3.  创建智能合同
4.  部署智能合同
5.  开发一个 dapp 来与智能合约交互。

但是，如果我们能够降低难度，允许普通开发人员创建 dapps，会怎么样呢？这就是[项目傻瓜](https://www.cloudfoundry.org/blog/cloud-foundry-summit-hackathon-project-blockhead/)的用武之地，它帮助开发者简化上面的前四个步骤，让他们专注于他们的 dapp。

那么什么是笨蛋呢？它是[开放服务代理 API (OSB API)](https://github.com/openservicebrokerapi/servicebroker) 的一个实现，提供了节点的按需供应以及智能合约的部署。这个想法是 dapp 开发人员应该专注于构建他们的应用程序，让笨蛋经纪人去担心节点和智能合同管理。

这个项目源于我在 2018 年北美[云铸造峰会上参加的一次黑客马拉松，后来被接受为](https://www.cloudfoundry.org/event/nasummit2018/) [CF-Extension](https://github.com/cloudfoundry/pmc-notes/blob/master/Extensions/2018/08-27-2018.md) 项目。团队 Blockhead 由[尼玛·卡维亚尼](https://www.linkedin.com/in/nimakaviani/)(IBM 高级云工程师)[乔纳森·伯克哈恩](https://www.linkedin.com/in/jonathan-berkhahn-285779103/)(IBM 开源贡献者)[摩根·鲍尔](https://www.linkedin.com/in/morganbauer/)(IBM 开源贡献者)和我组成。自黑客马拉松以来，该团队一直在重写 Golang 中的代理，我们很高兴在即将举行的[云铸造峰会](https://www.cloudfoundry.org/event/eusummit2018/)上展示它。

## Blockhead 和开放服务代理 API

斯韦塔·雷帕库拉

Swetha 是一名软件工程师，在 IBM 的开放技术部门工作。自 2017 年底以来，她一直致力于 Hyperledger Fabric，这是一个 EVM 集成的开源区块链平台。之前，她是 Cloud Foundry 的全职开源贡献者。Swetha 拥有加州大学伯克利分校的电气工程和计算机科学学士学位。

OSB API 最初来自 [Cloud Foundry](https://www.cloudfoundry.org/) ，它为应用程序定义了一组通用的 API，以便轻松创建和连接关系数据库等云服务。该规范有助于将应用程序与它们所依赖的服务分离开来，允许将两者的管理分开。Blockhead 实现了应用程序开发人员在使用 OSB API 代理时可以预期的五个端点，通过它可以管理部署到[平台即服务(PaaS)](https://searchcloudcomputing.techtarget.com/definition/Platform-as-a-Service-PaaS) 平台的区块链节点的生命周期。

这就是标准 OSB API 端点如何转化为管理区块链节点的过程:

1.  catalog:*GET/v2/catalog*
    blockhead broker 返回可用服务的信息。目前只支持一个服务，一个已经在开发模式下启动的以太坊节点。
2.  provision:*PUT/v2/service _ instances/:instance _ id*
    在这个阶段，代理启动一个 Docker 容器，这个容器内置了以太坊节点。通过创建 docker 容器，启动了区块链节点，并为其创建了一个新的区块链用户帐户。
3.  绑定:*PUT/v2/service _ instances/:instance _ id/service _ bindings/:binding _ id*
    绑定时，用户必须提供想要部署的 solidity smart 契约。代理将依次下载、编译合同，并通过节点将其部署到区块链。部署智能合约后，代理返回已创建的用户帐户地址、合约地址以及区块链节点的 IP 地址和端口，以便应用程序可以连接到它。在这个阶段，使用 web3.js 等库的应用程序可以很容易地与已经创建的开发以太坊网络进行通信。根据用于托管 dapp 的 PaaS，这些信息可以作为环境变量使用。
4.  unbind:*DELETE/v2/service _ instances/:instance _ id/service _ bindings/:binding _ id*
    目前，blockhead broker 对以太坊节点不做任何处理。然而，大多数 PaaS 会从应用程序的环境中删除连接信息。
5.  de provision:*DELETE/v2/service _ instances/:instance _ id*
    代理将停止并删除一直运行以太坊节点的 docker 容器。

## 部署和注册代理

推荐的部署 Blockhead 代理的方法是通过 Bosh 或构建 docker 文件。

下面的教程是针对 Bosh 代理的(关于如何在没有 Bosh 的情况下部署代理的说明可以在这里找到: [Readme](https://github.com/cloudfoundry-incubator/blockhead/blob/master/README.md) ):

1.  创建一个清单。该版本中包括一个清单，可用于 bosh-lite 和“cf-deployment”bosh-lite 云配置。
2.  部署代理。在存储库的根目录下运行以下命令。Bosh cli 应该已经指向正确的 Bosh director:Bosh-d block head deploy block head . yml–vars-store creds.yml
    将创建“creds . yml ”,它将具有身份验证所需的密码。
3.  向 PaaS 注册代理。(本教程针对云代工厂的 PaaS。)以管理员用户身份登录后，运行以下命令。您将需要可以在上一步中创建的“creds.yml”文件中找到的密码:
    *cf register-broker block head admin<密码>*
4.  启用对所需计划的服务访问。目前，代理仅在开发模式下支持“geth”:
    cf enable-service eth dev
5.  验证计划在市场上可用:cf marketplace。您应该看到可用的“eth”服务。

## 使用 Blockhead 服务

Dapp 开发人员使用注册了 Blockhead broker 的 PaaS，可以使用该服务来简化他们的开发过程。下面的教程是面向 Cloud Foundry 用户的，但是并行的步骤也可以使用其他 PaaS 来完成，比如已经采用了 OSBAPI 的 Kubernetes。在执行这些步骤之前，请确保您使用“cf”CLI 登录到平台。

1.  下载演示应用程序:git 克隆[https://github.com/swetharepakula/blockhead-broker-demo](https://github.com/swetharepakula/blockhead-broker-demo)
2.  *cd 木头人-经纪人-演示*
3.  无需启动即可启动 dapp，以便连接您的服务:*cf push myApp–no-start*
4.  创建服务:
    *cf 创建服务 eth dev myEth*
5.  绑定应用:
    *cf bind-service myApp*myEth*-c ' { " contract _ URL ":" https://github . com/swetharepakula/block head-broker-demo/blob/master/poll . sol " }*
6.  你的应用程序的环境应该揭示你需要连接到 geth *节点的所有信息:cf env myApp*
7.  启动你的应用程序。确保你的应用程序被设计成从环境变量中读取:*“VCAP _ 服务”*
    *cf start myApp*

## 未来计划

我们计划关注一系列事情，从部署方法到代理上支持的服务。未来发展的一个领域是让运营商选择在 Kubernetes 上部署代理。对于开发人员，该团队正在考虑增加对 Hyperledger Fabric 与部署在受支持的 PaaS 平台上的应用程序集成的支持。

该团队将在瑞士巴塞尔举行的[云铸造峰会欧盟](https://www.cloudfoundry.org/event/eusummit2018/)上展示新版 Go 版的 Blockhead broker。上面的教程将由 Nima 和这位作者进行主题演示，然后在 Nima 和 Morgan 主持的分组会议上深入探讨经纪人。

加入我们在巴塞尔，了解更多关于傻瓜经纪人！

![](img/3c28874669ffae10b9e381740ccdb2b0.png)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>