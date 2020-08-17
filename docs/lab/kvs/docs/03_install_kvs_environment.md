## Lab3:安装KVS运行环境
```
$ sudo apt-get update

$ sudo apt-get install openjdk-8-jdk
```
```
$ sudo apt-get install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev gstreamer1.0-plugins-base-apps

$ sudo apt-get install gstreamer1.0-plugins-bad gstreamer1.0-plugins-good gstreamer1.0-plugins-ugly   gstreamer1.0-tools
```
```
$ git clone --recursive https://github.com/awslabs/amazon-kinesis-video-streams-producer-sdk-cpp.git
```
```
$ sudo mkdir -p amazon-kinesis-video-streams-producer-sdk-cpp/build

$ cd amazon-kinesis-video-streams-producer-sdk-cpp/build

$ sudo apt install cmake

$ sudo cmake .. -DBUILD_GSTREAMER_PLUGIN=ON -DBUILD_JNI=TRUE
```

```
$ sudo make
```
```
$ sudo apt-get install libssl-dev libcurl4-openssl-dev liblog4cplus-dev libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev gstreamer1.0-plugins-base-apps gstreamer1.0-plugins-bad gstreamer1.0-plugins-good gstreamer1.0-plugins-ugly gstreamer1.0-tools
```

```
$ cd ~

$ sudo vim kvs.sh
```

```
#!/bin/bash

cd ~/amazon-kinesis-video-streams-producer-sdk-cpp

export GST_PLUGIN_PATH=`pwd`/build
export LD_LIBRARY_PATH=`pwd`/open-source/local/lib

echo $GST_PLUGIN_PATH
echo $LD_LIBRARY_PATH

gst-launch-1.0 -v filesrc location=$2 ! qtdemux name=demux ! queue ! h264parse ! video/x-h264,stream-format=avc,alignment=au ! kvssink name=sink stream-name=$1 access-key="<ACCESS-KEY>" secret-key="<SECRET-KEY>" aws-region="ap-southeast-1"

#备注: <ACCESS-KEY> 和 <SECRET-KEY> 请使用之前下载excel中的AK和SK
```
```
$ cat kvs.sh

$ exit
```
```
$ scp -i "sgp-kvs-demo.pem" <客户本地录像文件路径> ubuntu@<EC2公网地址>:~/ 

#Example：scp -i "sgp-kvs-demo.pem" ~/Downloads/Snowflakes.mp4 ubuntu@ec2-xx.ap-southeast-1.compute.amazonaws.com:~/

```
```
$ sudo chmod u+x kvs.sh
$ sudo ./kvs.sh <StreamName> <FileName>

#Example: sudo ./kvs.sh MyStream ~/Snowflakes.mp4

```