---
layout: post
title: "前端的几个小问题"
description: "little problem about front-end wor0"
category: work
tags: [work, code, iframe, onerror]
---
{% include JB/setup %}

在工作中遇到了几个小问题，也算是几个坑，这里记载一下自己的心得。

#### 当Iframe 遇到劫持

当Iframe遇到SP运营商的流氓劫持时，也就是它也用iframe来套我们产品的时候，一些组件的运用会出现问题。例如iframe的垮域自适应高度，在面对劫持时会失效。直接使用parent来找父级可能会遇到问题，需有一些改动，这里有很好的说明：[js操作frameset frame对象](http://lillian1205.iteye.com/blog/558057)

#### IMG onerror

`onerror`用于图片加载失败之后浏览器的处理，浏览器会再次调用`onerror`，在`onerror`中写入新的替代图片。
例如：

	<img src="avatar_01.jpg" onerror="this.src=avatar_normal.jpg"/>

这里有一个问题，如果onerror里的地址也不存在，就会继续调用onerror，形成循环，出现错误。在IE浏览器中会弹出 stack overflow at line: 0的错误。

在网上搜了下，解决方案有几种。我觉得最好的方案是这样，先清空onerror，然后再重新赋值。即：

	<img src="avatar_01.jpg" onerror="this.onerror='';this.src=avatar_normal.jpg"/>
	
#### Flash Object classid 

遇到的一个插入flash问题。在指定了classid之后，Flash无法在ff/chrome/safari下显示，只能在IE下显示。而你如果不指定classid，对IE来说会有麻烦。这一特性和IE的ActiveX控件有关，必须得指定。
那么如何让flash在ff/chrome/safari下正常显示呢？
既然是现代浏览器，当然使用HTML5啦！

	<embed src="**.swf"/>

在常规flash object 传参数使用<param>，<embed>同样可以传参数。

	<param name="FlashVars" value="">
	<embed src="**.swf" FlashVars = "" wmode=""></embed>
