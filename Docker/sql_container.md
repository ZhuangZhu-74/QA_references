### 接下来的步骤展示了将docker主机的sql文件（来源于《SQL学习指南》的资料）导入到docker容器的数据库。

#### 1. 创建容器

```
docker container run -d -p 3306:3306 --name 'learnsql' -e MYSQL_ROOT_PASSWORD=123456 mysql:5.7
```

#### 2. docker cp 将 sql 文件复制到容器 /tmp 下

```
docker container cp ./Desktop/LearningSQLExample.sql learnsql:/tmp/
```

#### 3. 使用 mysql 连接到后台运行的容器中。

```
docker container exec -it learnsql mysql -u root -p
```

#### 4.1 进入容器，执行创建数据库命令

```
create database learn;
```

#### 4.2 进入数据库

```
use learn;
```

#### 4.3 导入sql文件

```
source /tmp/LearningSQLExample.sql
```

#### 4.4 退出mysql cli

```
\q;
```

#### 5 查看容器 learnsql mount -> volume 路径

> 可采用的方式 go template; grep; json:jq; 

```
docker inspect -f '{{range .Mounts}}{{.Source}}{{end}}' learnsql learnsql
```
或者
```
docker inspect -f '{{json .Mounts}}' learnsql |grep -Po "(?<=Source\":\").+?(?=\")"
```

> 6.TODO 创建软连接到方便的位置，然后用于其他容器的挂载。
