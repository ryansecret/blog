---
title: fresh
date: 2020-06-04 10:33:26
tags:
---

1. 提高性能
```text

压缩代码
提取页面公共资源 基础包cdn\splitchunks
Tree shaking 
scope hoisting
图片压缩 
动态polyfill 

```

1. 哪些操作会造成内存泄漏？
```text
1.意外的全局变量
2.被遗忘的计时器或回调函数
3.脱离 DOM 的引用
4.闭包
```
  
1. CSS3中，伪类与伪元素在语法上也有所区别，伪元素修改为以::开头。
   
``` text
伪元素控制的内容和元素是没有差别的，但是它本身只是基于元素的抽象，并不存在于⽂档中，所以称为伪元素。⽤于将特殊的效果添加到某些选择器
伪类：其核⼼就是⽤来选择DOM树之外的信息,不能够被普通选择器选择的⽂档之外的元素，⽤来添加⼀些选择器的特殊效果。
⽐如:hover :active :visited :link :visited :first-child :focus :lang等

伪类和伪元素都不出现在源⽂件和DOM树中。也就是说在html源⽂件中是看不到伪类和伪元素的。
不同之处：
伪类其实就是基于普通DOM元素⽽产⽣的不同状态，他是DOM元素的某⼀特征。
伪元素能够创建在DOM树中不存在的抽象对象，⽽且这些抽象对象是能够访问到的。
```

1. DOMContentLoaded事件触发时：仅当DOM解析完成后，不包括样式表，图片等资源。
```text

CSS不会阻塞DOM解析，但会阻塞DOM渲染。
CSS会阻塞JS执行，并不会阻塞JS文件下载
``` 

2. prototype
```text
   function f() {}
var a = f.prototype, b = Object.getPrototypeOf(f);
a === b    
解析：a是构造函数f的原型 ： {constructor: ƒ}
b是实例f的原型对象 ： ƒ () { [native code] }
```

2. 只要出现多个插槽，请始终为所有的插槽使用完整的基于`<template>`  的语法
```html
   <current-user>
   <template v-slot:default="slotProps">
    {{ slotProps.user.firstName }}
  </template>

  <template v-slot:other="otherSlotProps">
    ...
  </template> 
</current-user>
```

2. 作用域插槽 this.$scopedSlots.header({ text: this.headerText })


3. 匹配驼峰： ([\:\-\_]+(.))

4. Vue.config.optionMergeStrategies  
  
6. Bem 是块（block）、元素（element）、修饰符（modifier）的简写，由 Yandex 团队提出的一种前端 CSS 命名方法论。
   
   `-` 中划线 ：仅作为连字符使用，表示某个块或者某个子元素的多单词之间的连接记号。

   __ 双下划线：双下划线用来连接块和块的子元素

   _ 单下划线：单下划线用来描述一个块或者块的子元素的一种状态

7.  HTMLElement.offsetParent 是一个只读属性，返回一个指向最近的（指包含层级上的最近）包含该元素的定位元素或者最近的 table,td,th,body元素。当元素的 style.display 设置为 "none" 时，offsetParent 返回 null。offsetParent 很有用，因为 offsetTop 和 offsetLeft 都是相对于其内边距边界的。
   
8.  jest.spyOn()方法同样创建一个mock函数，但是该mock函数不仅能够捕获函数的调用情况，还可以正常的执行被spy的函数。实际上，jest.spyOn()是jest.fn()的语法糖，它创建了一个和被spy的函数具有相同内部代码的mock函数。
 
9.  Vue Test Utils 允许你通过 shallowMount 方法只挂载一个组件而不渲染其子组件 (即保留它们的存根)：
    Vue beforecreated:data vue 实例化、init events
 
10. 首先通过 Vue.options = Object.create(null) 创建一个空对象，然后遍历 ASSET_TYPES: 
    Vue.options.components = {}
    Vue.options.directives = {} 
    Vue.options.filters = {}

