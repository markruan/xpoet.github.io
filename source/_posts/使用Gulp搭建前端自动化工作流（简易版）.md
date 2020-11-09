---
title: 使用gulp搭建前端自动化工作流环境（简易版）
date: 2017-11-30 11:18:48
tags: [Gulp, 前端自动化]
categories: [前端]
---

> 本文通过简单且实用的案例，讲解使用 gulp 搭建前端自动化工作流环境详细步骤，带领大家快速入门。

### 什么是 gulp？

来自官网的简介：Automate and enhance your workflow. gulp is a toolkit for automating painful or time-consuming tasks in your development workflow, so you can stop messing around and build something.

大致意思是讲 gulp 是一款自动化构建工具，可用于增强你的开发工作流程，提高工作效率！前端界的友友们，这个工具可不要错过了哟~

- [gulp 官网](https://gulpjs.com/)
- [gulp 中文网](http://www.gulpjs.com.cn/)

### gulp 优点

- **易于使用** 通过代码优于配置的策略，gulp 让简单的任务简单，复杂的任务可管理。
- **构建快速** 利用 Node.js 流的威力，你可以快速构建项目并减少频繁的 IO 操作。
- **插件高质** gulp 严格的插件指南确保插件如你期望的那样简洁高质得工作。
- **易于学习** 通过最少的 API，掌握 gulp 毫不费力，构建工作尽在掌握：如同一系列流管道。

### 准备工作

**gulp 依赖 Node.js，参考本教程的朋友们，请先在本地环境安装好 Node.js，并确认 Node.js、npm 可正常使用。**

### 步骤

#### 第一步 新建项目根文件夹(例：gulp-demo)，并在项目根目录下使用 npm 安装必要的包

```
$ npm install gulp gulp-less gulp-concat gulp-cssnano gulp-uglify gulp-htmlmin browser-sync --save-dev
```

本案例使用的 gulp 插件介绍：

- **gulp-less** 将 less 编译成 css
- **gulp-concat** 将多个 JavaScript 合并
- **gulp-cssnano** css 压缩
- **gulp-uglify** JavaScript 压缩并混淆
- **gulp-htmlmin** html 压缩
- **browser-sync** 多浏览器同步操作

#### 第二步 在项目根文件夹(例：gulp-demo)下创建相关的文件结构

##### src [gulp 编译之前的源文件]

- **css** 我们在此处编写 css 文件
- **img** 我们在此处放置图片文件
- **js** 我们在此处编写 css 文件
- **index1.html**
- **index2.html**
- **.......**

##### node_modules

通过 npm 安装的包及其依赖包的库，自动生成文件夹。

##### gulpfile.js

gulp 的入口文件，我们在此处编写相关任务代码。

##### dist [gulp 编译之后的文件，即我们最终要得到文件]

- **css**
- **img**
- **js**
- **index.html**

#### 第三步 在 gulpfile.js 文件里编写具体的任务代码

##### 载入所需要的模块

```javascript
"use strict"; // 启用JavaScript严格模式
var gulp = require("gulp");
var less = require("gulp-less");
var cssnano = require("gulp-cssnano");
var concat = require("gulp-concat");
var uglify = require("gulp-uglify");
var htmlmin = require("gulp-htmlmin");
var browserSync = require("browser-sync");
```

##### less 编译、压缩

```javascript
// 定义LESS编译、压缩的任务：css
gulp.task("css", function () {
  gulp
    .src(["src/css/*.less", "!src/css/_*.less"])
    .pipe(less())
    .pipe(cssnano())
    .pipe(gulp.dest("dist/css"))
    .pipe(
      browserSync.reload({
        stream: true,
      })
    );
});
```

##### JavaScript 合并、压缩、混淆

```javascript
// 定义多个JavaScript文件合并、压缩混淆的任务：js
gulp.task("js", function () {
  gulp
    .src("src/js/*.js")
    .pipe(concat("index.js")) // JS合并之后，文件命名为index.js
    .pipe(uglify()) // JS压缩混淆
    .pipe(gulp.dest("dist/js"))
    .pipe(
      browserSync.reload({
        stream: true,
      })
    );
});
```

##### 将 src 文件夹下 img 图片复制到 dist 文件夹下 img

```javascript
// 定义image复制的任务：img
gulp.task("img", function () {
  gulp
    .src("src/img/*.*")
    .pipe(gulp.dest("dist/img"))
    .pipe(
      browserSync.reload({
        stream: true,
      })
    );
});
```

##### html 代码压缩

```javascript
// 定义HTML压缩的任务：html
gulp.task("html", function () {
  gulp
    .src("src/*.html")
    .pipe(htmlmin({ collapseWhitespace: true }))
    .pipe(gulp.dest("dist"))
    .pipe(
      browserSync.reload({
        stream: true,
      })
    );
});
```

##### 多浏览器同步操作，开启 gulp 监视文件变动

```javascript
// 定义浏览器同步操作服务的任务：browserSync
gulp.task("browserSync", function () {
  browserSync(
    {
      server: {
        baseDir: ["dist"],
      },
    },
    function (err, bs) {
      console.log(bs.options.getIn(["urls", "local"]));
    }
  );
  // 开启gulp监视
  gulp.watch("src/css/*.less", ["css"]); // less文件改动时，执行css任务
  gulp.watch("src/js/*.js", ["js"]); // js文件改动时，执行js任务
  gulp.watch("src/img/*.*", ["img"]); // image文件改动时，执行img任务
  gulp.watch("src/*.html", ["html"]); // html文件改动时，执行html任务
});
```

### 使用

- 1 `$ gulp css` LESS 编译 压缩 合并
- 2 `$ gulp js` JavaScript 合并 压缩 混淆
- 3 `$ gulp img` image 复制
- 4 `$ gulp html` HTML 压缩
- 5 `$ gulp browserSync` 多浏览器同步操作，gulp 监视 JS/CSS/HTML 文件改变

[点击此处，下载本案例源代码](https://github.com/itPoet/gulp)
