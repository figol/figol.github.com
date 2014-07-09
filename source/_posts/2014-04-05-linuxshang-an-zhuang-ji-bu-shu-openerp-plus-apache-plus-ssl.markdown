---
layout: post
title: "Linux上安装及部署Openerp 7.0 + Apache + SSL"
date: 2014-04-05 09:16
comments: true
categories: openerp
---
<pre>本文将主要介绍以下几点：
1. 在Centos 6.4上Openerp安装方法
2. 在Centos 6.4上apache 2.4安装方法
3. 以apache代理+SSL方式访问Openerpr的配置方法
</pre>
<h3>安装环境：CentOS 6.5 64bit，不保证在其它环境下本方法能安装成功。</h3>
<p>假设已经将openerp-7.0.tar.gz、postgresql-9.2.1.tar.gz、pcre-8.32.zip、apr-1.4.5.tar.gz、apr-util-1.5.1.tar.gz上传至server。
<code class="python">
    <VirtualHost *:443>
	 ServerName openerp.servername.com
	 SSLEngine On
	 SSLCertificateFile /etc/apache2/ssl/server.crt
	 SSLCertificateKeyFile /etc/apache2/ssl/server.key
	 ProxyRequests Off
	 <Proxy *>
		 Order deny,allow
		 Allow from all
	 </Proxy>
	 ProxyVia On
	ProxyPass / http://127.0.0.1:8069/
	<location / >
		ProxyPassReverse /  
	</location>
	RequestHeader set "X-Forwarded-Proto" "https"
	#Fix IE problem (httpapache proxy dav error 408/409)
	SetEnv proxy-nokeepalive 1
	RewriteEngine On
  	RewriteCond %{HTTPS} off
  	RewriteRule (.*) https://%{HTTP_HOST}%{REQUEST_URI}
    </VirtualHost>
</code>

