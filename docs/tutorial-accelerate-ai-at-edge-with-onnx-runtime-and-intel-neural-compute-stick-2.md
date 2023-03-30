# 教程:利用 ONNX 运行时和英特尔神经计算棒 2 在边缘加速人工智能

> 原文：<https://thenewstack.io/tutorial-accelerate-ai-at-edge-with-onnx-runtime-and-intel-neural-compute-stick-2/>

本文是开放神经网络交换(ONNX)系列介绍教程的第五篇也是最后一篇，ONNX 是 AWS、微软和脸书的一项倡议，旨在定义跨机器学习平台的互操作性标准。参见:

[Part 1](https://thenewstack.io/open-neural-network-exchange-brings-interoperability-to-machine-learning-frameworks/)

,

[Part 2](https://thenewstack.io/tutorial-using-a-pre-trained-onnx-model-for-inferencing/)

,

[Part 3](https://thenewstack.io/tutorial-train-a-deep-learning-model-in-pytorch-and-export-it-to-onnx/)

，以及

[Part 4](https://thenewstack.io/tutorial-import-an-onnx-model-into-tensorflow-for-inference/)

.

在本系列的前几部分中，我们已经探讨了 ONNX 模型格式和运行时的概念。在最后也是最后一个教程中，我将带您了解在基于英特尔 m ovidius Neural Compute Stick(NCS)2 和英特尔 OpenVINO Toolkit 发行版的边缘设备上加速 ONNX 模型的步骤。我们将首先在基于 CPU 的桌面上运行微小的 YOLO2 模型，然后在几乎不改变代码的情况下在边缘设备上运行。

### 快速回顾— ONNX 运行时

除了带来跨深度学习框架的互操作性，ONNX 还承诺根据硬件的可用性优化神经网络图的执行。ONNX 运行时抽象了各种硬件架构，如 AMD64 CPU、ARM64 CPU、GPU、FPGA 和 VPU。

例如，同一个 ONNX 模型在没有对模型进行任何优化的情况下对 GPU 后端运行时，可以提供更好的推理性能。这是可能的，因为 ONNX 的插件模型支持多个执行提供者。

【T2![](img/36abaff11cb4cec05ee3c2d46af94481.png)

在创建推理会话之前向 ONNX 运行时提供一个提示，可以显著提高性能。

以下代码片段是 ONNX 运行时利用英特尔集成显卡后端的优化提示示例。

```
import onnxruntime as rt
rt.capi._pybind_state.set_openvino_device("GPU_FP32")
sess  =  rt.InferenceSession('TinyYOLO.onnx')

```

当同一型号用于由英特尔 NCS 设备驱动的智能摄像机时，后端可以更改为针对 MYRIAD 视觉处理单元(VPU)。

```
rt.capi._pybind_state.set_openvino_device("MYRIAD_FP16")

```

在下面的章节中，我们将基于流行的微型 YOLO v2 模型构建一个简单的对象检测系统。我们将首先在 PC 上运行它，在将它移动到带有 VPU 的边缘设备之前，针对 CPU 后端执行该模型。

### 先决条件

要完成本教程，您需要以下内容:

### 设置环境

首先为项目创建一个 Python 虚拟环境。

```
python  -m  venv demoenv
source demoenv/bin/activate

```

用所需的 Python 模块创建一个`requirements.txt`文件。

因为我们要检测多达 20 个对象，创建一个名为`labels.txt`的文件，标签如下:

```
aeroplane,bicycle,bird,boat,bottle,bus,car,cat,chair,cow,diningtable,dog,horse,motorbike,person,pottedplant,sheep,sofa,train,tvmonitor

```

最后，从 [ONNX 模型动物园](https://github.com/onnx/models)下载[微型 YOLO v2](https://github.com/onnx/models/tree/master/vision/object_detection_segmentation/tiny-yolov2) 模型。

### 在桌面上用微小的 YOLO V2 检测物体

我们现在已经准备好编写基于微型 YOLO v2 和 ONNX 运行时的推理程序了。创建一个文件，`infer.py`，代码如下:

```
import cv2
import numpy as np
import onnxruntime as rt

def preprocess(msg):
  inp  =  np.array(msg).reshape((len(msg),1))
  frame  =  cv2.imdecode(inp.astype(np.uint8),  1)
  frame  =  cv2.cvtColor(frame,  cv2.COLOR_BGR2RGB)
  frame  =  np.array(frame).astype(np.float32)
  frame  =  cv2.resize(frame,  (416,  416))
  frame  =  frame.transpose(2,  0,  1)
  frame  =  np.reshape(frame,  (1,  3,  416,  416))
  return frame

def infer(frame,  sess,  conf_threshold):
  input_name  =  sess.get_inputs()[0].name
  output={}

  def softmax(x):
  return np.exp(x)  /  np.sum(np.exp(x),  axis=0)

  def sigmoid(x):
  return  1/(1+np.exp(-x))

  pred  =  sess.run(None,  {input_name:  frame})
  pred  =  np.array(pred[0][0])

  labels_file  =  open("labels.txt")
  labels  =  labels_file.read().split(",")

  tiny_yolo_cell_width  =  13
  tiny_yolo_cell_height  =  13
  num_boxes  =  5
  tiny_yolo_classes  =  20

  for bx in range  (0,  tiny_yolo_cell_width):
  for by in range  (0,  tiny_yolo_cell_height):
  for bound in range  (0,  num_boxes):
  channel  =  bound*25
  tx  =  pred[channel][by][bx]
  ty  =  pred[channel+1][by][bx]
  tw  =  pred[channel+2][by][bx]
  th  =  pred[channel+3][by][bx]
  tc  =  pred[channel+4][by][bx]

  confidence  =  sigmoid(tc)
  class_out  =  pred[channel+5:channel+5+tiny_yolo_classes][bx][by]
  class_out  =  softmax(np.array(class_out))
  class_detected  =  np.argmax(class_out)
  display_confidence  =  class_out[class_detected]*confidence
 if display_confidence  &gt;  conf_threshold:
 output['object']=labels[class_detected]
 output['confidence']=display_confidence
  return output

def main():
  cam=0
  conf_threshold=0.10
  sess  =  rt.InferenceSession('TinyYOLO.onnx')
  while  (True):
  cv2.waitKey(5)
  cap  =  cv2.VideoCapture(cam)
  ret,  frame  =  cap.read()
  #cv2.imshow('frame',frame)
  ret,  enc  =  cv2.imencode('.jpg',  frame)
  enc  =  enc.flatten()
  fr=preprocess(enc.tolist())
  p=infer(fr,sess,conf_threshold)
  print(p)

if __name__  ==  "__main__":
    main()

```

如果你熟悉 [OpenCV](https://opencv.org/) 和基本卷积神经网络(CNN)，代码是不言自明的。

它做三件事:

1.  1.  从网络摄像头中抓取帧
    2.  按照模型的预期转换和预处理帧
    3.  最后，它对帧执行推理，以检测与置信度匹配的对象，并将其与 CSV 文件中的一个标签配对

如果机器上连接了多个摄像机，不要忘记通过改变`cam`变量的值来适当地更新索引。

执行代码会显示它找到的对象以及置信度得分。根据您的需求调整置信度阈值。

```
{'object':  'diningtable',  'confidence':  0.1934369369567218}
{'object':  'diningtable',  'confidence':  0.12359955877868607}
{'object':  'diningtable',  'confidence':  0.11795787527541246}
{'object':  'chair',  'confidence':  0.13212954996625334}
{'object':  'diningtable',  'confidence':  0.1899228051957825}
{'object':  'chair',  'confidence':  0.1374235041020961}
{'object':  'chair',  'confidence':  0.1632368686534813}

```

这个场景表示 ONNX 运行时对 CPU 后端执行推理。下一步，我们将移植该代码，使其在基于英特尔 NCS 2 的边缘设备上运行。

### 微小 YOLO·V2 在边缘的物体检测

假设您有一台 Ubuntu 18.04 机器连接到运行最新版本的英特尔 OpenVINO Toolkit 的英特尔 NCS 2 设备，您就可以在边缘执行代码了。否则，按照[文档](https://docs.openvinotoolkit.org/latest/openvino_docs_install_guides_installing_openvino_linux.html)中的步骤配置英特尔 NCS 2 和 OpenVINO Toolkit。

如果你有一个正方 AI 视觉 X 套件，你可以在本教程中使用它。

即使你没有安装完整的 OpenVINO 工具包，也要确保你根据[参考](https://docs.openvinotoolkit.org/latest/_docs_install_guides_installing_openvino_linux.html#additional-NCS-steps)在主机上安装了无数的 NCS 规则驱动程序。

微软已经为主流环境提供了 [Docker 镜像和 Docker 文件](https://github.com/microsoft/onnxruntime/tree/master/dockerfiles)。让我们从用 Myriad 下载 OpenVINO Toolkit 的容器映像开始。

```
docker pull mcr.microsoft.com/azureml/onnxruntime:latest-openvino-myriad

```

在 Ubuntu 电脑上创建一个目录`tinyyolo`，然后从你的电脑上复制文件。您的目录应该包含以下文件:

`infer.py`

`requirements.txt`

`labels.txt`

`TinyYOLO.onnx`

在我们执行代码之前，让我们添加一行代码，告诉 ONNX 运行时英特尔 NCS 设备的存在。

打开`infer.py`，在创建推理会话变量之前添加下面一行。

```
rt.capi._pybind_state.set_openvino_device("MYRIAD_FP16")

```

我们将基于 Myriad 设备在 Docker 容器中运行推理代码。

让我们通过映射`/dev`目录并挂载`tinyyolo`目录来启动 Docker 容器。我们还需要添加`--privileged`和`--network host`标志来提供访问摄像机和 NCS USB 设备的适当权限。

在`tinyyolo`目录中，执行下面的命令:

```
docker run  \
--privileged  \
-v  /dev:/dev  \
-v  $PWD:/tinyyolo  \
--network host  \
-it  --rm mcr.microsoft.com/azureml/onnxruntime:latest-openvino-myriad  /bin/bash

```

进入 shell 后，让我们进入目录，安装先决条件。

```
cd  /tinyyolo
pip install  -r  requirements.txt

```

执行代码，查看终端中的推理输出。

图表加载和预热可能需要几分钟时间。现在，您应该可以在终端中看到摄像机检测到的对象。

这个场景可以很容易地扩展到将推理输出发布到本地或云中配置的 MQTT 通道。参考我之前的 [AIoT 教程](https://thenewstack.io/how-i-built-an-aiot-project-with-intel-ai-vision-x-developer-kit-and-arduino-yun/)和这个用例的一个[视频演示](https://thenewstack.io/tns-demo-get-started-with-machine-learning-at-the-edge/)。

*贾纳基拉姆·MSV 的网络研讨会系列“机器智能和现代基础设施(MI2)”提供了涵盖前沿技术的信息丰富、见解深刻的会议。在 [http://mi2.live](http://mi2.live) 注册参加即将举行的 MI2 网络研讨会。*

由来自 Pixabay 的 Robert Balog 拍摄的特写图像，

目前，新堆栈不允许直接在该网站上发表评论。我们邀请所有希望讨论某个故事的读者通过推特或脸书与我们联系。我们也欢迎您通过电子邮件发送新闻提示和反馈:[feedback @ thenewstack . io](mailto:feedback@thenewstack.io)。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>