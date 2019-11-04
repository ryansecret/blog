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
  
   http header 中使用location 进行302跳转 
   
   URL.createObjectURL() 静态方法会创建一个 DOMString，其中包含一个表示参数中给出的对象的URL。这个 URL 的生命周期和创建它的窗口中的 document 绑定。这个新的URL 对象表示指定的 File 对象或 Blob 对象。

####http 
```text
http 1.1 添加cache-contol 

长连接：HTTP1.0需要使用keep-alive参数来告知服务器建立一个长连接，而HTP1.1默认支持长连接
节约宽带：HTTP1.1支持只发送一个header信息（不带任何body信息）
host域（设置虚拟站点，也就是说，web server上的多个虚拟站点可以共享同一个ip端口）：HTTP1.0没有host域


http 2.0
采用二进制格式传输;
多路复用，其实就是将请求数据分成帧乱序发送到 TCP 中。TCP 只能有一个 steam，所以还是会阻塞;
报头压缩;
服务器推送主动向 B 端发送静态资源，避免往返延迟。
1.http2采用的二进制文本传输数据，而非http1文本格式，二进制在协议的解析和扩展更好
2.数据压缩：对信息头采用了HPACK进行压缩传输，节省了信息头带来的网络流量
3.多路复用：一个连接可以并发处理多个请求
4.服务器推送：我们对支持HTTP2.0的web server请求数据的时候，服务器会顺便把一些客户端需要的资源一起推送到客户端，免得客户端再次创建连接发送请求到服务器端获取。这种方式非常合适加载静态资源

http 3.0
采用 QUIC 协议,自定义连接机制;自定义重传机制;无阻塞的多路复用

2.按缓存分：强缓存和协商缓存：
2.1强缓存：利用 cache-control 和 expires 设置，直接返回一个过期时间，所以在缓存期间不请求，If-modify-since；
2.2协商缓存：响应头返回 etag 或 last-modified 的哈希值，第二次请求头 If-none-match 或 IF-modify-since 携带上次哈希值，一致则返回 304。
F5 刷新会忽略强缓存不会忽略协商缓存，ctrl+f5 都失效
```       

1. Https https://zhuanlan.zhihu.com/p/27395037    https://blog.51cto.com/11883699/2160032
1. Ca 使用证书颁发机构的证书中的公钥去解密被颁发者的指纹算法和指纹，并计算比对指纹，正确才能验证身份