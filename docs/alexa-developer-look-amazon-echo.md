# 关于 Alexa 的一切:一个开发者研究亚马逊 Echo

> 原文：<https://thenewstack.io/alexa-developer-look-amazon-echo/>

根据最近的头条新闻，亚马逊 Echo 既[充满承诺](http://www.nytimes.com/2016/03/10/technology/the-echo-from-amazon-brims-with-groundbreaking-promise.html)又[变得困惑并劫持了你的恒温器](http://qz.com/637326/amazon-echo-home-alone-with-npr-on-got-confused-and-hijacked-a-thermostat/)。

但声控智能扬声器现在越来越受到关注，并得到了最终用户和开发者的一些积极评价。有新的传言称谷歌[正在打造他们自己的版本](http://arstechnica.com/gadgets/2016/03/report-google-is-building-an-amazon-echo-clone-nest-has-a-security-system/)。这一切都证明，亚马逊已经找到了进入一个有吸引力的重要利基市场的方法，他们正在积极鼓励开发者帮助他们改善他们的人工智能助手。

9 个月前刚刚发布的亚马逊 Echo 是一种支持语音的桌面个人助理(具有远场语音识别功能，所以你可以在房间的另一端激活它)。本月，亚马逊还发布了新的 Echo Dot，让用户可以将语音助手扩展到任何房间(具有相同的“远场”范围)。新的亚马逊 Tap(也在本月宣布)将通过杜比立体声扬声器提供音频输出。但在不到一年的时间里，亚马逊 Echo 已经吸引了一些积极的评论。

TechCrunch 最近称 Echo 是“一个令人惊讶的好产品”，指出它现在还可以[支付你的信用卡账单](http://techcrunch.com/2016/03/11/amazon-alexa-can-now-pay-your-capital-one-bill/)，[打电话给优步](http://techcrunch.com/2016/02/05/amazon-alexa-can-now-order-an-uber-from-your-echo-speaker-or-fire-tv/)，以及[订购披萨](http://techcrunch.com/2016/02/03/amazon-echo-can-now-order-your-pizza/)。“第三方技能增加了更多的功能，”亚马逊在 SDK 的网页上解释道，“比如从达美乐订购披萨，从优步请求搭车，用 Garageio 打开车库。”你可以播放来自 Pandora、Spotify、Amazon Music、TuneIn 和 iHeartRadio 的音乐，或者听有声读物(来自亚马逊的 Audible 服务)。Echo 可以宣布体育比分和赛程，设置闹钟，计算最快的上班路线，甚至可以搜索 Yelp。

![Using Echo (from Amazon page)](img/ce7d0c4228e18dcf40c6bfb235eedca0.png)

《纽约时报》最近的一篇文章补充道，亚马逊 Echo 还可以提供天气预报和购物清单，以及开发人员正在开发的新技能——但更重要的是，这项服务正在逐步发展。一位科技专栏作家写道:“起初，这些技术有点傻，就像一个神奇的 8 球模拟器或一个提供搭讪线的模拟器。”。但亚马逊鼓励开发者为 Echo 的个人助理想出自己的新鲜新花样。她的名字叫 Alexa，你可以教她新的“技能”——当然——[Alexa 技能包](https://developer.amazon.com/appsandservices/solutions/alexa/alexa-skills-kit),这是一个自助式 API 的集合。

在 [IFTTT](https://ifttt.com/) 已经有了一系列令人印象深刻的与其他云服务的连接，其中许多是亚马逊自己贡献的。除了该网站寻找丢失手机的“秘方”,你还可以创建一个你听过的歌曲列表，然后将其作为状态更新发送到脸书或推特，或者导出到谷歌文档的电子表格中。

在《纽约时报》的一篇热情洋溢的评论之后，波士顿开发者 Jean-Charles Sisk 在 Hacker News 的评论中分享了他自己为 Echo [开发的经历。除了鼠标或键盘之外，接受输入似乎也很优雅。“这是一个自然的界面，有一个体面的交互模型，”Sisk 写道。“Echo 感觉像是第一个不完全是噱头的基于语音的界面。”](https://news.ycombinator.com/item?id=11253130)

但更重要的是，它使提供真正有用的服务成为可能。“我的祖父最近去世了，我的祖母有可怕的视力，”西斯克在黑客新闻上分享道。"我写了一个技能，使我的祖母能够请求开始打电话. "然后询问她想给谁打电话。一旦她说出一个名字，她就会在她的座机上收到一个电话，被问候，然后电话被转接到预定的接收者。

“有一个小的学习曲线(你不能只说，‘打电话给约翰’，你必须让她‘开始打电话’)，但这很有效，为一位视力不好、经常感到困惑的老年妇女提供了一种与亲人联系的直接方式，”Sisk 写道。

他的祖母仍然不得不单独拿起她的电话，这是一个小成本，因为电话最终是使用 Twilio 打的。但他称赞当今世界上可用的高质量语音到文本的功能，并特别称赞了远场语音识别，这是 Echo 的一大部分。“在这种情况下，硬件和平台一样重要。”

“不需要语音识别或自然语言理解方面的经验，”亚马逊的 David Isbitski 解释道，他是亚马逊 Alexa 和 Echo 的首席传播者，在去年 6 月该设备首次发布时，他在博客文章中写道。“亚马逊做了所有的工作来倾听、理解和处理客户的口头请求，所以你不必这么做。

“早点进入，”他补充道，“自然用户界面，比如那些基于语音的界面，代表着计算领域的下一个重大突破……”

当然，也提到了云服务和亚马逊自己的云产品套件。“如果你有一个现有的基于云的服务，你可以很容易地使用它来启动。如果没有，AWS Lambda 是一种计算服务，它使构建基于云的服务变得非常容易，可以快速响应语音请求，”Isbitski 写道。

## 一个新兴的开发者社区

Hackster.io 上已经有了一个官方的开发者社区[，亚马逊甚至为早期预营收公司创建了](https://www.hackster.io/amazon-alexa)[Alexa 基金](https://developer.amazon.com/public/solutions/alexa/alexa-fund)，一直到知名品牌。他们计划花费高达 1 亿美元投资于语音技术的创新应用。

除了提供资金，他们还为开发者提供支持(最终是营销)，加上 AWS Activate 会员资格(为选定的初创公司提供低成本的云资源)。

对于其他人来说，亚马逊每周二都提供网络研讨会，并且还与 Alexa 技术布道者举行每周一次的“办公时间”。

从它的网页来看，为 Amazon Echo 开发很像构建一个 Android 应用程序。开发者仍然定义意图来处理用户请求，这些请求现在将被传递给他们自己的基于云的服务。但是在 Amazon Echo 中，这一切都是由一个 *voice* 命令启动的，然后这个命令会通过一些简单的 JSON 映射到一个 intent 上。

Alexa 技能套件甚至带有一系列内置意图，周二亚马逊宣布了一些新的意图。现在可以在你的应用程序中添加声控定时器和闹钟，以及任何正在播放的媒体的声控暂停，静音/取消静音功能，以及调节音量的声控方式。

但是开发者也可以创建他们自己的意图。请记住，如果您正在构建自己的语言，您还需要提供一个“示例话语”文件，该文件列出了实际用户可能说出的命令的每种排列。

当然，开发人员也可以为 intents(在 Alexa universe 中称为“slots ”)指定参数，用于他们的服务需要接收的任何类型的附加数据。每当用户说话时，他们所说的任何参数都将被翻译成文本。同样，还有一些已经内置的参数。例如，表示日期的口语单词可以转换为服务的实际日期格式，甚至是更抽象的单词，如“今天”、“明天”和“七月”还可以从口语中提取数字，Alexa 还可以识别每个人口超过 10 万的城市的名称，以及数千个流行的名字。

每个人的命令最终都由一个在线服务处理，这个服务可以由 AWS Lambda 中的 Amazon Lambda 函数托管，也可以在你自己的服务器上托管。只需确保您使用的是 SSL，并且您的服务通过 HTTPS 返回响应，并在端口 443 上接受 HTTPS 请求。第一步是验证每个请求的签名(并检查其时间戳)。但是一般来说，您的服务将启动或结束会话，或者处理特定的请求——代码可以用多种语言编写，包括但不限于 Java。

Alexa 将它从你的服务中收到的任何文本转换回语音给幸运的最终用户。

“回声有办法潜入你的日常生活，”法尔哈德·曼朱在《纽约时报》 的 *[中写道。“当 Alexa 为你重新订购爆米花或为你叫一辆优步汽车时，当你的孩子开始要求 Alexa 在购物清单上添加冰棒时，你开始希望生活中的几乎所有其他事情也能支持 Alexa。”](http://www.nytimes.com/2016/03/10/technology/the-echo-from-amazon-brims-with-groundbreaking-promise.html)*

如果这是下一个重大的颠覆性技术，亚马逊已经在划定自己的地盘了。这可能会给他们一个强大的新工具，从亚马逊吸引新的购买。

图片来自亚马逊。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>