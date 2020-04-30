---
title: CSS实现元素垂直居中的几种方法
date: 2018-02-02 16:54:40
tags: [CSS, 垂直居中]
categories: [前端]
---
> __*以下几种CCS实现元素垂直居中的方法，均不考虑低版本浏览器。*__

##### 方法一：子绝父相（子元素绝对定位，父元素相对定位）
1.1 不知道子元素高度和父元素高度的情况。
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
1.2 知道子元素高度和父元素高度的情况。
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


##### 方法二：子元素相对定位
父元素设置了高度，而且父元素里面只有一个子元素，可使用子元素相对定位。
```css
.parentElement {
    height: xxxx;
}

.childElement {
    position: relative;
    top: 50%;
    transform: translateY(-50%);
}
```

##### 方法三：CSS3 flex 布局
如果不考虑低版本浏览器兼容性，用CSS3的flex布局就非常简单咯。
```css
.parentElement {
    display: flex;
    align-items: center;
}
```