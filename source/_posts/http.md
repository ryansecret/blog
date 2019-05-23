---
title: http
date: 2019-05-14 15:17:39
tags: http
---

####XST 的全称是 Cross-Site Tracing

    客户端发 TRACE 请求至服务器，如果服务器按照标准实现了 TRACE 响应，则在 response body 里会返回此次请求的完整头信息。通过这种方式，客户端可以获取某些敏感的头字段，例如 httpOnly 的 Cookie。

    TRACE方法让客户端测试到服务器的网络通路，回路的意思如发送一个请返回一个响应，这就是一个请求响应回路

####Set-Cookie
    用于设置Cookie。
    
    Set-Cookie: name=value; secure; HttpOnly
    secure 只在进行HTTP通信时发送Cookie。
    HttpOnly 指定不能从JavaScript脚本代码访问Cookie值。
    
 ####X-Download-Options: noopen
    noopen 用于指定IE 8以上版本的用户不打开文件而直接保存文件。在下载对话框中不显示“打开”选项。
 
 ####keepalive 
 
    若connection 模式为close，则服务器主动关闭TCP连接，客户端被动关闭连接，释放TCP连接;若connection 模式为keepalive，则该连接会保持一段时间，在该时间内可以继续接收请求;   
    http 1.0中默认是关闭的，需要在http头加入"Connection: Keep-Alive"，才能启用Keep-Alive；http 1.1中默认启用Keep-Alive，如果加入"Connection: close "，才关闭。目前大部分浏览器都是用http1.1协议，也就是说默认都会发起Keep-Alive的连接请求了，所以是否能完成一个完整的Keep-Alive连接就看服务器设置情况。
    
 ####headers
 
 Accept-Charset： 浏览器申明自己接收的字符集 
 Accept-Encoding： 浏览器申明自己接收的编码方法，通常指定压缩方法，是否支持压缩，支持什么压缩方法（gzip，deflate） 
 
  Age：当代理服务器用自己缓存的实体去响应请求时，用该头部表明该实体从产生到现在经过多长时间了。   