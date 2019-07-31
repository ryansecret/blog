---
title: vue
date: 2017-01-19 15:19:03
tags: vue eventloop js 
---
### js
1. js 链接 defer 和 async
```text
defer 和 async 都是并行加载的，主要区别在于下载后何时执行。
每一个 async 属性的脚本都在它下载结束之后立刻执行，所以就有可能出现脚本执行顺序被打乱的情况
每一个 defer 属性的脚本会在 HTML 解析完成后, DOMContentLoaded 之前，按照 DOM 中的顺序执行（ie>=10）
defer 和 async 都只适用于外部脚本文件，对与内联的 script 标签是不起作用

```
1. preload 用 “as” 或者用 “type” 属性来表示他们请求资源的优先级（比如说 preload 使用 as="style" 属性将获得最高的优先级）。没有 “as” 属性的将被看作异步请求，“Early”意味着在所有未被预加载的图片请求之前被请求（“late”意味着之后）
1. WebRTC，名称源自网页即时通信（英语：Web Real-Time Communication）的缩写，是一个支持网页浏览器进行实时语音对话或视频对话的API。
1. Vue-intro  新功能引导  
1. __proto__ 属性，这是历史遗留的非标准的语法，但在现代浏览器中广泛实现。获得原型的更可靠方法是使用 Object.getPrototypeOf(new Object())；例如：
 ```javascript
const car = {}
const list = []
 
console.log(Object.getPrototypeOf(car));
console.log(Object.getPrototypeOf(list));
```
1. Object.prototype.toString.call(variable) 用这个方法来判断变量类型目前是最可靠的了，它总能返回正确的值。
   
   该方法返回 "[object type]", 其中type是对象类型。
1.  document.getElementsByClassName('test');
1.    

### 内部机制 

vue-loader 

compiler 目录包含 Vue.js 所有编译相关的代码。它包括把模板解析成 ast 语法树，ast 语法树优化，代码生成等功能。


微任务的例子：micortask

process.nextTick
promise
Object.observe

宏任务的例子：

setTimeout
setInterval
setImmediate
I/O

需要注意的是node 和 浏览器的 event loop 是有区别的：

```text
浏览器的事件循环：

执行全局Script同步代码，这些同步代码有一些是同步语句，有一些是异步语句（比如setTimeout等）；
全局Script代码执行完毕后，调用栈Stack会清空；
从微队列microtask queue中取出位于队首的回调任务，放入调用栈Stack中执行，执行完后microtask queue长度减1；
继续取出位于队首的任务，放入调用栈Stack中执行，以此类推，直到直到把microtask queue中的所有任务都执行完毕。注意，如果在执行microtask的过程中，又产生了microtask，那么会加入到队列的末尾，也会在这个周期被调用执行；
microtask queue中的所有任务都执行完毕，此时microtask queue为空队列，调用栈Stack也为空；
取出宏队列macrotask queue中位于队首的任务，放入Stack中执行；
执行完毕后，调用栈Stack为空；
重复第3-7个步骤；
重复第3-7个步骤；
……

NodeJS中微队列主要有2个：
Next Tick Queue：是放置process.nextTick(callback)的回调任务的
Other Micro Queue：放置其他microtask，比如Promise等

具体参见： https://segmentfault.com/a/1190000016278115

```


