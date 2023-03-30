# 现成的黑客:完善机器人头骨中的声音-颌同步

> 原文：<https://thenewstack.io/off-the-shelf-hacker-refining-voice-jaw-synchronization-in-robotic-skulls/>

实际上，让机器人的下巴与合成声音同步移动是一个挑战。Frightprops 有 [PicoTalk 伺服控制器](https://www.frightprops.com/controllers-electronics/frightideas-controllers/picoboo-controllers/picotalk-servo-controller.html)售价约 80 美元。Skulltronix 以 125 美元的价格提供了 Chuckee board 的儿子[。虽然有点贵，但除了下巴之外，这些板还为眼睛、平移、倾斜等提供伺服控制。](http://www.skulltronix.com/soc.shtml)

最终，我自己的会说话的头骨项目，[头骨赫德利](https://thenewstack.io/hedley-the-robotic-skulls-orthognathic-surgery/)，应该从他的板载树莓 Pi 上进行文本到语音的转换。我设想各种应用程序将赫德利的声音输出到扬声器，同时将位置数据输出到颌控制器。让赫德利通过亚马逊的语音服务“说出”结果，从一个脚本，甚至从一条 MQTT 消息，打开了许多有趣的展示可能性。

虽然现成的主板很有前途，但我认为它们不够灵活，无法满足我的目的。我希望能够摆弄音频实际上是如何分析的，这样我就可以获得最佳的音频与下颌运动的同步。

通过结合使用硬件、固件和软件，Arduino 和 Raspberry Pi 当然可以实现实时音频/下巴移动。今天，我们将检查等式的 Arduino-jaw 侧。Raspberry Pi 的声音和应用程序将在后面的故事中讨论。

## Arduino 颌控制器

在早先的[“现成的黑客:赫德利机器人头骨说话”](https://thenewstack.io/off-the-shelf-hacker-hedley-the-robotic-skull-speaks/)故事中，我们看到了使用一个带有小型[驻极体麦克风](https://www.adafruit.com/product/1713?gclid=EAIaIQobChMI8Zv8xfuP3QIVmUoNCh0ytA9JEAQYAiABEgK6-vD_BwE)的 Arduino 来移动下颚伺服系统。此后，我修改了伺服限制并添加了代码，以从赫德利的 Raspberry Pi 3 读取串行数据，而不是从硬连线麦克风输入。钳夹伺服系统连接到数字引脚 6。目前，音频分析程序的原型是在 Linux 笔记本电脑上完成的。代码最终将转移到赫德利的 Raspberry Pi 3 上，因此他的操作不需要外部计算机。

一个巨大的突破是将颅骨颌位置的数量减少到 10 个，并缩放串行输入以适应该运动范围颌在 0 时关闭，在位置 9 时完全打开。我的理由是，仅仅将“0”到“9”作为文本字符串发送会将数据传输的大小保持在最低限度。从完全打开到完全关闭，我们只有大约 30 度的颚行程。除以 10，我们得到每一步大约三度的移动。

在现实生活中，以三度的步长递增地移动伺服系统会给出相当同步的下颌运动，而没有以前版本代码的抖动。我们可以减少每步的度数，以获得更高的分辨率和更平滑的移动。这意味着我们也必须对串行数据规模做出相应的改变。

另一个现实世界的注意是，我使用了一个几乎是古董的 Arduino NG 作为下颚伺服控制器。这款旧主板的工作频率为 16MHz，使用 8 位数据寻址。与最近的 Arduino 模块相比，它的马力当然非常适中。

然而，NG 完全能够跟踪来自我的运行处理语言音频分析程序的 Linux 笔记本的数据，在音频和下巴运动之间没有明显的滞后。在微控制器领域，性能往往会随着时间的推移而提高，因此使用较旧的电路板进行初始原型制作是一个很好的起点。随着项目的成熟，当新的硬件/软件被替换到位时，事情会变得更顺利、更有能力。

## 更新的代码

Arduino NG 代码非常简单。在编译和上传的时候，一定要指定 NG 板，否则，你会得到错误，下巴根本不会动。不要忘记，在用 NG 板上传固件之前，你必须按下复位按钮。

```
#include 

Servo myservo;
int  s  =  105;
int varpos  =  105;

int closepos  =  95;      // closed servo-jaw limit value
int openpos  =  128;      // open servo-jaw limit value
String inString  =  "";
int steppos  =  100;

void setup()
{  
  myservo.attach(6);
  myservo.write(s);
  Serial.begin(115200);
  while  (!Serial)  {
    ;  // wait for serial port to connect. Needed for native USB port only
  }

}

void loop()  {
  // Read serial input:
  while  (Serial.available()  &gt;  0)  {
    int inChar  =  Serial.read();
    if  (isDigit(inChar))  {
      // convert the incoming byte to a char and add it to the string:
      inString  +=  (char)inChar;
    }
    // if you get a newline, print the string, then the string's value:
    if  (inChar  ==  '\n')  {
      Serial.println(inString.toInt());
      steppos  =  map(inString.toInt(),  0,  9,  closepos,  openpos);
      Serial.println(steppos);
      if  (steppos  &gt;=  closepos  &amp;&amp;  steppos  &lt;=  openpos)  {
      myservo.write(steppos);
      }
      // clear the string for new input:
      inString  =  "";
    }
  }
}

```

变量在文件的开头被初始化。

请注意打开和关闭位置值。这些都是通过反复试验找到的。这些数字与我的伺服机构和颌机构的几何结构一起工作，所以你需要做一些实验来找到适合你的情况的值。准备好立即拉动 USB 电缆，如果伺服对停止猛击。

还有一个初始位置值“105。旧款 NG 在重启后有一个内置的 10 秒固件上传周期。如果 NG 通过 USB(串行)线获得任何数据，例如从 Raspberry Pi 音频分析应用程序向其发送位置数据，其固件将被破坏，您会坐在那里想知道为什么什么也没有发生。给电路板加电后，程序运行，并在 10 秒启动期结束时将夹爪移动到安全位置。我只是等待 jaw 初始化，然后知道我可以安全地开始发送 jaw 数据。没有下巴运动，我知道重新烧 NG 的固件。

接下来，我们打开串行端口并开始累积字符，直到收到“\n”为止。然后，该字符串被转换成一个整数，并输入到 map 函数中。映射功能将张开和闭合钳夹的位置缩放到输入的 0 到 9 的数字。

最后，缩放后的颌位置数字被馈送到颌伺服系统，并且程序循环通过来自音频分析程序的串行数据流，该音频分析程序当前在 Linux 笔记本上运行。我正致力于将分析转移到树莓派上，尽管我们还没到那一步。

## 下一步是什么

我对 jaw 与音频分析数据的同步非常满意。我在 Linux 笔记本上写了一个[处理](https://processing.org/)语言程序，播放音频，把声音的幅度转换成需要的串行 0 到 9 的值。全尺寸的业余爱好伺服系统似乎可以胜任在演讲时将赫德利的下巴摆动 30 度的工作。

很快，我会在赫德利的口腔顶部安装一个小扬声器，这样声音就会从正确的地方发出。当然，当我们在舞台上时，赫德利必须有他自己的麦克风。

当一切最终走到一起时，这应该是一个非常酷的效果。

请在下一篇文章中继续关注使用处理语言的音频分析程序。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>