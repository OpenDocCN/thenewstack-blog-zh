# Ruby Devs:在升级到 Ruby on Rails 之前先试试 Sinatra

> 原文：<https://thenewstack.io/ruby-devs-try-sinatra-before-moving-up-to-ruby-on-rails/>

你有没有想过是否有可能从零开始制作一个功能性的网站，而不需要花费大量的时间学习如何编程？不要害怕！辛纳特拉支持你。Sinatra 被描述为一种领域特定语言(DSL)，“用 Ruby 快速创建 web 应用程序，只需最少的努力。”

那么你为什么要尝试辛纳屈，它到底是什么？Sinatra 是一个简单的 web 框架，它为开发者提供了构建动态网站的“砖块”。它是由 Ruby 语言驱动的，代表着在升级到它更著名的老大哥 Ruby on Rails 之前迈出了坚实的一步。

Sinatra 令人兴奋的是，你可以多快地编写网站，通过输出有用的信息(浏览器上的 HTML 页面)来响应用户(即 HTTP 请求)——所有这些都不需要几十年的编程经验。还有其他技术可以帮助你快速将这些网站放到网上，比如 [Heroku](https://www.heroku.com/) 或 [Engine Yard](http://engineyard.com) 。

Ruby 因其易用性而受到开发人员的喜爱。它由一个充满活力的社区监管，从它衍生出来的项目也是如此。有时读到一些奇怪的名字会让你怀疑自己是否走错了夜总会，但不要过度担心。把这篇文章当成一次游览所有景点的敞篷巴士之旅。所以如果你对这些都不熟悉，慢慢来。我只是假设你有基本的计算机知识，并且喜欢坐公交。

您需要的唯一工具是您拥有管理员权限的笔记本电脑或虚拟机，以及终端或命令提示符。出于本文的目的，我假设您面前有一台 Mac，安装了 Homebrew。但是一旦你下载了一个 Ruby 安装，大多数步骤在 Windows 上的工作方式是完全一样的。确保你有一个可用的文本编辑器。

所以让我们从安装 Ruby 开始。之后，我们可以安装 Ruby 构建 Sinatra 所需的模块(名为“ **gems** ”)。(是的，有一种“依赖漩涡”或引导已经在进行了——“在运行 Y 之前，你首先需要有 X”。这种情况经常发生。)

在提示符下键入以下内容:

有没有看到一些版本信息？好的。但是如果你没有把它放在那里，你可能应该不去管这个 Ruby 的安装，因为你的系统可能正在使用它，并且希望它不要改变。所以检查:

```
>  ~  which ruby
/usr/bin/ruby

```

如果你确实看到了`/usr/bin/ruby`，那就是预装的 macOS 系统 Ruby。

所以不管怎样，用自制软件安装一个漂亮的新 Ruby:

Homebrew 将开始安装(或更新) *Ruby* 的漫长过程。它应该告诉你运行一个命令，以确保你的 Mac 将找到路径上的新鲜红宝石。最后几位可能不同，但是运行这个和下面的“source”命令来更新路径和您正在使用的 shell。在我的案例中我看到:

```
>  ~  echo  'export PATH="/usr/local/opt/ruby/bin:$PATH"'  >>  ~/.zshrc
>  ~  source  ~/.zshrc

```

现在，如果你再次运行上面的版本命令，它应该会反映出你更新的 Ruby。再次运行“which”命令也将确认您正在从其他地方运行它。如果你还没有做的话，你可能还想给自己做一个工作目录:

```
>  ~  mkdir singing-with-sinatra
>  ~  cd singing-with-sinatra
>  singing-with-sinatra

```

现在我们已经安装了 ruby，尝试下面的方法:

```
>  singing-with-sinatra ruby  -e  'puts "hello world"'  
hello world

```

正如你所猜测的，我们要求 Ruby 立即运行或“执行”一个简单的程序，它做到了。它使用“puts”命令显示了我们的欢迎声明。当然，通常我们会在一个整洁的文件中编写程序。

接下来，让我们将 Sinatra 安装为红宝石。所以我们将要求安装的 gem 管理器程序来做这件事:

如果一切正常，您应该会得到一个已安装 gems 的列表，包括一个 Sinatra 版本和各种依赖项。一个名字，你也将看到在异国情调的宝石名单是机架。这是 Sinatra 用来解释 HTTP 命令的 gem，并使它们易于开发人员使用。(如果 Ruby 在构建原生库时遇到问题，Mac 用户可能需要安装一些 Xcode，这是苹果的开发者工具套件。尝试“xcode-select —install”)

现在让我们为一个名为 Puma 的 web 服务器添加 gem:

Sinatra 的工作是与 web 服务器通信，而 Puma 恰好是它已经熟悉的一个服务器。

所以现在我们肯定可以做一些网络的东西了吧？哦，是的，我们可以。打开一个编辑器，写下以下内容，然后保存为“singing-with-sinatra.rb”。当然，任何名字都可以，但是使用后缀“rb”来表示一个 Ruby 程序:

现在我们将运行我们自己的本地 web 服务器，运行我们相当简单的站点代码，看看我们得到了什么:

```
>  ruby singing-with-sinatra.rb

```

现在，您应该会得到如下所示的输出。接下来，我们需要快速分析这一切意味着什么:

```
==  Sinatra  (v2.2.0)  has taken the stage on  4567  for development with backup from Puma
Puma starting in single mode...
*  Puma version:  5.6.2  (ruby  3.0.1-p64)  ("Birdie's Version")
*  Min threads:  0
*  Max threads:  5
*  Environment:  development
*          PID:  8413
*  Listening on http://127.0.0.1:4567
*  Listening on http://[::1]:4567
Use Ctrl-C  to stop

```

依赖漩涡正在全面展开，所以这里有相当多的信息:

*   Sinatra 刚刚建立的网站只存在于我们的本地机器上，可以通过 URL[http://127 . 0 . 0 . 1:4567](http://127.0.0.1:4567/hi)访问(要查看我们的欢迎页面，请添加“/hi”)。“127.0.0.1”或“localhost”只是引用本地机器的网络方式。
*   “4567”是 Sinatra 在开发过程中通常非正式使用的端口。
*   web 服务器 Puma 的版本不同于最新的 Ruby 版本。
*   操作系统识别特定的进程标识符(PID)。请记住，您的操作系统是一切的幕后推手，让演出继续进行。
*   另外，我们的壳不再是我们的了。直到我们按下 Ctrl-C，我们才拿回来！

当 Sinatra 在舞台上时，如果您浏览到 [http://localhost:4567/hi](http://localhost:4567/hi) ，您应该会看到欢迎响应，并且您还会看到服务器在 shell 中记录了什么:

```
::1  -  -  [14/Mar/2022:15:01:23  +0000]  "GET /hi HTTP/1.1"  200  12  0.0122
::1  -  -  [14/Mar/2022:15:01:23  +0000]  "GET /favicon.ico HTTP/1.1"  404  469  0.002

```

在我要求你离开旅游巴士去探索之前，让我们先证明我们确实在创建一个真实的网页。在下面的例子中，我添加了一些额外的位:

*   我们现在有一些非常简单的 HTML 标签和文本。
*   我多加了一条**路线**。在 Sinatra 中，路由是与 URL 匹配模式(例如“/hi”)配对的 HTTP 方法。并且每个路由与一个代码块相关联。
*   我让 Ruby 在输出中插入一些代码。你可以看到代码包含了时间。

所以如果你运行新程序:

```
>  ruby encore-with-sinatra.rb

```

…然后你浏览到 [http://localhost:4567/hi](http://localhost:4567/hi) 你会看到:

[![Sinatra](img/940a83a0c6590728db2356f83d691b66.png)](https://cdn.thenewstack.io/media/2022/03/3d1fa8d9-image1.png)

如果你浏览到[http://localhost:4567/bye](http://localhost:4567/bye)你会看到这样的内容:

[![Sinatra](img/70f013422f700ef685bf56d8eff5844e.png)](https://cdn.thenewstack.io/media/2022/03/386a759f-image2.png)

好了，现在是时候离开大巴，徒步探索了。一些建议:

*   用[捆绑器](https://bundler.io/)控制你的宝石。这是优秀的开发人员所做的。
*   用 rvm 对你的 Ruby 安装进行更多的控制。
*   用你的新知识，看看你如何部署你的 *Sinatra* 站点与 [Heroku](https://devcenter.heroku.com/articles/rack) 一起直播。
*   或者在我的例子里看到更多可爱的辛纳特拉[这里](https://github.com/eastmad/Swiss-Army-Knife)。

我希望你喜欢这次旅行！

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>