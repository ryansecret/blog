---
title: security
date: 2019-12-09 18:11:18
tags: web 安全
---


### xss

XSS 的原理是恶意攻击者往 Web 页面里插入恶意可执行网页脚本代码，当用户浏览该页之时，嵌入其中 Web 里面的脚本代码会被执行，从而可以达到攻击者盗取用户信息或其他侵犯用户安全隐私的目的。

1. 反射型 XSS 

一般是通过给别人发送带有恶意脚本代码参数的 URL，当 URL 地址被打开时，特有的恶意代码参数被 HTML 解析、执行。
不过一些浏览器如Chrome其内置了一些XSS过滤器，可以防止大部分反射型XSS攻击。

反射型 XSS 漏洞常见于通过 URL 传递参数的功能，如网站搜索、跳转等

非持久型 XSS 漏洞攻击有以下几点特征：

即时性，不经过服务器存储，直接通过 HTTP 的 GET 和 POST 请求就能完成一次攻击，拿到用户隐私数据。
攻击者需要诱骗点击,必须要通过用户点击链接才能发起
反馈率低，所以较难发现和响应修复
盗取用户敏感保密信息

2. 存储型 XSS

持久型 XSS 漏洞，一般存在于 Form 表单提交等交互功能，如文章留言，提交文本信息等，黑客利用的 XSS 漏洞，将内容经正常功能提交进入数据库持久保存，当前端页面获得后端从数据库中读出的注入代码时，恰好将其渲染执行。

这种攻击常见于带有用户保存数据的网站功能，如论坛发帖、商品评论、用户私信等。

持久型 XSS 有以下几个特点：

持久性，植入在数据库中
盗取用户敏感私密信息
危害面广

3.DOM xss

它不需要服务器解析响应的直接参与，触发XSS靠的是浏览器端的DOM解析，可以认为完全是客户端的事情。  解决方案通过csp: sript-src 的nonce值处理。

4.jsonp 服务端做处理

防御措施：1. httponly 2. csp 3.转义字符---现在的后端模板引擎都实现了转义 

增加攻击难度，降低攻击后果


https://xss-game.appspot.com/level1

如果用 Vue/React 技术栈，并且不使用 v-html/dangerouslySetInnerHTML 功能，就在前端 render 阶段避免 innerHTML、outerHTML 的 XSS 隐患。

### csrf

CSRF（Cross-site request forgery）跨站请求伪造：攻击者诱导受害者进入第三方网站，在第三方网站中，向被攻击网站发送跨站请求。利用受害者在被攻击网站已经获取的注册凭证，绕过后台的用户验证，达到冒充用户对被攻击的网站执行某项操作的目的。


CSRF的特点
攻击一般发起在第三方网站，而不是被攻击的网站。被攻击的网站无法防止攻击发生。
攻击利用受害者在被攻击网站的登录凭证，冒充受害者提交操作；而不是直接窃取数据。
整个过程攻击者并不能获取到受害者的登录凭证，仅仅是“冒用”。
跨站请求可以用各种方式：图片URL、超链接、CORS、Form提交等等。部分请求方式可以直接嵌入在第三方论坛、文章中，难以进行追踪。

针对已上特点：同源检测 

1. 同源检测 

在HTTP协议中，每一个异步请求都会携带两个Header，用于标记来源域名：

+ Origin Header
+ Referer Header
  这两个Header在浏览器发起请求时，大多数情况会自动带上，并且不能由前端自定义内容。 服务器可以通过解析这两个Header中的域名，确定请求的来源域

但是Origin在以下两种情况下并不存在：
 + IE11同源策略： IE 11 不会在跨站CORS请求上添加Origin标头，Referer头将仍然是唯一的标识。最根本原因是因为IE 11对同源的定义和其他浏览器有不同，有两个主要的区别，可以参考MDN Same-origin_policy#IE_Exceptions

+ 302重定向： 在302重定向之后Origin不包含在重定向的请求中，因为Origin可能会被认为是其他来源的敏感信息。对于302重定向的情况来说都是定向到新的服务器上的URL，因此浏览器不想将Origin泄漏到新的服务器上。

#### 使用Referer Header确定来源域名

根据HTTP协议，在HTTP头中有一个字段叫Referer，记录了该HTTP请求的来源地址。 对于Ajax请求，图片和script等资源请求，Referer为发起请求的页面地址。对于页面跳转，Referer为打开页面历史记录的前一个页面地址。因此我们使用Referer中链接的Origin部分可以得知请求的来源域名。

