---
title: fresh
date: 2020-06-04 10:33:26
tags:
---
1. jest.spyOn()方法同样创建一个mock函数，但是该mock函数不仅能够捕获函数的调用情况，还可以正常的执行被spy的函数。实际上，jest.spyOn()是jest.fn()的语法糖，它创建了一个和被spy的函数具有相同内部代码的mock函数。
1. Node 高消耗任务：1. Regex 2. 加密、压缩、fs 同步操作 3.json.stringfy
1. 事件循环线程只负责协调客户端的请求，而不是独自执行完所有任务。 对一个复杂的任务，最好把它从事件循环线程转移到工作线程池上。
1. webworker-threads  node 多线程模块处理计算密集任务
1. crumb 面包屑
1. SCSS 是 Sass 3 引入新的语法，其语法完全兼容 CSS3，并且继承了 Sass 的强大功能。也就是说，任何标准的 CSS3 样式表都是具有相同语义的有效的 SCSS 文件
1. SCSS提供了一个选择器可以选中当前元素的父元素，使用&表示.
1. $border-color:#ccc !default; //声明变量 !default只能使用与变量中
1. 使用%定义一个被继承的样式，类似静态语言中的抽象类，他本身不起作用，只用于被其他人继承。
1. sass 的控制指令
    ```text
      .el-col-0 {
         display: none;
       }

       @for $i from 0 through 24 {
         .el-col-#{$i} {
           width: (1 / 24 * $i * 100) * 1%;
         }
       }
    ```
1.
1. Vue Test Utils 允许你通过 shallowMount 方法只挂载一个组件而不渲染其子组件 (即保留它们的存根)：
    Vue beforecreated:data vue 实例化、init events
1. !important，作用是提高指定样式规则的应用优先权
1. components，filters，directives
   两个对象合并的时候，不会相互覆盖，而是 权重小的 被放到 权重大 的 的原型上
1. 数组叠加   包括生命周期函数和watch
1. 函数合并叠加   包括选项：data，provide，权重大的优先
1.
1. HTML <sup> 元素定义了一个文本区域，出于排版的原因，与主要的文本相比，应该展示得更高并且更小。
1. indexedDB 的特点：存储空间大：存储空间可以达到几百兆甚至更多；

               >> 支持二进制存储：它不仅可以存储字符串，而且还可以存储二进制数据；
               >> IndexedDB 有同源限制，每一个数据库只能在自身域名下能访问，不能跨域名访问；
               >> 支持事务型：IndexedDB 执行的操作会按照事务来分组的，在一个事务中，要么所有的操作都成功，要么所有的操作都失败；
               >> 键值对存储：IndexedDB 内部采用对象仓库（object store）存放数据。所有类型的数据都可以直接存入，包括 JavaScript 对象。对象仓库中，数据以 “键值对” 的形式保存，每一个数据记录都有对应的主键，主键是独一无二的，不能有重复，否则会抛出一个错误。
               >> 数据操作是异步的：使用 IndexedDB 执行的操作是异步执行的，以免阻塞应用程序。

               1. localForage 是一个快速简单的 JavaScript 存储库。 它通过使用类似于 localStorage 的简单 API 来使用异步存储（IndexedDB 或 WebSQL)），进而改善你的 Web 应用程序的离线体验。
1. ImmortalDB 是在浏览器中存储持久键值数据的最佳方法。保存到 ImmortalDB 的数据被冗余地存储在 Cookies，IndexedDB 和 localStorage 中，并且如果其中的任何数据被删除或损坏，它们将不断进行自我修复。
1. web-storage-cache 对HTML5 localStorage 和sessionStorage 进行了扩展，添加了超时时间，序列化方法。可以直接存储json对象，同时可以非常简单的进行超时时间的设置。
1. 全局的components ，通过vue 的options merge 到组件上。 最后通过 extend(Vue.options.components, builtInComponents) 把一些内置组件扩展到 Vue.options.components 上，
Vue 的内置组件目前有 <keep-alive>、<transition> 和 <transition-group> 组件，这也就是为什么我们在其它组件中使用 <keep-alive> 组件不需要注册的原因
1.  首先通过 Vue.options = Object.create(null) 创建一个空对象，然后遍历 ASSET_TYPES:VuVue.options.components = {}
    Vue.options.directives = {} Vue.options.filters = {}
