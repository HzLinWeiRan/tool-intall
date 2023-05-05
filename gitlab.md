以下是在 Linux Docker 中安装 GitLab 的步骤：

1. 安装 Docker

首先，您需要在 Linux 系统上安装 Docker。请按照以下步骤安装 Docker：

- 在 Linux 中打开终端。
- 运行以下命令以安装 Docker：

```
sudo apt-get update
sudo apt-get install docker.io
```

- 运行以下命令以启动 Docker 服务：

```
sudo systemctl start docker
sudo systemctl enable docker
```

2. 下载 GitLab 镜像

接下来，您需要从 Docker Hub 下载 GitLab 镜像。请运行以下命令：

```
sudo docker pull gitlab/gitlab-ce
```

3. 启动 GitLab 容器

现在，您可以使用以下命令启动 GitLab 容器：

```
sudo docker run --detach \
  --hostname gitlab.example.com \
  --publish 443:443 --publish 80:80 --publish 22:22 \
  --name gitlab \
  --restart always \
  --volume /srv/gitlab/config:/etc/gitlab \
  --volume /srv/gitlab/logs:/var/log/gitlab \
  --volume /srv/gitlab/data:/var/opt/gitlab \
  gitlab/gitlab-ce:latest
```

在上面的命令中，您需要将 `gitlab.example.com` 替换为您的 GitLab 主机名，并将 `/srv/gitlab` 替换为您要将 GitLab 数据保存到的目录。

4. 访问 GitLab

现在，您可以通过在 Web 浏览器中输入 `http://<your-server-ip>` 或 `http://<your-domain-name>` 来访问 GitLab。在第一次访问时，您需要设置管理员帐户的用户名和密码。

这就是在 Linux Docker 中安装 GitLab 的步骤。
