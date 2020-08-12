---
title: cookies
date: 2019-06-24 14:40:18
tags: 零碎
---

:smile:
### 发版
1. 发布阶段：更新chagelog ,打 git tag 。

### word
1. analogy 类比 [əˈnælədʒi]
1. pache [ə’pætʃɪ]
2. deflate 放气，紧缩
3. Sanitize 消毒，净化
4. access [‘ækses]
5. Azure [‘æʒə]
6. avatar [‘ævətɑː]
7. ASCII [‘æski]
8. archive [‘ɑːkaɪv]
9. debt  [det]
10. typical [‘tɪpɪkl]  
11. resume [rɪ'zju:m]
12. parameter [pə’ræmɪtə] 
13. integer  [‘ɪntɪdʒə]
14. matrix [ˈmeɪtrɪks]
15. height [haɪt]
16. shallow  肤浅的 
17. tenant  租户，房客
18. coerce [kəʊˈɜːs]  强制 
19. indeterminate  [ˌɪndɪˈtɜːrmɪnət]
20. sup 一口；饮酒  
21. crumb 面包屑   
22. prune  修剪；减少；
23. Unify 整合、统一 
24. contiguous  kənˈtɪɡjuəs
### js
1. 堆
堆的底层实际上是一棵完全二叉树，可以用数组实现
每个的节点元素值不小于其子节点 - 最大堆
每个的节点元素值不大于其子节点 - 最小堆

1.  浏览器中 customevent
    
```js
var event = new CustomEvent("cat", {  detail: {    hazcheeseburger: true  }});obj.dispatchEvent(event);
```

1.  window.requestAnimationFrame() 告诉浏览器——你希望执行一个动画，并且要求浏览器在下次重绘之前调用指定的回调函数更新动画。该方法需要传入一个回调函数作为参数，该回调函数会在浏览器下一次重绘之前执行
1. Element.getBoundingClientRect() 方法返回元素的大小及其相对于视口的位置。
1.  regex  y stick 粘连修饰符 

1.普通函数在被调用时，JS引擎会创建一个栈帧，在里面准备好局部变量、函数参数、临时值、代码执行的位置（也就是说这个函数的第一行对应到代码区里的第几行机器码），在当前栈帧里设置好返回位置，然后将新帧压入栈顶。待函数执行结束后，这个栈帧将被弹出栈然后销毁，返回值会被传给上一个栈帧。

   当执行到yield语句时，Generator的栈帧同样会被弹出栈外，但Generator在这里耍了个花招——它在堆里保存了栈帧的引用（或拷贝）！这样当iter.next方法被调用时，JS引擎便不会重新创建一个栈帧，而是把堆里的栈帧直接入栈。因为栈帧里保存了函数执行所需的全部上下文以及当前执行的位置，所以当这一切都被恢复如初之时，就好像程序从原本暂停的地方继续向前执行了。

    而因为每次yield和iter.next都对应一次出栈和入栈，所以可以直接利用已有的栈机制，实现值的传出和传入。
1. Array(10)  稀疏矩阵
2. clone
```text
function initData(target) {
  return new target.constructor()
}
return Object(Symbol.prototype.valueOf.call(targe));

function cloneReg(targe) {
    const reFlags = /\w*$/;
    const result = new targe.constructor(targe.source, reFlags.exec(targe));
    result.lastIndex = targe.lastIndex;
    return result;
}
```     
1. js 在底层存储变量的时候，会在变量的机器码的低位1-3位存储其类型信息👉
   
   000：对象
   010：浮点数
   100：字符串
   110：布尔
   1：整数
   
   but, 对于 undefined 和 null 来说，这两个值的信息存储是有点特殊的。
   
   null：所有机器码均为0
   
   undefined：用 −2^30 整数来表示
1. console 分组
```javascript
console.group('action', 'A');

console.log('%c prev state', "color: #dddddd", '\n', {
    name: 'a'
});
console.log('%c next state', "color: #dddddd", '\n',  {
    name: 'b'
});

console.groupCollapsed();
console.log('我是group折叠内容');
console.groupEnd();
console.groupEnd();
```
1.  Object.create(null) 和 {}
1.  每次JavaScript对DOM的操作都会改变当前页面的呈现，并重新刷新整个页面，从而消耗了大量的时间。而createDocumentFragment()的作用，就是可以创建一个文档碎片，
把所有的新节点附加其上，然后把文档碎片的内容一次性添加到document中。

1. indexedDB 的特点：存储空间大：存储空间可以达到几百兆甚至更多；

               >> 支持二进制存储：它不仅可以存储字符串，而且还可以存储二进制数据；
               >> IndexedDB 有同源限制，每一个数据库只能在自身域名下能访问，不能跨域名访问；
               >> 支持事务型：IndexedDB 执行的操作会按照事务来分组的，在一个事务中，要么所有的操作都成功，要么所有的操作都失败；
               >> 键值对存储：IndexedDB 内部采用对象仓库（object store）存放数据。所有类型的数据都可以直接存入，包括 JavaScript 对象。对象仓库中，数据以 “键值对” 的形式保存，每一个数据记录都有对应的主键，主键是独一无二的，不能有重复，否则会抛出一个错误。
               >> 数据操作是异步的：使用 IndexedDB 执行的操作是异步执行的，以免阻塞应用程序。
5. Usecapture:
   true - 事件句柄在捕获阶段执行。事件捕获从父到子。
   false- false- 默认。事件句柄在冒泡阶段执行
1. 浏览器标签页被隐藏或显示的时候会触发visibilitychange事件. document.addEventListener('visibilitychange')
2. Object.assign 继承的否Object.keys & Object.assign & JSON.stringify: excluding non-enumerable & __proto__

3. let is not global while var is.
4. download
```javascript
function download (url, name) {
  const a = document.createElement('a')
  a.download = name
  a.rel = 'noopener'
  a.href = url
  // 触发模拟点击
  a.dispatchEvent(new MouseEvent('click'))
  // 或者 a.click()
}

// 方案一：Text -> DataURL
const dataUrl = `data:,${str}`
download(dataUrl, 'demo.json')

// 方案二：Text -> Blob -> ObjectURL
const url = URL.createObjectURL(new Blob(str.split('')))
download(url, 'demo1.json')

```  
1. stringfy 格式化
```js

const json = {
  a: 3,
  b: 4,
  c: 5
}
const str = JSON.stringify(json, null, 2)

```  
1. proxy 
```js
const negativeArray = els =>
    new Proxy(els, {
        get: (target, propKey, receiver) =>
            Reflect.get(
                target,
                +propKey < 0 ? String(target.length + +propKey) : propKey,
                receiver
            )
    });
const unicorn = negativeArray(["京", "程", "一", "灯"]);
unicorn[-1]; 
``` 
1. 能优化[1,2,5,10].sort()  默认按照字典序  
1.  对于 undeclared 变量的引用，浏览器会报引用错误，如 ReferenceError: b is not defined 。
1. Es6->babel paser->babel traverse->babel core
1.  类数组向数组转换 Array.from slice 。 aguments 就是arrarylike   
1.  xhr  
```js
 
var request = new XMLHttpRequest()
 request.open('GET', 'index/a/b/c?name=TianTian', true);
 request.onreadystatechange = function () {
   if(request.readyState === 4 && request.status === 200) {
     console.log(request.responseText);
   }};
 request.send();
```   
1. V8 对重复的js代码有优化 即时编译技术，如果发现一段代码经常使用，则不用转字节码 直接执行机器码

1. 随机字符串 Math.random().toString(36).substr(2));

