# 现成的黑客:与机器人头骨赫德利的对话

> 原文：<https://thenewstack.io/off-the-shelf-hacker-conversations-with-hedley-the-robotic-skull/>

我的一个梦想一直是在表演和小规模演示期间与[赫德利](https://thenewstack.io/off-shelf-hacker-hedley-formerly-old-one-eye/)、[机器人头骨](https://thenewstack.io/off-the-shelf-hacker-hedley-the-robotic-skull-speaks/)、[进行对话。对着一个头骨说话并让它以任何有意义的实时方式回答是相当复杂的。Alexa 风格的响应是可能的，尽管它需要一个稳固的互联网连接。这并不总是可行的，在供应商赞助的当地酒吧演出中，坐在户外的露台桌旁。独立硬件人工智能(AI)机器视觉正变得相当成熟。赫德利的](https://thenewstack.io/traveling-with-hedley-the-robotic-skull/) [JeVois](http://jevois.org/) 机器视觉传感器就是一个很好的例子。人工智能演讲，不太多。

像其他会说话的机器人一样，我的解决方案是用赫德利的回答来“模拟”一场对话。我和他成了适时说台词的演员。

我们已经[介绍了赫德利的 Arduino 和颌伺服组合](https://thenewstack.io/off-the-shelf-hacker-hedley-the-robotic-skull-gets-a-partial-maxillectomy/)以及最近添加的安装在他口腔顶部的音频放大器和扬声器。

最后一个主要部分是用于控制赫德利在交流中的话语的软件。我在 9 月[日](https://thenewstack.io/off-the-shelf-hacker-creating-voice-jaw-data-with-a-processing-script/)报道了一个基线处理程序，但当时没有开发任何音频文件列表步进或按钮代码。

## 制作脚本

在这个最新版本中，这个程序打开了一个预先录制好的 WAV 声音文件列表，当我和赫德利相互交谈时，它会一步一步地浏览这些文件。此外，声音在飞行中被分析，产生一个数字流，输入 Arduino-jaw 伺服子系统。声音文件可以使用麦克风和 Audacity 录制，也可以通过保存文本到语音命令行工具的音频输出来录制，比如 T2 的 eSpeak T3。你可以在 Linux 笔记本上开发大部分代码，然后把所有代码都转移到 Raspberry Pi 上来完成按钮代码。或者，您可以使用处理版本 3.4 IDE 工具选项卡下的[“上传到 Pi”功能](https://github.com/gohai/processing-uploadtopi)。这让您可以在笔记本上开发，并通过网络在 Pi 上运行。确保将音频列表文本和 WAV 文件放在 Pi 上的适当目录中。

这是在赫德利的树莓派上运行的代码。

| )(这)(就)(是)(这)(些)(事)(,)(我)(们)(在)(这)(些)(事)(上)(没)(有)(什)(么)(可)(能)(看)(到)(这)(么)(的)(情)(况)(,)(只)(是)(这)(些)(事)(,)(只)(是)(在)(这)(些)(事)(上)(才)(有)(一)(个)(实)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)(验)( )(我)(们)(都)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(不)(知)(道)(,)(我)(们)(还)(有)(些)(什)(么)(好)(的)(情)(情)(。 )(我)(们)(都)(没)(想)(到)(这)(些)(事)(,)(我)(们)(还)(没)(想)(到)(这)(些)(事)(,)(就)(是)(这)(些)(事)(,)(我)(们)(还)(没)(想)(到)(这)(些)(事)(。 )(这)(就)(是)(这)(些)(事)(,)(我)(们)(还)(没)(想)(到)(这)(些)(事)(,)(就)(是)(这)(些)(事)(,)(我)(们)(还)(没)(想)(到)(这)(些)(事)(。 | 

import processing.sound.*;

import processing.serial.*;

import processing.io.*;

Serial myPort;

SoundFile sample;

Amplitude rms;

float scale=1;

float smooth_factor=.2;

float sum;

int valpos;

int sendpos;

int  i  =  0;

int playfile  =  0;

int sendout  =  0;

String[]  lines;

int noframes  =  0;

int playall  =  0;

int lineno  =  -1;

int  a  =  0;

float dur  =  0;

int incfile  =  0;

public void setup()  {

    size(100,100);

    GPIO.pinMode(16,  GPIO.INPUT_PULLUP);

    myPort  =  new Serial(this,  "/dev/ttyUSB0",  115200);

    // read control text file for audio files and servo positional data

    lines  =  loadStrings("/home/rob/hedleytheskull/roblist.txt");

    println("there are "  +  lines.length  +  " lines");

    for  (int  i  =  0  ;  i  &lt;  lines.length;  i++)  {

        println(lines[i]);

        }

    }

public void draw()  {

if  (GPIO.digitalRead(16)  ==  GPIO.LOW)  {

 fill(204);

 println("button pushed");

 delay(300);

 if  (lineno  &lt;  lines.length  -  1)  {

          ++lineno;

          println(lines[lineno]);

 }

 else  {

          exit();

 }  

    }

    else  {

 fill(155);

 playfile  =  -1;

 }

    stroke(255);

    ellipse(width/2,  height/2,  width*0.75,  height*0.75);

    if  (playfile  ==  0)  {

 sample  =  new SoundFile(this,  lines[lineno]);

 sample.rate(.45);

 sample.play();

 dur  =  sample.duration();

 rms  =  new Amplitude(this);

 rms.input(sample);

 playfile  =  1;

 sendout  =  1;

    }  

    if  (sendout  ==  1)  {

 sum  =  sum  +  (rms.analyze()  -  sum)  *  smooth_factor;

 myPort.write(str(int(map((sum *  700),  30,  85,  8,  3))));

 myPort.write('\n');

    }

    if  (a  &lt;  int((dur *  70)))  {

      a++;

      // print(", ");

      // println(int(dur * 70));    

    }

    else  {

      // println("done");

      playfile  =  0;

      a  =  0;

      dur  =  0;

      // ++lineno;

    }

}

 |

像往常一样，我们开始初始化变量、常量和库。接下来，我们计算音频文件列表中的行数，以便在遍历列表时用作每个短语的索引。

进入主程序(draw)，我们需要检查按钮状态。没有注意到任何，它将只是播放第一个音频文件使用 SoundFile 函数。按下按钮将增加到下一个音频文件。您可以改变回放速度和其他参数，以获得您想要的声音。振幅函数为我们提供了音频文件的数字记录，然后我们可以在下一个语句块中的 **rms.analyze** 函数中引用它。 **Rms.analyze** 返回一个数字数据流，然后我们通过 USB 线将它发送到赫德利的 Arduino Nano 微控制器。Nano 解释流并根据数据移动伺服系统，同时跟踪音频。

整个过程非常快。从赫德利嘴里发出的声音和他同步的下颌运动之间有一点小小的延迟。大多数观众可能看不到。

## 更进一步

虽然[处理](https://processing.org/)程序运行良好，但仍有很大的改进空间。例如，我考虑过取消 Arduino Nano 控制的下颚伺服系统，直接从树莓 Pi 启动下颚。我不认为它会比在开始时添加一个对伺服库的引用，并重写代码以通过 Pi 上的通用(GPIO)引脚向伺服发送伺服角度(从 0 到 30 度)要多得多。倪星纳米将简化整体电源管理，甚至可能消除音频和下巴运动之间的微小滞后。

我想探索的另一个领域是接近实时的文本到语音转换和语音识别。对赫德利说一句话或一个短语，然后让他用自己合适的短语来回应，这不是很酷吗？我们可以从简单开始，让他根据我说的一两个关键词说一些短语。

我不确定处理是否能胜任这种近乎实时的工作。我们可能需要研究其他编程语言，比如 c。我会随时通知你。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>