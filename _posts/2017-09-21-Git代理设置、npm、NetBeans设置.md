---
layout:     post
title:      Git代理设置、npm、NetBeans设置
subtitle:   Spring中的AOP相关概念整理
date:       2017-09-21
author:     MK
header-img: img/post-bg-hacker.jpg
catalog: true
tags:
    - Git
    - IDE
---

# 如果你手上有代理是 http 的，那么可以这样设置

 - 通过 http 链接 clone 代码时走 http 代理
       git config --global http.proxy "http://127.0.0.1:6667"
 - 通过 https 链接 clone 代码时走 http 代理
       git config --global https.proxy "http://127.0.0.1:6667"
   设置完成后，可以 clone 一份代码试一下有没有效果。 这些设置最终会保存在用户目录下的 .gitconfig 文件中，打开这个文件可以看到类似的几行配置

	[http]
   		 proxy = http://127.0.0.1:6152
	[https]
   		 proxy = http://127.0.0.1:6152
如果端口有变动也可以直接在这里修改。

# npm的代理设置
 	npm config set proxy http://my.proxyserver.com:80

# 将默认的Netbeans中文版设置为英文界面/如何将Netbeans 6.5设置为英文界面
 - 进入netbeans8.2/etc ，其中netbeans 8.2为netbeans的安装路径。 
 - 编辑netbeans.conf 
 - 将其中的#command line switchs下面那行中增加两个启动参数： 
 -                -J-Duser.language=zh -J-Duser.country=US 变为：

   netbeans_default_options="-J-client -J-Xverify:none -J-Xss2m -J-Xms32m -J-XX:PermSize=32m -J-XX:MaxPermSize=200m -J-Dapple.laf.useScreenMenuBar=true -J-Dsun.java2d.noddraw=true -J-Duser.language=zh -J-Duser.country=US"
