---
title: 深入解析Servlet
date: 2018-03-23 17:11:30
categories: JavaWeb
tags:
- "JavaWeb"
- "Servlet"
---
以为servlet是很复杂的东西，**事实上，servlet就是一个Java接口**，interface! 打开idea，ctrl + shift + n，搜索servlet，就可以看到是一个只有5个方法的interface!  

所以，提问中说的网络协议、http什么的，servlet根本不管！也管不着！ 

那servlet是干嘛的？很简单，接口的作用是什么？规范呗！

servlet接口定义的是一套处理网络请求的规范，所有实现servlet的类，都需要实现它那五个方法，其中最主要的是两个生命周期方法 init()和destroy()，还有一个处理请求的service()，也就是说，所有实现servlet接口的类，或者说，所有想要处理网络请求的类，都需要回答这三个问题：
1. 你初始化时要做什么
2. 你销毁时要做什么
3. 你接受到请求时要做什么

这是Java给的一种规范！就像阿西莫夫的机器人三大定律、行尸走肉里Rick的那三个问题一样，规范！  

servlet是一个规范，那实现了servlet的类，就能处理请求了吗？

**答案是，不能。**

你可以随便谷歌一个servlet的hello world教程，里面都会让你写一个servlet，相信我，**你从来不会在servlet中写什么监听8080端口的代码，servlet不会直接和客户端打交道！**  

那请求怎么来到servlet呢？答案是servlet容器，比如我们最常用的tomcat，同样，你可以随便谷歌一个servlet的helloworld教程，里面肯定会让你把servlet部署到一个容器中，不然你的servlet压根不会起作用。  

**tomcat才是与客户端直接打交道的家伙**，他监听了端口，请求过来后，根据url等信息，确定要将请求交给哪个servlet去处理，然后调用那个servlet的service方法，service方法返回一个response对象，tomcat再把这个response返回给客户端。

作者：Javdroider Hong
链接：https://www.zhihu.com/question/21416727/answer/339012081
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。
