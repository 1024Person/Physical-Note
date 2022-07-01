# git命令

> 经常用的那些最最基础的就不说了，只说一些不怎么用的。

## remote

添加远程连接

```base
git remote add (远程连接名字) 仓库链接
```

查看所有的远程仓库链接

```base
git remote -v
```

## config

查看所有配置信息

```bash
git config -l
```

config 命令的基本模式	

```bash
git config [<options>]
```

config的全部命令

<img src="https://cdn.jsdelivr.net/gh/1024Person/pic-raw@main/img/image-20220627202339354.png" alt="image-20220627202339354" style="zoom:50%;" />

<img src="https://cdn.jsdelivr.net/gh/1024Person/pic-raw@main/img/image-20220627202622822.png" alt="image-20220627202622822" style="zoom:50%;" />



## add

![image-20220701182728155](https://cdn.jsdelivr.net/gh/1024Person/pic-raw@main/img/image-20220701182728155.png)

> **子目录**下无法实现全部文件的git add 的操作，必须返回**根目录**进行，重新提交