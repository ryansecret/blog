---
title: cookies
date: 2019-06-24 14:40:18
tags: 零碎
---
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


## mac
1. Mac 设置path  export PATH=$PATH:
1.  查看端口占用：lsof -i:3001

## npm
1. npm config edit
1. npm config set init.author.name "ryansecreat"
1. npm config set init.email='chenjingnan@jd.com’
1. npm config set init.license "MIT"
1. npm start --prefix path/to/your/folder   //指定目录下运行
1. npm repo   浏览器中打开repo
1. npm publish --registry=http://registry.npmjs.org  --registry=https://registry.npm.taobao.org
1.    

### node
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
1.http2
```text
http2基础理论

HTTP2是二进制协议
这是一个复用协议。并行的请求能在同一个链接中处理，移除了HTTP/1.x中顺序和阻塞的约束。
压缩了headers。因为headers在一系列请求中常常是相似的，其移除了重复和传输重复数据的成本。
其允许服务器在客户端缓存中填充数据，通过一个叫服务器推送的机制来提前请求。
对Alt-Svc的支持允许了给定资源的位置和资源鉴定，允许了更智能的CDN缓冲机制。
Client-Hints 的引入允许浏览器或者客户端来主动交流它的需求，或者是硬件约束的信息给服务端。
在Cookie头中引入安全相关的的前缀，现在帮助保证一个安全的cookie没被更改过。

```
1. Https https://zhuanlan.zhihu.com/p/27395037    https://blog.51cto.com/11883699/2160032
1. Ca 使用证书颁发机构的证书中的公钥去解密被颁发者的指纹算法和指纹，并计算比对指纹，正确才能验证身份
1. const { EventEmitter } = require('events’);  EventEmitter 的继承
1. Require.resovle() 获取模块的绝对路径  

### egg
1. 启动顺序
```text
Master 启动后先 fork Agent 进程
Agent 初始化成功后，通过 IPC 通道通知 Master
Master 再 fork 多个 App Worker
App Worker 初始化成功，通知 Master
所有的进程初始化成功后，Master 通知 Agent 和 Worker 应用启动成功
```

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