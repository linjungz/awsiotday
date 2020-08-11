# 基于AWS Kinesis Video Stream动手搭建云Camera
基于AWS KVS构建云Camera的演示环境，并作为IoT Builder's Day的动手实验材料

## 目标
- 此实验基于ubuntu模拟camera设备,读取本地视频文件向Kinesis Video Stream推流 , media-viewer提供web演示播放视频流。
- 操作文档与界面截图均为中文

### 内容框架

### AWS KVS 基本功能

#### [Lab0:创建新用户](kvs/docs/00_create_user.md)
在这个实验中我们将会演示如何创建新用户，后续会以此用户的Access Key和Secret Key用于后续shell脚本以及web的输入参数。

#### [Lab1:创建Kinesis Video Stream视频流](kvs/docs/01_create_kvs_stream.md)
创建一路视频流用于后续推流和拉流

#### [Lab2:创建Ubuntu实例](kvs/docs/02_create_ubuntu_instance.md)
创建一个带弹性IP的ubuntu实例

#### [Lab3:安装KVS运行环境](kvs/docs/03_install_kvs_environment.md)
安装KVS环境并推流到Kinesis Video Stream

#### [Lab4:播放演示](kvs/docs/04_viewer_play.md)
演示从Kinesis Video Stream拉流播放





 



 

 



 

 