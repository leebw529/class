# Markdown  语法

## 标题语法

一级标题 #

二级标题 ##

*

.

.

六级标题 ######

## 字体样式设置

加粗 **加粗文本**  前后两个**

斜体  *斜体文本* 前后使用一个*

删除线 ~~删除线~~  前后使用两个 ~~

~~***删除加粗斜体***~~   可以嵌套 



## 引用文本

在引用的文字前加>即可。引用也可以嵌套，如加两个>>三个>>> n个...

>Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档。
>
>> Markdown 语言在 2004 由约翰·格鲁伯（英语：John Gruber）创建。
>>
>> > Markdown 编写的文档可以导出 HTML 、Word、图像、PDF、Epub 等多种格式的文档。
>> >
>> > > Markdown 编写的文档后缀为 .md, .markdown

## 分割线

***

---

---      *** 这都行

## 图片	

[这里边写图片介绍](这里写地址)

![v2-fb3ccb796766fc48a89a5f112e7726d6_hd](C:\Users\16098\Pictures\Saved Pictures\v2-fb3ccb796766fc48a89a5f112e7726d6_hd.jpg)



## 超链接

[点击跳转](地址url)

<a href="url" target="_blank">超链接</a>





## 列表

-+。这个三个都是无序列表样式

- 1  
- 2
- 3

1. 数字加  .  有序列表
2. 对
   - 二级列表 三个空格 （有无序都可）
3. 

## 表格

| 姓名 | 年龄 | 傻子 |
| :--- | ---- | ---- |
|      |      |      |

| :--- | ---- | ---- | ---- |  竖线+内容



## 代码

单行代码：代码之间分别用一个反引号包起来

`var 小傻子 `

代码块：代码之间分别用三个反引号包起来，且两边的反引号单独占一行

```php
function fun(){
         echo "这是一句非常牛逼的代码";
    }
    fun();
```



## 流程图

```flow
st=>start: 来啦老弟
a=>condition: 是否已经购买泰国大象
b1=>operation: 您已购买泰国大象可以使用markdown语法
c=>end: 欢迎使用泰国大象
b2=>operation: 还未能成功购买泰国大象但你可以免费试用10天
d=>condition: 是否要购买泰国大象
e1=>operation: 您已成功购买泰国大象欢迎使用
e2=>operation: 试用10天后将会到期欢迎购买

st->a
a(yes)->b1->c
a(no)->b2->d
d(yes)->e1->c
d(no)->e2
```


```flow
st=>start: 开始
op=>operation: My Operation
cond=>condition: Yes or No?
e=>end
st->op->cond
cond(yes)->e
cond(no)->op
&```


```