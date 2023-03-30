# 近距离观察微软视觉人工智能套件

> 原文：<https://thenewstack.io/a-closer-look-at-microsoft-vision-ai-kit/>

上周，微软和高通联合发布了 [Vision AI Kit](https://aka.ms/visionaidevkit) ，这是一款由高通 AI 加速器芯片和微软 [Azure 物联网边缘平台](https://azure.microsoft.com/en-us/overview/iot/)驱动的智能相机。

视觉人工智能开发工具包是一个学习卷积神经网络如何工作的伟大设备。探索 Azure IoT Edge 的概念也是一个很好的起点。这个开发者套件与 [AWS DeepLens](https://thenewstack.io/deep-dive-amazon-deeplens/) 非常相似。这两种设备都被配置为边缘设备，相机充当图像处理器。这两款设备都运行人工智能模型，在边缘执行推理，并将输出发送回云端。

硬件规格和软件配置详情，参考我的[福布斯文章](https://www.forbes.com/sites/janakirammsv/2019/09/09/microsoft-vision-ai-developer-kit-simplifies-building-vision-based-deep-learning-projects/)。在我之前的一篇文章[New Stack](https://thenewstack.io/azure-iot-edge-a-technology-primer/)中，我也谈到了 Azure IoT Edge 的架构。

![](img/433d73ae5b6582ec706ea9bb35ad9371.png)

与 AWS DeepLens 相比，Microsoft Vision AI Kit 看起来是一款复杂而精致的设备。开发者体验比 AWS DeepLens 好很多。

在本教程中，我将引导您完成配置和连接 Microsoft Vision AI Dev Kit 的步骤。

### 第一次运行:将开发工具包连接到云

一旦设备被打开并打开，它就会广播一个 Wi-Fi SSID，通常以 MSIoT_XXXX 开头。将您的开发机器连接到 SSID。不要试图用你的手机来配置它。你需要一个成熟的浏览器来完成设置。

连接到设备 Wi-Fi 后，在您的机器上访问**http://setupaicamera . ms**(注意:仅在连接到相机 WiFi 后，链接才起作用)。

![](img/12ab6adfdfd32f71f2d4524ecb7964fd.png)

您可以为 Wi-Fi 设置密码，也可以通过添加用户名和密码来配置 SSH 访问。

![](img/c4eeb813350370f1b881b72a765891e0.png)

下一步，您通过现有的 Wi-Fi 网络将设备连接到互联网。

![](img/ba7b18587926a2820361832043fc4c3b.png)

![](img/e2558c6fa5af03da99d19b8eb5fba97f.png)

![](img/10b2c4ed08b865dfdc21890eecca7c2f.png)

在下一步中，您将看到一个令牌，以便使用 Azure 进行身份验证。复制令牌，然后单击下一步。

![](img/7b7446f66a6069cc849da19276e835fb.png)

使用 Azure 完成身份验证过程。

![](img/73cc9467899a5f06e40bc72fd61573a3.png)

在接下来的两个步骤中，我们配置与摄像机相关联的 Azure 资源。

![](img/fdb90d9852009a184e8b5895d8851e42.png)

![](img/8dbec0a0e8b8d17d5f6b0f9d86c6212a.png)

提供用于向 Azure IoT Hub 注册相机的名称，然后单击“下一步”。

![](img/e7f433b5bd789e907b060fa5b3473250.png)

该设备将开始下载 Azure IoT Edge 平台所需的模块。![](img/86916b24f8d9fdb8d631b66b381ee5dd.png)

几分钟后，我们得到了一个到摄像头的链接，通过它我们可以访问网络流。这表明安装已经成功。

![](img/a1b3a680aeac26a44a64e1bf6d02906b.png)

访问上述 URL 会在浏览器窗口中显示摄像头馈送。尝试在相机前放置物品，以执行对象检测。下面的截图显示了摄像头检测到一辆汽车。

![](img/06e6b1935a45ad67d074cd436a27984f.png)

恭喜你！你已经准备好将定制的 AI 模型部署到相机上了。

我钻进相机，进一步探索这个平台。该设备运行定制版本的 Yocto Linux 发行版。![](img/57c6dcb7ab7f645b4f5d00795dfb1029.png)

为了运行 Azure 物联网边缘模块，微软和高通将 Docker 引擎移植到 Yocto。容器运行时与 Docker API 1.40 兼容。

![](img/2bf231e539c55b2e42c178d176ec17c0.png)

该设备运行 4 个容器来提供开箱即用的体验。容器***visionsamplemodule:1 . 1 . 3-arm 32v 7***运行 MobileNet SSD V1，而***visionsamplemodule:webstream _ 0 . 0 . 13-arm 32v 7***运行基于 Node.js 的 WebSocket 应用程序来流式传输摄像机馈送。

剩下的两个容器是核心 Azure IoT Edge runt ime 的一部分。

![](img/f42b341e153d531625437dfcfb917bc2.png)

我们也可以通过运行*io edge list*命令来列出模块。 ![](img/036099a9a7f8cd42e5fcdc1f6cc220dd.png)

如果您执行到 AIVisionDevKitGetStartedModule，您可以在 *models* 目录中看到 MobileNet SSD 文件的优化版本。该文件负责对入站摄像机馈送进行推断。 ![](img/d9241d9d0f23743d450a91bca446eb5e.png) Azure Portal 也显示了在设备中运行的同一套模块。

![](img/f5a58e5a524d555a4fd52f12f874a0cc.png)

在下一篇文章中，我将演示如何部署使用 CustomVision 训练的模型。人工智能汽车服务。敬请期待！

贾纳基拉姆·MSV 的网络研讨会系列“机器智能和现代基础设施(MI2)”提供了涵盖前沿技术的信息丰富、见解深刻的会议。在 [http://mi2.live](http://mi2.live/) 上注册参加即将举行的 MI2 网络研讨会。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>