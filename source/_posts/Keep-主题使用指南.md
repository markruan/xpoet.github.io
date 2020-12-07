---
title: Keep 主题使用指南
date: 2020-04-07 21:55:14
tags: [Hexo, Keep]
categories: [Keep]
sticky: 9999
---

如你所见，Keep 界面设计十分简洁、清爽，但功能齐全、不失优雅，这正是 Keep 的开发理念。也曾尝试过花里胡哨，发现不仅配置繁琐、也容易审美疲劳，而且背驰了写博客的初衷，记录生活、展示文字，应该才是搭建博客网站的最终追求，为此 Keep 主题应运而生。简约轻快、化繁为简、配置简单、突出内容、长期维护，如果你也喜欢或认可这些主题特点，一起来探索吧~

<!-- more -->

~~关于主题名 **"ILS"** 的由来：在主题开发之初，作者想到的几个名字都被已被用，词穷，后来干脆将名字取自 **"I Like Simple「我喜欢简单」"** 首字母，就是这么简单。~~

**`v3.0.0` 起，原 Hexo 主题 ILS 正式改名为 Keep。**

Keep 全新设计、全面提升，更轻、更快、更强，愿你坚持写作、保持热爱。

## Features 功能特性

### Completed 已完成

- [x] 恰到好处的留白，简约大气
- [x] 响应式设计，适配平板/手机
- [x] 日间/夜间模式自由切换
- [x] 多种代码高亮方案
- [x] 多语言，支持中/英文
- [x] 内置多款评论插件
- [x] 支持全站文章搜索
- [x] 支持文章顶置
- [x] 代码块一键复制
- [x] TOC 目录结构
- [x] RSS 订阅
- [x] 网站 UV 和 PV 统计
- [x] 文章阅读次数统计
- [x] 文章字数统计
- [x] 文章阅读时长统计
- [x] 大图查看器
- [x] 文章版权信息
- [x] 在线更改字号
- [x] 页面滚动进度条提示
- [x] 一键快速回到顶部

### Unfinished 未完成

- [ ] 图片懒加载
- [ ] 文章点赞功能
- [ ] 代码块折叠
- [ ] 在线更改字体
- [ ] 打赏功能
- [ ] ......

## Get start 快速开始

**在开始使用主题之前，强烈建议你先阅读 「Easy Hexo 团队」撰写的 Hexo 教程！**  
**链接：https://easyhexo.com/**

### Install 安装

- 使用 Git SSH

  ```bash
  git clone --depth=1 git@github.com:XPoet/hexo-theme-keep.git themes/keep
  ```

  该方式获取的是 Master 分支最新代码，包含该主题最新的功能，但无法保证完全稳定。

