### 接下来的步骤展示了在 `fedora:latest` 镜像的基础上安装最新的 `bash5.1` 的过程。

#### 1 运行容器，使用 `fedora:latest` 镜像。

```
docker container run -it --name 'fedora_bash51' fedora:latest
```

#### 2 yum 安装 package

> gcc（bash依赖）

```
yum install -y gcc
```

> 安装 man 和 info （查看帮助手册）

```
yum install -y man info
```

#### 3 下载 ftp 上的 bash 5.1 并安装

> 从官方 ftp 下载压缩包到 /tmp

```
curl --output /tmp/bash-5.1.tar.gz ftp://ftp.gnu.org/gnu/bash/bash-5.1.tar.gz
```

> 解压并进入 bash-5.1 目录，按照官方要求安装

```
cd /tmp
tar -zxf bash-5.1.tar.gz
cd ./bash-5.1
```

> 之后按照官方步骤安装，不再写出。

> http://www.gnu.org/software/bash/manual/html_node/Basic-Installation.html

#### 4 退出容器。

```
exit
```

#### 5 重启容器

```
docker container restart fedora_bash51
```


