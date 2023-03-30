# 使用 Cloudant 构建地理空间应用程序来显示科罗拉多滑雪区

> 原文：<https://thenewstack.io/building-a-geospatial-application-with-cloudant-to-show-colorado-ski-areas/>

编者按:地理数据的使用传统上是地理信息专家的领域。但越来越多的事实证明，地理数据对希望为应用程序添加更深层次功能的开发人员非常有用。这一点在我参加

[Esri User Conference](http://www.esri.com/events/user-conference)

本月初。开发人员正在寻找各种使用地理数据的新方法。但是从我们的角度来看，我们需要更多的例子来说明地理数据是如何增加更多的内容和阐明以前看不到的信息的。Cloudant 在这方面的贡献只是数据库如何用于将地理数据集成到应用程序中的一个例子。我们期待更多突出地理数据项目并为我们所有人提供使用指南的贡献。

这篇文章的目的是为在第三方应用程序中查询和呈现来自 [Cloudant](https://cloudant.com/) 的地理空间数据提供构建模块。具体来说，我们将讨论如何将[传单](http://leafletjs.com/)与 Cloudant 整合，以构建这个[站点](https://normanb.cloudant.com/colorado_skiing/geo/demos/cloudant/index.html)。传单是一个开源的 JavaScript 库，用于移动友好的交互式地图。

[![skiing](img/67ac14ad5aa7ee205c5f17d8ad0a4cce.png)](https://thenewstack.io/wp-content/uploads/2014/07/skiing.png)

### 积木

该网站是使用[传单矢量图层](http://jasonsanford.github.io/leaflet-vector-layers/)和[传单绘图](https://github.com/Leaflet/Leaflet.draw)构建的。你可以在这里找到所有代码。传单矢量图层从地理网络服务提供商(包括 ArcGIS Server、Arc2Earth、CartoDB 和 Geocommons)获取矢量要素。传单绘图是一个矢量绘图和传单编辑插件。

我们使用了来自 [GeoIQ](http://www.geoiq.com/) 的现有数据集，其中包括落基山脉科罗拉多地区滑雪场的 GeoJSON 数据:

```
{

    "type":  "Feature",  

    "id":  11,  

    "properties":  {

        "Name":  "Breckenridge Ski Area",  

        "Status":  "Open",  

        "XCOORD":  -106.079136,  

        "YCOORD":  39.459103

    },  

    "geometry":  {

        "type":  "Point",  

        "coordinates":  [

            -106.07913649885852,  

            39.45910306740733,  

            0

        ]

    }

}

```

将数据更新到 Cloudant 后，通过 Cloudant 管理用户界面创建数据库。(注意:如果你不熟悉 Cloudant，注册并让 support@cloudant.com 知道你想加入地理空间集群。)

[![dashboard](img/b196533713baf23638180ecc0b19efa8.png)](https://thenewstack.io/wp-content/uploads/2014/07/dashboard.png)

我们使用下面的 Cloudant 设计文档将 GeoJSON 索引为 R*Tree 二级空间索引。

```
{

    "_id":  "_design/SpatialView",  

    "indexes":  {

        "ski_areas":  {

            "index":  "function(doc){ if (doc.geometry) { st_index(doc.geometry);}}"

        }

    }

}

```

上面的设计文档是使用 HTTP POST 请求在 Cloudant 中创建的:

```
curl  -X  POST  -d  @designDoc.json https://username:password@cloudant.com/colorado_skiing

  -H  "Content-Type: application/json"

```

我使用了一个简单的 Python 脚本来加载科罗拉多滑雪场剩余的 GeoJSON 要素集合:

```
import json

import requests

headers  =  {"content-type":  "application/json"}

# parse json feature collection

json_data  =  open(areas)

data  =  json.load(json_data)

for feature in data["features"]:

 Id  =  feature["id"]

 # delete feature type and duplicate id

 del feature[“id”]

 requests.post(dbUrl,  data=json.dumps(feature),  headers=headers)

json_data.close()

```

上面的脚本使用 Python 请求来提取 GeoJSON 要素集合，并将其解析为要在 Cloudant 空间索引中索引的单个文档。

包装在传单矢量图层中的 Cloudant Geo OpenSearch API 添加了一个数据源，相当于编辑 index.html 来设置感兴趣的区域。

传单矢量图层将为您的数据提供半径、边界框和多边形查询。

诺曼·巴克是 IBM 公司 Cloudant 的 Geo 总监。10 多年来，他一直在开发地理空间程序，并领导 Cloudant 的分布式地理空间索引的开发。他的主要兴趣是如何使用非结构化的地理空间数据。

通过 Flickr 知识共享[的特色图片。](https://www.flickr.com/photos/80497449@N04/7392329216/in/photolist-cgeBW1-kjyUmp-Fju3G-53Uzwa-b7mPSF-aKQ87x-7iSrs3-bZUzHQ-fuHAbs-dUJJgf-dHsohH-7SoaAB-9cF7zD-8Voph9-9MFBHp-2ffjk-kjzvyM-cBfRrh-8oZXEi-8p48ZU-5Dj8zC-dxKGEX-kjxEoM-3iuW1m-3iquAx-3iv3bf-drZkoK-85GPHs-iGhArd-6oiBZW-83Ryjn-6oi8JA-7HSxoE-7kuBae-m2rwJx-8qrEGA-59ssnf-7jTats-8qmzxN-9tmLxQ-bsohpQ-am3b1c-895Yb8-4RB2dR-h5AKH-68r86Q-eS7Qpx-eSjgtQ-D6Afv-kjBmUu)

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>