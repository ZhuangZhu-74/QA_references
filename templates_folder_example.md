### 通过在 `模板` 文件夹放置模板实现快速创建脚本文件（以 bash 为例）

#### 模板文件夹位置和作用

- 模板文件夹通常是 `~/Templates`。
- 当你将自定义好的模板文件放在该文件夹下后，在图形界面点击右键菜单 `New Document` 展开子菜单即可看到它们。
- 当然，你也可以在 `~/.bashrc` 中定义函数来实现终端创建。

#### 模板的作用

- 节省重复工作。

#### 我自己定义的 `bash` 脚本模板：

```
#!/bin/bash
#
# 关于该文件的描述：

# set 设置，主要用于调试，具体解析详见：http://www.ruanyifeng.com/blog/2017/11/bash-set.html
set -e
set -u
set -o pipefail
set -x

##############################
# 命令行传参错误时调用

function usage(){
  echo 'usage: '
  exit
}

# 定义不同类型的错误，增加主代码部分的易读性：

function error_foldernotexist(){
  # $1 为 文件夹
  echo 'folder $1 not found'
  exit 2
}
```

> 关于 `bash` 脚本的第一行到底是用 `#!/bin/bash`（或 `#!/usr/bin/bash`） 还是用 `#!/usr/bin/env bash`
> 是存在争议的，具体可以使用 `bing` 搜索国际版查看相关结果。


#### 更多相关文章：

1. [完善的 Bash 脚本的最简单形式（英文）](https://betterdev.blog/minimal-safe-bash-script-template/)

> 来源于 [科技爱好者周刊（第 139 期）](http://www.ruanyifeng.com/blog/2020/12/weekly-issue-139.html)
文章部分 -> 8 

