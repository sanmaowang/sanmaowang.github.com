---
layout: post
title: "几个前端小问题"
description: "little problem about front-end wor0"
category: work
tags: [work, code, iframe, onerror]
---
{% include JB/setup %}

在工作中遇到了几个小问题，也算是几个坑，这里记载一下自己的心得。

#### 当Iframe 遇到劫持

当页面中存在Iframe时，又遇到了SP运营商的流氓劫持时，也就是它也用iframe来套我们产品，形成多层iframe套用的情况。一些组件的运用会出现问题，例如我们产品中的iframe垮域自适应高度。  

我们发现直接使用parent来找父级会遇到问题，操作frame都失效了，需有一些改动，这里有很好的说明：[js操作frameset frame对象](http://lillian1205.iteye.com/blog/558057)

	var ifrm = this.parent.$("#" + getRequest("data-frameid"));
	if(ifrm){
		this.self.parent.frameElement.style.height = height + 'px';

#### IMG onerror

`onerror`用于图片加载失败之后浏览器的处理，浏览器会再次调用`onerror`，在`onerror`中写入新的替代图片。

例如：

	<img src="avatar_01.jpg" onerror="this.src=avatar_normal.jpg"/>

这里有一个问题，如果onerror里的地址也不存在，就会继续调用onerror，形成循环，出现错误。在IE浏览器中会弹出 stack overflow at line: 0的错误。

在网上搜了下，解决方案有几种。我觉得最好的方案是这样，先清空onerror，然后再重新赋值。即：

	<img src="avatar_01.jpg" onerror="this.onerror='';this.src=avatar_normal.jpg"/>
	
#### Flash Object classid 

遇到的一个插入flash问题。在指定了classid之后，Flash无法在ff/chrome/safari下显示，只能在IE下显示。而你如果不指定classid，对IE来说会有麻烦。如果没有classid，IE会向服务器发送请求询问此object的类型，服务器会返回keep alive的连接，这样IE会去一直等待服务器返回类型。那么如何让flash在ff/chrome/safari下正常显示呢？可以使用

	<embed src="**.swf"/>

常规传参数使用param，可embed同样可以很好的传参数。

	<param name="FlashVars" value="">
	<embed src="**.swf" FlashVars = "" wmode=""></embed>
