# 使用 Kubernetes 加速机器学习开发

> 原文：<https://thenewstack.io/use-kubernetes-to-speed-machine-learning-development/>

[](https://mapr.com/)

 [贾斯汀·布兰登伯格

贾斯汀·布兰登伯格是 MapR 专业服务集团的数据科学家。Justin 在从禁毒到网络入侵分析等多个数据领域拥有丰富的经验。在过去的项目中，他利用机器学习、计量经济学、图形分析和基于代理的建模来满足客户需求。他拥有弗吉尼亚理工大学的经济学学士学位、约翰霍普金斯大学的经济学硕士学位和乔治梅森大学的计算社会科学硕士学位。](https://mapr.com/) [](https://mapr.com/)

随着行业转向使用容器部署应用的[微服务方法](https://mapr.com/ebook/microservices-and-containers/)，数据科学家可以从中获益。数据科学家使用特定的框架和操作系统，这些框架和操作系统经常会与生产系统的需求发生冲突。这导致了 IT 部门和研发部门之间的许多冲突。它不会改变操作系统来满足需要特定框架的模型的需求，该框架不会在 RHEL 7.2 上运行。

容器允许数据科学家构建自包含环境，打包必要的依赖项和逻辑。这也让数据科学家在讨论从开发运维转向数据运维时有了一席之地。当数据到达并被解析价值时，执行特定任务的容器可以在此过程中被分段，从而在新的传入数据上创建机器学习工作流，这在几年前是不可能的。

数据科学家可以部署多个容器来考虑数据的调整或模型的变化。这允许组织并行运行模型以进行评估，然后选择他们认为更有价值的模型，因为它应用于新的实时数据，而不是针对历史数据进行优化。

对于这个例子，我在 AWS ec2 实例上使用 kubeadm 安装了 [Docker 和 Kubernetes](https://mapr.com/blog/making-data-actionable-at-scale-part-1-of-3/) 来创建一个运行 centos 7.5 的双节点 Kubernetes 集群:

```
[justin@ip-10-0-0-105  ~]$  rpm  --query centos-release
centos-release-7-5.1804.el7.centos.2.x86_64
[justin@ip-10-0-0-105  ~]$  python  -V
Python  2.7.5
[justin@ip-10-0-0-105  ~]$  kubectl cluster-info
Kubernetes master is running at https://10.0.0.105:6443
KubeDNS is running at https://10.0.0.105:6443/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
[justin@ip-10-0-0-105  ~]$  kubectl get nodes

NAME                           STATUS          ROLES             AGE    VERSION

ip-10-0-0-149.ec2.internal     Ready               &lt;none&gt;            5h          v1.11.3
ip-10-0-0-236.ec2.internal     Ready               master             5h          v1.11.3

```

数据科学家通常在研发环境中开发、培训、测试和优化他们的模型，研发环境可以根据他们的需求进行配置。这是我在沙盒中编写的 Tensorflow 模型，它将递归神经网络应用于模拟的时间序列数据。

```
import pandas as pd
import numpy as np
import os
import random
import shutil
import tensorflow as tf
import tensorflow.contrib.metrics as metrics
import tensorflow.contrib.rnn as rnn

def main():
     random.seed(111)
     rng  =  pd.date_range(start='1/01/2000',  end='9/21/2018')
     ts  =  pd.Series(np.random.uniform(-10,  10,  size=len(rng)),  rng).cumsum()
     TS  =  np.array(ts)
     num_periods  =  100

     f_horizon  =  1   #forecast horizon, one period into the future
     x_data  =  TS[:(len(TS)-(len(TS)  %  num_periods))]
     x_batches  =  x_data.reshape(-1,  100,  1)
     y_data  =  TS[1:(len(TS)-(len(TS)  %  num_periods))+f_horizon]
     y_batches  =  y_data.reshape(-1,  100,  1)

     #number of periods per vector we are using to predict one period ahead

     num_periods  =  100                   

     inputs  =  1                  #number of vectors submitted
     hidden  =  100               #number of neurons we will recursively work through
     output  =  1                  #number of output vectors

     #create variable objects

     X  =  tf.placeholder(tf.float32,  [None,  num_periods,  inputs])      
     y  =  tf.placeholder(tf.float32,  [None,  num_periods,  output])

     #create our RNN

     model  =  tf.nn.rnn_cell.BasicRNNCell(num_units=hidden,  activation=tf.nn.relu)    

     #choose dynamic over static

     rnn_output,  states  =  tf.nn.dynamic_rnn(model,  X,  dtype=tf.float32)                      
     learning_rate  =  0.001 

     #change the form into a tensor

     stacked_rnn_output  =  tf.reshape(rnn_output,  [-1,  hidden])           
     stacked_outputs  =  tf.layers.dense(stacked_rnn_output,  output)   
     outputs  =  tf.reshape(stacked_outputs,  [-1,  num_periods,  output]) 

     #define the cost function which evaluates the quality of our model

     loss  =  tf.reduce_sum(tf.square(outputs  -  y))             

     #gradient descent method

     optimizer  =  tf.train.AdamOptimizer(learning_rate=learning_rate)               

     #train the result of the application of the cost_function

     training_op  =  optimizer.minimize(loss)                                    
     saver  =  tf.train.Saver()    #we are going to save the model
     DIR="/tmp/model/"
     init  =  tf.global_variables_initializer()
     epochs  =  1000        

     with tf.Session()  as sess:
              init.run()
              model_performance  =  []
              for ep in range(epochs):
              sess.run(training_op,  feed_dict={X:  x_batches,  y:  y_batches})
              mse  =  loss.eval(feed_dict={X:  x_batches,  y:  y_batches})
              model_performance.append((ep,  mse))
              saver.save(sess,  os.path.join(DIR,"model"),global_step  =  epochs)

if __name__==  "__main__":

   main()

```

我在研发环境中构建了这个，但是现在我想把它转移到生产环境中。我将使用 Docker 构建一个映像，然后可以将我的模型放入其中，并使用 Kubernetes 进行部署。

首先，我将创建一个 docker 文件，它将允许我用 Ubuntu OS 构建一个映像，并安装我的模型运行所需的依赖项和包。

```
[justin@ip-10-0-0-105  ~]$  mkdir dockbuild
[justin@ip-10-0-0-105  ~]$  cd dockbuild/
[justin@ip-10-0-0-105  dockbuild]$  vi Dockerfile

FROM ubuntu:16.04
RUN apt-get update  &amp;&amp;  apt-get install  -y  \
 build-essential  \
 curl  \
 git  \
 libfreetype6-dev  \
 libpng12-dev  \
 libzmq3-dev  \
 mlocate  \
 pkg-config  \
 python-dev  \
 python-numpy  \
 python-pip  \
 software-properties-common  \
 swig  \
 zip  \
 zlib1g-dev  \
 libcurl3-dev  \
 openjdk-8-jdk\
 openjdk-8-jre-headless  \
 wget  \
 &amp;&amp;  \
 apt-get clean  &amp;&amp;  \
 rm  -rf  /var/lib/apt/lists/*

RUN echo  "deb [arch=amd64] http://storage.googleapis.com/tensorflow-serving-apt stable tensorflow-model-server tensorflow-model-server-universal"  \

 |  tee  /etc/apt/sources.list.d/tensorflow-serving.list

RUN curl https://storage.googleapis.com/tensorflow-serving-apt/tensorflow-serving.release.pub.gpg \

 |  apt-key add  -

RUN apt-get update  &amp;&amp;  apt-get install  -y  \

 tensorflow-model-server

RUN pip install  --upgrade pip
RUN pip install pandas tensorflow tensorflow-serving-api
CMD  ["/bin/bash"]

```

我将使用 Tensorflow 服务 API 在 Docker 容器中执行和保存我的模型。接下来，构建映像，然后运行它:

```
[justin@ip-10-0-0-105  dockbuild]$  sudo docker build  -t  justin-tf_serving  .
[justin@ip-10-0-0-105  dockbuild]$  sudo docker run  --name=rnn_model_1  -it justin-tf_serving

root@1c48c2df62f8:/# cd
root@1c48c2df62f8:~# vi rnn_model_1.py
root@1c48c2df62f8:~# python rnn_model_1.py

```

复制模型，然后运行 python 脚本。模型参数将保存在容器内的/tmp/文件夹中。要退出容器并让它继续在后台运行，请按 Ctrl+P 和 Ctrl+Q。我需要持久保存我对 justin-tf_serving 容器所做的更改，以便永久保留我的模型数据。检索容器 ID 并将更改提交到一个名为 tf_kube1 的新映像中。

```
[justin@ip-10-0-0-105  dockbuild]$  sudo docker ps  -a
[justin@ip-10-0-0-105  dockbuild]$  sudo docker commit  07845b9c7ec5  tf_kube1
[justin@ip-10-0-0-105  dockbuild]$  sudo docker stop rnn_model_1

```

Kubernetes 允许您从私有或本地图像中心获取图像，但在本例中，我们将从 Docker 中心推送然后获取新图像。用你的用户名和密码锁定。

```
[justin@ip-10-0-0-105  dockbuild]$  sudo docker login  --username=jbrandenburg
Password:
Login Succeeded
[justin@ip-10-0-0-105  dockbuild]$  sudo docker tag tf_kube1 jbrandenburg/kube-example
[justin@ip-10-0-0-105  dockbuild]$  sudo docker push jbrandenburg/kube-example

```

一旦我们的映像在 Docker Hub 上，我们需要指定我们希望 Kubernetes 如何在我们的集群上使用映像。我们通过一个. yaml 文件来实现。我们设置了一个容器部署，它也将作为服务运行。

```
[justin@ip-10-0-0-105  dockbuild]$  vi kube_example.yaml apiVersion:  v1 kind:  Deployment metadata:     name:  tfrnn-deployment spec:     replicas:  3     template:               metadata:                labels:                app:  tfrnn-server               spec:                containers:                -  name:  rnn-model-1                image:  jbrandenburg/kube-example                command:                -  /bin/sh                args:                -  -c                -  tensorflow_model_server  --model_name=model  --model_base_path=/tmp/model                ports:                -  containerPort:  8500  ---  apiVersion:  v1 kind:  Service metadata:     labels:               run:  tfrnn-service     name:  tfrnn-service spec:     ports:     -  port:  8500               targetPort:  8500     selector:               app:  tfrnn-server     type:  LoadBalancer Create the Kubernetes objects:  [justin@ip-10-0-0-105  dockbuild]$  kubectl get nodes  [justin@ip-10-0-0-105  dockbuild]$  kubectl create  -f  kube_example.yaml deployment.extensions/tfrnn-deployment created service/tfrnn-service created  [justin@ip-10-0-0-105  dockbuild]$  kubectl get deployments NAME               DESIRED    CURRENT    UP-TO-DATE    AVAILABLE    AGE tfrnn-deployment    3              3            3            3            23s  [justin@ip-10-0-0-105  dockbuild]$  kubectl get pods NAME                                       READY             STATUS          RESTARTS    AGE tfrnn-deployment-868f55dd5-7s4tw    1/1                Running    0                  42s  tfrnn-deployment-868f55dd5-mnvlb    1/1               Running    0                  42s  tfrnn-deployment-868f55dd5-qf5j6    1/1    Running    0                  42s  [justin@ip-10-0-0-105  dockbuild]$  kubectl get services NAME               TYPE                 CLUSTER-IP EXTERNAL-IP    PORT(S)                   AGE kubernetes      ClusterIP          10.96.0.1           &lt;none&gt;             443/TCP            1m  tfrnn-service    LoadBalancer    10.106.86.19    &lt;pending&gt;               8500:31723/TCP    1m  [justin@ip-10-0-0-105  dockbuild]$  kubectl describe service tfrnn-service Name:                     tfrnn-service Namespace:                default Labels:                  run=tfrnn-service Annotations:             &lt;none&gt;  Selector:                app=tfrnn-server Type:                     LoadBalancer IP:                      10.106.86.19  Port:                     &lt;unset&gt;   8500/TCP TargetPort:              8500/TCP NodePort:                &lt;unset&gt;   31723/TCP Endpoints:                  Session Affinity:         None External Traffic Policy:   Cluster Events:                    &lt;none&gt;  Log in to one of the three pods that we just instantiated:  [justin@ip-10-0-0-105  dockbuild]$  kubectl exec  -it tfrnn-deployment-868f55dd5-7s4tw  --  /bin/bash root@tfrnn-deployment-868f55dd5-7s4tw:/# ls /tmp/model/ checkpoint  model-1000.data-00000-of-00001  model-1000.index  model-1000.meta

```

Kubernetes 现在正在运行我们的 Docker 映像，其中包含我们创建的经过训练的 [Tensorflow 模型](https://mapr.com/blog/deep-learning-tensorflow/)。现在，我们可以通过模型推送新数据，我们的模型可以评估这些数据并给出我们的结果。我们可以通过调整模型超参数来创建第二个图像，并且我们的 pod 可以并排运行模型 A 和模型 B 来比较结果。

我们的模型在他们的容器中有他们需要运行的所有东西。容器被配置为在生产环境中运行。Kubernetes 将允许我们指定资源，以提高分配给我们的模型的计算效率，并让我们知道容器是否表现不佳。

就在两年前，一旦我完成了我的分析并从数据中获得了洞察力，我就再也无法采取下一步并运用这种洞察力。我会写一份报告，发一封电子邮件，或者展示一些幻灯片，但是我的价值仅限于决策者会用它做什么。将我的工作流逻辑和模型转移到生产就绪的应用程序中需要许多人的认可和软件开发人员的奉献。在一个动态的行业中，这种滞后可能会导致数据发生变化，从而降低模型结果的意义。

随着容器和 Kubernetes 的发展，这种情况不再需要。数据科学的价值取决于它对数据的洞察力。随着实时解决挑战的能力越来越强，这一价值只会增加。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>