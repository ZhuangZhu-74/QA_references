Python3

## 官网
https://www.python.org/

## github

## 下载地址（国外）
https://www.python.org/downloads/

## 镜像源（国内）

## 软件包管理器
[pip](https://pypi.org/)

## 软件包管理器镜像源（国内）
- pip
  - Windows (`用户目录/pip/pip.ini`)
  - Linux (`~/.pip/pip.conf`)

编辑文件，输入以下内容并保存（阿里镜像）
```
[global]
index-url = https://mirrors.aliyun.com/pypi/simple/

[install]
trusted-host=mirrors.aliyun.com
```

- anaconda
  - [tuna](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/)

## 安装
- windows
 - 直接点击安装包，按提示操作即可。
- linux
 - 系统一般自带了python

## 环境变量
`PYTHONPATH`：指向python安装目录

`PATH`：安装目录以及安装目录下的Scripts、Libs文件夹要追加到 `PATH`。

## 其他
自动补全：

a 建议安装`IPython`

b 编辑 `~/.pystartup` 并保存（Linux)

```
import atexit, os, readline, rlcompleter
readline.parse_and_bind('tab:complete')
```
并且还要在`~/.bashrc` 添加 `export PYTHONSTARTUP=~/.pystartup`

pip
```
# 导出依赖包列表
pip freeze > requirements.txt

# 从依赖包列表中安装
pip install -r requirements.txt
```

