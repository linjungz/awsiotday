## 目标
- 通过AWS IoT服务将一个模拟设备接入AWS IoT，通过模拟设备向AWS IoT云端发送传感器数据，利用AWS IoT Shadow来进行设备状态的控制和对传感器数据进行实时展示.

## 内容框架
### AWS IoT 基本功能

#### [Lab0:实验环境准备](iot-connect/00_cloud9.md)
在这个实验中我们将会演示如何启动Cloud9 Web IDE环境，后续实验会以此实例运行相应的python脚本，以模拟IoT设备行为。

#### [Lab1:IoT接入与消息发送](iot-connect/01_connect_publish.md)
在这个实验中我们将演示如何创建一个IoT Thing并将模拟设备接入AWS IoT，通过模拟设备向AWS IoT云端发送传感器数据

#### [Lab2:设备状态控制](iot-connect/02_control.md)
在这个实验中我们将演示如何利用AWS IoT Shadow来进行设备状态的控制

#### [Lab3:数据实时展示](iot-connect/03_data_visualize.md)
在这个实验中我们将演示如何将AWS IoT云端收集到的传感器数据通过Rule Engine保存至ElasticSearch中，并利用Kibana进行实时展现