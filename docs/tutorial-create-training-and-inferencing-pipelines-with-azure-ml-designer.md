# 教程:使用 Azure ML Designer 创建培训和推理管道

> 原文：<https://thenewstack.io/tutorial-create-training-and-inferencing-pipelines-with-azure-ml-designer/>

在本系列的第一部分中，我介绍了 [Azure ML 管道](https://docs.microsoft.com/en-us/azure/machine-learning/concept-ml-pipelines)的概念。在当前教程中，我们将探索 Azure ML 的交互式设计器，为简单的机器学习模型构建训练和推理管道。

在本教程结束时，我们将建立一个二元分类/逻辑回归模型，根据数据集中包含的某些诊断测量结果来预测患者是否患有糖尿病。

关于 Azure ML 的背景，参考这篇[文章](https://thenewstack.io/how-the-azure-ml-streamlines-cloud-based-machine-learning/)和[教程](https://thenewstack.io/build-and-deploy-a-machine-learning-model-with-azure-ml-service/)。

### 创建 Azure 资源组和 ML 工作区

首先在一个支持 Azure 的区域中创建一个新的 ML 工作区。确保选择工作区的企业版，因为设计器在基本版中不可用。

![](img/01cd5e160bd44350915fcfdf50a8a5d6.png)

一旦工作区准备好了，通过点击 launch now 按钮切换到新的 Azure ML studio 界面。

![](img/4821e13fb8c8b91c88549e6b9ac6a6a6.png)这将带您进入新的 ML studio 界面，其中包含设计器。

![](img/00efddc3c205a75e3d5f4c0e60af794f.png)

### 创建数据集

对于本教程，我们将使用在加州大学欧文分校机器学习库中发布的 Pima Indian 糖尿病数据集。你可以从 [Kaggle](https://www.kaggle.com/uciml/pima-indians-diabetes-database) 下载 CSV 文件。

一旦下载了 CSV 文件，就用 Azure ML 将其注册为数据集。为此，单击左侧导航栏上的数据集链接，并选择从本地文件创建数据集选项。

![](img/a6057484ceb55d0b6fcb0f44f9fe8a66.png)

从本地硬盘上传文件。确定您在“设置和预览”部分选取了“使用第一个文件的头”。

![](img/8af95a978b152277b4e99573df43bfdb.png)

最后，单击 create 按钮完成数据集的注册。

![](img/863732f4c45d5311282c33d0189f42fc.png)

### 建立培训渠道

有了数据集，现在让我们构建培训管道。在设计器环境中，选择第一个选项来创建新的管道草图。

![](img/ec90304b1179c440bfe46874f99312e5.png)

重命名管道，并单击选择计算目标以创建用于训练的集群。

![](img/ab65e885e0c1c5eb95475da2a755ef1a.png)

计算目标将用于管道的各个阶段，包括数据准备、转换、培训、评分和评估。

让我们创建一个具有预定义配置的双节点集群。我们称之为演示集群。

![](img/d19363c84bd8ac604a642b2838946d3b.png)

等待计算群集变得可用。这可能需要几分钟。

让我们从定义用于管道的数据集开始。拖放在上一步中创建的糖尿病数据集。它位于我的数据集部分下的调色板的数据集选项卡中。

![](img/007a680ef411abdcdd502f2774bab90f.png)

现在，让我们将模块拖放到画布上，选择数据转换选项卡下可用的数据集中的列。

![](img/42dd5410acd797c7f711d044e9f7d99c.png)

在“选择列”对话框中，选择“所有列”。

![](img/7f49e5c4a7a4cdd9055ff52215bbb97b.png)

接下来，让我们通过拆分数据模块拆分数据集来创建训练和测试数据集。选择 0.7 作为行的分数，以用 70%的数据和剩余的测试数据创建定型数据集。

![](img/c2f08be900c8ac7426ce0942decec8aa.png)

我们现在准备好对模型进行训练、评分和评估。拖动以下模块并连接它们，如下图所示:

*   两类逻辑回归(机器学习算法)
*   训练模型(模型训练)
*   评分模型(模型评分和评估)
*   评估模型(模型评分和评估)

![](img/6dfcff5dae696afe20efd25cf34f5110.png)

将训练模块的标签列设置为结果。这是我们希望模型预测的值。

![](img/073dab751554fff3c490af63f29ad4cf.png)

点击提交按钮开始执行管道。为管道运行创建一个新实验。

![](img/5f8adcf2e682ade96feaba58f54f4060.png)

![](img/5f9fff21a8d84f0c63414ff7ac785ef6.png)

等待管道运行完成执行。您应该会在每个模块上看到绿色勾号，表示所有模块都已成功运行。

![](img/baaf877c9f1ef84a18bde74db459af84.png)

右键单击评估模型模块，查看评分模型的准确性指标。

![](img/46dd653ca393d8f768357627a0ff5e79.png)

我们现在准备创建推理管道。

### 创建推理管道

在这一步中，我们将创建一个 REST 端点来预测模型的结果。Azure ML designer 负责创建部署和公开模型的管道。

单击创建推理管道按钮，然后选择实时推理管道。这将在画布上创建一个新的绘制管线。

![](img/64146279c4819937b2475d3cf22d74f5.png)

点击提交并选择用于培训的相同实验。

![](img/a3855f57019892128a607dcbed249b95.png)

等待管道完成执行。

我们需要一个计算环境来托管模型。在发布管道之前，让我们创建一个 Azure Kubernetes 服务(AKS)集群，它将成为推理管道的计算目标。

![](img/64146279c4819937b2475d3cf22d74f5.png)

导航到工作区的计算部分，然后选择推理簇。用所需的配置创建一个 Kubernetes 集群。不要忘记选择开发测试作为环境。这将使我们能够部署具有更少 CPU 内核的型号。

![](img/84f923eaf72073f6cf8e6ff6c2e0592c.png)

单击“deploy ”,选择 AKS 集群作为计算目标。

几分钟后，该模型就会部署到 AKS 集群中。可以从任何支持发送 HTTP 请求的客户机通过 REST 端点访问它。

![](img/838e3d45552895c3963329f6635bc1eb.png)

导航到工作区的端点部分，找到由设计者创建的糖尿病实时推断。

我们现在可以通过发送与数据集模式匹配的 HTTP 有效负载来调用端点。

用下面的 JSON 有效负载创建一个文件，并通过 curl 发送它。

```
{
  "Inputs":  {
    "WebServiceInput0":  [
      {
        "Pregnancies":  6,
        "Glucose":  148,
        "BloodPressure":  72,
        "SkinThickness":  35,
        "Insulin":  0,
        "BMI":  33.6,
        "DiabetesPedigreeFunction":  0.627,
        "Age":  50,
        "Outcome":  1
      }
    ]
  },
  "GlobalParameters":  {}
}

```

```
export AUTH="erBZZwCkvzBBkUZlP7g1yWD1HOEOYO04"

```

```
curl  --header  "Content-Type: application/json"  -H  "Authorization: Bearer $AUTH"  -d  @data.json http://20.43.161.173:80/api/v1/service/diabetes-real-time-inference/score

```

您将从 web 服务中获得标签和得分概率。注意，我们需要在请求中包含标签 Outcome，以满足模式需求。但是，Azure ML 评分在推理时不会考虑这一点。

```
{"Results":  {"WebServiceOutput0":  [{"Pregnancies":  6,  "Glucose":  148,  "BloodPressure":  72,  "SkinThickness":  35,  "Insulin":  0,  "BMI":  33.6,  "DiabetesPedigreeFunction":  0.627,  "Age":  50,  "Outcome":  1,  "Scored Labels":  1,  "Scored Probabilities":  0.6230318022487494}]}}

```

在本系列的下一部分，我们将使用 Python SDK 来创建管道。敬请关注。

*贾纳基拉姆·MSV 的网络研讨会系列“机器智能和现代基础设施(MI2)”提供了涵盖前沿技术的信息丰富、见解深刻的会议。在 [http://mi2.live](http://mi2.live/) 注册参加即将举行的 MI2 网络研讨会。*

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>