2. Babel pollyfy 的作用 ：https://zhuanlan.zhihu.com/p/29058936

3. Babel stag2 的功能  https://github.com/babel/babel/tree/master/packages/babel-preset-stage-2
1. 所有的babel 包  https://github.com/babel/babel/tree/master/packages
1.  npx babel-upgrade
1. ES2019 中为Symbol对象添加了只读属性 description ，该对象返回包含Symbol描述的字符串。
1. 变量的临时死区  
1. SET 操作的时间复杂度
1. 如果你传的 context 就 null 或者 undefined，那么 window 对象就是默认的 context（严格模式下默认 context 是 undefined）
1. 高阶函数的定义
1. 作用域以及作用域链  函数作用域 —闭包
1. ES6 模块功能是它的导入模块是导出时模块的实时只读视图。（相比起 CommonJS，导入的是导出模块的拷贝副本，因此也不是实时的）。只读视图和内存拷贝的区别。
1. atob() 对经过 base-64 编码的字符串进行解码,btoa() base64加吗
1. Console.dir  显示对象所有的属性和方法
1. Broadcast Channel API 允许同一原始域和用户代理下的所有窗口,iFrames 等进行交互。也就是说，如果用户打开了同一个网站的的两个标签窗口，如果网站内容发生了变化，那么两个窗口会同时得到更新通知。
1. escape 在处理 0xff 之外字符的时候，是直接使用字符的 unicode 在前面加上一个 「%u」，而encodeURI则是先进行 UTF-8，再在 UTF-8 的每个字节码前加上一个 「%」； 所以通过encodeUrI 可以获取utf-8 字节长度
1. js value
1. Prototype 包含constructor 和 __proto__. 原型链存储共有的属性和方法，减少内存
1. 基本的数据类型 
```text
基本的数据类型
undefined
null
string
boolean
number
symbol(ES6)

```
1. navigator.userAgent: 返回当前浏览器的user agent字符串
1. 懒加载：
   Javascript 脚步通常要等到 DOM 加载完后才会执行，如果加载的资源过多，可能会影响网页的正常使用。
   能够节省流量和减轻服务器压力，更近一步就是能够为公司省成本。
