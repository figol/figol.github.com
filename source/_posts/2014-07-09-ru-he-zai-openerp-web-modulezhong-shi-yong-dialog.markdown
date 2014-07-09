---
layout: post
title: "如何在openerp web module中使用dialog"
date: 2014-07-09 17:25
comments: true
categories: 
---
<h3>最近群有经常有人发问，你做的是什么模块，感觉好酷哦。</h3>
<pre>
	其实只是应用了一点点openerp web模块的东西；
	这个东西就是openerp封装的dialog，它可以弹出犹如wizard的对话框,使界面变得高大上；
	具体调用方法如下：
</pre>
<code>
	var dialog = new instance.web.Dialog(self,{
    	title: 'Scanner Error', autoOpen:true, width:700, resizable:false, modal:true,
        buttons:{
        	"Close": function () {
       		    _dialog.destroy();
           	}
       	}
    }, '<h1>hello world!</h1>');
</code>
