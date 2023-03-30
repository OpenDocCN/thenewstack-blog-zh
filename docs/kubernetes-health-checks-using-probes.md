# Kubernetes 使用探针进行健康检查

> 原文：<https://thenewstack.io/kubernetes-health-checks-using-probes/>

[](https://in.linkedin.com/in/roshan-shetty-7905a746)

 [罗山谢蒂

罗山是夸夸特公司的现场可靠性工程师。他是一个开源爱好者，主要致力于构建解决企业可靠性问题的工具。他喜欢在空闲时间为开源项目做贡献，比如 SLO-tracker(github.com/roshan8/slo-tracker)。](https://in.linkedin.com/in/roshan-shetty-7905a746) [](https://in.linkedin.com/in/roshan-shetty-7905a746)

Kubernetes 是一个开源的容器编排平台，它极大地简化了应用程序的创建和管理。

像 Kubernetes 这样的分布式系统可能很难管理，因为它们涉及许多移动部件，所有这些部件都必须为系统的运行而工作。即使一小部分损坏，也需要检测、布线和修复。

这些操作也需要自动化。Kubernetes 允许我们在就绪性和活性探针的帮助下做到这一点。在这篇博客中，我们将详细讨论这些探索。但在此之前，我们先来讨论一下健康检查。

## **什么是健康检查？**

健康检查是让系统知道你的应用实例是否工作的简单方法。如果您的应用程序实例不工作，其他服务不应该访问它或向它发送请求。相反，应该将请求发送到另一个已准备好的实例，或者您应该重试发送请求。

系统应该能够使你的应用程序进入健康状态。默认情况下，Kubernetes 将在 pod 中的所有容器都启动后开始向 pod 发送流量。当容器崩溃时，Kubernetes 将重新启动容器。这种默认行为应该足以开始。由于 Kubernetes 有助于创建定制的运行状况检查，因此使部署更加健壮变得相对简单。但在此之前，我们先来讨论一下 pod 的生命周期。

## **Pod 生命周期**

一个 [Kubernetes](https://www.squadcast.com/blog/implementing-istio-in-kubernetes-cluster) pod 遵循一个确定的生命周期。这些是不同的阶段:

*   当 pod 第一次被创建时，它从一个*挂起*阶段开始。调度程序试图找出放置 pod 的位置。如果调度程序找不到放置 pod 的节点，它将保持挂起状态。(要检查 pod 处于挂起状态的原因，请运行`kubectl describe pod <pod name>`命令)。
*   一旦 pod 被调度，它就进入容器*创建*阶段，在那里应用程序所需的图像被提取，容器启动。
*   一旦容器在 pod 中，它移动到*运行*阶段，在那里它继续直到程序成功完成或终止。

要检查 pod 的状态，运行`kubectl get pod`命令并检查`STATUS`列。如您所见，在这种情况下，所有的 pod 都处于*运行*状态。此外，`READY`列表示 pod 已准备好接受用户流量。

```
# kubectl get pod

NAME READY STATUS RESTARTS AGE

my-nginx-6b74b79f57-fldq6  1/1  Running  0  20s

my-nginx-6b74b79f57-n67wp  1/1  Running  0  20s

my-nginx-6b74b79f57-r6pcq  1/1  Running  0  20s

```

## **Kubernetes 中不同类型的探针**

[Kubernetes](https://www.squadcast.com/blog/introduction-to-kubernetes-storage) 为您提供以下类型的健康检查:

*   **准备就绪探测器:**这个探测器会告诉你你的应用什么时候准备好服务流量。Kubernetes 将在允许服务向 pod 发送流量之前确保就绪性探测通过。如果就绪探测失败，Kubernetes 将不会向 pod 发送流量，直到它通过。
*   **活跃度探测器:**活跃度探测器会让 Kubernetes 知道你的应用是否健康。如果你的应用程序是健康的，Kubernetes 不会干扰 pod 的功能，但如果它是不健康的，Kubernetes 会破坏 pod 并启动一个新的来取代它。

为了进一步理解这一点，让我们使用一个真实的场景作为例子。您有一个应用程序，它需要一些时间来预热或从一些外部来源(如 GitHub)下载应用程序内容。在完全准备好之前，您的应用程序不应该接收流量。默认情况下，Kubernetes 会在容器内部的进程启动后立即开始发送流量。使用就绪探测器，Kubernetes 将等到应用程序完全启动后，才允许服务向新副本发送流量。

让我们看另一个场景，您的应用程序由于代码中的一个错误而崩溃(可能是一种边缘情况)，它无限期地挂起并停止为请求提供服务。因为您的流程在默认情况下继续运行，Kubernetes 会将流量发送到中断的 pod。使用活跃度探测器，Kubernetes 将检测到应用程序不再服务于请求，并默认重启故障 pod。

理论部分完成后，让我们看看如何定义探针。有三种类型的探头:

**注意:**您可以选择从定义就绪性或活性探测器开始，因为两者的实现都需要类似的模板。例如，如果我们首先定义 livenessProbe，我们可以用它来定义 readinessProbe，反之亦然。

*   **HTTP 探测器(`httpGet` ):** 这是最常见的探测器类型。即使您的应用程序不是 HTTP 服务器，您通常也可以在应用程序内部创建一个轻量级 HTTP 服务器来响应活跃度探测。Kubernetes 将在给定的端口(本例中为 8080)ping 一条路径(例如，`/healthz`)。如果它得到 200 或 300 范围内的 HTTP 响应，它将被标记为健康。(有关 HTTP 响应代码的更多信息，请参考此[链接](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status))。否则会被标记为不健康。下面是定义 HTTP livelinessProbe 的方法:

`livenessProbe:
httpGet:
path: /healthz
port: 8080`

HTTP 就绪探测器的定义与 HTTP livelinessProbe 一样；你只需要用准备状态代替活跃状态。

`readinessProbe:`


*   **TCP 探针(`tcpSocket` ):** 使用 TCP 探针，Kubernetes 将尝试在指定的端口上建立 TCP 连接(例如，下例中的端口 8080)。如果可以建立连接，则认为该容器是健康的。如果不能，就认为是失败的。在 HTTP 或命令探针不能很好工作的地方，这些探针会很方便。例如，FTP 服务将能够使用这种类型的探测器。

`readinessProbe:
tcpSocket:
port: 8080`

*   **Command probes (exec 命令):**对于 Command probes，Kubernetes 将在您的容器中运行一个命令。如果命令返回退出代码零，容器将被标记为健康。否则会被标记为不健康。当您不能或不想运行 HTTP 服务器时，这种类型的探测非常有用，但是您可以运行一个命令来检查您的应用程序是否正常。在下面的例子中，我们检查文件`/tmp/healthy`是否存在，如果命令返回退出代码零，容器将被标记为健康的；否则会被标记为不健康。

`livenessProbe:
exec:
command:
- cat
- /tmp/healthy`

可以根据探测器运行的频率、成功和失败阈值以及等待响应的时间，以多种方式配置探测器。

*   **initialDelaySeconds(缺省值 0):** 如果你知道你的应用需要 n 秒(例如 30 秒)预热，你可以使用`initialDelaySeconds`增加延迟秒数，直到第一次检查被执行。
*   **周期秒(默认值 10):** 如果您想指定执行检查的频率，您可以使用`periodSeconds`来定义。
*   **超时秒数(默认值 1):** 这定义了探头操作超时前的最大秒数。
*   **successThreshold(默认值 1):** 这是失败后探针被认为成功之前的尝试次数。
*   **失败尿道阈值(默认值 3):** 如果探针失败，Kubernetes 会在探针被标记为失败之前进行多次尝试。

**注意:**默认情况下，如果应用程序在三次尝试后仍未准备好，探头将停止。在活动探测的情况下，它将重新启动容器。在准备就绪探测的情况下，它会将 pod 标记为不健康。

有关探头配置的更多信息，请参考此[链接](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/#configure-probes)。

让我们把到目前为止讨论的所有内容结合起来。这里需要注意的关键是 readinessProbe 与`httpGet`的使用。第一次检查将在 10 秒后执行，然后每隔 5 秒重复一次。

```
apiVersion:  v1

kind:  Pod

metadata:

labels:

run:  nginx

name:  nginx

spec:

containers:

-  image:  nginx

name:  nginx

readinessProbe:

httpGet:

path:  /

port:  80

initialDelaySeconds:  10

periodSeconds:  5

```

*   要创建一个 pod，使用`kubectl create`命令并用`-f`标志指定 YAML 清单文件。您可以给文件起任何名字，但是它应该以扩展名`.yaml`结尾。

```
kubectl create  -f  readinessprobe.yaml

pod/nginx created

```

*   如果您现在检查 pod 的状态，它应该在`STATUS`列下显示运行状态。但是如果你检查`READY`列，它仍然会显示 0/1，这意味着它还没有准备好接受新的连接。

```
kubectl get pod

NAME READY STATUS RESTARTS AGE

nginx  0/1  Running  0  16s

```

*   几秒钟后验证状态，因为我们设置了一秒钟的初始延迟。现在，分离舱应该在运行了。

```
kubectl get pod

NAME READY STATUS RESTARTS AGE

nginx  1/1  Running  0  28s

```

*   检查所有参数的详细状态(例如，initialDelaySeconds、periodSeconds 等。)定义准备就绪探测器时使用，运行`kubectl describe`命令。

```
kubectl describe pod nginx  |grep  -i  readiness

Readiness:  http-get http://:80/ delay=10s timeout=1s period=5s #success=1 #failure=3

```

让我们借助一个例子来进一步强化活性和就绪性探测的概念。首先，让我们从活性探针开始。在下面的例子中，我们正在执行一个命令，'`touch healthy; sleep 20; rm -rf healthy; sleep 600`'。

通过这个命令，我们使用`touch`命令创建了一个文件名“healthy”。该文件将在前 20 秒存在于容器中，然后使用`rm -rf`命令将其删除。最后，容器将休眠 600 秒。

然后我们定义了活性探针。它首先使用`cat healthy`命令检查文件是否存在。它以五秒钟的初始延迟来完成。我们进一步定义了参数`periodSeconds`，它每五秒执行一次活性探测。一旦我们删除了该文件，20 秒后探测器将处于失败状态。

```
apiVersion:  v1

kind:  Pod

metadata:

labels:

name:  liveness-probe-exec

spec:

containers:

-  name:  liveness-probe

image:  busybox

args:

-  /bin/sh

-  -c

-  touch healthy;  sleep  20;  rm  -rf healthy;  sleep  600

livenessProbe:

exec:

command:

-  cat

-  healthy

initialDelaySeconds:  5

periodSeconds:  5

```

*   要创建一个 pod，将上述代码存储在一个以`.yaml`结尾的文件中(例如，`liveness-probe.yaml`)，并使用`-f <file name>`执行`kubectl create`命令，这将创建 pod。

```
# kubectl create -f liveness-probe.yaml

pod/liveness-probe-exec created

```

*   运行`kubectl get events`命令，您将看到活跃度探测失败，容器被终止并重启。

```
54s  Normal Scheduled pod/liveness-probe-exec Successfully assigned default/liveness-probe-exec to controlplane

53s  Normal Pulling pod/liveness-probe-exec Pulling image  "busybox"

52s  Normal Pulled pod/liveness-probe-exec Successfully pulled image  "busybox"  in  384.330188ms

52s  Normal Created pod/liveness-probe-exec Created container liveness-probe

52s  Normal Started pod/liveness-probe-exec Started container liveness-probe

18s  Warning Unhealthy pod/liveness-probe-exec Liveness probe failed:  cat:  can't open 'healthy':  No such file or directory

18s  Normal Killing pod/liveness-probe-exec Container liveness-probe failed liveness probe,  will be restarted

```

*   您还可以使用`kubectl get pods`命令来验证它，正如您在 restart 列中看到的，容器被重启了一次。

```
# kubectl get pods

NAME READY STATUS RESTARTS AGE

liveness-probe-exec  1/1  Running  1  24s

```

*   现在您已经理解了活跃度探测器是如何工作的，让我们通过调整上面的示例将其定义为就绪性探测器来理解就绪性探测器是如何工作的。在下面的例子中，我们在容器内部执行一个命令(sleep 20 触摸健康；睡眠 600)，先睡眠 20 秒，创建文件，最后睡眠 600 秒。由于初始延迟设置为 15 秒，第一次检查延迟 15 秒执行。

```
apiVersion:  v1

kind:  Pod

metadata:

labels:

name:  readiness-probe-exec

spec:

containers:

-  name:  readiness-probe

image:  busybox

args:

-  /bin/sh

-  -c

-  sleep  20;touch healthy;sleep  600

readinessProbe:

exec:

command:

-  cat

-  healthy

initialDelaySeconds:  15

periodSeconds:  5

```

*   要创建一个 pod，将上述代码存储在一个以`.yaml`结尾的文件中，并执行`kubectl create`命令，这将创建 pod。

```
# kubectl create -f readiness-probe.yaml

pod/readiness-probe-exec created

```

*   如果您在这里执行`kubectl get events`，您将看到探测失败，因为文件不存在。

```
63s  Normal Scheduled pod/readiness-probe-exec Successfully assigned default/readiness-probe-exec to controlplane

62s  Normal Pulling pod/readiness-probe-exec Pulling image  "busybox"

62s  Normal Pulled pod/readiness-probe-exec Successfully pulled image  "busybox"  in  156.57701ms

61s  Normal Created pod/readiness-probe-exec Created container readiness-probe

61s  Normal Started pod/readiness-probe-exec Started container readiness-probe

42s  Warning Unhealthy pod/readiness-probe-exec Readiness probe failed:  cat:  can't open 'healthy':  No such file or directory

If you check the status of the container initially,  it is not in  a  ready state.

# kubectl get pods

NAME READY STATUS RESTARTS AGE

readiness-probe-exec  0/1  Running  0  5s

```

*   但如果 20 秒后再检查，应该是在运行状态。

```
# kubectl get pods

NAME READY STATUS RESTARTS AGE

readiness-probe-exec  1/1  Running  0  27s

```

## **结论**

任何分布式系统都需要健康检查，Kubernetes 也不例外。使用健康检查为您的 Kubernetes 服务提供了坚实的基础、更好的可靠性和更长的正常运行时间。

## **Plug:使用 K8s 配合 Squadcast 以获得更快的分辨率**

[Squadcast](https://www.squadcast.com/) 是一款事故管理工具，专门用于现场可靠性工程。它可以让您摆脱不想要的警报，接收相关通知，并与流行的 ChatOps 工具集成。您还可以使用虚拟事件作战室协同工作，并使用自动化来消除辛劳。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>