# 容器中的 Ruby

> 原文：<https://thenewstack.io/ruby-in-containers/>

乔安娜·南杰凯

乔安娜·南杰凯是一名来自乌干达坎帕拉的软件工程师。她是一个值得骄傲的开源贡献者，接受过 Rails Girls Summer of Code 和 Outreachy 等项目的指导，主要编写 Python、Ruby 和 Golang。她是 Apress 出版的《Python 2 和 3 的兼容性》一书的作者。她还组织了铁路女孩坎帕拉。最近读了很多关于最新的开发工具和空间。

软件改变环境，从开发机器到 UAT(用户验收测试)服务器环境，甚至从测试环境到生产环境。要求软件在流程中的这些环境下一致可靠地运行。

曾经有一段时间，部署软件是一个事件，一个仪式，因为保持这种一致性是很困难的。团队花了很多时间让目标环境像源环境一样运行软件。此后，他们祈祷上帝让软件在生产中像在开发中一样完美运行。

有了容器，部署变得更加频繁，因为我们将我们的应用程序和它们的库打包成一个单元，使它们可移植，从而帮助我们在不同环境之间移动软件时保持一致性和可靠性。对于开发人员来说，这是提高生产力、可移植性和易于扩展。

由于这种可移植性，容器已经成为云的通用语言，允许我们将软件从一个云转移到另一个云，而没有太多麻烦。

在本文中，我将讨论在 Ruby 中使用容器时需要注意的两个主要概念。我将讨论如何创建小容器图像以及如何测试它们。

## 要求

要按照教程运行源代码，您可能需要在系统上安装以下工具。

