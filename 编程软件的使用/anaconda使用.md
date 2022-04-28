# anaconda的使用教程

## 1、命令行运行环境

![image-20220402231629643](C:\Users\ASUS\Desktop\编码\编程软件的使用\image-20220402231629643.png)

## 2、查看所有环境、创建环境以及激活环境

- 查看所有环境

  ```bash
  conda info --envs
  ```

- 创建环境

  ```bash
  conda create --name 环境名字 python=[版本号] [包名]
  ```

- 激活环境

  ```python
  activate 环境名字
  ```

  

- 退出环境

  ```bash
  deactivate
  ```

  

- 复制环境

  ```bash
  conda create -n （复制之后的）环境名称 --clone （被复制的）环境名称
  ```

  

- 删除环境

  ```bash
  conda env remove -n 环境名称
  ```

  

  

## 3、管理包

- 查看已经安装的包

  ```bash
  conda list
  ```

- 查找一个包

  ```bash
  conda search 包名
  ```

  

- 安装一个新包

  ```bash
  conda install --name 包名
  ```

  

- 移除包

  ```bash
  conda remove -n 包名
  ```

## 4、anaconda和vscode配合使用

![image-20220402233747789](C:\Users\ASUS\Desktop\编码\编程软件的使用\image-20220402233747789.png)

点击右下角圈出来的

![image-20220402233831663](C:\Users\ASUS\Desktop\编码\编程软件的使用\image-20220402233831663.png)

选一个环境

然后，运行的时候，直接点击那个运行的那个三角形，不要从下拉菜单里面去选。

## 5、conda报错：Solving environment: failed with initial frozen solve. Retrying with flexibl



[参考网址](https://blog.csdn.net/weixin_45552562/article/details/109668589)

这个还是比较靠谱的，网上就会胡咧咧，

## 6、pip和conda的关系

在conda的环境下面最好还是用conda进行安装包，实在不行的时候，再用pip进行安装，并且pip安装的包也是在当前环境下面的，这个不用担心，因为在当前环境下使用pip命令就是当前环境（文件夹）下面的pip，所以安装就是安装在了当前环境下面了。



## 7、jupyter指定python解释器

1. 切换环境（想要用哪一个解释器，就切换到那个环境里面）

2. 安装包`ipykernel`，这里使用清华园就行（关闭加速器）

   清华源镜像网址：

   ​		https://pypi.tuna.tsinghua.edu.cn/simple

   命令：

   ```python
   pip install -i https://pypi.tuna.tsinghua.edu.cn/simple package_name
   ```

3. 使用下面命令为juypter notebook添加解释器

   1、简易版本

   ```python
   python -m ipykernel install --name environment_name
   ```

   2、完整版本

   ```python
   python -m ipykernel install --user --name 虚拟环境名 --display-name 在jupyter中显示的名称
   ```

4. 从juypter notebook中移除python解释器

   ```python
   jupyter kernelspec remove 名称
   ```

   