- 下载 Release 版本

  [点击此处进入该主题 Releases 版本下载页面](https://github.com/XPoet/hexo-theme-keep/releases) 请下载最新版本，下载完成后解压到 Hexo 博客目录的 themes 文件夹里面并重命名为 `keep`。

### Enable 启用

修改 Hexo 根目录下的 `_config.yml` 配置文件，将 `theme` 设置为 `keep` 。

```yml
theme: keep
```

### Update 更新

- 使用 Git SSH
  ```bash
  cd themes/keep
  git pull
  ```
- 下载 [主题最新 Release 版本](https://github.com/XPoet/hexo-theme-keep/releases) 。

## How to use 如何使用

### Configuration 配置

请查看 [Keep 主题配置指南](https://keep.xpoet.cn/2020/11/Keep-主题配置指南/) 。

如遇到无法解决的问题，可以给作者提 [Issue](https://github.com/XPoet/hexo-theme-keep/issues) 。

### Comment 评论

主题内置了 Valine 和 Gitalk 两款评论插件，你只能使用其他一款，如果两款评论插件的 enable 都设为了 true，将使用 Valine。

#### Valine

前往 https://github.com/xCss/Valine 查看 Valine 如何使用，获取必要的参数，填写在配置文件里。

#### Gitalk

1. 在自己的 GitHub 账号下创建新的 OAuth App，链接：https://github.com/settings/applications/new ，Homepage URL 和 Authorization callback URL 均填写自己的域名即可。
   例 `https://keep.xpoet.cn/`

2. 在自己的 GitHub 账号下创建新的 repository 并打开 Issues，用于存储评论内容。

3. 把自己的 GitHub 用户名称、repository 名称 、OAuth App 的 Client ID 、Client Secret 分别填写在主题配置文件里。

前往 https://github.com/gitalk/gitalk 查看 Gitalk 更多信息。

### Post top 文章顶置

实现文章顶置功能，需在文章页添加 `sticky` 属性，`sticky` 值越大，顶置的文章越靠前，参考如下。

```markdown
---
title: Hexo 主题 Keep 使用指南
date: 2020-04-07 21:55:14
tags: [Hexo]
categories: [Hexo]
+ sticky: 9999
---
```

### Local search 本地搜索

1. 启用本地搜索功能，需在 Hexo 博客根目录下安装插件 **`hexo-generator-searchdb`**。

   ```bash
   npm install hexo-generator-searchdb
   ```

2. 在 Hexo 配置文件 `_config.yml` 增加如下配置。

   ```yml
   # Search
   ## https://github.com/theme-next/hexo-generator-searchdb
   search:
     path: search.json
     field: post
     content: true
     format: striptags
   ```

3. 修改主题配置文件 `_config.yml`。

   ```yml
   local_search:
     enable: true
     trigger: auto # values: auto | manual
     unescape: false
     preload: true
   ```

### RSS 订阅

1. 启用 RSS 订阅功能，需先在 Hexo 博客根目录下安装插件 **`hexo-generator-feed`**。

   ```bash
   npm install hexo-generator-feed
   ```

2. 在 Hexo 配置文件 `_config.yml` 增加如下配置。

   ```yml
   # Feed Atom
   # npm install hexo-generator-feed
   feed:
     type: atom
     path: atom.xml
     limit: 20
   ```

3. 修改主题配置文件 `_config.yml`。

   ```yml
   rss:
     enable: true
   ```

### Add page 添加页面

**Hexo 初始并没有 categories（分类）、about（关于）、links（友链）、tags（标签） 等页面，需要自己手动创建。**

以创建「关于」页面为例：

1. 在 Hexo 博客目录下执行命令，即可生成 `about` 文件夹。
   ```bash
   hexo new page about
   ```
2. 创建成功后，打开博客目录下 `/source/about/index.md` 文件，即可填写自己的内容。
   支持 Markdown 和 HTML 格式；`comments: true` 表示该页面开启评论功能。

   参考如下示例：

   ```markdown
   ---
   title: about
   date: 2020-03-19 14:59:53
   comments: true
   ---

   content...
   ```

3. 在主题配置文件启用 `about` 导航菜单。
   ```yml
   # navigation menu
   menu:
     Home: /
     Archives: /archives
     # Category: /category
     # Links: /links
     About: /about
     # ...
   ```

其他页面的生成方式跟「关于」页面类似，此处不再赘述。

### MathJax 数学公式

如果要在文章中显示数学公式，可以使用插件 **`hexo-filter-mathjax`**，详情参考：https://github.com/next-theme/hexo-filter-mathjax/ 。

或按下列步骤完成相关配置：

1. 在 Hexo 博客根目录下安装插件 **`hexo-filter-mathjax`**。

   ```bash
   npm install hexo-filter-mathjax --save
   ```

2. 在 Hexo 配置文件 `_config.yml` 增加如下配置。

   ```yml
   mathjax:
     tags: none # or 'ams' or 'all'
     single_dollars: true # enable single dollar signs as in-line math delimiters
     cjk_width: 0.9 # relative CJK char width
     normal_width: 0.6 # relative normal (monospace) width
     append_css: true # add CSS to every page
     every_page: false # if true, every page will be rendered by mathjax regardless the `mathjax` setting in Front-matter of each article
   ```

3. 在文章页添加 `mathjax: true`，至此，就可以在该页面中写公式了。

   ```yml
   ---
   title: MathJax Test
   date: 2020-09-12 16:02:07
   tags: MathJax
   categories: MathJax
   mathjax: true
   ---
   $$
   i\hbar\frac{\partial}{\partial t}\psi=-\frac{\hbar^2}{2m}\nabla^2\psi+V\psi
   $$
   ```

## Contribution 贡献

欢迎各种形式的贡献，包括但不限于：美化样式、增加功能、改进代码、 修复 Bug 等。

请查看 [Keep 代码贡献指南](https://keep.xpoet.cn/2020/11/Keep-代码贡献指南/) 。

## Feedback 反馈

在使用该主题过程中，如果遇到问题，请仔细阅读使用文档，或者给作者提 `Issue`。

## Licence 许可

[MIT](https://github.com/XPoet/hexo-theme-keep/blob/master/LICENSE) Copyright (c) 2020 XPoet
