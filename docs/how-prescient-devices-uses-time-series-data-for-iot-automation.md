# 预见性设备如何将时序数据用于物联网自动化

> 原文：<https://thenewstack.io/how-prescient-devices-uses-time-series-data-for-iot-automation/>

随着机器上的传感器收集越来越多的数据，工业过程变得越来越自动化。这些数据中的大部分都有[的时间戳](https://www.influxdata.com/what-is-time-series-data/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-11_spnsr-ctn_prescient-devices_tns)，可以帮助公司改进流程。如果公司管理不当，这些大量的[传感器数据](https://www.influxdata.com/sensor-data-is-time-series-data/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-11_spnsr-ctn_prescient-devices_tns)会变得难以处理。

公司需要能够处理时间序列数据的生命周期，从实时分析到历史数据的下采样。许多公司使用专门构建的数据管理工具和产品来帮助解决这一问题。

[有先见之明的设备](https://www.prescientdevices.com)构建了一个工业物联网( [IoT](https://thenewstack.io/managing-time-series-data-in-industrial-iot/) )数据管理平台，由 InfluxDB 提供支持，帮助公司构建应用程序来快速轻松地管理边缘设备。

## 连接边缘和云

Prescient Devices 创建了 Prescient Designer，这是一个帮助企业管理分布式边缘设备的 SaaS 平台。它有一个用户安装在边缘设备上的代理和一个用户构建和实现应用程序的界面。InfluxDB 是 Prescient Designer 的主干，处理带时间戳的数据。

Prescient Devices 使用 Node-RED 构建了该平台，Node-RED 是一个开源项目，具有低代码的可视化界面。Prescient Designer 还使用 InfluxDB Cloud、TensorFlow 和 Grafana，并可以与公司需要的其他工具集成。

预知边缘是预知设备的边缘管理软件。它使用了 [Node-RED](https://thenewstack.io/node-red-hits-1-0-looks-to-a-serverless-microservices-future/) 、InfluxDB OSS、TensorFlow 和一个运行时系统。预见性边缘部署可以包括用户在预见性设计器中构建的应用程序。来自边缘设备的数据有多种格式。Prescient Devices 使用户能够收集各种传感器数据，如温度、湿度和加速度，以及来自摄像头、API 和工业设备的数据。

数据以两个单独的流进入 Prescient Designer，一个用于用户数据，另一个用于应用程序管理和部署数据。预知设备包括一个代理，用于连接预知设计器和运行预知边缘的设备。

如果用户需要 HIPAA 或 GDPR 等合规性要求的支持，他们的系统还支持定制代理。对于数据可视化，Prescient Designer 利用 Grafana 仪表板为用户提供对其应用程序的实时洞察。

## 低代码框架

预见性设计器基于 Node-RED，允许用户使用最少的代码创建应用程序。这降低了进入门槛，使公司更容易快速开发应用程序和解决方案。

这种方法还使公司能够让非开发人员的主题专家更直接地参与构建应用程序。因此，数据工程师、系统集成商和其他创新者等关键利益相关者都可以使用有先见之明的设备来构建更好的边缘到云数据解决方案，而不必是经验丰富的编码人员。Prescient Designer 的可视工作区还让用户可以在一个地方查看整个系统。

## 节省时间

Prescient Devices 帮助解决的两个关键数据问题是规模和速度。物联网环境拥有来自数百台设备的海量数据，每台设备都处理大量数据。公司需要考虑如何快速地将边缘应用程序投入运行并更新它们，以及如何快速地处理输入数据。

有先见之明的设备最初使用 [Telegraf](https://www.influxdata.com/time-series-platform/telegraf/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-11_spnsr-ctn_prescient-devices_tns) ，InfluxData 的开源插件驱动的代理来收集指标，以收集和处理来自边缘设备的数据。他们最终选择使用 InfluxDB 云作为他们的[时间序列数据库](https://www.influxdata.com/the-best-way-to-store-collect-analyze-time-series-data/?utm_source=vendor&utm_medium=referral&utm_campaign=2022-11_spnsr-ctn_prescient-devices_tns)，因为它支持 Node-RED，并且在资源有限的边缘设备上运行良好。许多 Prescient Devices 的客户已经使用了 InfluxDB，并明确要求在平台中支持 InfluxDB。

有先见之明的设计师让物联网公司快速创建分布式系统。用户可以在几周内构建应用程序，并在几小时到几秒内更新和部署对这些应用程序的更改。因为用户可以在可视化界面中构建应用程序，所以专家即使不是开发人员也可以构建应用程序。这使得物联网制造商能够快速自动化他们的系统，并从他们的数据中获得更好的洞察力。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>