通过refer 检测，可以定义不同的refer policy 
攻击者可以在自己的请求中隐藏Referer。 
CSRF大多数情况下来自第三方域名，但并不能排除本域发起。如果攻击者有权限在本域发布评论（含链接、图片等，统称UGC），那么它可以直接在本域发起攻击，这种情况下同源策略无法达到防护的作用。

综上所述：同源验证是一个相对简单的防范方法，能够防范绝大多数的CSRF攻击。但这并不是万无一失的，对于安全性要求较高，或者有较多用户输入内容的网站，我们就要对关键的接口做额外的防护措施。

#### CSRF Token
CSRF攻击之所以能够成功，是因为服务器误把攻击者发送的请求当成了用户自己的请求。那么我们可以要求所有的用户请求都携带一个CSRF攻击者无法获取到的Token。服务器通过校验请求是否携带正确的Token，来把正常的请求和攻击的请求区分开，也可以防范CSRF的攻击。

Token是一个比较有效的CSRF防护方法，只要页面没有XSS漏洞泄露Token，那么接口的CSRF攻击就无法成功。

验证码和密码其实也可以起到CSRF Token的作用哦，而且更安全。

#### 双重Cookie验证

利用CSRF攻击不能获取到用户Cookie的特点，我们可以要求Ajax和表单请求携带一个Cookie中的值。

此方法相对于CSRF Token就简单了许多。可以直接通过前后端拦截的的方法自动化实现。后端校验也更加方便，只需进行请求中字段的对比，而不需要再进行查询和存储Token。

当然，此方法并没有大规模应用，其在大型网站上的安全性还是没有CSRF Token高，原因我们举例进行说明。

1. 用双重Cookie防御CSRF的优点：

无需使用Session，适用面更广，易于实施。
Token储存于客户端中，不会给服务器带来压力。
相对于Token，实施成本更低，可以在前后端统一拦截校验，而不需要一个个接口和页面添加。

2. 缺点：

无法使用httponly，这样造成了cookie的安全风险。
难以做到子域名的隔离。
为了确保Cookie传输安全，采用这种防御方式的最好确保用整站HTTPS的方式，如果还没切HTTPS的使用这种方式也会有风险。

Samesite Cookie属性

####Samesite Cookie属性

防止CSRF攻击的办法已经有上面的预防措施。为了从源头上解决这个问题，Google起草了一份草案来改进HTTP协议，那就是为Set-Cookie响应头新增Samesite属性，它用来标明这个 Cookie是个“同站 Cookie”，同站Cookie只能作为第一方Cookie，不能作为第三方Cookie，Samesite 有两个属性值，分别是 Strict 和 Lax，下面分别讲解：

Samesite=Strict
这种称为严格模式，表明这个 Cookie 在任何情况下都不可能作为第三方 Cookie，绝无例外。比如说 b.com 设置了如下 Cookie：

Samesite=Lax 打开链接或者页面跳转时可带Cookie

1. 另外一个问题是Samesite的兼容性不是很好，现阶段除了从新版Chrome和Firefox支持以外，Safari以及iOS Safari都还不支持，现阶段看来暂时还不能普及。
2. SamesiteCookie目前有一个致命的缺陷：不支持子域。例如，种在topic.a.com下的Cookie，并不能使用a.com下种植的SamesiteCookie。这就导致了当我们网站有多个子域名时，不能使用SamesiteCookie在主域名存储用户登录信息。每个子域名都需要用户重新登录一次。


1. 点击劫持
1. url 跳转漏洞(url 钓鱼)
1. 图片钓鱼
1. iframe 钓鱼
1. os 命令注入


strict-transport-security HTTP Strict Transport Security（通常简称为HSTS）是一个安全功能，它告诉浏览器只能通过HTTPS访问当前资源，而不是HTTP

1. post 请求，用户访问该网页后激发 2. 链接类 用户点击后激发

利用的form 表单、URL 跳转


waf:
1. Web攻击防护：帮助您防护SQL注入、XSS跨站攻击等常见的Web攻击。
1. CC攻击防护：帮助您防护针对页面请求的CC攻击。
1. 恶意IP惩罚：帮助您自动封禁在短时间内进行多次Web攻击的客户端IP。
1. 地理IP封禁：帮助您一键封禁来自指定国内省份或海外地区的IP的访问请求。


1. XST 的全称是 Cross-Site Tracing，客户端发 TRACE 请求至服务器，如果服务器按照标准实现了 TRACE 响应，则在 response body 里会返回此次请求的完整头信息。通过这种方式，客户端可以获取某些敏感的头字段，例如 httpOnly 的 Cookie。