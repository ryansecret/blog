---
title: http
date: 2019-05-14 15:17:39
tags: http
---

#### Quic 
1. 多路复用，避免队头阻塞
1. 减少 RTT，请求更快速
1. 快速迭代，广泛支持

传统的 HTTP2 + SSL + TCP 协议栈有哪些缺点？
1.SSL 的会话恢复依然需要一个 RTT，而且难以合并到 TCP 层
1. TCP 的滑动窗口存在队头阻塞问题
1. TCP 的重传纠错会浪费一个 RTT

网络请求中一个常见的名词是 RTT(Round Trip Time)，表示客户端从发出一个请求数据，到接收到响应数据之间间隔的时间。

#### Dns 本地dns解析器和host->本地dns服务器 
#### http 请求限制
默认情况下，浏览器会针对这些情况使用同一个连接：

同一域名下的资源；

不同域名下的资源，但是满足两个条件：1）解析到同一个 IP；2）使用同一个证书；

使用多域名加上相同的 IP 和证书部署 Web 服务有特殊的意义：让支持 HTTP/2 的终端只建立一个连接，用上 HTTP/2 协议带来的各种好处；而只支持 HTTP/1.1 的终端则会建立多个连接，达到同时更多并发请求的目的。这在 HTTP/2 完全普及前也是一个不错的选择。

####cors
简单请求 可以直接发不用预检。简单请求
1. Content-Type：只限于三个值application/x-www-form-urlencoded、multipart/form-data、text/plain
1. Method head,get,post


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

1. 缓存的分类：
```text
   强缓存：在缓存数据未失效的情况下，不需要再和服务器发生交互.cache-control :no-cache 走协商缓存
   协商缓存：需要与服务端校验是否使用缓存。etag If-None-Match HTTP 请求头内提供 ETag
```


1. https 
```text
这些ＣＡ本身也有证书来证明自己的身份，并且ＣＡ的信用是像树一样分级的，高层的ＣＡ给底层的ＣＡ做信用背书，而操作系统／浏览器中会内置一些顶层的ＣＡ的证书，相当于你自动信任了他们。　

公钥+个人信息+其它信息—》hash 算法 —》信息摘要-》用ca的私钥加密—》数字签名   签名+信息=数字证书 
Ca 的公钥解密—》hash hash 算法 —》信息摘要-》对比是否一致

```

1. content-type
```text
multipart/form-data

请求消息头中, Content-Type: multipart/form-data; boundary=----WebKitFormBoundarykALcKBgBaI9xA79y
boundary为分隔符.

application/x-www-form-urlencoded
```

1. Nat network adreess translation 网络地址转换.
  当访问外网时自动分配一个端口，这个端口和内网的机器建立了映射关系。
1. Defer

   这个属性的用途是表明脚本在执行时不会影响页面的构造。也就是说，脚本会被延迟到整个页面都解析完毕后再运行。因此，在script元素中设置defer属性，相当于告诉浏览器立即下载，但延迟执行。
   但与defer不同的是，标记为async的脚本并不保证按照它们的先后顺序执行。
1.    在 http 1.1 中，在响应头中设置 keep-alive 可以在一个 TCP 连接上发送多个 http 请求
      
      避免了重开 TCP 连接的开销
      避免了刷新时重新建立 SSL 连接的开销
      避免了QPS过大时，服务器的连接数过大
      
1. 缓存协商
 
 ```text
我们知道协商缓存有两种方式

Last-Modified/if-Modified-Since  ** Last-Modified 是由一个 unix timestamp 表示，则意味着它只能作用于秒级的改变**
ETag/If-None-Match
```     
1. window.opener 表示打开当前窗体页面的的父窗体的是谁。例如，在 A 页面中，通过一个带有 target="_blank" 的 a 标签打开了一个新的页面 B，那么在 B 页面里，window.opener 的值为 A 页面的 window 对象。   rel=noopener 规定禁止新页面传递源页面的地址，通过设置了此属性的链接打开的页面，其 window.opener 的值为 null。
1. Gzip 不要使用再图片以及其它二进制文件上

