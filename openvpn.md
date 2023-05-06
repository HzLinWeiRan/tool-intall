1. 安装 docker

在 Linux 系统上，可以通过以下命令安装 Docker：

```
sudo apt-get update
sudo apt-get install docker.io
```

2. 下载 OpenVPN 镜像

可以从 Docker Hub 上下载 OpenVPN 镜像：

```
docker pull kylemanna/openvpn
```

3. 创建 OpenVPN 容器

可以通过以下命令创建 OpenVPN 容器：

```
docker run -v /path/to/config:/etc/openvpn --rm -it kylemanna/openvpn ovpn_genconfig -u udp://VPN.SERVERNAME.COM
```

其中，/path/to/config 是配置文件的存放路径，VPN.SERVERNAME.COM 是 VPN 服务器的域名或 IP 地址。

4. 生成证书和密钥

可以通过以下命令生成证书和密钥：

```
docker run -v /path/to/config:/etc/openvpn --rm -it kylemanna/openvpn ovpn_initpki
```

5. 启动 OpenVPN 容器

可以通过以下命令启动 OpenVPN 容器：

```
docker run -v /path/to/config:/etc/openvpn -d -p 1194:1194/udp --cap-add=NET_ADMIN kylemanna/openvpn
```

其中，/path/to/config 是配置文件的存放路径。

```
docker run -v /path/to/config:/etc/openvpn --rm -it kylemanna/openvpn easyrsa build-client-full test nopass
docker run -v /path/to/config:/etc/openvpn --rm kylemanna/openvpn ovpn_getclient test > /tmp/test.ovpn
```

6. 安装 OpenVPN 客户端

在客户端上安装 OpenVPN 客户端，并使用生成的证书和密钥连接到 VPN 服务器。
