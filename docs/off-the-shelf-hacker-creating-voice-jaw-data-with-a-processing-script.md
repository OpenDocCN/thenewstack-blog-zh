# 现成的黑客:用处理脚本创建语音下巴数据

> 原文：<https://thenewstack.io/off-the-shelf-hacker-creating-voice-jaw-data-with-a-processing-script/>

上周我们看了赫德利的 Arduino-jaw 伺服端，我会说话的机器人头骨。最初，他的下巴与连接到 Arduino NG 微控制器的小型模拟[驻极体](https://www.britannica.com/science/electret)麦克风同步移动。在我说话的声音和赫德利拍打的下颌之间，它给出了平庸的结果。

当前现成的音频到颌伺服控制器的工作方式类似。他们获取原始音频，并将其转换为脉冲宽度调制信号，以移动颌伺服系统。音频通过有线连接到扬声器或 Raspberry Pi 耳机输出，输入到模拟输入。虽然这种方法对简单的道具很有效，但赫德利的下巴必须移动，以响应来自机载应用程序的数据。

赫德利不是一个远程呈现机器人。他是一个独立的智能机器人原型系统。在我的一次技术演讲中，不会有助手在幕后远程回答我的问题或发表评论。我最终希望赫德利能够使用类似 Alexa 的响应进行回复，不管有没有网络连接。

上次我们看了 Arduino-jaw 伺服子系统。今天，我们将研究等式的“脚本”或数据创建方面。

## 我们需要一些短语

目前，技术演讲的“表演”将由赫德利和我自己“编写”。它会给人一种交谈的错觉。当然，前提是我能记住我的台词。这应该是一个很好的效果，并为更复杂的人工智能(AI)对话过程的启动和运行奠定了基础。一切都将走向人工智能，你知道。

对于有剧本的表演，我们当然需要一些录音回应。自然，赫德利应该听起来像一个机器人。这项工作的合理选择是使用 [eSpeak](http://espeak.sourceforge.net/) ，它很容易集成到 Linux 脚本中。它甚至会通过使用“-w”选项将音频发送到一个. wav 文件中。几周前我们报道过这个文本到语音转换程序。

这里有一个例子。

```
robnotebook%  espeak  "My name is Hedley, please help me welcome Doctor Torq to the stage"  -v  en-us  -p  30  -s  200  -k  20  -w  intro-drtorq2.wav

```

“-v”选项将声音设置为美国英语，音高(“-p”选项)设置为 30，速度(“-s”选项)设置为 200，大写强调(“-k”)设置为 20。

你应该尝试声音和其他设置，找到一个组合，给你的机器人一个独特而有趣的声音。

接下来，我需要能够从应用程序中获取文本响应或某种数据，并将其转换为赫德利嘴里的扬声器发出的声音。与此同时，必须对音频进行分析，并将结果数据发送到赫德利的 Arduino-jaw 伺服子系统。

我生成了几个。wav 文件，带有用于测试目的的各种响应。与。wav 文件准备好了，现在让我们把注意力转向基于处理的音频分析程序。

## 将. wav 文件转换为数据

[处理](https://processing.org/)编程语言拥有丰富的函数库，使得几乎实时地播放. wav 音频文件和分析波形变得很容易。这一点很重要，因为声音和下颌运动之间的任何滞后都会破坏“会说话的头骨”效果。有一堆不同的功能在处理各种复杂的音频和视觉效果。

此外，处理过程与 Arduino 的代码布局非常相似。为什么不在 Linux 笔记本或 Raspberry Pi 上为 Arduino 和您的视听代码使用本质上相同的代码结构呢？

我选择了一个[“调幅”功能](https://processing.org/reference/libraries/sound/Amplitude.html)来捕捉音频波形的突出点。它给出了相当真实的下颌运动。对于您的项目，您肯定需要调整处理数据分析端和 Arduino-jaw 伺服程序的设置，以获得最佳效果。

如果你想变得更狡猾，你可以探索[快速傅立叶变换(FFT)函数](https://processing.org/reference/libraries/sound/FFT.html)，以捕捉音频波形的特定部分。如果你想试一试，它就在那里。FFT 根据频率分析音频，因此您可以针对特定声音精确定制输出数据。小小的聊天板做了类似的事情，尽管大部分工作是在硬件中完成的。赫德利说，他很高兴现在用振幅函数说话。

这是处理代码。

```
import processing.sound.*;
import processing.serial.*;

Serial myPort;

SoundFile sample1;
SoundFile sample2;
Amplitude rms;

float scale=8;

float smooth_factor=.2;

float sum;
int valpos;
int sendpos;
int  i  =  0;
int execloop  =  1;

public void setup()  {
    size(640,360);
    myPort  =  new Serial(this,  "/dev/ttyUSB0",  115200);
    }      

public void draw()  {
    background(125,255,125);
    noStroke();
    fill(255,0,150); 

    if  (execloop  ==  1)  {
 sample1  =  new SoundFile(this,  "/home/rob/hedleytheskull/intro-torq1.wav");
 sample1.rate(.45);
 sample1.play();
 rms  =  new Amplitude(this);
 rms.input(sample1);
 execloop  =  0;
    }
    else if  (execloop  ==  2)  {
 sample2  =  new SoundFile(this,  "/home/rob/hedleytheskull/intro-torq2.wav");
 sample2.rate(.45);
 sample2.play();
 rms  =  new Amplitude(this);
 rms.input(sample2);
 execloop  =  0;
    }    

    sum  +=  (rms.analyze()  -  sum)  *  smooth_factor;  
    myPort.write(str(int(map((sum *  700),  30,  85,  8,  3))));
    myPort.write('\n');
}

```

顶部是通常的库和变量初始化。然后启动串行线，这样我们就可以发送结果分析数据来移动夹爪。真正神奇的事情发生在绘图循环中，音频文件被播放，然后用振幅函数检查。输出数据稍加平滑，然后按比例映射到 Arduino-jaw 伺服子系统预期的 0 到 9 范围内。每个数据点都以换行符结束。

请注意，我使用了两个不同的。wav 文件。我只是在运行时使用“execloop”变量选择了其中的一个。我的计划是把音频响应文件名放在一个文本文件中，然后在我和赫德利谈话的时候浏览列表。我将在我的有线滑动点击器上添加一个新的按钮，当我想跳到下一个短语时，就用它作为触发器。一个假的古董麦克风会放在遥控器上面，但此时不会连接任何东西。稍加练习，我们应该看起来像是在互相交谈。

我在几个朋友和家人身上测试过赫德利，他们认为他的“会说话的头骨”效果看起来很酷，也很逼真。

## 更进一步

随着十月底[嵌入式系统大会(ESC)展会](https://minn18.mapyourshow.com/7_0/sessions/session-details.cfm?ScheduleID=31)的临近，我们还有很多事情要做。赫德利越来越渴望回到舞台上。

的。wav 文件列表功能是下一步，然后我将编程额外的按钮，通过短语前进。赫德利和我还必须把我们表演时要用到的一些对话组合起来。当然，会有很多排练…所以我记得我的台词。我们的特色需要和幻灯片结合在一起。

顺便说一下，我们将使用赫德利板载树莓 Pi 3 的 LibreOffice 运行幻灯片。也许我应该开始称他为我的“笔记本电脑”说说你的案例 mod！

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>