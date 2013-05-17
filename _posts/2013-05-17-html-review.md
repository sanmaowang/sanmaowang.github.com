---
layout: post
title: "HTML复习和总结"
description: ""
category: 
tags: [Front-end, html]
---
{% include JB/setup %}
HTML(Hypertext Markup Languate)即超文本标记语言。HTML不是编程语言，而是一种标记语言。

## 文档类型

文档类型申明是告诉浏览器此文档什么类型，用什么版本编写。浏览器要了解使用哪个DTD（DTD是文档类型定义）来解释网站。  
>```<!DOCTYPE html PUBLIC “-//W3C//DTD XHTML 1.0 Strict//EN” "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
```  
HTML4/XHTML1均规定了三种文档类型，Strict/Transitional/Frameset。但在实际中，即便你使用strict.dtd，却还是可以用iframe这个Tag。  

这是因为浏览器对文档的解析，主要是要看服务器以什么格式来提供这个文档。即是 "text/html" 和 "application/xhtml+xml"。在后者提供的文档是按XML方式来渲染的。IE7之前的版本，并不支持后者。所以目前绝大部分的文档都是以"text/html"方式提供。所以即使你在Doctype中申明了xhtml，如果是按"text/html"来提供，其实还是按HTML来解析的。HTML的容错性很强，浏览器其实最后并没有完全按照你声明的DTD来渲染你的文档。他只是看你是否申明了，申明是否正确，如果你没有申明Doctype或者申明有错，那么浏览器会启用怪异模式Quirks Mode来处理文档。

所以我们现在干脆一点，抛弃那些不必要的麻烦。直接写：```<!doctype html>```  

## 标准模式 和 怪异模式

浏览器厂商们为了兼容过去没有按标准规范编写的网页，提供了两套模式来解析。即标准模式(standards mode也称strict mode)和怪异模式（quirks mode），当然还有Almost standards mode模式。Quirks mode和Standards mode中最大的区别即针对block elments的盒子模型的问题。

>**Standards mode**
>css width : content width
>
>**Quirks mode**
>css width : padding + border + width

##HTML元素
如```<html><head><body><p>```，HTML中的元素有很多，不同的标签有各自的职责和语意。head定义文档各种属性，body定义文档内容，p是文档段落。

## Block & Inline
HTML元素可分为块级元素(block)和行内元素(inline)。常见的block element有: ```h1-h6, p, ul, dl, ol, table, form..``` 常见的inline elemnt有: ```img, a, span, strong, em, input..``` block元素默认是垂直排列，占据文档流一行。而行内元素默认是水平横排。由于html强大的包容性，是允许block和inline混排的。以前说inline里不可有block，其实也未必。当然一般情况下都是block中包含inline了。 block走盒子模型，inline没有，inline只有line-height，和上下的padding及margin。

##HTML属性
属性是元素的属性，是元素的附加信息。如```href, src, data-attr```等等。

##Web语意化
不同元素本就有自身的含义，如h1-h6自然是标题1－标题6，ul无序列表，form表单等等。HTML5增加了一些新的标签，如 ```<header><article><section><footer><canvas>```等等，这些均是为了更好的做到语意化。语意化的目标是做到人机共读，便于让机器也能更好的理解当前这段内容是什么，是标题，还是段落。不仅是元素，同样很多属性也是可为语意化服务。例如meta的属性值用于描述网页、rel属性nofollow，google不跟踪此链接、ARIA属性，让屏幕阅读器更好识别网页内容等等。

##HTML5
HTML5是HTML/XHTML的新标准。它提供了一系列的新元素和新属性，以及新的API，如：
Canvas, Video, Audio, Geo, Cross-document(postMessage), XHR level2, WebSockets, Local Storage… 等等。我自己还没太深入了解，这里就暂且不继续了。

 




