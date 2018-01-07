---
layout: post
title: CSS调整图片居中显示
categories: rwd
permalink: /:categories/:title.html
tags: 在网站内容的构建中，简单的三句话，解决图片排版问题
---

虽然有将图片居中显示的可视化调整工具，但每次调整每张图片都要做调整总是一件很繁琐的事情。这几天，一直在寻找本博客中博文出现的图片居中显示的方法，非常感谢这篇文章[《How to center images with CSS》](http://imagecss.com/center.html)

根据这篇文章给出的方法，打开一篇有图片的博文(在调整为居中之前，原图片都是左对齐的)，在css查看器里添加上面这篇文章里图片居中的代码：

```css
img.center {
    display: block;
    margin-left: auto;
    margin-right: auto;
}
```

然后在博文对应的图片处，按照给出的代码实例`<img src="images/yourimagefile.jpg" class="center" />`在博文对应的图片处添加了`class="center"`属性，测试发觉真的居中了。可是，在博客主题中一直都没找到往图片添加`class="center"`属性的位置。捣鼓测试了半天，还是没搞定，最后不得不返回来琢磨上面那段CSS代码。想了老半天，以前学过的编程语言的感觉，`.center`应该是属于`img`属性的，也就是把上面那段代码合并到`img`里是完全没问题的，并且可以实现图片居中显示。

将调整图片居中显示的代码添加进CSS文件后，博客主题的`img`属性是这样的：

```css
img{
	max-width:100%;
	margin:20px auto;
	height:auto;
	border:0;
	outline:0
	-webkit-box-shadow: 1px 4px 16px 8px #5CA2BE;
    -moz-box-shadow: 1px 4px 16px 8px #5CA2BE;
    box-shadow: 1px 4px 16px 8px #5CA2BE;
    /*set the images aligned*/
    display: block;
    margin-left: auto;
    margin-right: auto;
	}
```

上面`/*set the images aligned*/`后面部分即是添加图片居中显示的代码。简单的三句话，完美解决图片排版的问题。
