以下是在 Linux 上安装禅道的步骤：

1. 安装 Docker

在 Linux 上安装 Docker 需要先安装 Docker 的依赖项。请按照以下步骤安装 Docker：

- 安装依赖项：

  ```
  sudo apt-get update
  sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
  ```

- 添加 Docker 的 GPG 密钥：

  ```
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  ```

- 添加 Docker 的 APT 仓库：

  ```
  sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
  ```

- 安装 Docker：

  ```
  sudo apt-get update
  sudo apt-get install docker-ce docker-ce-cli containerd.io
  ```

2. 下载禅道镜像

在 Docker Hub 上搜索禅道镜像，然后使用以下命令下载：

```
docker pull easysoft/zentao
```

3. 运行禅道容器

使用以下命令运行禅道容器：

```
docker run --name zentao -p 80:80 -d easysoft/zentao
```

其中，`--name` 参数指定容器名称，`-p` 参数指定将容器的 80 端口映射到主机的 80 端口，`-d` 参数指定容器在后台运行。

4. 访问禅道

在浏览器中访问 `http://localhost` 或 `http://服务器IP`，就可以看到禅道的登录页面了。默认的管理员账号是 admin，密码是 123456。

注意：如果您使用的是云服务器，需要在安全组中开放 80 端口才能访问禅道。
