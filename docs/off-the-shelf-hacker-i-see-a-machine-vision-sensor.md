# 现成的黑客:“我看到一个机器视觉传感器”

> 原文：<https://thenewstack.io/off-the-shelf-hacker-i-see-a-machine-vision-sensor/>

上周我们讲述了用语音合成进行物体识别的基础知识。JeVois 智能机器视觉传感器“看到”物体， [eSpeak](http://espeak.sourceforge.net/) 命令行程序“说出”名称， [guvcview](http://guvcview.sourceforge.net/) 程序与传感器接口，处理脚本管理整个工作。我在老式的华硕 Linux 笔记本上运行了它。

这一周，我已经成功地将所有东西移植到机器人头骨赫德利上运行，它有内置的树莓 Pi 和一堆 Arduino 板。JeVois 传感器被重新安装在他的右眼窝，一个小型音频放大器让他通过树莓 Pi 音频端口和头骨安装的扬声器说话。

该设置被简化为仅使用一个[处理语言脚本](https://processing.org/)，而不需要通过 guvcview 提供视频。我们也不再需要通过 Arduino 串行监视器向 JeVois 发送命令。它是这样工作的。

## 准备 Pi

赫德利用 Raspbian GNU/Linux 9 运行一个 Raspberry Pi 3 模型 B+处理 IDE 的版本是 3.5.3。我还使用 Synaptic 程序管理器加载了 luvcview 和 guvcview。顺便说一句，在 Pi 3 上伸展跑得很好。

这两个程序在测试 JeVois 识别和发送数据方面非常有效。请注意，guvcview 将处理器利用率锁定在 100%，因为它非常占用资源。大约一分钟后，主桌面显示器上的高温 CPU 指示灯将亮起。对于长期测试，请使用 luvcview。下面是一个测试命令行示例。用于退出。

`luvcview -f YUYV -s 640x498`

我已经升级了上周的代码，以便在您每次点击处理 IDE 中的“run”时配置 JeVois。它不再需要网络摄像头查看器或 Arduino 串行监视器来开始识别对象。

这是新的处理代码。

```
---------------------
// Example by Tom Igoe

import processing.serial.*;

int lf  =  10;  // Linefeed in ASCII
String myString  =  null;
Serial myPort;  // The serial port

void setup()  {
// Open the port you are using at the rate you want:
myPort  =  new Serial(this,  "/dev/ttyACM0",  115200);

myPort.write("streamoff\n");
myPort.write("setpar serout All\n");
// myPort.write("setmapping2 YUYV 320 240 15.0 JeVois TensorFlowEasy\n");
// myPort.write("setmapping2 YUYV 640 480 15.0 JeVois DetectionDNN\n");
myPort.write("setmapping2 YUYV 640 480 15.0 JeVois DarknetYOLO\n");
myPort.write("streamon\n");
myPort.write("setpar serstyle Normal\n");
myPort.clear();

}

void draw()  {
if  (myPort.available()  &gt;  0)  {
myString  =  myPort.readStringUntil(lf);

if  (myString  !=  null)  {
println(myString);
String[]  q  =  splitTokens(myString,  " :");
if  (q[0].equals("N2")  ==  true)  {
exec("espeak",  "I see a "  +  q[1]);
}
}
delay(3000);
myPort.clear();
}
}
----------------------

```

## 代码详情

注意，在 setup 部分，我们有一堆 myPort.write()语句。这些设置 JeVois 通过 USB 串行端口进行通信，将数据细节设置为“正常”并选择要使用的识别算法。DarknetYOLO one 可以很好地识别人、椅子、键盘、遥控器等等。还要注意，所有行都以换行符结束。您必须在每个命令的末尾包含一个换行符，这样它才能在 JeVois 串行接口环境中执行。如果你把“\n”关了，你会数小时地转动轮子，想知道为什么算法不变，或者为什么数据从不流动。

当没有需要识别的内容时，我在整理各种响应文本、实际数据和空白行时遇到了一些问题。JeVois 使用一种标准化的数据格式，这种格式根据所选择的详细程度而变化。典型的代码行可能如下所示。

```
N2 dog:68  -629  -259  581  734

```

我也偶尔得到“好的”，作为 JeVois 的回应。如果您只是得到一个“OK”，即使该行不为空，处理也会生成一个数组越界错误，因为我们试图索引一个不存在的行元素。没有其他代币了。我在其他处理项目中遇到过这种情况。简单的解决方案是处理数据行，如果它不为空，并且我们在第一个文本数据元素中找到一个细节级别指示符。n 对应正常，T 对应简洁等等。

同样，显然处理不能用简单的逻辑&&或||测试来比较字符串。您必须使用字符串比较函数。在使用 splitTokens()函数分隔数据行元素之后，我们可以使用 q[0]将第一个数据文本字符串与“N2”进行比较。等于(“N2”)函数。如果为真，我们继续说出第二个文本位置(q[1])中的对象名称，而没有数组越界错误。

代码中还有几个 myPort.clear()调用。当我们从 JeVois 传感器读取新的数据行时，这些确保我们在串行端口馈送中没有任何残留的奇怪数据。delay(3000)调用在识别的对象之间给出了三秒钟的暂停。如果没有适当的延迟，当 JeVois 每隔 250 秒发送一次新的对象点击时，扬声器中就会出现非常恼人的对象名称回声。赫德利女士试图在三秒钟内考虑到社交方面的问题。

[https://www.youtube.com/embed/CZXkITzrKB8?feature=oembed](https://www.youtube.com/embed/CZXkITzrKB8?feature=oembed)

视频

为了这个项目，我改变了赫德利的一些其他东西。一个是断开从 JeVois 到全景伺服 Arduino 的硬件串行线，在他的头骨顶部。弄清楚如何通过连接 Raspberry Pi 的 USB 电缆将跟踪数据路由到 pan 伺服子系统是现在要做的事情。我将不得不制定出一些协调方案来控制来自 Pi 的平移、颌和其他伺服系统，以及来自 JeVois 和其他传感器的输入。数据将通过 USB 串行线流动，而不是通过硬件串行端口。看起来我可能需要某种“显示”脚本程序。

我还暂时解开了下颚伺服系统。当前使用处理脚本基于预先记录来移动颌。WAV 音频文件。我需要将新的对象识别和语音合成脚本与旧程序中真实驱动颌伺服的分析相集成。

## 后续步骤

我正在寻找一种可靠的方法，通过 Pi 和子系统运行，将下巴运动与对象识别/语音合成同步。低延迟很重要，因为我们不希望实际声音输出和下巴上下摆动之间有任何延迟。即使 200 毫秒的延迟也会破坏“通话”效果。

我也在寻找动态调整 JeVois 识别算法的方法。例如，对于赫德利来说，长时间坐在那里可能是有用的，如果他面前有运动(比如说，使用[惊喜记录器模块](http://jevois.org/moddoc/SurpriseRecorder/modinfo.html)，切换到[暗网 YOLO 算法](http://jevois.org/moddoc/DarknetYOLO/modinfo.html)进行面部和物体识别。在更远的距离上探测到运动会让他醒来注意到面孔和物体，这在更远的地方是很难探测到的。

为特定的脸或物体生成我自己的自定义网络也可能很酷。另一个想法是将几个模块组合起来，扩展被识别的内容。也许说阿鲁科符号和物体。

赫德利认为我们在解释和记录现成项目的过程中做得非常好。他很想听到读者的反馈。嗯……我们正在研究语音识别。尽管如此，你也可以通过给 doc@drtorq.com[发一封短信来提出新的话题和新的探索。](mailto:doc@drtorq.com)

*赶【Torq 博士的 [现成黑客专栏](https://thenewstack.io/tag/off-the-shelf-hacker/)，每周六，只上新栈！在[doc@drtorq.com](mailto:doc@drtorq.com)或 407-718-3274 直接联系他咨询、演讲和委托项目。*

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>