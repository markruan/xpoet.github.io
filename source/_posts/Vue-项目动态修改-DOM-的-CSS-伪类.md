---
title: Vue 项目动态修改 DOM 的 CSS 伪类
date: 2020-11-09 16:03:06
tags: [Vue, CSS 伪类]
categories: [前端]
---

在 Vue 项目中，如何动态修改某个 DOM 元素的 CSS 伪类？实现方法非常简单，其原理是使用 CSS3 的 **`var()`** 函数和 **`--`** 变量。

以下列代码为例，实现动态修改 `class` 为 demo 的 `div` 元素鼠标悬浮时的背景颜色：

- `template` 中，绑定一个 `--` 变量 `--hover-background-color`。

- `script` 中，定义一个变量 `hoverBackgroundColor`，用以动态背景颜色。

- `style` 中，`background` 的值用 `var(--hover-background-color)` 表示。

```html
<template>
  <div
    class="demo"
    :style="{
                '--hover-background-color': hoverBackgroundColor
            }"
  ></div>
</template>

<script>
  export default {
    data() {
      return {
        hoverBackgroundColor: "#ccc",
      };
    },
  };
</script>

<style>
  .demo:hover {
    background: var(--hover-background-color);
  }
</style>
```
