---
title: cookies
date: 2019-06-24 14:40:18
tags: 零碎
---

:smile:
### 发版
1. 发布阶段：更新chagelog ,打 git tag 。

### word
1. deflate 放气，紧缩
1. Sanitize 消毒，净化
1. 
### js

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
1. 

  
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