要在Linux上安装Yapi，您需要先安装Docker。以下是在Linux上安装Yapi的步骤：

1. 安装Docker

您可以使用以下命令安装Docker：

sudo apt-get update
sudo apt-get install docker.io

2. 创建Yapi容器

在安装Docker之后，您可以使用以下命令创建Yapi容器：

sudo docker run -d \
--name yapi \
-p 3000:3000 \
--restart=always \
-e TZ=Asia/Shanghai \
-e LANG=en_US.UTF-8 \
-e LANGUAGE=en_US.UTF-8 \
-e LC_ALL=en_US.UTF-8 \
-v /data/yapi/mongo:/data/db \
-v /data/yapi/config.json:/app/config.json \
registry.cn-hangzhou.aliyuncs.com/xiaoyu-yu/yapi

在上述命令中，我们使用了阿里云Docker镜像，您也可以使用其他Docker镜像。

3. 访问Yapi

在容器创建后，您可以通过访问http://your_ip_address:3000来访问Yapi。

以上是在Linux上安装Yapi的步骤。请注意，您需要在安装之前确保您的系统满足Yapi的要求。
