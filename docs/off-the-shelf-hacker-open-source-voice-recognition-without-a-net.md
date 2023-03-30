# 现成的黑客:无需网络的开源语音识别

> 原文：<https://thenewstack.io/off-the-shelf-hacker-open-source-voice-recognition-without-a-net/>

赫德利，[机器人头骨](https://thenewstack.io/off-the-shelf-hacker-hedley-the-robotic-skull-speaks/)需要对语音命令做出反应，这样他就可以做很酷的事情，并在我寻求统治世界的过程中帮助我。亚马逊基于云的 Alexa 语音服务可以很容易地在嵌入赫德利颅骨的 Raspberry Pi 3 上实现。去年早些时候，我写了关于把 [Alexa 放到 Pi](https://thenewstack.io/off-shelf-hacker-build-alexa-voice-assistant-raspberry-pi/) 上的文章。

这很好，如果你的机器人在无线热点附近。如果不是，它就是不听。

然而，有一个好消息，即 [PocketSphinx](https://github.com/cmusphinx/pocketsphinx) 是一个从卡耐基梅隆大学(CMU)分离出来的语音识别框架，它给出了非常好的结果，并在设备上发挥了它的所有魔力。不需要网络连接。

今天，我们将讨论如何让 PocketSphinx 在赫德利的 Raspberry Pi 3 板上运行。我们需要互联网连接来安装软件和建立语言模型。之后，PocketSphinx 可以在没有网络的情况下使用，并拥有自己的板载单词列表。

## 安装 Pocketsphinx

安装 PocketSphinx 最简单的方法是使用 [Synaptic 应用管理器](https://www.lifewire.com/guide-to-synaptic-package-manager-2205707)。

在 Raspberry Pi 上启动 synaptic，使用搜索功能获得与“PocketSphinx”相关的程序列表。选中要安装的列表项目。接下来，单击主 synaptic 工具栏中的“应用”按钮，然后单击摘要弹出窗口中的另一个“应用”按钮。synaptic 将通过它的步伐，在 Pi 上安装 PocketSphinx。

完成后，退出 synaptic，继续使用基于浏览器的“lmtool”程序构建语言模型。

当您运行 PocketSphinx 程序并对着麦克风说话时，lmtool 会将单词和短语的常规文本文件转换为相应的声音，这些声音是可以“识别”的。

我使用 [vim 编辑器](https://www.engadget.com/2012/07/10/vim-how-to/)构建了一个简单的语言模型文本文件。任何输出常规 ASCII 文本的编辑器都可以工作。我将下面几行放在一个名为 commands.txt 的文件中，并保存在我的/home/pi/hedleytheskull 目录中。

```
hello hedley
introducing doctor torq
turn light on
turn light off

```

你可能想用少于几十个短语来加快识别速度。模型中的单词越多，响应越慢。在没有特定的-dic 和-lm 文件选项的情况下运行 PocketSphinx 非常慢，因为它使用了一个很大的默认语言模型。该程序还将在您的语言模型中混合和匹配单词，因此它将识别单词的组合，而不是在文件中专门拼成一行。例如，“你好，torq 医生”会被识别。

我打开火狐浏览器，进入 CMU 的斯芬克斯知识库工具页面。接下来，我单击“浏览”按钮，显示“上传句子语料库文件”,并从/home/pi/hedleytheskull 目录中选择 commands.txt。

然后，您可以保存。dic 和。lm 文件放到您的工作目录中。或者，下载并解压缩 tar 文件。tgz)文件将这两个文件放到您的工作目录中。我用 lmtool 程序运行时生成了一个名为 TAR9363.tgz 的文件。

```
pi@hedley:~  tar  -xvzf TAR9363.tgz

```

tar 将文件解压成以下集合。

```
9363.dic
9363.lm
9363.log_pronounce
9363.sent
9363.vocab

```

安装 PocketSphinx 和构建语言模型到此为止。现在让我们看看如何从命令行识别语音。

## 跟我说话

我使用标准的[罗技 C270 USB 网络摄像头](https://www.logitech.com/en-us/product/hd-webcam-c270)，内置麦克风作为语音输入设备。

PocketSphinx 有超过 120 个命令行选项。在命令行输入 pocketphinx_continuous 可以看到一个列表。你只需要几个就能让它识别你的话。

这是我使用的一个示例命令行。

```
pi@hedley:~  pocketsphinx_continuous  -dict  /home/pi/hedleytheskull/speech/9363.dic  -lm  /home/pi/hedleytheskull/speech/9363.lm  -inmic yes  -adcdev plughw:2,0  -logfn  /dev/null

```

注意，我使用了完整的路径名。dic 和。lm 文件。-inmic yes 选项基本上是打开麦克风进行输入。使用-logfn /dev/null 来暂停堆积如山的日志数据，如果不使用该选项，您通常会在屏幕上看到这些数据。日志数据对于诊断非常有用，但是如果您需要的话。

-adcdev 选项花了一些时间才弄清楚。该选项与 Linux 音频子系统一起工作，并定义您的捕获设备。运行以下命令来查找合适的设备。

```
pi@hedley:~  cat  /proc/asound/pcm

```

这是赫德利的调查结果。

```
00-00:  bcm2835 ALSA  :  bcm2835 ALSA  :  playback  7
00-01:  bcm2835 ALSA  :  bcm2835 IEC958/HDMI  :  playback  1
01-00:  MAI PCM vc4-hdmi-hifi-0  :  :  playback  1
02-00:  USB Audio  :  USB Audio  :  capture  1

```

注意底部的捕捉设备。将行首的数字插入到 plughw 参数中，就可以开始了。

输入命令，等待几秒钟，然后说出一个语言模型行来使用程序。您应该会看到一个“ready”提示，然后很快就会看到屏幕上出现所说的台词。

## 继续说

我推荐在最新版本的 [Raspbian](https://www.raspberrypi.org/downloads/raspbian/) 的干净版本上安装 PocketSphinx。几周前，当我第一次设置这个程序时，识别的速度几乎是实时的。从那以后，我在赫德利的 8GB 低端微型 SD 卡上添加了很多软件。它大约有 95%的容量，可能会减慢速度。

最近的测试需要 10 到 15 秒来识别一个短语。我将很快在一张新的 32GB 三星 EVO+卡上安装 Raspbian，并期待响应恢复正常。我强烈推荐这些卡片。

您还可以尝试其他命令行选项，根据您的需要定制程序行为。

下一步是使用 PocketSphinx-to-Python API 将语音集成到我的一些 Python 程序中。我们将在以后的专栏中探讨这个主题。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>