*   红宝石
*   码头工人
*   Linux 操作系统使用容器测试框架实现的映像测试目前可能无法在 windows 上运行。
*   获取完整的[源代码](https://github.com/nanjekyejoannah/Ruby-in-Containers)。

当我们开始时，给定一个 hello world sinatra 应用程序，比如这个:

```
#app.rb
require  '
sinatra
'
require  '
sinatra
/base'class MyApp  &lt;  Sinatra::Base
get  '/'  do
"Welcome to sinatra in Containers"
end
end

```

```
# Gemfile
source  'https://rubygems.org'
gem  'sinatra'
gem  'thin'

#config.ru
$:.unshift(File.dirname(__FILE__))
require  'app'
run MyApp

```

用 Docker 封装这个应用程序需要我们编写一个 Docker 文件，如下所示。在 Docker 网站上阅读更多关于如何创建 Docker 文件的信息。

```
FROM ubuntu:  latest
RUN apt-get updateRUN apt-get  -y  update
RUN apt-get  -y  install git git-core curl gawk  g++  gcc make libc6-dev libreadline6-dev  \
zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 autoconf  \
libgdbm-dev libncurses5-dev automake libtool bison pkg-config libffi-dev
RUN apt-get install  -y  postgresql postgresql-contrib postgresql-client libpq5 libpq-dev
RUN curl  -sSL https://rvm.io/mpapis.asc | gpg --import -
RUN curl  -L  https://get.rvm.io | bash -s stable
ENV PATH  /usr/local/rvm/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
RUN rvm install ruby-2.1.5
RUN rvm reload
CMD source  /etc/profile
CMD source  /usr/local/rvm/scripts/rvm
RUN apt-get install  -y  nodejs npm
RUN ln  -s  /usr/bin/nodejs  /usr/bin/node
RUN  ["/bin/bash",  "-l",  "-c",  "rvm use 2.1.5 --default"  ]
RUN  ["/bin/bash",  "-l",  "-c",  "rvm requirements; gem install bundler --no-ri --no-rdoc"]
RUN  ["/bin/bash",  "-l",  "-c",  "gem list"]
RUN apt-get update  -qq  &amp;amp;&amp;amp;  apt-get install  -y  build-essential libpq-dev
RUN mkdir  /myapp
WORKDIR  /myapp
ADD Gemfile  /myapp/Gemfile
RUN  ["/bin/bash",  "-l",  "-c",  "bundle install "]

```

我们需要关心图像的性能和安全性。确保良好性能和安全图像的方法是减小其尺寸。这还不够，我们还需要考虑其他方面来创造有效的图像。

一个小的映像需要更短的时间来构建，推入和拉出映像注册表。

小图像也具有小的攻击表面积，因此减少了安全漏洞。让我们讨论一些创建小 Docker 图像的技巧。

## 缩小图像的尺寸

我们用来创建容器图像的指令会影响最终图像的大小。要减小图像大小，请使用以下最佳实践:

*   使用小的基本图像。
*   命令链。
*   清理你的容器。
*   安装您需要的东西。

让我们深入讨论每一个问题。

## 小型基础图像

在为 Ruby 应用程序创建 docker 文件时，有三个选项可用于基本映像。像 Ubuntu、轻量级 Linux Alpine、Ruby 基础映像和 Ruby alpine 基础映像这样的标准操作系统映像。我们以不同的方式使用这些基本图像，它们有不同的尺寸。

对可用基本映像大小的仔细分析使我们得出结论，Linux Alpine 映像是最小的。

使用小的基本图像会显著减小容器图像。我们现在可以更改 Dockerfile 文件，使用 Linux alpine 作为基本映像。

Linux alpine 是轻量级的，可能会导致额外的开发工作，因为与完整的操作系统相比，它没有附带一些库。有些情况下，使用完整的操作系统可以减少开发工作，但同时也符合完整操作系统的标准和安全性。

## 链接命令

诸如 RUN 之类的命令可以放在单独的行上，但是这增加了图像的容器层。我们的层数越多，图像就越大。为了减少层次，我们应该链接这些命令。

```
FROM alpine:latest
MAINTAINER nanjekyejoannah  "https://github.com/nanjekyejoannah"
RUN apk  --update add  --virtual build-dependencies ruby-dev build-base
ENV APP_ROOT  /var/www/docker-sinatra
RUN mkdir  -p  $APP_ROOT
WORKDIR  $APP_ROOT
ADD Gemfile*  $APP_ROOT/
ADD  .  $APP_ROOT
RUN gem install bundler  --no-ri  --no-rdoc  &amp;&amp;  cd  /$APP_ROOT
RUN bundle install  --without development test  &amp;&amp;  apk del build-dependencies
RUN chown  -R  nobody:nogroup  /app
USER nobody
ENV RACK_ENV production
EXPOSE  80
CMD  ["bundle",  "exec",  "rackup",  "config.ru",  "-p",  "80",  "-s",  "thin",  "-o",  "0.0.0.0"]
RUN gem install bundler  --no-ri  --no-rdoc  &amp;&amp;  cd  /app  ;  bundle install  --without development test  &amp;&amp;  apk del build-dependencies
RUN chown  -R  nobody:nogroup  /app
USER nobody
ENV RACK_ENV production
EXPOSE  80
CMD  ["bundle",  "exec",  "rackup",  "config.ru",  "-p",  "80",  "-s",  "thin",  "-o",  "0.0.0.0"]

```

安装你需要的东西 RUN 命令被链接成一个。

在 Linux 中安装软件包时，使用-no-install-recommendes 标志来只安装软件包中您需要的部分。

```
FROM alpine:latest
MAINTAINER nanjekyejoannah  "<a class="ext-link" href="https://github.com/nanjekyejoannah" rel="external ">https://github.com/nanjekyejoannah</a>"

ENV APP_ROOT  /var/www/docker-sinatra
RUN mkdir  -p  $APP_ROOT
WORKDIR  $APP_ROOT
ADD Gemfile*  $APP_ROOT/
RUN bundle install
ADD  .  $APP_ROOT
RUN apk  --update add  --virtual build-dependencies ruby-dev build-base  &amp;&amp;  \     gem install bundler  --no-ri  --no-rdoc  &amp;&amp;  \      cd  /app  ;  bundle install  --without development test  &amp;&amp;  \   apk del build-dependencies  -no-install-recommends
RUN chown  -R  nobody:nogroup  /app
USER nobody
ENV RACK_ENV production
EXPOSE  80
CMD  ["bundle",  "exec",  "rackup",  "config.ru",  "-p",  "80",  "-s",  "thin",  "-o",  "0.0.0.0"]

```

清理您的容器通过省去推荐的软件包，我们能够处理我们需要的东西，同时受益于较小的图像。

在容器中安装软件包后，清理所有缓存文件以缩小映像。

```
FROM alpine:latest
MAINTAINER nanjekyejoannah  "<a class="ext-link" href="https://github.com/nanjekyejoannah" rel="external ">https://github.com/nanjekyejoannah</a>"
ENV APP_ROOT  /var/www/docker-sinatra
RUN mkdir  -p  $APP_ROOT
WORKDIR  $APP_ROOT
ADD Gemfile*  $APP_ROOT/
RUN bundle install
ADD  .  $APP_ROOT
RUN apk  --update add  --virtual build-dependencies ruby-dev build-base  &amp;&amp;  \  gem install bundler  --no-ri  --no-rdoc  &amp;&amp;  \     cd  /app  ;  bundle install  --without development test  &amp;&amp;  \    apk del build-dependencies  -no-install-recommends  &amp;&amp;  \   rm  -rf  /var/lib/apt/lists/*
RUN chown  -R  nobody:nogroup  /app

USER nobody

ENV RACK_ENV production

EXPOSE  80
CMD  ["bundle",  "exec",  "rackup",  "config.ru",  "-p",  "80",  "-s",  "thin",  "-o",  "0.0.0.0"]

```

我们从 Docker 文件构建一个映像并启动容器，同时将容器端口 80 映射到 localhost:4000。这都是为了创造更小的图像。经过这些更改后，我们现在可以构建并启动我们的容器了。

```
sudo docker build  -t  ruby-image  .
sudo docker run  -p  4000:80  ruby-image

```

## 单元测试 Docker 图像

容器映像是一个蓝图，我们可以从中创建几个容器实例。我们使用 Dockerfile 文件中的指令创建这个图像。就像软件一样，我们需要确保在容器投入生产之前，对其进行测试，以确保其按照要求工作。

我们根据需要对容器映像进行单元测试，以验证 docker 文件中的指令。应该在开发过程中测试容器图像，以便在将容器运送到生产环境之前确定容器的结构和内容。

## 容器结构测试框架

今年年初，Google 发布了容器结构测试框架来帮助我们验证容器图像的结构。

## 设置

测试在. yaml 或中指定。json 文件，并通过独立的二进制文件或 Docker 映像运行。在这里下载二进制文件[或者下载 Docker 镜像。](https://console.cloud.google.com/gcr/images/gcp-runtimes/GLOBAL/container-structure-test) 

```
sudo docker docker
pull gcr.io/gcp-runtimes/container-structure-test

```

下载二进制文件或提取 docker 映像后，使用二进制文件运行如下测试:

## 运行测试

```
./container-structure-test-linux-amd64 test  --image sample-docker-image sample_test_config.yaml

```

利用码头工人形象；

```
./structure-test  -test.v  -image sample-docker-image sample_test_config.yaml

```

回到我们的 docker 文件，让我们用以下内容为它创建一个测试文件。

ruby _ container _ image _ test . YAML

```
schemaVersion:  '2.0.0'
globalEnvVars:
-  key:  "VIRTUAL_ENV"
value:  "/env"
-  key:  "PATH"
value:  "/env/bin:$PATH"

fileExistenceTests:
-  name:  'Gemfile'
path:  '/app/Gemfile'
shouldExist:  true
permissions:  '-rwxr-xr-x'
-  name:  'Gemfile lock'
path:  '/app/.lock'
shouldExist:  true
permissions:  '-rwxr-xr-x'

fileContentTests:
-  name:  'Gemfile'
path:  '/Gemfile'
expectedContents:  [''https://rubygems.org'']

commandTests:
-  name:  "ruby package installation"
command:  "which"
args:  ["ruby"]
expectedOutput:  ["/usr/bin/ruby"]

-  name:  "bundler package installation"
command:  "which"
args:  ["bundler"]
expectedOutput:  ["/usr/bin/bundler"]

metadataTest:
env:
-  key:  'RACK_ENV'
value:  'production'
labels:
-  key:  'MAINTAINER'
value:  'Joannah Nanjekye'
workdir:  ['/app']
exposedPorts:  ['9292']
cmd:  ["bundle",  "exec",  "rackup",  "config.ru",  "-p",  "80",  "-s",  "thin",  "-o",  "0.0.0.0"]

```

命令测试使用此框架，我们可以对容器映像执行四种类型的测试；

这些测试允许我们在容器映像中执行给定的命令，并验证输出是否与预期的相匹配，或者是一个错误。命令测试的一个很好的例子是验证容器映像中的包或二进制文件的安装。

在我们的例子中，我们测试 ruby 和 bundler 安装。

```
commandTests
:
-  name:  "ruby package installation"
command:  "which"
args:  ["ruby"]
expectedOutput
:  ["/
usr
/bin/ruby"]-  name:  "bundler package installation"
command:  "which"
args:  ["bundler"]
expectedOutput

:  ["/
usr
/bin/bundler"]

```

文件存在测试用于检查容器映像中预期文件的存在。我们经常在容器映像中创建工作目录，甚至将文件转移到这个目录。我们可以通过文件存在测试来检查文件是否存在于工作目录中。

## 文件存在测试

对于 Dockerfile，我们将测试 Gemfile 和 Gemfile.lock 是否存在。

```
fileExistenceTests:

-  name:  'Gemfile'
path:  '/app/Gemfile'
shouldExist:  true
permissions:  '-rwxr-xr-x'

-  name:  'Gemfile lock'
path:  '/app/.lock'
shouldExist:  true
permissions:  '-rwxr-xr-x'

fileContentTests:
-  name:  'Gemfile'
path:  '/Gemfile'
expectedContents:  ['echo']

```

## 文件内容测试

这些用于验证文件容器文件系统的内容。

```
FileContentTests:
-  name:  'Gemfile'
path:  '/Gemfile'
expectedContents:  [''https://rubygems.org' ']

```

该测试检查以确保给定的容器元数据是准确的。使用元数据测试来检查 ENV、LABEL、ENTRYPOINT、CMD、EXPOSE、VOLUME、WORKDIR 等指令。

## 元数据测试

```
metadataTest:   
   env:
   -  key:  'RACK_ENV'
      value:  'production'
   labels:
   -  key:  'MAINTAINER'
      value:  'Joannah Nanjekye'
   workdir:  ['/app']
   exposedPorts:  ['9292']
   cmd:  ['ruby app.py']

```

添加完这些测试后，让我们在上面运行测试。

```
./structure-test  -test.v  -image ruby-image 
ruby_container_image_test.yaml

```

小容器映像为我们的应用程序提供了更好的性能和安全性。为了确保生产中可靠的容器，使用 Google 的容器结构测试框架对容器图像进行单元测试，以验证它们的结构。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>