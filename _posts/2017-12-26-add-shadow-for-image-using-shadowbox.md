---
layout: post
title: 用shadowbox.js为图片添加阴影效果
categories: rwd
permalink: /:categories/:title.html
tags: 图片外框添加阴影效果挺美观的,结合老师上课教授的知识点,发现以下知识点
---


当我发觉为图片外框添加阴影效果挺美观的。于是我也开始捣鼓给自己的博客添加图片阴影效果。用Chrome查看人家博客的CSS样式，发觉`img`中多了shadowbox这一项，然后自己直接复制过去，发觉没用。只能放狗一搜了，原来用了JS插件。查了一些资料，比较杂，真正对自己有用的是这货[shadowbox.js](http://www.shadowbox-js.com/index.html)。下载主页提供的文件包后，解压，发觉不止有`shadowbox.js`文件，还多了`shadowbox.css`样式文件，有点莫名其妙，之前我用`audio.js`时是没有css样式的。本小子没管那么多，直接把`shadowbox.css`放在css文件夹里，`shadowbox.js`放在js文件夹下。按照[Shadowbox.js](http://www.shadowbox-js.com/index.html)主页使用说明：

> The simplest way to set up Shadowbox is to include the JavaScript and CSS files in the <head> of your document (web page) and then call Shadowbox.init, like this:

```html
<link rel="stylesheet" type="text/css" href="shadowbox.css">
<script type="text/javascript" src="shadowbox.js"></script>
<script type="text/javascript">
Shadowbox.init();
</script>
```

在自己博客的`default.html`文件`<head>`标签之间采用上面的代码进行初始化，具体如下：

```html
<link rel="stylesheet" type="text/css" href="/public/css/shadowbox.css">
<script type="text/javascript" src="/public/js/shadowbox.js"></script>
<script type="text/javascript">
Shadowbox.init();
</script>
```

修改完后，还要添加css样式。说到这，不得不提一下两个非常有用的网址：[Box-shadow, one of CSS3′s best new features](http://www.css3.info/preview/box-shadow/)和[BOX SHADOW](http://www.cssmatic.com/box-shadow)。前者对于理解shadowbox的参数设置非常有帮助，后者则是一个在线shadowbox阴影效果生成器，可视化，非常的方便。

在`main.css`的`img`添加了如下的阴影效果代码：

```css
-webkit-box-shadow: 1px 4px 16px 8px #5CA2BE;
-moz-box-shadow: 1px 4px 16px 8px #5CA2BE;
box-shadow: 1px 4px 16px 8px #5CA2BE;
```

添加完后push到github上面，发觉阴影效果有了，但图片上面的字与下面图片的间距挨得太近了，放狗一搜，发觉`margin:20px auto;`似乎有用，测试了一下，果然有用，将它添加进样式里，就可以看见现在博文里图片的阴影效果了，over。