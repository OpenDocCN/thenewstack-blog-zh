# 现成的黑客:让你的树莓皮说话

> 原文：<https://thenewstack.io/off-the-shelf-hacker-get-your-raspberry-pi-talking/>

人机界面现在非常流行。

存在大量联网的 Alexa 风格的语音识别和机器语音解决方案。它们栩栩如生，使用人工智能的力量，在某个地方使用互联网连接的云服务器来施展它们的魔法。去年早些时候，我报道过在树莓派上设置 Alexa。

虽然所有这些都很有趣和有用，但互联网连接的任何中断都会使其无法运行。幸运的是，随着今天的纳米 Linux 系统(如 Raspberry Pi)内置了巨大的马力，我们不需要互联网连接。我们可以在本地进行文本到语音的转换，就在黑板上，使用 eSpeak。

[赫德利，机器人头骨](https://thenewstack.io/off-shelf-hacker-hedley-formerly-old-one-eye/)肯定需要与人类对话的能力，特别是当他没有连接到互联网的时候。

今天，我将讲述如何在树莓 Pi 3 上开始使用 [eSpeak](http://espeak.sourceforge.net/) 。注意，在这篇文章中，我使用了一个 HDMI 显示器和一个 Logitech 无线键盘/鼠标垫连接到常规桌面配置中的 Pi。Raspbian Linux 还有另一个现成的文本到语音转换程序叫做 [Festival](https://en.wikipedia.org/wiki/Festival_Speech_Synthesis_System) 。我用过几次，听起来也很不错。也许我们会在以后的文章中讨论节日。

## 安装 eSpeak

eSpeak 软件是一个标准软件包，可以在 Raspbian Linux 的“扩展”版本中获得。我使用 Synaptic 包管理器进行安装，尽管您也可以轻松地使用 apt-get。以下命令行在您的计算机上安装 eSpeak。

```
pi@hedley:~$ sudo apt-get install espeak

```

安装程序后，确保你的音量开到一半。我使用主任务栏上的小扬声器图标来调节音量。

接下来，用双引号括起来的短语运行 eSpeak。这里有一个例子。

```
pi@hedley:~$  espeak  "My name is Hedley and I'd like to introduce Doctor Torq...hello Doctor Torq"

```

您应该会听到这句话从 HDMI 显示器的扬声器中传出。默认情况下，eSpeak 似乎有点男性英语口音。如果您听不到任何声音，则声音可能被传送到模拟音频端口。请插入耳塞，然后再次尝试该命令。你可能会听到耳机里的声音。右键单击扬声器图标，选择 HDMI 将声音传送到显示器的扬声器。再次运行该命令，单词应该从显示器扬声器中出来。

我想用美国人的声音，所以我把它改成了"-v en-us "选项。键入“e speak–voices”以查看所有可用的声音。

假设你想要一个美国女性的声音？在声音名称后使用“+f”:

```
pi@hedley:~$  espeak  "My name is Hedley and I'd like to introduce Doctor Torq...hello Doctor Torq"  -v  en-us+f1

```

“+f”后面可选地跟一个数字。不同的数字调整音高和重音。用“1，2，3”等等来做实验，看看什么声音最好听。正如您所料，附加在“-v”选项上的“+m”表示男性的声音。

您也可以用其他参数来调整讲话的声音:

```
pi@hedley:~$  espeak  "My name is Hedley, please help me welcome Doctor Torq to the stage"  -v  en-us  -p  30  -s  150

```

这个例子使用“-p”选项表示音高，使用“-s”选项表示速度。使用“espeak–help”获取完整的选项列表。

我在 Xubuntu Linux 笔记本和 Raspbian Linux Raspberry Pi 上都用过 eSpeak。它在任何一台上都可以可靠地工作。有趣的是，当在不同的机器上使用完全相同的短语和选项时，音调和音调会有所不同。我将让读者去思考这些对我们机器对人类的未来的影响。

## 将演讲融入你的项目

以上总结了使用命令行 eSpeak 程序的基本知识。给它一个短语，它就会说出单词。

我的计划是，当我按下连接到通用输入/输出(GPIO)引脚的按钮时，使用 Python 程序说出一个短语。我正在研究从 Python 内部调用 eSpeak 的最佳方法，尽管我在其他 Python 项目中进行过系统调用，没有出现问题。

我想让骷髅头赫德利在一次会议技术演讲的开始向我的听众介绍我。当开始的时候，我会按下一个按钮，赫德利可能会说出前面例子中的一个短语。然后我可以回答“谢谢你，赫德利”然后他可以说一些关于我再按一次按钮会覆盖的内容。使用这种方法，我们可以在开始我的演讲之前进行一个简短的对话。通过实践，脚本对话应该给人一种真实的人机交互的错觉。

我还在努力使赫德利的下巴运动和他说的话同步。当它们一起工作的时候应该会很酷。

现在，我们还需要多久才能分辨出这是一次真正的对话还是仅仅是一场“表演”？只有[现成的黑客](/tag/off-the-shelf-hacker/)能回答这个问题。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>