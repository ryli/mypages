title: web style 总结
date: 2014-10-26 04:22:57
categories: css
tags: css
---
###1.去掉点击后阴影
>    tap后会出现一个半透明的灰色背景，（被批...），起初以为是outline作怪，加上后发现没反应，最后发现是tap后的背景高亮，要重设这个表现，则需要设置-webkit-tap-highlight-color为所需色彩，直接透明

```css
a,img,button,input,textarea{-webkit-tap-highlight-color:rgba(255,255,255,0);}
```

###2.去掉textarea,input的默认样式（IOS上的圆角及内阴影等，Android未测试)
```css
input,textarea{-webkit-appearance:none;}
input {line-height: normal;} /* 修复低版本Android提示偏上bug*/
```

###3.view port
```css
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-touch-fullscreen" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
/* * 1、2条的作用是删除IOS默认的工具栏和菜单栏并且全屏显示，这个请配合第4、5条理解。
* 第3条的作用是改变状态栏样式，默认值为default（白色）
* 可选项为black（黑色）和black-translucent（灰色半透明）
**/
<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1.0, user-scalable=0, maximum-scale=1.0">
<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1.0, user-scalable=0, maximum-scale=1.0, minimal-ui">
/* * 对比一下，第4条就比第5条少了个minimal-ui * initial-scale 初始的缩放比例
* minimum-scale 允许用户缩放到的最小比例
* maximum-scale 允许用户缩放到的最大比例 * user-scalable 用户是否可以手动缩放
* minimal-ui    iOS7.1移动端Safari浏览器不显示地址栏和工具栏
* 综上：viewport标记是用来控制屏幕缩放的
**/
<link rel="apple-touch-icon" href="图标地址">
/* * 设置web app的放置主屏幕上icon文件路径。
* 图片尺寸可以设定为57*57PX(iPhone) | 114*114PX(Retina) | 72*72PX(iPad)
**/
<link href="" media="(device-width: 320px)" rel="apple-touch-startup-image">
/* * 启动画面图像(media相关不做介绍)**/
<meta name="format-detection" content="telephone=no">
<meta name="format-detection" content="email=no">
/* * 第8条：禁止将数字当做电话号码
* 第9条：禁止将邮箱变为可以点击
**/
```

###4.mac 字体优化
```
.os_mac {
    font-family: "ff-tisa-web-pro-1","ff-tisa-web-pro-2","Lucida Grande","Hiragino Sans GB","Hiragino Sans GB W3";
    -webkit-font-smoothing:antialiased
}
```

###4.禁止当手机由竖屏转向横屏的时内容中的文字自动调整大小
```
-webkit-text-size-adjust : none ;
-moz-text-size-adjust : none ;
-ms-text-size-adjust : none ;
text-size-adjust : none;
```
