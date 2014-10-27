title: css垂直居中
date: 2014-10-26 06:33:51
categories:
- css
tags:
- css

---
##css垂直居中总结
<!--more-->
```css
/* margin: auto; 必须声明元素高度, Windows Phone上不起作用 */
.element {
    width: 600px; /* 支持百分比,max-width, min-width等 */
    height: 400px;
    position: absolute; /* 或者fixed. relative无效 */
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    margin: auto;    /* 有了这个就自动居中了 */
    overflow:auto;    /* 推荐 */
}

/* transform */
.element {
    width: 600px; height: 400px;
    position: absolute;
     left: 50%; top: 50%;
     transform: translate(-50%, -50%);    /* 50%为自身尺寸的一半 */
}
```
