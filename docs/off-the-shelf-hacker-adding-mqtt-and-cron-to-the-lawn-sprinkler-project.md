# 现成的黑客:将 MQTT 和 Cron 添加到草坪洒水项目中

> 原文：<https://thenewstack.io/off-the-shelf-hacker-adding-mqtt-and-cron-to-the-lawn-sprinkler-project/>

本周我们将继续建造自动喷水灭火系统的旅程。该项目强调了现成的黑客将在他们构建的系统中面临的关键设计和实现概念。

虽然我们可以直接在独立的 Arduino 上为每个独立的喷头编程开/关时间，但联网方法有几个好处。网络允许设备之间的交互，因此它们可以一起完成事情，也许是跨越很远的距离。此外，支持网络的 Arduino 克隆产品，如 [NodeMCU 板](https://www.banggood.com/3Pcs-NodeMcu-Lua-WIFI-Internet-Things-Development-Board-Based-ESP8266-CP2102-Wireless-Module-p-1121409.html?rmmds=search&cur_warehouse=CN)几乎和普通的老式非网络 Arduino 一样便宜。不妨利用它们。还有大量的库和示例程序，您可以在最初的基本概念验证冲刺中加以利用。无需从头开始创建所有代码。

在我们的例子中，我们使用 node MCU/中继板作为边缘设备。它的程序和物理空间有限。它也很便宜，而且只有几个零件，这使得它在车库里非常坚固耐用。我的钻机使用 NodeMCU 作为中继控制器，并接收来自“更智能”的 Raspberry Pi 的命令，该命令将管理洒水器调度、分析以及与生产线上其他系统的交互。

你如何让小工具互相交谈？我使用的是 [MQTT](http://mqtt.org/) 消息协议。让我们大致了解一下为什么以及如何使用 MQTT 进行喷水控制。node MCU/中继板的代码稍后会出现。

## 为什么使用 MQTT？

对于网络化物理计算和物联网(IoT)项目，MQTT 是一个很好的通信模型，因为它简单、可靠、轻量级。它也是主流，是为工业环境设计的。早在 2018 年 1 月，我就写过关于在可穿戴设备上使用[MQTT](https://thenewstack.io/off-shelf-hacker-run-mqtt-wearable/)的文章。一般安装说明在该文章中。为了这个项目，我在头骨赫德利上安装了 MQTT，而不是会议徽章。如今，MQTT 代理和客户机应用程序是我所有 Linux 设备的标准组件。

自动喷水灭火系统由两个基本组件和几个可选组件组成。为了方便起见，MQTT 代理驻留在赫德利。在某个时候，代理将被转移到一个专用的 Raspberry Pi 服务器或云上。每当赫德利启动时，MQTT 就会自动启动。MQTT 客户端驻留在 node MCU/中继板设备上，并作为 Arduino 代码的一部分嵌入。

我们还可以在另一台 Linux 机器上安装一个可选的客户端，比如我的华硕笔记本。我安装了整个 MQTT 包，其中包括客户端和代理部分。我用笔记本做测试。

喷水灭火系统的控制思想是使用 MQTT 向 NodeMCU 发送数据，并打开或关闭继电器。一旦代理在赫德利上运行，我们可以简单地从笔记本中用下面的命令行发送数据到一个主题。

```
drtorq-laptop%  mosquitto_pub  -h  192.168.1.107  -t  inTopic  -m  1

```

这个特殊的组合开启了继电器#1。192.168.1.107 是 MQTT 代理(位于赫德利)的本地网络地址。

一旦通过代理向 NodeMCU/relay 手动发送数据确认了功能，我们就可以使用 cron 来自动化这个过程。

## 用 cron 触发继电器

[Cron](https://en.wikipedia.org/wiki/Cron) 是一个用于调度自动化程序执行的原生 Linux 程序。传统上，Unix/Linux 系统管理任务，如运行夜间数据备份过程，是由 cron 管理的。用你想要的程序执行时间建立一个简单的文本文件，当时间到了，程序就会运行。使用 cron，您几乎可以自动化任何任务。

为了进行测试，我输入了几个洒水喷头的开始和停止时间，并使用 mosquitto_pub 命令，通过-m (message)选项索引相应的 NodeMCU/relay。发送“1”开启#1 继电器。“8”键打开#8 继电器，依此类推。发送“0”会关闭所有继电器。虽然我们可以一次打开多个继电器，但 NodeMCU 的小电压调节器只能在过热前为几个继电器提供足够的电力。在设计你的小工具时，要注意电源需求以及它们对硬件组件的影响。

为了验证概念，我在我的华硕 Linux 笔记本上使用了 cron。你可以很容易地在骷髅赫德利、蒸汽朋克会议徽章或你网络上的任何其他 Linux 机器上设置 cron 表。记住，我们正在赫德利上运行 MQTT 代理。如果需要，您甚至可以在与代理相同的机器上使用 MQTT 客户机。只需打开一个终端，键入一个 mosquitto_pub/mosquitto_sub 命令。只要设备通电并连接到网络，一切都会正常工作。

省去一些麻烦，使用传统的“crontab -e”命令来编辑 cron 表。

对表格进行编辑，然后使用“Ctrl-o”和 Ctrl-x”退出。保存文件并退出 crontab 后，cron 守护程序将自动重启。如果不重新启动守护进程，您的文件将永远不会运行。遗憾的是，在我做 Unix 系统管理员的时候，我花了很长时间才搞清楚最后一点。当时我还没有一个小的 crontab -e 脚本。

这是我在 Linux 笔记本上的 cron 表。

```
SHELL=/bin/bash
MAILTO=doc@drtorq.com
PATH=/bin:/sbin:/usr/bin:/usr/sbin:/usr/local/bin:/usr/local/sbin
#
# Each line contains the date/time followed by the command and any options
# note: the user-name defaults to your login user.
#
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name  command to be executed
#
# run the mosquitto_pub commands
# 
30  07  *  *  *  mosquitto_pub  -h  192.168.1.107  -t  inTopic  -m  8
30  09  *  *  *  mosquitto_pub  -h  192.168.1.107  -t  inTopic  -m  0
45  09  *  *  *  mosquitto_pub  -h  192.168.1.107  -t  inTopic  -m  2
30  10  *  *  *  mosquitto_pub  -h  192.168.1.107  -t  inTopic  -m  0

```

## NodeMCU 代码

我们的 NodeMCU 设备的代码非常简单。我用 Arduino IDE 的 1.8.7 版本把它从我的 Linux 笔记本上传到 NodeMCU 板上。

```
/*
 Basic ESP8266 MQTT example
*/

#include 
#include 

// Update these with values suitable for your network.

const char*  ssid  =  "my-local-ap";
const char*  password  =  "falala-lala";
const char*  mqtt_server  =  "192.168.1.107";

WiFiClient espClient;
PubSubClient client(espClient);
long lastMsg  =  0;
char msg[50];
int value  =  0;

```

```
void setup_wifi()  {

  delay(10);
  // Connect to a WiFi network
  Serial.println();
  Serial.print("Connecting to ");
  Serial.println(ssid);

  WiFi.begin(ssid,  password);

  while  (WiFi.status()  !=  WL_CONNECTED)  {
    delay(500);
    Serial.print(".");
  }

  randomSeed(micros());

  Serial.println("");
  Serial.println("WiFi connected");
  Serial.println("IP address: ");
  Serial.println(WiFi.localIP());
}

```

```
void callback(char*  topic,  byte*  payload,  unsigned int length)  {
  Serial.print("Message arrived [");
  Serial.print(topic);
  Serial.print("] ");
  for  (int  i  =  0;  i  &lt;  length;  i++)  {
    Serial.print((char)payload[i]);
  }
  Serial.println();

  // Switch on the LED if an 1 was received as first character
  if  ((char)payload[0]  ==  '1')  {
    digitalWrite(16,  LOW);  
  }  
  else if((char)payload[0]  ==  '2')  {
    digitalWrite(5,  LOW);
  }  
  else if((char)payload[0]  ==  '3')  {
    digitalWrite(4,  LOW);  
  }  
  else if((char)payload[0]  ==  '4')  {
    digitalWrite(0,  LOW);
  }  
  else if((char)payload[0]  ==  '5')  {
    digitalWrite(2,  LOW);  
  }
  else if((char)payload[0]  ==  '6')  {
    digitalWrite(14,  LOW);  
  }
  else if((char)payload[0]  ==  '7')  {
    digitalWrite(12,  LOW);  
  }
  else if((char)payload[0]  ==  '8')  {
    digitalWrite(13,  LOW);  
  }
  else  {
    digitalWrite(16,  HIGH);
    digitalWrite(5,  HIGH);
    digitalWrite(4,  HIGH);
    digitalWrite(0,  HIGH);
    digitalWrite(2,  HIGH);
    digitalWrite(14,  HIGH);
    digitalWrite(12,  HIGH);
    digitalWrite(13,  HIGH);
  }

}

```

```
void reconnect()  {
  // Loop until we're reconnected
  while  (!client.connected())  {
    Serial.print("Attempting MQTT connection...");
    // Create a random client ID
    String clientId  =  "ESP8266Client-";
    clientId  +=  String(random(0xffff),  HEX);
    // Attempt to connect
    if  (client.connect(clientId.c_str()))  {
      Serial.println("connected");
      // Once connected, publish an announcement...
      client.publish("outTopic",  "hello world");
      // ... and resubscribe
      client.subscribe("inTopic");
    }  else  {
      Serial.print("failed, rc=");
      Serial.print(client.state());
      Serial.println(" try again in 5 seconds");
      // Wait 5 seconds before retrying
      delay(5000);
    }
  }
}

```

```
void setup()  {
  pinMode(16,  OUTPUT); // Initialize the BUILTIN_LED pin as an output
  pinMode(5,  OUTPUT);
  pinMode(4,  OUTPUT);
  pinMode(0,  OUTPUT);
  pinMode(2,  OUTPUT);
  pinMode(14,  OUTPUT);
  pinMode(12,  OUTPUT);
  pinMode(13,  OUTPUT);

  digitalWrite(16,  HIGH);
  digitalWrite(5,  HIGH);
  digitalWrite(4,  HIGH);
  digitalWrite(0,  HIGH);
  digitalWrite(2,  HIGH);
  digitalWrite(14,  HIGH);
  digitalWrite(12,  HIGH);
  digitalWrite(13,  HIGH);

  Serial.begin(115200);
  setup_wifi();
  client.setServer(mqtt_server,  1883);
  client.setCallback(callback);
}

void loop()  {

  if  (!client.connected())  {
    reconnect();
  }
  client.loop();

  long now  =  millis();
  if  (now  -  lastMsg  &gt;  2000)  {
    lastMsg  =  now;
    ++value;
    snprintf  (msg,  50,  "hello world #%ld",  value);
    Serial.print("Publish message: ");
    Serial.println(msg);
    client.publish("outTopic",  msg);
  }
}

```

我们进行通常的初始化，包括网络和 MQTT 库。

回调部分是所有代码/物理操作发生的地方，从 MQTT 代理获取消息，并根据需要打开/关闭中继。请注意，每当我们得到“0”时，我会关闭所有继电器这有助于限制一次只能打开一个继电器。

我们还会在设置阶段关闭所有继电器。我注意到，每当 NodeMCU 加电时，它都会默认打开所有的继电器。只要添加一点代码，问题就解决了。

一些串行打印语句在整个代码中都是可见的。一旦一切都稳定和幸福，这些都可以被移除。

## 下一步是什么

为了与行业惯例保持一致，安全性是这个概念验证的一个补充。显然，如果这将是一个商业系统，这个主题将需要相当大的关注。现在，设置将驻留在我的网络防火墙后面。如果有一天我回到家，发现所有的洒水器都在同时运行，我可能会有更大的问题。

添加一些默认行为可能是有意义的，比如在一段设定的时间后关闭所有中继，而不管来自 MQTT 代理的数据。这类似于[“看门狗定时器”](https://en.wikipedia.org/wiki/Watchdog_timer)，如果正在运行的程序中出现重大错误，它将重置处理器。虽然 MQTT 消息的传递非常可靠，但我们仍然必须考虑丢失消息的情况。如果 NodeMCU 没有收到消息或出现错误，我们当然不希望一个喷头(或所有喷头)连续运行 72 小时。切断电路板、继电器和螺线管的电源可能是一条出路。这就是所谓的[“死亡开关”](https://en.wikipedia.org/wiki/Dead_man%27s_switch)

另一个想法是从院子里收集一些数据，比如读取雨量计，并将其发送到我们的物理计算堆栈链进行分析。该功能很容易添加到 NodeMCU/relay Arduino 代码中，以及 Raspberry Pi 上的一些传感器和分析程序中。

通过 Pixabay 的特征图像。

<svg xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 68 31" version="1.1"><title>Group</title> <desc>Created with Sketch.</desc></svg>