---
title: fresh
date: 2020-06-04 10:33:26
tags:
---

1. ① 不能通过 new 关键字调用, 没有原型
   ② 不可以改变 this 绑定，由外层非箭头函数决定，所以使用 call, apply, bind 也不会影响
   ③ 不支持 arguments，所以根据作用域链，会拿到外层函数的 arguments
   ④ 不支持重复命名参数
   ⑤ 隐式返回
1. v-once v-pre
1. readystate  
```text
 是HTTP请求的状态，当一个XMLHttpRequest初次创建时，这个属性的值从0开始，直到接收到完整的HTTP响应，这个值增加到4
 
4：（完成）数据接收完毕，此时可以通过responseXml和responseText获取完整的回应数据
```
1. babel-register 则提供了动态编译。换句话说，我们的源代码能够真正运行在生产环境下，不需要 babel 编译这一环节。坏处是动态编译，导致程序在速度、性能上有所损耗。（ npx babel-node app.js） babel-node

1. UMD先判断是否支持Node.js的模块（exports）是否存在，存在则使用Node.js模块模式。再判断是否支持AMD（define是否存在），存在则使用AMD方式加载模块。
1. Ztext.js 3d化文本支持中文
1. Data URLs 由四个部分组成：前缀(data:)、指示数据类型的MIME类型、如果非文本则为可选的base64标记、数据本身：
```text
data:[<mediatype>][;base64],<data>
mediatype 是个 MIME 类型的字符串，例如 "image/jpeg" 表示 JPEG 图像文件。如果被省略，则默认值为 text/plain;charset=US-ASCII

如果数据是文本类型，你可以直接将文本嵌入 (根据文档类型，使用合适的实体字符或转义字符)。如果是二进制数据，你可以将数据进行base64编码之后再进行嵌入。

下面是一些示例：

data:,Hello%2C%20World!
简单的 text/plain 类型数据
data:text/plain;base64,SGVsbG8sIFdvcmxkIQ%3D%3D
上一条示例的 base64 编码版本
data:text/html,%3Ch1%3EHello%2C%20World!%3C%2Fh1%3E
一个HTML文档源代码 <h1>Hello, World</h1>
data:text/html,<script>alert('hi');</script>
一个会执行 JavaScript alert 的 HTML 文档。注意 script 标签必须封闭。

```
1. Url-loader 是将资源转换为base64
4. 浏览器进程 1. 插件 2. 网络 3.Gpu 4.浏览器 5.渲染进程 浏览器为每个tab创建一个渲染进程，运行在沙箱模式下。包括 gui 线程等。

1.  jest.spyOn()方法同样创建一个mock函数，但是该mock函数不仅能够捕获函数的调用情况，还可以正常的执行被spy的函数。实际上，jest.spyOn()是jest.fn()的语法糖，它创建了一个和被spy的函数具有相同内部代码的mock函数。
 
2.  Vue Test Utils 允许你通过 shallowMount 方法只挂载一个组件而不渲染其子组件 (即保留它们的存根)：
    

12. 而对于作用域插槽，父组件在编译和渲染阶段并不会直接生成 vnodes，而是在父节点 vnode 的 data 中保留一个 scopedSlots 对象，存储着不同名称的插槽以及它们对应的渲染函数，
只有在编译和渲染子组件阶段才会执行这个渲染函数生成 vnodes，由于是在子组件环境执行的，所以对应的数据作用域是子组件实例。


1. 红黑树
其实红黑树和上面的平衡二叉树类似，本质上都是为了解决排序二叉树在极端情况下退化成链表导致检索效率大大降低的问题，
```text
1.节点是红色或黑色。

2.根节点是黑色。

3.每个叶子节点都是黑色的空节点（NIL节点）。

4 每个红色节点的两个子节点都是黑色。(从每个叶子到根的所有路径上不能有两个连续的红色节点)

5.从任一节点到其每个叶子的所有路径都包含相同数目的黑色节点。

```



2. 这种可以并行执行、交换执行权的线程（或函数），就称为协程。
   
   从实现上看，在内存中，子例程只使用一个栈（stack），而协程是同时存在多个栈，但只有一个栈是在运行状态，也就是说，协程是以多占用内存为代价，实现多任务的并行。
   普通的线程是抢先式的，到底哪个线程优先得到资源，必须由运行环境决定，但是协程是合作式的，执行权由协程自己分配。
   
 


