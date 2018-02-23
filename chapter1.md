# OIDC在 ASP.NET Core中的应用

我们在《ASP.NET Core项目实战的课程》第一章里面给identity server4做了一个全面的介绍和示例的练习 。

如果想完全理解本文所涉及到的话题，你需要了解的背景知识有：

* 什么是OpenId Connect \(OIDC\)Identity Server4又是什么

* ASP.NET Core的权限体系中的OIDC认证框架（客户端）

* Identity Server4提供的OIDC认证服务（服务端）

* 客户端与服务端的集成

### 什么是 OIDC

在了解OIDC之前，我们先看一个很常见的场景。假使我们现在有一个网站要集成微信或者新浪微博的登录，两者现在依然采用的是oAuth 2.0的协议来实现 。如果不熟悉oAauth2.0的同学建议去复习一下（OIDC也是建议在oAauth2.0协议之上） 同时关于微信和新浪微博的登录大家可以去看看它们的开发文档。

在我们的网站集成微博或者新浪微博的过程大致是分为四步：

1. 准备工作：在微信/新浪微博开发平台注册一个应用，得到AppId和AppSecret

2. 发起 oAauth2.0 中的 Authorization Code流程请求Code

3. 根据Code再请求AccessToken（通常在我们应用的后端完成，用户不可见）

4. 根据 AccessToken 访问微信/新浪微博的某一个API，来获取用户的信息



