---
title: html
date: 2020-08-13 16:17:07
tags: html
---
1. 
1. 当用户输入关键字并键入回车之后，这意味着当前页面即将要被替换成新的页面，不过在这个流程继续之前，浏览器还给了当前页面一次执行 `beforeunload` 事件的机会，`beforeunload` 事件允许页面在退出之前执行一些数据清理操作，还可以询问用户是否要离开当前页面。

1. 对HTML5有什么了解？
   
   良好的移动性，以移动设备为主；
   响应式设计，以适应自动变化的屏幕尺寸；
   支持离线缓存技术，webStorage本地缓存；
   新增了canvas，video，audio等新标签元素；以及特殊内容元素：article，footer，header，nav，section等；以及表单控件：calendar，date，time，email，url，search等；
   新增webSocket/webWork技术；
   还有新增的地理位置等。
1. label 标签来定义表单控制间的关系，当用户选择该标签时，浏览器会自动将焦点转到和标签相关的表单控件上。    
1.  最新的HTML5标准中的API是什么
   
   Canvas ：Canvas由HTML代码中定义的具有高度和宽度属性的可绘制区域组成。JavaScript代码可以通过一组完整的绘图函数访问该区域，这与其他常见的2D API类似，因此允许动态生成图形。Canvas 的一些预期用途包括构建图形、动画、游戏和图像合成。
   媒体定时回放；
   离线存储数据库；
   文档编辑；
   拖放；
   跨文档消息传递；
   浏览器历史管理；
   MIME类型和协议处理程序注册；
1. 对布局属性进行动画，浏览器需要为每一帧进行重绘并上传到 GPU 中
对合成属性进行动画，浏览器会为元素创建一个独立的复合层，当元素内容没有发生改变，该层就不会被重绘，浏览器会通过重新复合来创建动画帧
1. HTML5文档类型：<!doctype html>    HTML5使用的编码 <meta charset=”UTF-8”>
1. Service Worker 是运行在浏览器背后的独立线程，一般可以用来实现缓存功能。使用 Service Worker的话，传输协议必须为 HTTPS。
3. visibilitychange,可以用来判断浏览器页签是否显示。
2. WebP是一种新的图片格式，目标是减少文件大小但达到和JPEG格式相同的图片质量，能够减少网络上的请求时间。
1. DOMContentLoaded事件触发时：仅当DOM解析完成后，不包括样式表，图片等资源。
```text

CSS不会阻塞DOM解析，但会阻塞DOM渲染。
CSS会阻塞JS执行，并不会阻塞JS文件下载
``` 
1. `<datalist>`标签，用来定义选项列表，与input元素配合使用钙元素，来定义input可能的值。
  datalist及其选项不会被显示出来，他仅仅是合法的输入列表值。
  `<input id="fruits" list="fruit" /><datalist id="fruit">  <option value="apple">  <option value="orange">  <option value="banana"></datalist>`
1. 首屏加载时间
    performance.timing.domContentLoadedEventStart-performance.timing.navigationStart
2.  preload 是声明式的 fetch，可以强制浏览器请求资源，同时不阻塞文档 onload 事件。Prefetch 提示浏览器这个资源将来可能需要，但是把决定是否和什么时间加载这个资源的决定权交给浏览器。
3. 优雅降级 graceful degradation： 一开始就构建完整的功能，然后再针对低版本的浏览器进行兼容。
4. aside  定义页面的侧边栏内容。
   progress 原生的进度条

5.  HTML `<sup>` 元素定义了一个文本区域，出于排版的原因，与主要的文本相比，应该展示得更高并且更小。
6. domPropsInnerHTML  domPropsInnerText
7. 根据 canvas 可以获取浏览器指纹信息
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
2. link属于HTML标签，而@import是CSS提供的页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载。
3. Web quality  : alt
4. 该WindowEventHandlers.onstorage属性包含一个在storage事件触发时运行的事件处理程序。当更改存储区域时会发生这种情况（例如，存储新项目）。
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