1. 302 临时重定向会改变method  
502  收到了上游相应但是无法解析  
504 上游解析超时
1. gzip 使用了 LZ77 算法与 Huffman 编码来压缩文件，重复度越高的文件可压缩的空间就越大
1. Etag etag = '{:x}-{:x}'.format(header.last_modified, header.content_lenth)
1. Mtime 文件最近内容改变的时间
1. https 解决三个安全问题 1. 内容隐私 2. 防篡改 3.身份认证
1. LRU AND LFU  最久未使用 最少使用
1. [浏览器进程](https://user-gold-cdn.xitu.io/2020/1/7/16f7ee19a85b3c8f?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)
1. 
HTTP/2引入二进制数据帧和流的概念，其中帧对数据进行顺序标识，如下图所示，这样浏览器收到数据之后，就可以按照序列对数据进行合并，而不会出现合并后数据错乱的情况。同样是因为有了序列，服务器就可以并行的传输数据，这就是流所做的事情。http2 静态资源的推送
1. 查看network请求发现，每一个文件都有etag响应头，如果Nginx使用了已有的gz文件，那么这个请求的etag值不带有W/，反之，如果是文件是Nginx压缩的，etag值则会带有W/

1. 总是设置 Vary: Origin，避免 CDN 缓存破坏 CORS 配置
2. QUIC 基于 UDP，UDP 的数据包在接收端没有处理顺序，即使中间 丢失一个包，也不会阻塞整条连接，其他的资源会被正常处理。
1. 30X 区分
```text
301，Moved Permanently。永久重定向，该操作比较危险，需要谨慎操作：如果设置了301，但是一段时间后又想取消，但是浏览器中已经有了缓存，还是会重定向。
302，Fount。临时重定向，但是会在重定向的时候改变 method: 把 POST 改成 GET，于是有了 307
307，Temporary Redirect。临时重定向，在重定向时不会改变 method
```

1.  Tcp 的滑动窗口增大了吞吐量，但是并没有解决队头堵塞得问题
1.  http 挥手 主动关闭有个time_wait,这个标准的持续时间是4分钟

      ISN(Initial Sequence Number) 是固定的么，
     
      客户端的syn_send 状态、服务端的syn_rcvd
      
      Tcp 报文段：tcp 首部+tcp 数据部分
     
      半链接队列—超时重传
      
      等待2个msl 确保服务端能收到ack,能正常关闭
     
      关闭连接时，当收到对方的FIN报文时，仅仅表示对方不再发送数据了但是还能接收数据，己方也未必全部数据都发送给对方了，所以己方可以立即close，也可以发送一些数据给对方后，再发送FIN报文给对方来表示同意现在关闭连接，因此，己方ACK和FIN一般都会分开发送。
2. 如果 300 的话会进行重定向，这里会有个重定向计数器，避免过多次的重定向，超过次数也会报错。 

3. 而HTTP的204(No Content)响应, 就表示执行成功, 但是没有数据, 浏览器不用刷新页面.也不用导向新的页面.  
     205 Reset Content, 表示执行成功, 重置页面(Form表单).

1. 子网是所属VPC IP地址范围内的 IP 地址块。目前私有网络中的云资源部署在子网内，如云主机、容器、负载均衡等。子网：子网是对VPC地址空间的再一次划分，用户可以在子网中创建云主机。

1. 可用区（Availability Zone）是电力及网络之间互相独立的物理区域，相同可用区内的实例之间较之同地域不同可用区内实例之间的网络延时更小。同地域内不同可用区之间提供内网互通环境，可用区之间可做到故障隔离。
  若您的业务要求有较低网络时延，建议将实例或者Pod部署在同一可用区内。
1. VPC：VPC是用户网络在京东云上的表现形式，包含了一系列的网络功能，与其他的VPC逻辑隔离。VPC有一个网络地址空间，用户可以在其中继续划分子网。
1. NAT 地址网络转换，通过在路由器上安装 NAT 软件，它至少有一个有效的公网 IP 地址，通过 NAT 路由器将内部私有 IP 转换成公网 IP。它的问题在于 NAT 设备自动屏蔽了非内网主机主动发起的连接，也就是说，从外网发往内网的数据包将被 NAT 设备丢弃，这使得位于不同 NAT 设备之后的主机之间无法直接交换信息.
  
1. 503 服务器资源不足问题导致的拒绝服务，比如熔断。
1. Options  
```text
   1. 检测服务支持的method
   2. Cors 预检
```
1. HTTP HEAD 方法 请求资源的头部信息, 并且这些头部与 HTTP GET 方法请求时返回的一致. 该请求方法的一个使用场景是在下载一个大文件前先获取其大小再决定是否要下载, 以此可以节约带宽资源.
1. WebSocket是基于Http协议的，或者说借用了Http协议来完成一部分握手，在握手阶段与Http是相同的。我们来看一个websocket握手协议的实现，基本是2个属性，upgrade，connection。
```text
Upgrade:webSocket
Connection:Upgrade
```     