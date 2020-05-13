---
title: 快速掌握 Markdown 基础语法
date: 2017-10-17 16:44:07
tags: [Markdown]
categories: [技术教程]
top: 10
---
### 什么是 Markdown
Markdown 是一种**「轻量级标记语言」**，用途广泛，其使用简洁的语法代替常见的排版格式，从而能使我们专心于写作，在最大程度上提高效率。Markdown 的语法十分简单，常用的标记符号也不超过十个，学习成本极低，一旦熟悉这种语法规则，将会有一劳永逸的效果。  

> We believe that writing is about content, about what you want to say – not about fancy formatting.
**我们坚信写作写的是内容，所思所想，而不是花样格式。**

### 使用 Markdown 的优点
 * 专注你的文字内容而不是排版样式；
 * 纯文本内容，兼容所有的文本编辑器；
 * 可读、直观、通用性高、学习成本低；  
 * 轻松导出 `HTML` 、`PDF` 等格式的文件；  
 * 随时可修改 `.md` 文件，不会因版本问题导致格式混乱；

### Markdown 语法规则

#### 标题 
标记符 `#`  
标题是文章最常用的格式，在 Markdown 中，如果一段文字被定义为标题，只需在这段文字前加 `#` 标记符。  
例如：
`# 一级标题`
`## 二级标题`
`### 三级标题`
......
以此类推，共六级标题，对应 `HTML` 的 h1 ~ h6。
**注意：`#` 和文字之间需加一个空格。**

![标题](https://user-images.githubusercontent.com/24516169/81159079-32133f80-8fbb-11ea-8e41-62332c25e52e.png) 

#### 字体加粗 
标记符 `**` 或 `__`
在需要表示为粗体的文字内容，用两个 `**` 或 `__` 标记符包裹。  
例如：`**字体加粗**` 或 `__字体加粗__`

![粗体](https://user-images.githubusercontent.com/24516169/81159428-87e7e780-8fbb-11ea-842d-48ad7756177f.png) 

#### 斜体
标记符 `*` 或 `_`
在需要表示为斜体的文字内容，用两个 `*` 或 `_` 标记符包裹。  
例如：`*斜体*` 或 `_斜体_`

![斜体](https://user-images.githubusercontent.com/24516169/81159675-cc738300-8fbb-11ea-8393-d2209a5f69a0.png) 

#### 引用
标记符 `>`
只需在引用的文字内容前面加上 `>` 标记符，就可以出现引用的效果。  
例如：`> 我是引用的句子哦`

![引用](https://user-images.githubusercontent.com/24516169/81160045-32f8a100-8fbc-11ea-8e51-87633bf50d0c.png)

#### 列表
##### 无序列表
标记符 `-` 或 `+` 或 `*`
在需要表示为无序列表的文字前加 `-` 或 `+` 或 `*` 标记符。

![无序列表](https://user-images.githubusercontent.com/24516169/81160433-a1d5fa00-8fbc-11ea-9330-60bf9857a244.png)


##### 有序列表 
标记符 `1.` 或 `2.` 或 `3.` ......  
在需要表示为有序列表的文字前面添加加 `1.` 或 `2.` 或 `3.` ...... 标记符。

![有序列表](https://user-images.githubusercontent.com/24516169/81160871-3cced400-8fbd-11ea-8240-c37b27ee6007.png)  

#### 链接
标记符 `[]()` 
在 Markdown 中，插入链接，例如：`[XPoet Blog](https://xtpoet.cn)`

![link](https://user-images.githubusercontent.com/24516169/81161086-9800c680-8fbd-11ea-9790-14374e010461.png)

#### 图片
标记符 `![]()`
图片示例：`![aliyun](https://img.alicdn.com/tfs/TB1Ly5oS3HqK1RjSZFPXXcwapXa-238-54.png)`

![image](https://user-images.githubusercontent.com/24516169/81164608-35122e00-8fc3-11ea-8840-b98ff54d6758.png)

#### 代码
##### 单行代码
标记符 **\`  \`**
需要引用代码时，如果引用的代码只有一行，可以用两个 **\`** 标记符将代码包裹起来。例如：

![单行代码](https://user-images.githubusercontent.com/24516169/81164997-cd101780-8fc3-11ea-86dc-e025a4e99b90.png)

##### 多行代码
标记符：**\`\`\`  \`\`\`**
多行代码，用两个 **\`\`\`** 标记符将代码块包裹起来。例如：

![多行代码](https://user-images.githubusercontent.com/24516169/81165249-43147e80-8fc4-11ea-88a7-6c3e752326f0.png)

#### 分割线
标记符：`***` 或 `---` 或 `___`
插入分割线，在一行中用三个以上的 `*` 或 `-` 或 `_` 标记符来建立一个分隔线，行内不能有其他内容，分隔符独占一行。
![分割线](https://user-images.githubusercontent.com/24516169/81165548-b7e7b880-8fc4-11ea-8b12-db002969a670.png)

#### 删除线
标记符：`~~` 
在需要添加删除线的文字内容，用两个 `~~` 标记符包裹。
例如：`~~ABC~~` ~~ABC~~

#### 换行
标记符： `两个空格符` 加 `回车`
在 Markdown 中进行换行，需在文字后面键入 `两个空格符` 加 `回车`。


#### 表格
在 Markdown 中插入表格的标记符比较复杂，大家直接看效果，需要用到时过来复制代码。

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
表格的列位置调整（默认左对齐，`:------:` 居中，`------:` 右对齐）
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

**由于不同平台的 Markdown CSS 存在差异，实际显示效果跟本文也会有所不同。**
