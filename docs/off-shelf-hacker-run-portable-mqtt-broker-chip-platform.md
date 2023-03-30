# 现成的黑客:用芯片平台运行一个可移植的 MQTT 代理

> 原文：<https://thenewstack.io/off-shelf-hacker-run-portable-mqtt-broker-chip-platform/>

出于各种不同的原因，创业公司一直在转型。传统思维认为你应该灵活、敏捷，能够顺应变化。

将您的想法原型化到物理计算堆栈项目中也没什么不同。做新东西总是有不确定性。有时你会掉进兔子洞，或者意识到你不能从这里到达那里。主板来了又走，产品停产，支持从未实现，承诺的功能没有进入芯片…列表几乎是无限的。

因此，对于我的项目，上周开始的[，构建一个可移植的 MQTT 代理，我正在从 Artik 10 转向芯片平台。](https://thenewstack.io/off-shelf-hacker-building-portable-mqtt-broker-artik/)

我意识到 Artik 10 最近停产了。Artik 7 现在是老大。我没有那种东西。尽管如此，并没有失去一切，因为我将 Artik 10 配置为一个接入点，然后用辛苦获得的知识用手头的[芯片板](https://getchip.com/pages/chip)做了同样的事情。

该芯片的母公司 [Next Thing Co.](https://getchip.com/) 最近推出了[芯片 Pro](https://getchip.com/pages/chippro) 。它售价 16 美元，面向业余爱好者/商业用户，看起来可能会生产一段时间。虽然它的闪存比芯片少，但电路板要小得多，并且有一个外部天线连接器。我正在探索便携式无线数据中心版本 2.0 或 3.0 的 Pro 模型。

硬件快车道上的生活。我们走吧。

## 把芯片做成 AP

与此同时，我们可以利用当前的芯片平台制作原型。旗舰主板配备了 1GHz 处理器、512MB 内存、4GB 闪存、WiFi B/G/N、蓝牙、一些数字 I/O 引脚和 Linux。当然，我欣赏 Linux 在 Flash 中运行，因为它实际上简化了构建过程。该芯片还在模块上集成了板载天线，这将满足 1.0 版本的便携式数据集线器。

便携式无线数据集线器的一个关键特性是能够充当自己的接入点(AP)。通过这种方式，您可以拥有自己的小型 WiFi 网络，可能会运行 MQTT 代理，从而促进边缘设备、ESP8266 传感器或其他 nano-Linux 微控制器模块之间的消息来回传递。

我找到一个[公开的 Slack 文件](https://slack-files.com/T02GVC9G6-F0H7G3WCT-25e7dfb781)是关于把芯片做成接入点的。按照说明操作会产生一个非常基本的、肯定不安全的本地网络，在支持 WiFi 的设备和芯片计算机之间传递信息。

步骤非常简单。这里有一个总结。

*   安装 dnsmasq 以允许 DHCP 连接到芯片。
*   编辑/etc/network/interfaces 文件以设置接入点 IP 地址。
*   启动 DHCP 服务器。
*   编辑/etc/hostapd.conf 文件，将 WLAN1 配置为接入点。
*   用 hostapd 启动接入点。
*   通过编辑/lib/systemd/system/hostapd-systemd . service 文件来配置 AP 启动。
*   使用 systemctl 命令为自动引导配置 systemd。

重启芯片后，您可以通过边缘设备上的 172.20.1.xxx IP 地址连接到接入点。

我还在/etc/hostapd/hostapd.conf 文件中添加了几行，以便在边缘设备尝试登录基于芯片的接入点时请求网络密码。同样，这是非常基本的，应该为安全的生产环境进行强化。对于我的原型来说，密码短语方法已经足够好了。

```
auth_algs=1
wpa=2
wpa_passphrase=moseshorwitz  (choose the passphrase here)
wpa_pairwise=TKIP CCMP
rsn_pairwise=CCMP

```

保存然后重启，使芯片准备就绪。

## 测试 MQTT

在[“使用 MQTT 的轻量级设备间消息传递”的故事](https://thenewstack.io/off-shelf-hacker-lightweight-inter-device-messaging-mqtt/)中，从去年 1 月开始，我介绍了在芯片上安装和运行 MQTT。从那以后，我没有对芯片做任何重大的改动，所以我希望 Mosquitto 代理在它启动时就开始运行。

果然，芯片正确启动了，我可以将我的 Linux 笔记本连接到新的接入点，我在 hostapd 文件中将其命名为“drtorq-port-1”。用 ifconfig，在笔记本上，我还看到它从芯片的 DHCP 服务器上抓取了一个 172.20.0.xxx 的 IP 地址。太棒了。

为了测试 mqtt，我在笔记本上打开了一个新的终端，并激活下面的命令行，在芯片的 IP 地址上设置对 MQTT 主题的订阅。

```
drtorq-notebook%  mosquitto_sub  -h  172.20.0.1  -t  mqtt

```

接下来，我打开另一个终端，运行 MQTT“pub”命令行。

```
drtorq-notebook%  mosquitto_pub  -h  172.20.0.1  -t  mqtt  -m  test1

```

我一按回车，mosquitto_sub 终端上就弹出了“测试 1”。我又试了几次，用了不同的尾号，只是为了确认一下。

## 滚动便携式

我们现在可以做很多有趣的事情，比如采用多个 ESP8266/PIR 传感器，也许可以向机器人/边缘设备发送消息，点亮 LED 灯串或运行电机。让您的协作边缘设备想象力发挥到极致。

我实际上用旧的 2400 mAh 手机电池尝试了芯片/MQTT 代理，我用它来制作树莓 Pi 供电的蒸汽朋克徽章。结果令人失望，因为芯片只运行了一分钟左右，然后芯片的发光二极管都变暗了。可能是拉的果汁太多了。必须进行调查并排除故障。

我刚出去试了试车里的芯片。非常有效。那是芯片挂在后视镜上，插在汽车 USB 适配器上。在芯片和我的 Linux 笔记本之间还有大约 50 英尺和四面墙。超越它！

这就是一个由芯片计算机制成的便携式无线数据中心的雏形。去做一些酷的东西。MQTT 无疑已经不再仅仅是工业控制领域的明星。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>