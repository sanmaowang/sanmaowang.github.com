---
layout: post
title: "关于17zuoye的首页设计"
description: "about the 17zuoye's homepage desgin"
category: products
tags: [17zuoye, work]
---
{% include JB/setup %}

##首页的目标

17zuoye 就目前看还是一个web app。恰好Tencent的cdc有一篇[工具型网站首页的设计思考](http://cdc.tencent.com/?p=5220)。我结合其文章的内容以及我自己的思考，对我们的网站首页设计提出一些建议。

	首页的目标  
	《designing for the social web》一书将用户的使用分为几个步骤：不了解——感兴趣——第一次使用——常规使用——有情感。而首页对于前面三个步骤至关重要！
 	
<a href="http://cdc.tencent.com/wp-content/uploads/2012/02/13.jpg" alt="首页目标" ><img src="http://cdc.tencent.com/wp-content/uploads/2012/02/13.jpg" width='630' alt='homepage desgin'/></a>

	这样看来，首页有两个目标：  
	1. 让不了解的用户了解网站并产生兴趣，最终促成用户使用。  
	2. 让有兴趣的用户尽快开始使用。

##现状

以这样两个目标来看我们的首页，如图：

<a href="http://linblog.b0.upaiyun.com/lin/17zuoye/homepage.jpg" alt="" class="lightbox"><img src="http://linblog.b0.upaiyun.com/lin/17zuoye/homepage.jpg" width='630' alt='homepage desgin'/></a>

首页没有满足目标，需要用户点击了解一起作业，跳转至新页面了解一起作业才能产生兴趣。而了解一起作业点击进去后是：

<a href="http://linblog.b0.upaiyun.com/lin/17zuoye/intro.jpg" alt="" class="lightbox"><img src="http://linblog.b0.upaiyun.com/lin/17zuoye/intro.jpg" width='630' alt='homepage desgin'/></a>

这个了解详情的页面绝不是一个好的设计。而至于可吐槽之处，我就不一一指出了。

##问题

我们回到首页来说，首页的问题我列举以下：

1. 用户输入区域 Login/ Register 在最左侧，设计将其独立出背景图却显得较为狭窄，而只能用类似placeholder占位符方式作为label名；

2. 三种Button样式，蓝色/绿色/橘黄色，Bootstrap的Default Buttons里蓝色是Action，绿色是Success，橘黄色是Warning。 按钮颜色过多和右侧背景的淡雅不是特别协调；

3. 链接和非链接的热线号码，以及Logo均为蓝色，不合理，且Logo不可点击；  

4. 页面没有介绍或任何Slogan，首次访问的用户到达首页，不会立即知道这个网站是做什么的，没有号召力和感染力，对自己品牌没有任何好处和树立；背景图片较为平淡，用户不会有冲动注册；

5. 没有填写用户名或者密码，会直接alert弹窗提示错误；若填写错误帐号和密码，错误提示出现在输入框顶部，和注册中的表单错误提示方式不同；

6. 在IE6/7浏览器显示：
> 一起作业紧急通知：微软倡导您对IE6、IE7说再见，为了您能够正常使用一起作业，请升级浏览器，点击图标免费下载： IE8中文浏览器  

	文案不专业（微软：关我嘛事）
	
<a href="http://linblog.b0.upaiyun.com/lin/17zuoye/intro.jpg" alt="" class="lightbox"><img src="http://linblog.b0.upaiyun.com/lin/17zuoye/notice.jpg" width='630' alt='homepage desgin'/></a>

##我的想法
<ol>
<li><p>重新设计 logo，按钮颜色需符合逻辑，页面颜色视觉上相关的需逻辑相关</p></li> 
<li><p>突出登陆而非注册，这是由需求决定</p></li>   
<li><p>提出明确价值主张</p></li>
<li><p>首页内容可放每期特别重要的活动</p></li> 
<li><p>统一错误提示方式和样式</p></li>
<li><p>修改提示文案</p></li>
</ol>

> 参考资料  
> 
> Tencent CDC [工具型网站首页的设计思考](http://cdc.tencent.com/?p=5220)
> 
