# drone-ci-compose

使用`docker-compose`搭建一个简单的`gogs + drone`的CI服务节点。

## 部署步骤

* [安装docker - Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

```bash
sudo apt-get update

sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

# 安装
sudo apt-get install docker-ce

# 测试安装结果
sudo docker run hello-world
# 输出 Hello from Docker!
```


* [安装docker-compose]

```bash
export LATEST_DOCKER_COMPOSE=1.22.0
sudo curl -L https://github.com/docker/compose/releases/download/${LATEST_DOCKER_COMPOSE}/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

* [创建docker实例启动服务]

```bash
# 在本目录下打开命令窗口，输入以下命令 （默认配置配置文件为当前目录下的 docker-compose.yml文件
sudo docker-compose up -d
```

* [初始化设置]
  
  打开http://localhost:3000，设置默认数据库为SQLite3，然后其他配置项默认设置。配置好后，注册一个gogs账户。
  打开http://localhost:8000, 可以查看drone CI（一个go语言写的持续集成工具）的管理界面，暂不需要配置。
