---
title: node
date: 2020-08-13 16:18:08
tags: node、egg 
---
1.  V8 浏览器会自动执行垃圾回收，但由于 JavaScript 也是运行在主线程上的，一旦执行垃圾回收，就要打断 JavaScript 的运行，可能会或多或少的造成页面的卡顿，影响用户体验，所以 V8 决定采用增量 标记算法回收：
   即把垃圾回收拆成一个个小任务，穿插在 JavaScript 中执行。
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