``` 
timers 阶段：这个阶段执行timer（setTimeout、setInterval）的回调
I/O callbacks 阶段：执行一些系统调用错误，比如网络通信的错误回调
idle, prepare 阶段：仅node内部使用
poll 阶段：获取新的I/O事件, 适当的条件下node将阻塞在这里
check 阶段：执行 setImmediate() 的回调
close callbacks 阶段：执行 socket 的 close 事件回调

timers 是事件循环的第一个阶段，Node 会去检查有无已过期的timer，如果有则把它的回调压入timer的任务队列中等待执行，事实上，Node 并不能保证timer在预设时间到了就会立即执行，因为Node对timer的过期检查不一定靠谱，它会受机器上其它运行程序影响，或者那个时间点主线程不空闲。比如下面的代码，setTimeout() 和 setImmediate() 的执行顺序是不确定的。

poll 阶段
poll 阶段主要有2个功能：

处理 poll 队列的事件
当有已超时的 timer，执行它的回调函数
even loop将同步执行poll队列里的回调，直到队列为空或执行的回调达到系统上限（上限具体多少未详），接下来even loop会去检查有无预设的setImmediate()，分两种情况：

若有预设的setImmediate(), event loop将结束poll阶段进入check阶段，并执行check阶段的任务队列
若没有预设的setImmediate()，event loop将阻塞在该阶段等待
注意一个细节，没有setImmediate()会导致event loop阻塞在poll阶段，这样之前设置的timer岂不是执行不了了？所以咧，在poll阶段event loop会有一个检查机制，检查timer队列是否为空，如果timer队列非空，event loop就开始下一轮事件循环，即重新进入到timer阶段。

check 阶段
setImmediate()的回调会被加入check队列中， 从event loop的阶段图可以知道，check阶段的执行顺序在poll阶段之后。


回顾上一篇，浏览器环境下，microtask的任务队列是每个macrotask执行完之后执行。而在Node.js中，microtask会在事件循环的各个阶段之间执行，也就是一个阶段执行完毕，就会去执行microtask队列的任务。详见：http://lynnelv.github.io/js-event-loop-nodejs

process.nextTick() 会在各个事件阶段之间执行，一旦执行，要直到nextTick队列被清空，才会进入到下一个事件阶段，所以如果递归调用 process.nextTick()，会导致出现I/O starving（饥饿）的问题

官方文档：https://nodejs.org/en/docs/guides/event-loop-timers-and-nexttick/

```



###vitual dom

 Vue.js 实现响应式的核心是利用了 ES5 的 Object.defineProperty，这也是为什么 Vue.js 不能兼容 IE8 及以下浏览器的原因，我们先来对它有个直观的认识。值改变时会触发set方法。
 
 核心就是利用 Object.defineProperty 给数据添加了 getter 和 setter，目的就是为了在我们访问数据以及写数据的时候能自动执行一些逻辑：getter 做的事情是依赖收集，setter 做的事情是派发更新
 
 它会先执行 vm._render() 方法，因为之前分析过这个方法会生成 渲染 VNode，并且在这个过程中会对 vm 上的数据访问，这个时候就触发了数据对象的 getter。
 
 它并不会每次数据改变都触发 watcher 的回调，而是把这些 watcher 先添加到一个队列里，然后在 nextTick 后执行 flushSchedulerQueue。

 

VD 最大的特点是将页面的状态抽象为 JS 对象的形式，配合不同的渲染工具，使跨平台渲染成为可能。如 React 就借助 VD 实现了服务端渲染、浏览器渲染和移动端渲染等功能。
js计算-》生成渲染树-》渲染页面

通过VD的比较，我们可以将多个操作合并成一个批量的操作，从而减少dom重排的次数，进而缩短了生成渲染树和绘制所花的时间。

在mounted 方法中会将template 编译成为render 方法。这是一个编译过程，render中会调用createElement 创建vnode。