11. 对于渲染 watcher 而言，它在执行 this.get() 方法求值的时候，会执行 getter 方法： updateComponent = () => {
   updateComponent = () => { vm._update(vm._render(), hydrating)

12. 而对于作用域插槽，父组件在编译和渲染阶段并不会直接生成 vnodes，而是在父节点 vnode 的 data 中保留一个 scopedSlots 对象，存储着不同名称的插槽以及它们对应的渲染函数，
只有在编译和渲染子组件阶段才会执行这个渲染函数生成 vnodes，由于是在子组件环境执行的，所以对应的数据作用域是子组件实例。

1. 这里对该vm注册一个Watcher实例，Watcher的getter为updateComponent函数，用于触发所有渲染所需要用到的数据的getter，进行依赖收集，就是在mounted的时候进行依赖收集。

用户的自定义 watcher 要优先于渲染 watcher 执行；因为用户自定义 watcher 是在渲染 watcher 之前创建的。Vm._watcher.update()

1. Dep 是一个 Class，它定义了一些属性和方法，这里需要特别注意的是它有一个静态属性 target，这是一个全局唯一 Watcher，这是一个非常巧妙的设计，
因为在同一时间只能有一个全局的 Watcher 被计算，另外它的自身属性 subs 也是 Watcher 的数组。

1. Observer 是一个类，它的作用是给对象的属性添加 getter 和 setter，用于依赖收集和派发更新。Render 时通过getter 进行依赖收集。

2. Service Worker 是运行在浏览器背后的独立线程，一般可以用来实现缓存功能。使用 Service Worker的话，传输协议必须为 HTTPS。

1. 函数式组件与普通组件的区别
   
   函数式组件需要在声明组件是指定functional
   函数式组件不需要实例化，所以没有this,this通过render函数的第二个参数来代替
   函数式组件没有生命周期钩子函数，不能使用计算属性，watch等等
   函数式组件不能通过$emit对外暴露事件，调用事件只能通过context.listeners.click的方式调用外部传入的事件
   因为函数式组件是没有实例化的，所以在外部通过ref去引用组件时，实际引用的是HTMLElement
   函数式组件的props可以不用显示声明，所以没有在props里面声明的属性都会被自动隐式解析为prop,而普通组件所有未声明的属性都被解析到$attrs里面，并自动挂载到组件根元素上面(可以通过inheritAttrs属性禁止)

2. 红黑树
其实红黑树和上面的平衡二叉树类似，本质上都是为了解决排序二叉树在极端情况下退化成链表导致检索效率大大降低的问题，
```text
1.节点是红色或黑色。

2.根节点是黑色。

3.每个叶子节点都是黑色的空节点（NIL节点）。

4 每个红色节点的两个子节点都是黑色。(从每个叶子到根的所有路径上不能有两个连续的红色节点)

5.从任一节点到其每个叶子的所有路径都包含相同数目的黑色节点。

```

1. 
「适合引入自动化测试的场景：」

公共库类的开发维护
中长期项目的迭代/重构
引用了不可控的第三方依赖

1. BST 查询二叉树
若任意节点的左⼦子树不不空，则左⼦子树上所有结点的值均⼩小于它的 根结点的值;
若任意节点的右⼦子树不不空，则右⼦子树上所有结点的值均⼤大于它的 根结点的值;
任意节点的左、右⼦子树也分别为⼆二叉查找树。

1. 管道符放到尾部：Hello(?:World|China|) 可以匹配 HelloWorld、HelloChina，也可以只匹配 Hello。


2. 这种可以并行执行、交换执行权的线程（或函数），就称为协程。
   
   从实现上看，在内存中，子例程只使用一个栈（stack），而协程是同时存在多个栈，但只有一个栈是在运行状态，也就是说，协程是以多占用内存为代价，实现多任务的并行。
   普通的线程是抢先式的，到底哪个线程优先得到资源，必须由运行环境决定，但是协程是合作式的，执行权由协程自己分配。
   
3.  块级元素垂直居中—-高度不固定：transform(0,-50%) 或者 display:table tabale-cell
4. Object.defineProperty无法监控到数组下标的变化，导致直接通过数组的下标给数组设置值，不能实时响应。 为了解决这个问题，经过vue内部处理后可以使用以下几种方法来监听数组
5. webpack hmr
```text
1.当修改了一个或多个文件；
2.文件系统接收更改并通知webpack；
3.webpack重新编译构建一个或多个模块，并通知HMR服务器进行更新；
4.HMR Server 使用webSocket通知HMR runtime 需要更新，HMR运行时通过HTTP请求更新jsonp；
5.HMR运行时替换更新中的模块，如果确定这些模块无法更新，则触发整个页面刷新。
```

1. vue diff 算法
```text
//相同的话进行patch
patchVnode (oldVnode, vnode) {
    const el = vnode.el = oldVnode.el
    let i, oldCh = oldVnode.children, ch = vnode.children
    if (oldVnode === vnode) return
    if (oldVnode.text !== null && vnode.text !== null && oldVnode.text !== vnode.text) {
        api.setTextContent(el, vnode.text)
    }else {
        updateEle(el, vnode, oldVnode)
    	if (oldCh && ch && oldCh !== ch) {
            updateChildren(el, oldCh, ch)
    	}else if (ch){
            createEle(vnode) //create el's children dom
    	}else if (oldCh){
            api.removeChildren(el)
    	}
    }
}
```

1. in操作符:检测指定对象(右边)原型链上是否有对应的属性值。 
    hasOwnProperty方法:检测指定对象自身上是否有对应的属性值。两者的区别在于in会查找原型链,而hasOwnProperty不会。
   
   for...in...遍历对象上除了Symbol以外的可枚举属性,包括原型链上的属性。
   
   Object.keys & Object.assign & JSON.stringify: excluding non-enumerable & __proto__
 

2. V8 浏览器会自动执行垃圾回收，但由于 JavaScript 也是运行在主线程上的，一旦执行垃圾回收，就要打断 JavaScript 的运行，可能会或多或少的造成页面的卡顿，影响用户体验，所以 V8 决定采用增量 标记算法回收：
   即把垃圾回收拆成一个个小任务，穿插在 JavaScript 中执行。

3. HTML5是HTML的新标准，其主要目标是无需任何额外的插件如Flash、Silverlight等，就可以传输所有内容。它囊括了动画、视频、丰富的图形用户界面等。

4. HTML5文档类型：<!doctype html>    HTML5使用的编码 <meta charset=”UTF-8”>

5. link属于HTML标签，而@import是css提供的；
   页面被加载时，link会同时被加载，而 @import引用的css会等到页面被加载完再加载；
   @import只在IE5以上才能识别，而link是XHTML标签，无兼容问题；
   link方式的样式的权重高于@import的权重。

6.  最新的HTML5标准中的API是什么
   
   Canvas ：Canvas由HTML代码中定义的具有高度和宽度属性的可绘制区域组成。JavaScript代码可以通过一组完整的绘图函数访问该区域，这与其他常见的2D API类似，因此允许动态生成图形。Canvas 的一些预期用途包括构建图形、动画、游戏和图像合成。
   媒体定时回放；
   离线存储数据库；
   文档编辑；
   拖放；
   跨文档消息传递；
   浏览器历史管理；
   MIME类型和协议处理程序注册；

11. 对HTML5有什么了解？
   
   良好的移动性，以移动设备为主；
   响应式设计，以适应自动变化的屏幕尺寸；
   支持离线缓存技术，webStorage本地缓存；
   新增了canvas，video，audio等新标签元素；以及特殊内容元素：article，footer，header，nav，section等；以及表单控件：calendar，date，time，email，url，search等；
   新增webSocket/webWork技术；
   还有新增的地理位置等。

12. <!doctype html> 的作用就是让浏览器进入标准模式，使用最新的 HTML5标准来解析渲染页面；如果不写，浏览器就会进入混杂模式，我们需要避免此类情况发生。   

13. label 标签来定义表单控制间的关系，当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。     

14. `<datalist>`标签，用来定义选项列表，与input元素配合使用钙元素，来定义input可能的值。
  datalist及其选项不会被显示出来，他仅仅是合法的输入列表值。
  `<input id="fruits" list="fruit" /><datalist id="fruit">  <option value="apple">  <option value="orange">  <option value="banana"></datalist>`
  

15. Git submodule 
  ```text
$ git submodule init
Submodule 'assets' (https://github.com/maonx/vimwiki-assets.git) registered for path 'assets'
```

```text
$ git submodule add https://github.com/maonx/vimwiki-assets.git assets

$ git submodule update —remote
```

1.  十进制转为 2 进制，除 2 取余，然后余数反向
    
    十进制转为 2 进制小时，**乘 2 取整**
    
2.  最优子结构、边界、动态转移方程。动态规划的核心—》从低向上，从而不会像递归那样保留调用栈。
    
 

---

    
2.  preload 是声明式的 fetch，可以强制浏览器请求资源，同时不阻塞文档 onload 事件。Prefetch 提示浏览器这个资源将来可能需要，但是把决定是否和什么时间加载这个资源的决定权交给浏览器。
    
3.  首屏加载时间
    performance.timing.domContentLoadedEventStart-performance.timing.navigationStart
    
4.  所以函数防抖适用的场景：监听窗口的滚动，缩放。高频发生的一些事件；函数节流适用的场景：涉及与后端交互的按钮，由于网络原因或者其他原因，导致接口没有返回值，用户一直点点点的问题。
    
5.  当用户输入关键字并键入回车之后，这意味着当前页面即将要被替换成新的页面，不过在这个流程继续之前，浏览器还给了当前页面一次执行 `beforeunload` 事件的机会，`beforeunload` 事件允许页面在退出之前执行一些数据清理操作，还可以询问用户是否要离开当前页面。

  
    
6.  而HTTP的204(No Content)响应, 就表示执行成功, 但是没有数据, 浏览器不用刷新页面.也不用导向新的页面.  
     205 Reset Content, 表示执行成功, 重置页面(Form表单).