1. String 和 new String 区别
1. 

```text
对象转原始类型，会调用内置的[ToPrimitive]函数，对于该函数而言，其逻辑如下：

如果Symbol.toPrimitive()方法，优先调用再返回
调用valueOf()，如果转换为原始类型，则返回
调用toString()，如果转换为原始类型，则返回
如果都没有返回原始类型，会报错
var a = {
  value: 0,
  valueOf: function() {
    this.value++;
    return this.value;
  }
};
console.log(a == 1 && a == 2);//true

```
1. Same origin 可以使用broadcast channel 两页面间通信。
1. 注意闭包内this的指向
1. 

#### 编译
1. 无论你使用的是解释型语言(JavaScript、Python、Ruby)还是编译型语言(c#、Java、Rust)，都有一个共同的部分:将源代码作为纯文本解析为 抽象语法树(abstract syntax tree, AST) 的数据结构。
1. AST 不仅以结构化的方式显示源代码，而且在语义分析中扮演着重要角色。在语义分析中，编译器验证程序和语言元素的语法使用是否正确。之后，使用 AST 来生成实际的字节码或者机器码。
1. 转义的过程：
   ```text
   编写ES6代码
   babylon 进行解析
   解析得到 AST
   plugin 用 babel-traverse 对 AST 树进行遍历转译
   得到新的 AST树
   用 babel-generator 通过 AST 树生成 ES5 代码
   ```
1. 要应用更新，Virtual DOM核心功能将发挥作用，即 协调算法，它的工作是提供最优的解决方案来解决以前和当前虚拟DOM 状态之间的差异。

## opentracing
1. Opentracing 的carrier 有多种实现，tracer 的inject（客户端进程） 和 extract（服务端进程），这样 客户端和服务端 就可以拥有相同的trace context。
1. Server 首先extract check 有没有注入的span，没有的话启动一个新的span

## mac
1. Mac 设置path  export PATH=$PATH:
1.  查看端口占用：lsof -i:3001
1. export http_proxy="http://localhost:8899"
1. Grep -A 5 显示后面5行信息
1. Mac 配置：
   Oh my zsh 
   brew install autojump  
   git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions
   git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
   plugins=(
     git zsh-autosuggestions autojump zsh-syntax-highlighting
   )
   
   
## npm
1. npm config edit
1. npm config set init.author.name "ryansecreat"
1. npm config set init.email='chenjingnan@jd.com’
1. npm config set init.license "MIT"
1. npm start --prefix path/to/your/folder   //指定目录下运行
1. npm repo   浏览器中打开repo
1. npm publish --registry=http://registry.npmjs.org  --registry=https://registry.npm.taobao.org
1. npm outdated  查看过时package
1. npm publish --tag=beta.
1. npm version patch -m "Upgrade to %s for reasons”
1. npm dist-tag add n-n-n-n@1.0.2-1 latest  将某个预发版本更新为最新   
1. npm ping [--registry <registry>]

### node
1. 
1. Node 高消耗任务：1. Regex 2. 加密、压缩、fs 同步操作 3.json.stringfy
1. epoll是event poll的简写，是Linux内核提供的一种由事件驱动的I/O通知机制。
1. 对第三方包和库做检测：NSP(Node Security Platform)
1. V8 机器码的体积要比字节码大的多，执行频率高的为热点代码，启动编译器进行编译，其它的解释器执行
1. Resovle 的任务进入微任务队列，暂停当前的协程，回到父协程
1. Npm ^ 限定minor 版本 ~限定patch 版本
1. Stream cork uncork
1. escape-html  This function will escape the following characters: ", ', &, <, and >.
1. domain模块，把处理多个不同的IO的操作作为一个组。注册事件和回调到domain，当发生一个错误事件或抛出一个错误时，domain对象会被通知，不会丢失上下文环境，也不导致程序错误立即退出，与process.on('uncaughtException')不同。
1. stream tranform
```text
const { Transform } = require('stream');

const myTransform = new Transform({
  transform(chunk, encoding, callback) {
    // ...
  }
});
```
1. 可以引入corejs实现feature
1. 性能分析
Node 性能分析，抓取火焰图 node --inspect app.js
Node  --prof-process  https://github.com/nswbmw/node-in-debugging/blob/master/1.3%20Tick%20Processor.md
 
1. 一个promise类 
```javascript
class Sleep {
then(resolve, reject){

}
}
```
1. Node 内置了pipeline  const { pipeline } = require('stream');
1. Elastic APM 是 Elastic 公司开源的一款 APM 工具
1. Error.prepareStackTrace:定制化堆栈信息    Error.captureStackTrace:隐藏内部的实现细节，优化错误栈。
1. const { EventEmitter } = require('events’);  EventEmitter 的继承
1. Require.resovle() 获取模块的绝对路径  
1. peerDependencies 相关模块安装
1. websocket 
1. cors 新浏览器
SameSite=Strict: The cookie is only sent if you are currently on the site that the cookie is set for. If you are on a different site and you click a link to a site that the cookie is set for, the cookie is not sent with the first request.
1. 主垃圾回收器：
   
   主垃圾回收器主要负责老生区中的垃圾回收。
   
   除了新生区中晋升的对象，一些大的对象会直接被分配到老生区。
   
   因此老生区中的对象有两个特点，一个是对象占用空间大，另一个是对象存活时间长。
   
1. V8 中会把堆分为新生代和老生代两个区域，
   
   新生代中存放的是生存时间短的对象，
   
   老生代中存放的生存时间久的对象。
   
   垃圾回收重要术语：
   
   代际假说
   大部分对象在内存中存在的时间很短
   不死的对象，会活得更久
   分代收集
   副垃圾回收器：
   
   主要负责新生代的垃圾回收。
   
   这个区域不大，但是垃圾回收比较频繁。
   
   新生代的垃圾回收算法是 Scavenge 算法。
   
   主要把新生代空间对半划分为两个区域：对象区域，空闲区域。
   
   当对象区域快被写满时，则会进行一次垃圾清理。
   


```text
WebSocket 使用了自定义的二进制分帧格式，把每个应用消息切分成一或多个帧，发送到目的地之后再组装起来，等到接收到完整的消息后再通知接收端。基本的成帧协议定义了帧类型有操作码、有效载荷的长度，指定位置的Extension data和Application data，统称为Payload data，保留了一些特殊位和操作码供后期扩展。在打开握手完成后，终端发送一个关闭帧之前的任何时间里，数据帧可能由客户端或服务器的任何一方发送。

• 帧：最小的通信单位，包含可变长度的帧首部和净荷部分，净荷可能包含完整或部分应用消息。
• 消息：一系列帧，与应用消息对等。
```
1. jwt 签名算法
```text
HS256 使用密钥生成固定的签名，RS256 使用成非对称进行签名。简单地说，HS256 必须与任何想要验证 JWT的 客户端或 API 共享秘密。
RS256 生成非对称签名，这意味着必须使用私钥来签签名 JWT，并且必须使用对应的公钥来验证签名。与对称算法不同，使用 RS256 可以保证服务端是 JWT 的签名者，因为服务端是唯一拥有私钥的一方。这样做将不再需要在许多应用程序之间共享私钥

这种方法可以让我们分离开签发与验证，签发时需要用一个密钥，验证时使用公钥，也就是有公钥的地方只能做验证，但不能签发 JWT。
```
### egg
1. 启动顺序
```text
Master 启动后先 fork Agent 进程
Agent 初始化成功后，通过 IPC 通道通知 Master
Master 再 fork 多个 App Worker
App Worker 初始化成功，通知 Master
所有的进程初始化成功后，Master 通知 Agent 和 Worker 应用启动成功
```
### 网络
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

### html
1. 优雅降级 graceful degradation： 一开始就构建完整的功能，然后再针对低版本的浏览器进行兼容。
1. aside  定义页面的侧边栏内容。
   progress 原生的进度条

1.  HTML `<sup>` 元素定义了一个文本区域，出于排版的原因，与主要的文本相比，应该展示得更高并且更小。
1. domPropsInnerHTML  domPropsInnerText
1. 根据 canvas 可以获取浏览器指纹信息
```text

绘制 canvas，获取 base64 的 dataurl
对 dataurl 这个字符串进行 md5 摘要计算，得到指纹信息
```
1. 一些性能要求极高的应用中虚拟 DOM 无法进行针对性的极致优化。比如VScode采用直接手动操作DOM的方式进行极端的性
1. 事件传播有三个阶段：
```text
捕获阶段–事件从 window 开始，然后向下到每个元素，直到到达目标元素事件或event.target。
目标阶段–事件已达到目标元素。
冒泡阶段–事件从目标元素冒泡，然后上升到每个元素，直到到达 window。

```

1.  将图片等未处理的文件放在assets中，打包减少体积。而对于第三方引入的一些资源文件如iconfont.css等可以放在static中，因为这些文件已经经过处理了
1. 浏览器 Context Group 是一组共享相同上下文的 tab、window或iframe。例如，如果网站（https://a.example）打开弹出窗口（https://b.example），则打开器窗口和弹出窗口共享相同的浏览上下文，并且它们可以通过 DOM API相互访问，例如 window.opener。
1. 影响dom解析以及渲染都会出现白屏的问题
1. V8 内存空间越大，执行时间越长，为了性能，限制了
1. 1.当 onload 事件触发时，页面上所有的DOM，样式表，脚本，图片，flash都已经加载完成了。
   
   2.当 DOMContentLoaded 事件触发时，仅当DOM加载完成，不包括样式表，图片，flash。
1. Host 支持虚拟站点
1. 
1. 如果有js 在header 中，js会等待css 加载完毕。
1. Object.prototype 是浏览器底层根据 ECMAScript 规范创造的一个对象。
1.  重绘 只是影响元素的外观和风格，不影响布局的  回流：元素的布局、隐藏等改变需要重新构建
1.   data-为前端开发者提供自定义属性，这些属性集可以通过对象的dataset属性获取，
1. 因为 DOM 是属于渲染引擎中的东西，而 JS 又是 JS 引擎中的东西。当我们通过 JS 操作 DOM 的时候，其实这个操作涉及到了两个线程之间的通信，那么势必会带来一些性能上的损耗。
1. link属于HTML标签，而@import是CSS提供的页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载
1. Web quality  : alt
1. 该WindowEventHandlers.onstorage属性包含一个在storage事件触发时运行的事件处理程序。当更改存储区域时会发生这种情况（例如，存储新项目）。
```javascript
   window.onstorage = function(e) { console.log('The ' + e.key + ' key has been changed from ' + e.oldValue + ' to ' + e.newValue + '.'); };
```
1. navigator.sendBeacon() 方法可用于通过HTTP将少量数据异步传输到Web服务器。
1. preload：  直接请求
   prefetch： 空闲时间请求
   
1. <link rel="dns-prefetch" href="//baidu.com”>
   比较小的图片例如icon，使用base64编码，可以减少一次图片的网络请求；
1. cache control 
```text
private：客户端可以缓存--打开新的窗口会重新访问、地址栏回车时第一次访问、后退不访问
public：客户端和代理服务器都可以缓存
max-age=t：缓存内容将在t秒后失效
no-cache：需要使用协商缓存来验证缓存数据
no-store：所有内容都不会缓存

```   
1. 我们可以使用 requestIdleCallback() 在浏览器空闲时运行高耗时、低优先级的任务。
  
1. 由于GUI渲染线程与JavaScript执行线程是互斥的关系，当浏览器在执行JavaScript程序的时候，GUI渲染线程会被保存在一个队列中，直到JS程序执行完成，才会接着执行。因此如果JS执行的时间过长，这样就会造成页面的渲染不连贯，导致页面渲染加载阻塞的感觉。
1. 浏览器定时计数器并不是由JavaScript引擎计数的, 因为JavaScript引擎是单线程的, 如果处于阻塞线程状态就会影响记计时的准确, 因此通过单独线程来计时并触发定时是更为合理的方案。
1.  当一个事件被触发时该线程会把事件添加到待处理队列的队尾，等待JS引擎的处理。这些事件可以是当前执行的代码块如定时任务、也可来自浏览器内核的其他线程如鼠标点击、AJAX异步请求等，但由于JS的单线程关系所有这些事件都得排队等待JS引擎处理。

1.   在XMLHttpRequest在连接后是通过浏览器新开一个线程请求， 将检测到状态变更时，如果设置有回调函数，异步线程就产生状态变更事件放到 JavaScript引擎的处理队列中等待处理。
1. dom树构建完成后document对象会派发事件DOMContentLoaded来通知dom树已构建完成。
   DOMContentLoaded事件用来标识dom树构建完成，那如何判断另外这些非阻塞型的资源加载完成呢？答案是window.onload。由于该事件派发的过晚，因此一般情况下我们用不着，而更多的是用DOMContentLoaded来尽早的的操作dom。
  
### vim 
j: 下移一行；

k: 上移一行；

w: 前移一个单词，光标停在下一个单词开头；

e: 前移一个单词，光标停在下一个单词末尾；

0: 移动到行首。

$: 移动到行尾。

n|: 把光标移到递n列上

zz: 将当前行移动到屏幕中央。

o: 在下面新建一行插入；

O: 在上面新建一行插入；

a: 在光标后插入；

A: 在当前行最后插入；

u: 取消一(n)个改动。

ctrl + r: 重做最后的改动。