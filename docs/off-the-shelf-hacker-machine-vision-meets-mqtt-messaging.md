# 现成的黑客:机器视觉遇到 MQTT 消息

> 原文：<https://thenewstack.io/off-the-shelf-hacker-machine-vision-meets-mqtt-messaging/>

在过去的几周里，我们已经讲述了用 [JeVois 传感器](http://jevois.org/)识别物体，并将数据发送到文本到语音转换[处理脚本](https://processing.org/)。我开始思考，使用 [MQTT](http://mqtt.org/) 协议将识别出的对象名称和位置数据传递给其他机器和系统，会带来很多额外的自动化可能性。MQTT 已经成为物联网(IoT)和[工业物联网(IIoT)](https://en.wikipedia.org/wiki/Industrial_internet_of_things) 世界的通用消息交换标准。

将 MQTT 消息传递集成到我们的处理脚本中相当简单，只需增加几行代码。将 MQTT 消息发布到一个联网的代理使得数据可以随时用于日志记录、公告、控制物理动作和其他用途。

## 机器视觉加 MQTT

我们需要一个 MQTT 代理来来回回发送消息。JakeMakes 有一个非常好的安装程序。我还在以前的[可穿戴设备故事](/off-shelf-hacker-run-mqtt-wearable/)中介绍过 MQTT 的安装。

我将 [Mosquitto](https://mosquitto.org/) MQTT broker 和 clients 安装在[我的基于 Raspberry Pi 的会说话的头骨](https://thenewstack.io/off-the-shelf-hacker-conversations-with-hedley-the-robotic-skull/)上。它会在启动时自动运行，所以当它需要处理发送到客户端或来自客户端的消息时就可以使用。我还通过处理 IDE 安装了 MQTT 贡献库。修改后的文本到语音处理脚本获取识别出的对象名，将其传递给 MQTT 发布函数，并通过代理使其可用。我还在我的 ASUS Linux 笔记本上使用 Synaptic 应用程序管理器安装了标准的 MQTT 代理/客户机包，以便能够在另一台联网的机器上测试新的处理脚本。一旦对处理脚本进行了软件更改，我可以使用下面的命令行检查消息(识别的名称和位置数据)。

下面是我在 Linux 笔记本上使用的命令行，用来查看来自 JeVois 传感器的 MQTT 消息。

```
pi%  mosquitto_sub  -h  192.168.1.111  -t  mqtt5

```

下面的过程通过处理 IDE 添加 MQTT 库。开始加工树莓酱。在“草图”选项卡下，单击“导入库”，然后单击“添加库”在贡献经理搜索框中键入“MQTT”，然后点击“Enter”单击 Joel Gaehwiler 的“基于 Eclipse Paho 项目的 MQTT 处理库”。按右下角的“安装”按钮安装库，安装完成后关闭窗口。我在华硕的 Linux 笔记本和赫德利的 Raspberry Pi 上使用的都是 3.5.3 版本的处理程序。两台机器上的 MQTT 处理库版本都是 1.7.1。Linux 笔记本上的 Mosquitto 代理和客户端版本为 1.4.15-2ubuntu0.18.04.3。

## 修改上周的代码

今天，关于物理计算项目原型的最酷的事情之一是，你可以将硬件模块插在一起，然后通过改变一些代码从根本上改变小工具的行为。在这里指向一个新安装的库，在那里添加几行代码，噗…新的功能。Processing 有许多有趣的库，您可能会觉得有用。表哥，Arduino IDE 也有类似的库。

这是处理代码。

```
import processing.serial.*;
import mqtt.*; 
MQTTClient client;  
int lf  =  10;  // Linefeed in ASCII
String myString  =  null;
Serial myPort;  // The serial port

void setup()  {
// Open the port you are using at the rate you want:
myPort  =  new Serial(this,  "/dev/ttyACM0",  115200);
// myPort = new Serial(this, "/dev/ttyUSB0", 115200);

myPort.write("streamoff\n");
myPort.write("setpar serout All\n");
// myPort.write("setmapping2 YUYV 320 240 15.0 JeVois TensorFlowEasy\n");
// myPort.write("setmapping2 YUYV 640 480 15.0 JeVois DetectionDNN\n");
myPort.write("setmapping2 YUYV 640 480 15.0 JeVois DarknetYOLO\n");
myPort.write("streamon\n");
myPort.write("setpar serstyle Normal\n");
myPort.clear();

client  =  new MQTTClient(this);
client.connect("mqtt://192.168.1.111",  "nothing");
// client.connect("mqtt://test.mosquitto.org", "nothing");
}

void draw()  {
if  (myPort.available()  &gt;  0)  {
myString  =  myPort.readStringUntil(lf);

if  (myString  !=  null)  {
println(myString);
String[]  q  =  splitTokens(myString,  " :");
if  (q[0].equals("N2")  ==  true)  {
// exec("espeak", "I see a " + q[1]);

client.publish("mqtt5",  q[1]  +  " at x= "  +  q[2]  +  " y = "  +  q[3]);

}
}
delay(3000);
myPort.clear();
}
}
void messageReceived(String topic,  byte[]  payload)  {
println("new message: "  +  topic  +  " - "  +  new String(payload));
}

```

MQTT 库和客户机引用在脚本开始时被初始化。然后用代理的 IP 地址建立客户机和连接。确保包含地址的“mqtt://”部分。您也可以使用外部 MQTT 代理。Mosquitto 有一个公共测试代理，可以免费使用。插入“mqtt://test.mosquitto.org”代替 IP 地址，如注释大纲所示。

发送到代理的实际消息由 client.publish()函数处理。在我们的例子中，“mqtt5”是主题。变量 q[1]指的是已识别的名称。q[2]和 q[3]对应于赫德利视野内被识别物体的 x 和 y 坐标。你能在你的机器视觉/MQTT 项目中使用物体位置数据吗？

我遇到的一个奇怪的情况是“runtime exception:MQTT]Callback not found”错误。不确定原因。“messageReceived()”函数出现在 MQTT 库下的一个示例程序中，所以我只是将它包含在代码中，它就消除了错误。

[https://www.youtube.com/embed/-h6SN62N8m4?feature=oembed](https://www.youtube.com/embed/-h6SN62N8m4?feature=oembed)

视频

## 后续步骤

JeVois 传感器数据和 MQTT 有很多可能的用例。

也许我们可以将 JeVois 传感器连接到一个 [NodeMCU 板](https://www.amazon.com/HiLetgo-Internet-Development-Wireless-Micropython/dp/B010O1G1ES)上，并使用 MQTT 消息通知我们有人在前门。Arduino IDE 有许多 MQTT 库。或者，使用 Linux 笔记本上的处理脚本进行远程文本到语音音频对象识别怎么样？或者，当前门传感器检测到汽车停在车道上时，使用 NodeMCU 板的联网灯会打开？嘿，打开洒水阀怎么样，用 MQTT 来阻止院子里的流浪动物？有了 MQTT，让数据在网络上可用变得简单而快速。

我们还能用这项技术做什么？

*赶【Torq 博士的 [现成黑客专栏](https://thenewstack.io/tag/off-the-shelf-hacker/)，每周六，只上新栈！在[doc@drtorq.com](mailto:doc@drtorq.com)或 407-718-3274 直接联系他咨询、演讲出场和委托项目。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>