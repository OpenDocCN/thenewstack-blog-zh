# 教程:将全栈应用程序部署到 Docker 群

> 原文：<https://thenewstack.io/tutorial-deploy-a-full-stack-application-to-a-docker-swarm/>

如果你想扩展 Docker 应用程序的部署，你需要确保将一组节点聚集成一个 Docker 集群。我已经在“[使用 GlusterFS](https://thenewstack.io/tutorial-create-a-docker-swarm-with-persistent-storage-using-glusterfs/) 创建具有持久存储的 Docker Swarm”中讨论了如何部署 Docker Swarm(具有持久存储)您不一定要部署带有持久性存储的 Swarm，但是如果您希望能够保留您的数据(如果发生了什么事情或者您希望迁移部署)，您将希望部署带有持久性的 Swarm。

运行 Docker Swarm 后，确保通过运行以下命令(在控制器上)来验证所有节点都已连接并准备就绪:

`docker node ls`

在输出中，您应该会看到类似这样的内容:

`tpsl7enzswhkeef3dh8uswkxp *  docker1    Ready     Active         Leader      20.10.17`

`xnye548afhe1hc832kulh5sui     docker2    Ready     Active                          20.10.17`

`cammaze2fcfcomjpdo0fwz105   docker3    Ready    Active                          20.10.17`

如果所有节点都列为就绪和活动状态，您就可以部署到堆栈了。如果没有，您需要排除故障，直到每个节点都这样列出。

## 部署本地注册表

随着 Swarm 的启动和运行，您的下一个任务是部署本地 Docker 注册中心。幸运的是，有一个专门为此目的创建的容器图像。在 Docker Swarm controller 节点上，使用以下命令部署注册表:

`docker service create --name registry --publish published=5000,target=5000 registry:2`

如果您发出命令 docker service ls，您应该看到注册表如下所示:

`zhquhrodsirp   registry   replicated   1/1        registry:2   *:5000->5000/tcp`

请注意，您的服务 ID 不会与您在上面看到的相同(第一列中的随机字符串)。如你所见，你已经准备好了。您还可以通过发出以下命令来验证注册表是否已成功部署:

`curl http://localhost:5000/v2/`

如果您看到的唯一输出是 *{}* ，那么一切都在按预期运行。

## 创建一个示例应用程序

猜猜我们要创造什么？如果你猜的是“你好，世界”，你答对了。创建一个新目录来存放项目:

`mkdir ~/swarmtest`

使用以下命令切换到新目录:

`cd ~/swarmtest`

首先，我们将使用以下命令创建一个名为 app.py 的 Python 文件:

`nano app.py`

在该文件中，粘贴以下内容:

```
from flask import Flask
from redis import Redis
app  =  Flask(__name__)
redis  =  Redis(host='redis',  port=6379)

@app.route('/')
def hello():
count  =  redis.incr('hits')
return  'Hello New Stack! I have been seen {} times.\n'.format(count)

if __name__  ==  "__main__":
app.run(host="0.0.0.0",  port=8000,  debug=True)

```

保存并关闭文件。

接下来，我们将使用以下内容创建一个需求文件:

`nano requirements.txt`

在该文件中，添加以下内容:

保存并关闭文件。

现在，我们将使用以下命令创建 docker 文件:

纳米 Dockerfile 文件

在该文件中，粘贴以下内容:

```
# syntax=docker/dockerfile:1
FROM python:3.4-alpine
ADD  .  /code
WORKDIR  /code
RUN pip install  -r  requirements.txt
CMD  ["python",  "app.py"]

```

最后，使用以下内容创建 docker-compose.yml 文件:

`nano docker-compose.yml`

在该文件中，粘贴以下内容:

```
version:  "3.9"

services:
web:
image:  127.0.0.1:5000/swarmtest
build:  .
ports:
-  "8000:8000"
redis:
image:  redis:alpine

```

保存并关闭文件。

## 部署应用程序

所有的部分都准备好了，我们现在可以将栈部署到 Docker Swarm。但是，在我们这样做之前，让我们测试一下，以确保它能与以下各项一起工作:

`docker-compose up -d`

如果您得到 docker-compose 命令找不到的错误消息，请使用以下命令安装它(在基于 Ubuntu 的发行版上):

`sudo apt-get install docker-compose -y`

部署完成后，使用以下工具测试应用程序:

`curl http://localhost:8000`

您应该会看到类似这样的内容:

```
Hello NewStack!  I  have been seen  1  time.

```

再次运行它，输出将是:

```
Hello NewStack!  I  have been seen  1  time.

```

使用命令关闭应用程序:

`docker-compose down --volumes`

## 将应用程序部署到 Docker Swarm

对于我们的下一个技巧，我们将应用程序部署到我们的 Docker 群。在此之前，我们必须首先将新生成的图像推送到我们的本地注册表中:

`docker-compose push`

此时，我们的文本图像对我们的本地注册中心是可用的，并且可以用于部署到 Swarm。我们可以通过以下方式部署堆栈:

`docker stack deploy --compose-file docker-compose.yml swarmtest`

验证堆栈正在运行:

`docker stack services swarmtest`

上面命令的输出应该是这样的:

```
ocfddicaivol         swarmtest_redis      replicated     1/1            redis:alpine
hbfv50ayxwrs     swarmtest_web        replicated     1/1            127.0.0.1:5000/swarmtest:latest     *:8000-&gt;8000/tcp

```

让我们确保它正在所有节点上运行。假设您的节点位于 IP 地址 192.168.1.60、192.168.1.61 和 192.168.1.63 上。发出命令:

`curl http://192.168.1.60:8000`

`curl http://192.168.1.61:8000`

`curl http://192.168.1.63:8000`

你应该这样输出:

```
Hello New Stack!  I  have been seen  1  times.
Hello New Stack!  I  have been seen  2  times.
Hello New Stack!  I  have been seen  3  times.

```

恭喜你！您刚刚在 Docker 群中部署了一个完整的堆栈应用程序。您可以使用以下命令关闭堆栈:

`docker stack rm swarmtest`

完了，完了。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>