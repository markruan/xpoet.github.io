---
title: CSS 元素垂直居中的几种常用方法
date: 2018-02-02 16:54:40
tags: [CSS, 垂直居中]
categories: [前端]
---

### 子绝父相

子绝父相：子元素绝对定位，父元素相对定位。

#### 不知道子元素高度和父元素高度的情况

```css
.parentElement {
    position: relative;
}

.childElement {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
}
```

#### 知道子元素高度和父元素高度的情况

```css
.parentElement {
    position: relative;
}

.childElement {
    position: absolute;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    margin: auto;
}
```


### 子元素相对定位

父元素设置了高度，而且父元素里面只有一个子元素，可使用子元素相对定位。

```css
.parentElement {
    height: xxpx;
}

.childElement {
    position: relative;
    top: 50%;
    transform: translateY(-50%);
}
```

### CSS3 flex

如果不考虑低版本浏览器兼容性，用CSS3的flex布局就非常简单咯。

```css
.parentElement {
    display: flex;
    align-items: center;
}
```