![流程图片](https://ustbhuangyi.github.io/vue-analysis/assets/new-vue.png)


回到 mountComponent 函数的过程，我们已经知道 createElement 是如何创建了一个 VNode，接下来就是要把这个 VNode 渲染成一个真实的 DOM 并渲染出来，这个过程是通过 vm._update 完成的

Vue 的 _update 是实例的一个私有方法，它被调用的时机有 2 个，一个是首次渲染，一个是数据更新的时候；由于我们这一章节只分析首次渲染部分，数据更新部分会在之后分析响应式原理的时候涉及。_update 方法的作用是把 VNode 渲染成真实的 DOM


在我们之前对 setter 的分析过程知道，当响应式数据发送变化后，触发了 watcher.update()，只是把这个 watcher 推送到一个队列中，在 nextTick 后才会真正执行 watcher 的回调函数。而一旦我们设置了 sync，就可以在当前 Tick 中同步执行 watcher 的回调函数。

deep watcher 和 sync watcher  



###  router 元数据 
 meta: { requiresAuth: true }  
 
#####  v-once 指令，你也能执行一次性地插值

#### v-slot 新的用法
v-slot 的别名是#。因此，可以用#header="data" 来代替 v-slot:header="data"。还可以使用 #header来代替 v-slot:header(前提:不是作用域插槽时)。对于默认插槽，在使用别名时需要指定默认名称。换句话说，需要这样写 #default="data" 而不是#="data"。


##### Mustache 不能在 HTML 属性中使用，应使用 v-bind 指令：

```
<div v-bind:id="dynamicId"></div>
```

##### 修饰符（Modifiers）是以半角句号 . 指明的特殊后缀，用于指出一个指定应该以特殊方式绑定。例如，.prevent 修饰符告诉 v-on 指令对于触发的事件调用 event.preventDefault()

```
<!-- 阻止单击事件冒泡 -->
<a v-on:click.stop="doThis"></a>
<!-- 提交事件不再重载页面 -->
<form v-on:submit.prevent="onSubmit"></form>
<!-- 修饰符可以串联  -->
<a v-on:click.stop.prevent="doThat"></a>
<!-- 只有修饰符 -->
<form v-on:submit.prevent></form>
<!-- 添加事件侦听器时使用事件捕获模式 -->
<div v-on:click.capture="doThis">...</div>
<!-- 只当事件在该元素本身（而不是子元素）触发时触发回调 -->
<div v-on:click.self="doThat">...</div>
<a v-on:click.once="doThis"></a>
```

##### 过滤器函数总接受表达式的值作为第一个参数。

```
new Vue({
  // ...
  filters: {
    capitalize: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.charAt(0).toUpperCase() + value.slice(1)
    }
  }
})
过滤器可以串联：
{{ message | filterA | filterB }}
```

##### v-bind 缩写


```
<!-- 完整语法 -->
<a v-bind:href="url"></a>
<!-- 缩写 -->
<a :href="url"></a>
v-on 缩写

<!-- 完整语法 -->
<a v-on:click="doSomething"></a>
<!-- 缩写 -->
<a @click="doSomething"></a>
```
 
 
##### 按键修饰符
记住所有的 keyCode 比较困难，所以 Vue 为最常用的按键提供了别名：

```
<!-- 同上 -->
<input v-on:keyup.enter="submit">
<!-- 缩写语法 -->
<input @keyup.enter="submit">
全部的按键别名：
.enter
.tab
.delete (捕获 “删除” 和 “退格” 键)
.esc
.space
.up
.down
.left
.right
```
##### 绑定属性值

```
<input
  type="checkbox"
  v-model="toggle"
  v-bind:true-value="a"
  v-bind:false-value="b"
>
```
##### 修饰符

```
在默认情况下， v-model 在 input 事件中同步输入框的值与数据 (除了 上述 IME 部分)，但你可以添加一个修饰符 lazy ，从而转变为在 change 事件中同步：
<!-- 在 "change" 而不是 "input" 事件中更新 -->
<input v-model.lazy="msg" >
.number

如果想自动将用户的输入值转为 Number 类型（如果原值的转换结果为 NaN 则返回原值），可以添加一个修饰符 number 给 v-model 来处理输入值：
<input v-model.number="age" type="number">
这通常很有用，因为在 type="number" 时 HTML 中输入的值也总是会返回字符串类型。
.trim

如果要自动过滤用户输入的首尾空格，可以添加 trim 修饰符到 v-model 上过滤输入：
<input v-model.trim="msg">
```