1.  git config --global --edit
1. 对于渲染 watcher 而言，它在执行 this.get() 方法求值的时候，会执行 getter 方法： updateComponent = () => {
   updateComponent = () => { vm._update(vm._render(), hydrating)

1. 而对于作用域插槽，父组件在编译和渲染阶段并不会直接生成 vnodes，而是在父节点 vnode 的 data 中保留一个 scopedSlots 对象，存储着不同名称的插槽以及它们对应的渲染函数，
只有在编译和渲染子组件阶段才会执行这个渲染函数生成 vnodes，由于是在子组件环境执行的，所以对应的数据作用域是子组件实例。
1. 这里对该vm注册一个Watcher实例，Watcher的getter为updateComponent函数，用于触发所有渲染所需要用到的数据的getter，进行依赖收集，就是在mounted的时候进行依赖收集。
用户的自定义 watcher 要优先于渲染 watcher 执行；因为用户自定义 watcher 是在渲染 watcher 之前创建的。Vm._watcher.update()

1. Dep 是一个 Class，它定义了一些属性和方法，这里需要特别注意的是它有一个静态属性 target，这是一个全局唯一 Watcher，这是一个非常巧妙的设计，
因为在同一时间只能有一个全局的 Watcher 被计算，另外它的自身属性 subs 也是 Watcher 的数组。

1. Observer 是一个类，它的作用是给对象的属性添加 getter 和 setter，用于依赖收集和派发更新。Render 时通过getter 进行依赖收集。
1. 每次JavaScript对DOM的操作都会改变当前页面的呈现，并重新刷新整个页面，从而消耗了大量的时间。而createDocumentFragment()的作用，就是可以创建一个文档碎片，
把所有的新节点附加其上，然后把文档碎片的内容一次性添加到document中。

1. Service Worker 是运行在浏览器背后的独立线程，一般可以用来实现缓存功能。使用 Service Worker的话，传输协议必须为 HTTPS。
1. prune  修剪；减少；
1. markdown-it :  markdown parser
   cp-cli  copy 跨平台
1. e
 在Vue2.5之前，使用函数式组件只能通过JSX的方式，在之后，可以通过模板语法来生命函数式组件
<!--在template 上面添加 functional属性-->
<template functional>
  <img :src="avatar ? avatar : 'default-avatar.png'" />
</template>
<!--根据上一节第六条，可以省略声明props-->

1. 堆
堆的底层实际上是一棵完全二叉树，可以用数组实现
每个的节点元素值不小于其子节点 - 最大堆
每个的节点元素值不大于其子节点 - 最小堆

1. 异步组件属性
```javascript

const AsyncComponent = () => ({
  // 需要加载的组件 (应该是一个 `Promise` 对象)
  component: import('./MyComponent.vue'),
  // 异步组件加载时使用的组件
  loading: LoadingComponent,
  // 加载失败时使用的组件
  error: ErrorComponent,
  // 展示加载时组件的延时时间。默认值是 200 (毫秒)
  delay: 200,
  // 如果提供了超时时间且组件加载也超时了，
  // 则使用加载失败时使用的组件。默认值是：`Infinity`
  timeout: 3000
})
```
1. 函数式组件与普通组件的区别
   
   函数式组件需要在声明组件是指定functional
   函数式组件不需要实例化，所以没有this,this通过render函数的第二个参数来代替
   函数式组件没有生命周期钩子函数，不能使用计算属性，watch等等
   函数式组件不能通过$emit对外暴露事件，调用事件只能通过context.listeners.click的方式调用外部传入的事件
   因为函数式组件是没有实例化的，所以在外部通过ref去引用组件时，实际引用的是HTMLElement
   函数式组件的props可以不用显示声明，所以没有在props里面声明的属性都会被自动隐式解析为prop,而普通组件所有未声明的属性都被解析到$attrs里面，并自动挂载到组件根元素上面(可以通过inheritAttrs属性禁止)
1. Object.create(null) 和 {}
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
1. this.$on('hook:updated', () => {})
1. Mind elixir 浏览器思维导图js module
1. js 在底层存储变量的时候，会在变量的机器码的低位1-3位存储其类型信息👉
   
   000：对象
   010：浮点数
   100：字符串
   110：布尔
   1：整数
   
   but, 对于 undefined 和 null 来说，这两个值的信息存储是有点特殊的。
   
   null：所有机器码均为0
   
   undefined：用 −2^30 整数来表示
1. Vm.$watch this._data.$$state 的值，/* 检测store中的_committing的值，如果是true代表不是通过mutation的方法修改的 */
1. /* 这里new了一个Vue对象，运用Vue内部的响应式实现注册state以及computed*/
    store._vm = new Vue({ data: {$$state: state }, computed })
1. Unify 整合、统一 
1. 红黑树
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
1. flex-basis 分配多余空间之前占据的主轴空间。
1. 管道符放到尾部：Hello(?:World|China|) 可以匹配 HelloWorld、HelloChina，也可以只匹配 Hello。
1. for await...of循环，则是用于遍历异步的 Iterator 接口。
```javascript
function main(inputFilePath) {
  const readStream = fs.createReadStream(
    inputFilePath,
    { encoding: 'utf8', highWaterMark: 1024 }
  );
  readStream.on('data', (chunk) => {
    console.log('>>> '+chunk);
  });
  readStream.on('end', () => {
    console.log('### DONE ###');
  });
}

// 异步遍历器写法
async function main(inputFilePath) {
  const readStream = fs.createReadStream(
    inputFilePath,
    { encoding: 'utf8', highWaterMark: 1024 }
  );

  for await (const chunk of readStream) {
    console.log('>>> '+chunk);
  }
  console.log('### DONE ###');
}
```

1. 这种可以并行执行、交换执行权的线程（或函数），就称为协程。
   
   从实现上看，在内存中，子例程只使用一个栈（stack），而协程是同时存在多个栈，但只有一个栈是在运行状态，也就是说，协程是以多占用内存为代价，实现多任务的并行。
   普通的线程是抢先式的，到底哪个线程优先得到资源，必须由运行环境决定，但是协程是合作式的，执行权由协程自己分配。
   
1.  块级元素垂直居中—-高度不固定：transform(0,-50%) 或者 display:table tabale-cell
1. Object.defineProperty无法监控到数组下标的变化，导致直接通过数组的下标给数组设置值，不能实时响应。 为了解决这个问题，经过vue内部处理后可以使用以下几种方法来监听数组
1. webpack hmr
```text
1.当修改了一个或多个文件；
2.文件系统接收更改并通知webpack；
3.webpack重新编译构建一个或多个模块，并通知HMR服务器进行更新；
4.HMR Server 使用webSocket通知HMR runtime 需要更新，HMR运行时通过HTTP请求更新jsonp；
5.HMR运行时替换更新中的模块，如果确定这些模块无法更新，则触发整个页面刷新。
```


1. 
vue 父子组件：
加载渲染过程
父beforeCreate->父created->父beforeMount->子beforeCreate->子created->子beforeMount->子mounted->父mounted
父beforeUpdate->子beforeUpdate->子updated->父updated
父组件更新过程
父beforeUpdate->父updated
销毁过程
父beforeDestroy->子beforeDestroy->子destroyed->父destroyed


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
1. 多行文本溢出隐藏变为...
     p {
       overflow: hidden;
       
       /* 限制在一个块元素显示的文本的行数，即行数设置 */
       line-clamp: 3;
      
     }
     
1. 
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
1. in操作符:检测指定对象(右边)原型链上是否有对应的属性值。 hasOwnProperty方法:检测指定对象自身上是否有对应的属性值。两者的区别在于in会查找原型链,而hasOwnProperty不会。
   
   for...in...遍历对象上除了Symbol以外的可枚举属性,包括原型链上的属性。
   
   Object.keys & Object.assign & JSON.stringify: excluding non-enumerable & __proto__

1. 
```text
function A () { 

}
 A.prototype.n = 1; 
var b = new A(); 
A.prototype = { n: 2, m: 3 } 
var c = new A(); 
console.log(b.n, b.m); 
console.log(c.n, c.m);
```

1. 
```text
var a = {n: 1}
var b = a
a.x = a = {n: 2}

console.log(a.n, b.n);
console.log(a.x, b.x);

```
1. V8 浏览器会自动执行垃圾回收，但由于 JavaScript 也是运行在主线程上的，一旦执行垃圾回收，就要打断 JavaScript 的运行，可能会或多或少的造成页面的卡顿，影响用户体验，所以 V8 决定采用增量 标记算法回收：
   即把垃圾回收拆成一个个小任务，穿插在 JavaScript 中执行。
1. contiguous  kənˈtɪɡjuəs
1. generic-pool  资源池，可以reuse 和限制一些比较贵的资源比如数据库链接。
1. aside  定义页面的侧边栏内容。
   progress 原生的进度条
1.
ReferenceError: Cannot access 'a' before initialization
 ```text

 var a = 1;
if(true){
    console.log(a);
    let a = 2;
}
```
1. new Date() month index 从0开始 
1. Array(10)  稀疏矩阵
1. 用快慢指针处理链表问题
1. git branch -m feature/stor-13711 feature/story-13711  修改分支名称
1. git reflog 命令获取到的内容为本地仓库所有发生过的变更
   HTML5是HTML的新标准，其主要目标是无需任何额外的插件如Flash、Silverlight等，就可以传输所有内容。它囊括了动画、视频、丰富的图形用户界面等。
1. 普通函数在被调用时，JS引擎会创建一个栈帧，在里面准备好局部变量、函数参数、临时值、代码执行的位置（也就是说这个函数的第一行对应到代码区里的第几行机器码），在当前栈帧里设置好返回位置，然后将新帧压入栈顶。待函数执行结束后，这个栈帧将被弹出栈然后销毁，返回值会被传给上一个栈帧。
   当执行到yield语句时，Generator的栈帧同样会被弹出栈外，但Generator在这里耍了个花招——它在堆里保存了栈帧的引用（或拷贝）！这样当iter.next方法被调用时，JS引擎便不会重新创建一个栈帧，而是把堆里的栈帧直接入栈。因为栈帧里保存了函数执行所需的全部上下文以及当前执行的位置，所以当这一切都被恢复如初之时，就好像程序从原本暂停的地方继续向前执行了。
   
   而因为每次yield和iter.next都对应一次出栈和入栈，所以可以直接利用已有的栈机制，实现值的传出和传入。
1. HTML5文档类型：<!doctype html>    HTML5使用的编码<meta charset=”UTF-8”>
1. 优雅降级 graceful degradation： 一开始就构建完整的功能，然后再针对低版本的浏览器进行兼容。
1. link属于HTML标签，而@import是css提供的；
   页面被加载时，link会同时被加载，而@import引用的css会等到页面被加载完再加载；
   @import只在IE5以上才能识别，而link是XHTML标签，无兼容问题；
   link方式的样式的权重高于@import的权重。
1. 最新的HTML5标准中的API是什么
   
   Canvas ：Canvas由HTML代码中定义的具有高度和宽度属性的可绘制区域组成。JavaScript代码可以通过一组完整的绘图函数访问该区域，这与其他常见的2D API类似，因此允许动态生成图形。Canvas 的一些预期用途包括构建图形、动画、游戏和图像合成。
   媒体定时回放；
   离线存储数据库；
   文档编辑；
   拖放；
   跨文档消息传递；
   浏览器历史管理；
   MIME类型和协议处理程序注册；
1. 对HTML5有什么了解？
   
   良好的移动性，以移动设备为主；
   响应式设计，以适应自动变化的屏幕尺寸；
   支持离线缓存技术，webStorage本地缓存；
   新增了canvas，video，audio等新标签元素；以及特殊内容元素：article，footer，header，nav，section等；以及表单控件：calendar，date，time，email，url，search等；
   新增webSocket/webWork技术；
   还有新增的地理位置等。
1. <!doctype html> 的作用就是让浏览器进入标准模式，使用最新的 HTML5标准来解析渲染页面；如果不写，浏览器就会进入混杂模式，我们需要避免此类情况发生。   
1.  label 标签来定义表单控制间的关系，当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。     
1. <datalist>标签，用来定义选项列表，与input元素配合使用钙元素，来定义input可能的值。
  datalist及其选项不会被显示出来，他仅仅是合法的输入列表值。
  
  <input id="fruits" list="fruit" /><datalist id="fruit">  <option value="apple">  <option value="orange">  <option value="banana"></datalist>
  
      
1.  regex  y stick 粘连修饰符 
1.  Git submodule 
  ```$xslt
$ git submodule init
Submodule 'assets' (https://github.com/maonx/vimwiki-assets.git) registered for path 'assets'
```

```$xslt
$ git submodule add https://github.com/maonx/vimwiki-assets.git assets

$ git submodule update —remote
```
1.  十进制转为 2 进制，除 2 取余，然后余数反向
    
    十进制转为 2 进制小时，**乘 2 取整**
    
2.  最优子结构、边界、动态转移方程。动态规划的核心—》从低向上，从而不会像递归那样保留调用栈。
    
3.  Element.getBoundingClientRect() 方法返回元素的大小及其相对于视口的位置。
    
4.  window.requestAnimationFrame() 告诉浏览器——你希望执行一个动画，并且要求浏览器在下次重绘之前调用指定的回调函数更新动画。该方法需要传入一个回调函数作为参数，该回调函数会在浏览器下一次重绘之前执行
    
5.  浏览器中 customevent
    

```
var event = new CustomEvent("cat", {  detail: {    hazcheeseburger: true  }});obj.dispatchEvent(event);
```

---

1.  Tcp 的滑动窗口增大了吞吐量，但是并没有解决队头堵塞得问题
    
2.  preload 是声明式的 fetch，可以强制浏览器请求资源，同时不阻塞文档 onload 事件。Prefetch 提示浏览器这个资源将来可能需要，但是把决定是否和什么时间加载这个资源的决定权交给浏览器。
    
3.  首屏加载时间
    performance.timing.domContentLoadedEventStart-performance.timing.navigationStart
    
4.  所以函数防抖适用的场景：监听窗口的滚动，缩放。高频发生的一些事件；函数节流适用的场景：涉及与后端交互的按钮，由于网络原因或者其他原因，导致接口没有返回值，用户一直点点点的问题。
    
5.  当用户输入关键字并键入回车之后，这意味着当前页面即将要被替换成新的页面，不过在这个流程继续之前，浏览器还给了当前页面一次执行 `beforeunload` 事件的机会，`beforeunload` 事件允许页面在退出之前执行一些数据清理操作，还可以询问用户是否要离开当前页面。
    
6.  wrong pronouce
```text
     analogy 类比 [əˈnælədʒi]
      Apache [ə’pætʃɪ]
      AJAX [‘eidʒæks]
      array [ə’rei]
      deque dek 双端队列
      Java ['dʒɑːvə]
      Realm [relm]
    
 ```
    
7.  http 挥手 主动关闭有个time_wait,这个标准的持续时间是4分钟

     ISN(Initial Sequence Number) 是固定的么，
     
      客户端的syn_send 状态、服务端的syn_rcvd
      
     Tcp 报文段：tcp 首部+tcp 数据部分
     
      Fuction 形参是引用类型的话，只是引用
      
      半链接队列—超时重传
      
     等待2个msl 确保服务端能收到ack,能正常关闭
     
      关闭连接时，当收到对方的FIN报文时，仅仅表示对方不再发送数据了但是还能接收数据，己方也未必全部数据都发送给对方了，所以己方可以立即close，也可以发送一些数据给对方后，再发送FIN报文给对方来表示同意现在关闭连接，因此，己方ACK和FIN一般都会分开发送。
 
    
8.  如果 300 的话会进行重定向，这里会有个重定向计数器，避免过多次的重定向，超过次数也会报错。
    
9.  而HTTP的204(No Content)响应, 就表示执行成功, 但是没有数据, 浏览器不用刷新页面.也不用导向新的页面.  
     205 Reset Content, 表示执行成功, 重置页面(Form表单).