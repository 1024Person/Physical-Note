# 农药网数据爬取

## selenium使用

### 1、基本流程

1. 下载chromedriver.exe，放置到项目目录下
2. 将chromedriver.exe放置到python解释器的同级路径下
3. 编码

```python
# 导入驱动
from selenium import webdriver
# 导入“依据”方式
from selenium.webdriver.common.by import By

# 初始话浏览器
browser = webdirver.Chrome()
# 网址以及请求
url = "http://www.icama.org.cn/hysj/index.jhtml"
browser.get(url=url)
```

### 2、查找某一个元素

**find_element以及find_elements_*() **系列函数

这个使用的原理如下

```python
next_page = browser.find_element(
   by=By.XPATH,#依据.XPATH语法
   value='/html/body/div[2]/div/ul/li[12]/a', # 这个是Xpath定位语句
)
```

像这种定位的用好这一个find函数就行了





### 问题 ：网页的动态加载问题

网页的动态加载方式分为两种，

1. 向服务器请求json数据包
2. 嵌入iframe框架

上面两种方式的共同点就是都是通过js代码来，但是第一种方法，我们很好办，找到那个json包，分析参数就行了，但是第二种方法并不会返回json数据包，我们需要通过selenium来加载frame中的内容，关键代码如下

```python
browser.switch_to.frame('iframepage')# iframepage是iframe的id，这个参数看具体情况
```

**核心就是：switch_to.frame方法**

### 问题：刷新页面之后，无法定位

刷新操作就相当于重新请求一次网址

```python
browser.get(url)
```

**那么这个时候，我们的定位又回到外层body里面了，所以，我们需要重新定位到iframe中**

```python
browser.switch_to.frame('iframepage')# iframepage是iframe的id，这个参数看具体情况
```

### 问题：“下一页”不管用

“下一页”这个按钮，在很多时候，可以一直点，但是，这个网站在“第7页”的时候，“下一页”按钮消失了，解决办法就是刷新页面，然后重新定位进frame里面，直接点击“第8页”，之后，“下一页”按钮就可以正常点击了。

### 问题：同一元素的xpath定位语法不一样

这个问题并不是针对于selenium出的问题，是针对网站设计的问题。

如下

- 第八页之前

  <img src="C:\Users\ASUS\Desktop\编码\中国农药网爬取\image-20220407171237676.png" alt="image-20220407171237676" style="zoom:67%;" />![image-20220407171145892](C:\Users\ASUS\Desktop\编码\中国农药网爬取\image-20220407171145892.png)

- 第八页之后

![image-20220407171145892](C:\Users\ASUS\Desktop\编码\中国农药网爬取\image-20220407171145892.png)

上面两种情况可以看出来，第八页之后，下面的按钮数变多了，所以，下一页的xpath定位也变了，这个在以后翻页的时候要注意，当然如果是request通过自己构造的url来请求的话，就完全不需要注意这个了



## BeautifulSoup的使用

### 1、构造

首先要构造一个BeautifulSoup对象

```python
from bs4 import BeautifulSoup

# 准备要解析的网页源码
page_source = browser.page_source
# 构造BeautifulSoup对象，这里要指明解析器
soup = BeautifulSoup(page_source,'lxml')
```

### 2、定位

主要通过一个方法就行了

```python
soup.select('select')# 参数用的Query查询语法，就和pyquery这个包里面用到的语法一样
```

### 3、获取内容

这里就说一下这个项目用到的，没用到的不说

```python
tag.get_text()# 获取当前节点以及当前节点下面所有的子孙节点的文本
tag.string	# 获取当前节点的文本，子孙节点的文本不获取
```



## CSV文件保存

### 1、构造

首先需要构造一个**writer**对象

```python
# 导包
import csv
# 数据源
data=[[....],[...],[...],...]
# 打开文件
with open('csv数据.csv','w',encoding='utf_8_sig',newline='') as f:
   writer = csv.writer(f,delimiter=',')
```

### 2、写入

写入有两个方法

```python
writer.writerows(data) # 写入多行数据 
writer.writerow(data) # 写入一行数据
```

### 问题：乱码

打开文件编码问题,解决办法：

> encoding='utf_8_sig'

### 问题：每行之间存在一个空行

解决办法：

打开文件的时候，设置**newline**这个参数

```python
with open(filename,'w',encoding='utf_8_sig',newline='') as f:
   pass
```

## 最后，做一只文明的爬虫

- 不要爬取的数据太多
- 不要爬取的速度太快
- 尽量不要爬良心网站
- **党和政府**的网站更加不能爬



