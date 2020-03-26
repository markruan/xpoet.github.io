---
title: 快速掌握Markdown基础语法
date: 2017-10-17 16:44:07
tags: [Markdown, md语法]
categories: [技术教程]
---
### 什么是Markdown？
Markdown是一种**轻量级标记语言**，用途广泛，其使用简洁的语法代替常见的排版格式，从而能使我们专心于写作，在最大程度上提高效率。Markdown 的语法十分简单，常用的标记符号也不超过十个，学习成本极低，一旦熟悉这种语法规则，将会有一劳永逸的效果。  

> We believe that writing is about content, about what you want to say – not about fancy formatting.
_**我们坚信写作写的是内容，所思所想，而不是花样格式。**_

### 使用Markdown的优点：
 * 专注你的文字内容而不是排版样式。
 * 纯文本内容，兼容所有的文本编辑器。
 * 可读、直观、通用性高、学习成本低。  
 * 轻松导出**HTML**、**PDF**等格式的文件。  
 * 随时可修改.md文件，不会因版本问题导致格式混乱。

### Markdown简要语法规则：
#### 1. 字体加粗 [标记符： `**` / `__` ]
在需要表示为粗体的文字内容，用**两个**`**` 或 `__`标记符包裹。
例如：`**字体加粗**` 或 `__字体加粗__`

![粗体](http://ojzaff7fe.bkt.clouddn.com/%E5%8A%A0%E7%B2%97.jpg) 

#### 2. 斜体 [标记符： `*` / `_` ]
在需要表示为斜体的文字内容，用两个`*` 或 `_`标记符包裹。
例如：`*斜体*` 或 `_斜体_`

![斜体](http://ojzaff7fe.bkt.clouddn.com/%E6%96%9C%E4%BD%93.jpg) 

#### 3. 标题 [标记符： `#` ]
标题是文章最常用的格式，在Markdown中，如果一段文字被定义为标题，只需在这段文字前加`#`标记符。  
例如：
`# 一级标题`
`## 二级标题`
`### 三级标题`
......
以此类推，共六级标题，对应HTML的h1~h6。
**注意：不包裹文字内容的标记符和文字之间需加一个空格！这是Markdown标准语法。**

![标题](http://ojzaff7fe.bkt.clouddn.com/%E6%A0%87%E9%A2%98.jpg) 

#### 4. 引用 [标记符： `>` ]
只需在引用的文字内容前面加上`>`标记符，就可以出现引用的效果。
例如：
`> 我是引用的句子哦`

![quote_image](http://ojzaff7fe.bkt.clouddn.com/%E5%BC%95%E7%94%A8.jpg)

#### 5. 列表
##### 无序列表 [标记符：`-` / `+` / `*` ]
在需要表示为无序列表的文字前加 `-` 或 `+` 或 `*` 标记符。

![unordered list image](http://ojzaff7fe.bkt.clouddn.com/%E6%97%A0%E5%BA%8F%E5%88%97%E8%A1%A8.jpg)


##### 有序列表 [标记符：`1.` 、 `2.` 、 `3.` ...... ]
在需要表示为有序列表的文字前直接加 `1.` 、 `2.` 、 `3.` 标记符。

![ordered list image](http://ojzaff7fe.bkt.clouddn.com/%E6%9C%89%E5%BA%8F%E5%88%97%E8%A1%A8.jpg)  

#### 6. 链接 [标记符： `[显示文字](链接地址)` ]
在Markdown中，插入**链接**，例如：
`[点击跳转itPoet](www.itpoet.cn)`

![link_image](http://ojzaff7fe.bkt.clouddn.com/%E9%93%BE%E6%8E%A5.jpg)

#### 7. 图片 [标记符： `![](图片链接地址)` ]
在Markdown中，插入**图片**，例如：
`![夏韵](http://ojzaff7fe.bkt.clouddn.com/zytyhxmy.jpg)`

![imageLink](http://ojzaff7fe.bkt.clouddn.com/%E5%9B%BE%E7%89%87.jpg)

#### 8. 引用代码
##### 单行代码 [标记符：**\`** ]
需要引用代码时，如果引用的代码只有一行，可以用两个 **\`** 标记符将代码包裹起来。例如：

![单行代码](http://ojzaff7fe.bkt.clouddn.com/%E5%8D%95%E8%A1%8C%E4%BB%A3%E7%A0%81%E5%BC%95%E7%94%A8.jpg)

##### 多行代码 [标记符：**\`\`\`** ]
多行代码，可以用两个 **\`\`\`** 标记符将代码块包裹起来。例如：

![多行代码](http://ojzaff7fe.bkt.clouddn.com/%E5%A4%9A%E8%A1%8C%E4%BB%A3%E7%A0%81.jpg)

#### 9. 分割线 [标记符：`*` / `-` / `_` ]
插入分割线，在一行中用三个以上的 `*` 或 `-` 或 `_` 标记符来建立一个分隔线，行内不能有其他内容。分隔符独占一行。
例如：`***` 、 `---`、 `___`

![分割线](http://ojzaff7fe.bkt.clouddn.com/%E5%88%86%E5%89%B2%E7%BA%BF.jpg)


#### 10. 换行 [标记符： `两个空格符` 加 `回车` ]
在Markdown中进行换行，需在文字后面键入 `两个空格符` 加 `回车`。


#### 11. 表格
在Markdown中插入表格的标记符比较复杂，大家直接看效果，需要用到时过来复制代码。

##### 默认表格样式
参考代码：
```
ColName1 | ColName2 | ColName3
---------|----------|---------
ColValue | ColValue | ColValue
ColValue | ColValue | ColValue
ColValue | ColValue | ColValue
ColValue | ColValue | ColValue
```

效果如下：

ColName1 | ColName2 | ColName3
---------|----------|---------
ColValue | ColValue | ColValue
ColValue | ColValue | ColValue
ColValue | ColValue | ColValue
ColValue | ColValue | ColValue

##### 表格列调整
表格的列位置调整（默认左对齐，`:------:`居中，`------:`右对齐）
参考代码：
```
|ColName1 | ColName2 | ColName3|
|---------|:--------:|--------:|
|ColValue | ColValue | ColValue|
|ColValue | ColValue | ColValue|
|ColValue | ColValue | ColValue|
|ColValue | ColValue | ColValue|
```

效果如下：

|ColName1 | ColName2 | ColName3|
|---------|:--------:|--------:|
|ColValue | ColValue | ColValue|
|ColValue | ColValue | ColValue|
|ColValue | ColValue | ColValue|
|ColValue | ColValue | ColValue|

**说明： 由于不同浏览器之间对Markdown编译存在差异，实际效果跟本文展示的效果也会有所不同。**
