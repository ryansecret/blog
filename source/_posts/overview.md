---
title: overview
date: 2021-12-13 17:38:48
tags: overview
---
1. watchEffect 不能检测深层的变化，因此reactive 中变化无效，如果需要则 toRefs 转换
1. V2 $attrs   1. custom events go into a @listerner bucket  2.不能绑定class 
1. Npm ls 查看依赖
1. 可以看到结果reactive是递归会将每一层包装成Proxy对象的，深度监听每一层的property
1. effectScope有一个可选参数为boolean，当传入true时表示阻断与父级的联系，阻断后这个scope对象将不会与父级关联，成为独立的scope。父级的stop也不会影响到它。 
1. Last-Modified,Etag,Expires 三个同时使用时。先判断 Expire ，然后发送 Http 请求，服务器先判断 last-modified ，再判断 Etag ，必须都没有过期，才能返回 304 响应
1. klona  fast utility to "deep clone" Objects, Arrays, Dates, RegExps, and more!
1. Grep string starting with (e.g. 'S’)    grep -o 'S.*’
1. ~: 如果写入的是 〜0.13.0，则当运行 npm update 时，会更新到补丁版本：即 0.13.1 可以，但 0.14.0 不可以。
1. >: 接受高于指定版本的任何版本。
1. ^: 只会执行不更改最左边非零数字的更新。 如果写入的是 ^0.13.0，则当运行 npm update 时，可以更新到 0.13.1、0.13.2 等，但不能更新到 0.14.0 或更高版本。 如果写入的是 ^1.13.0，则当运行 npm update 时，可以更新到 1.13.1、1.14.0 等，但不能更新到 2.0.0 或更高版本。
2. firefox 子元素不缩小需要设置  You need to add min‑width:0
3. flex 布局中子级超过了父级的宽度，需要设置 width:0 ,完全由flex 分配宽度。
4. POSIX stands for Portable Operating System Interface.
5.  @supports CSS at-rule 相当于功能选择器
   ```
   @supports (display: flex) {
  body {
    display: flex;
    min-height: 100vh;
  }
}
   ```
2. https://github.com/cuixiaorui/mini-vue  vue3 source code 
3. react 被 startTransition 回调包裹的 setState 触发的渲染 被标记为不紧急渲染，这些渲染可能被其他紧急渲染所抢占。
4. https://hyper.is/ electron console
5. https://cmder.net/ windows 端的console 模拟器
6. Access-Control-Request-Private-Network: true 在所有私有网络预检请求上设置
   Access-Control-Allow-Private-Network: true 必须在所有私有网络预检响应上设置
7. 使用 Fragments，我们不需要在DOM中添加额外的节点。我们只需要用 React.Fragment 或才简写 <> 来包裹内容就行了
8. vite 虚拟模块  虚拟模块是一种很实用的模式，使你可以对使用 ESM 语法的源文件传入一些编译时信息。
9.  glob Match files using the patterns the shell uses, like stars and stuff.
10. click.self 
我们知道在自定义组件上，只能监听自定义事件，一些原生事件（比如click）是没有办法直接触发的，但是使用.native修饰符可以帮我们办到这点
1. offset-path  定义动画运行路径
1. Tauri 是一个为所有主流桌面平台构建小型、快速二进制文件的框架。开发人员可以集成任何编译成 HTML、 JS 和 CSS 的前端框架来构建他们的用户界面。应用程序的后端是一个 Rust 二进制文件，具有前端可以与之交互的 API。
1.  gitsecreat 使用： https://www.mikesay.com/2020/12/16/git-encrypt-file-in-repository/#git-secret%E7%9A%84%E5%AE%89%E8%A3%85%E5%92%8C%E4%BD%BF%E7%94%A8
1. svg2pdf.js 图片转pdf
1. stream 的另外一个模式: objectMode。它是一种对象模式，我们把一件事情、或一个文件、或一个操作，抽象成一个对象。
   ```
   const Readable = require('stream').Readable

   const readable = Readable({ objectMode: true })

    readable.push('a')
    readable.push('b')
    readable.push({})
    readable.push(null)

    readable.on('data', data => console.log(data))

   ```
2. git config --global push.followTags true
3. Markraw 标记不会被reactive
4. watcheffect onInvalidate 在重新运行或者停止的时候执行
5. composedPath() 是 Event 接口的一个方法，当对象数组调用该侦听器时返回事件路径。
6. customref  track and trigger  
7. vueuse useMemoize 对结果加cache
8. elementFromPoint 根据point 获取element
9.  Change-case Transform a string between camelCase, PascalCase, Capital Case, snake_case, param-case, CONSTANT_CASE and others.
10. p-retry It does exponential backoff and supports custom retry strategies for failed operations.
11. MutationObserver 观察dom 变化
12. requestFullscreen
13. passive: Boolean，设置为true时，表示 listener 永远不会调用 preventDefault()。如果 listener 仍然调用了这个函数，客户端将会忽略它并抛出一个控制台警告
14. shallowReacive  shallowRef  shallowRef生成非递归响应数据，只监听第一层数据的变化
15. 推荐在大部分时候用 watch 显式的指定依赖以避免不必要的重复触发，也避免在后续代码修改或重构时不小心引入新的依赖。watchEffect 适用于一些逻辑相对简单，依赖源和逻辑强相关的场景（或者懒惰的场景 ）。
16. Object.fromEntries
17. URL.revokeObjectURL() 静态方法用来释放一个之前已经存在的、通过调用 URL.createObjectURL() 创建的 URL 对象。
18. querySelector  返回第一个匹配元素
19. Array.prototype.at()接收一个正整数或者负整数作为参数，表示获取指定位置的成员
20. IFC全称：Inline Formatting Context，名为行级格式化上下文。    触发：块级元素中仅包含内联级别元素
21. The Notification interface of the Notifications API is used to configure and display desktop notifications to the user.
22. TinyMCE 富文本编辑器
23. Window.innerHeight  浏览器窗口的视口（viewport）高度（以像素为单位）；如果有水平滚动条，也包括滚动条高度。
24. vuedraggable 处理拖动数据
25. path-to-regexp   Turn a path string such as /user/:name into a regular expression. The compile function will return a function for transforming parameters into a valid path:
26. vue router 重新render,redirect+fullpath.通过添加一个中转页实现。
27. import { storeToRefs } from "pinia”;
28. html5 input number
 ```
.no-arrow::-webkit-outer-spin-button,
.no-arrow::-webkit-inner-spin-button {
  -webkit-appearance: none;
}
 ``` 
2. vue3 类型 MayBeRef
3. 暂停watch后更新，
```
ignoreUpdates(() => {
  source.value = 'ignored'
})
```

1. dsp 读取json,csv,xlxs 数据
1. limu 创建imutable 对象
2. controlledRef set peek,控制数据的更新
 ```
 const num = controlledRef(0, {
  onBeforeChange(value, oldValue) {
    // disallow changes larger then ±5 in one operation
    if (Math.abs(value - oldValue) > 5)
      return false // returning `false` to dismiss the change
  },
})
 ```

1. flush: post 推迟副作用的初始运行，直到组件的首次渲染完成。
   watch 通过更改设置 flush: 'sync'，我们可以为每个更改都强制触发侦听器，尽管这通常是不推荐的
   ```

- `'pre'`: buffers invalidated effects in the same 'tick' and flushes them before rendering
- `'post'`: async like 'pre' but fires after component updates so you can access the updated DOM
- `'sync'`: forces the effect to always trigger synchronously

 { flush: 'post' }
)

   ```
1. transx vue 动画组件   一个小巧玲珑的 vue 组件切换动画库
2. ts-morph 修改ts 代码，封装后的ts compiler api
3. esno 执行ts
4. https://mermaid-js.github.io/mermaid/#/     mermaid 及其方便的画图工具
5. vue-parallaxy Is a compontent for fast 60fps parallax scroll effects in vue 2. 实现滚动的视差效果。
6. useWatermark,Layzcontainer. context menu  vue-vben-admin 中
7. localForage is a fast and simple storage library for JavaScript。Wraps IndexedDB, WebSQL, or localStorage using a simple but powerful API.
8.  markRaw 标记对下不会被reactive
9.  indexeddb-fs is a module that allows you to store data in the browser using an API similar to that of Node's fs module.
10. 临时安全令牌（Security Token Service，STS）
11. *** 获取文本px宽度* @param font{String}: 字体样式**

```
String.prototype.pxWidth = function(font) {
  // re-use canvas object for better performance
  var canvas = String.prototype.pxWidth.canvas || (String.prototype.pxWidth.canvas = document.createElement("canvas")),
      context = canvas.getContext("2d"); 3

  font && (context.font = font);
  var metrics = context.measureText(this);

  return metrics.width;
}
```

1. 先保存各个实例的values信息， helm get values [release] > xxx.yaml


1. 
HTTP协议中用头部字段Accept-Encoding 和 Content-Encoding对「采用何种编码格式传输正文」进行了协定，请求头的Accept-Encoding会列出客户端支持的编码格式。当响应头的 Content-Encoding指定了gzip时，浏览器则会进行对应解压

1. Transfer-Encoding，是一个 HTTP 头部字段，字面意思是「传输编码」。实际上，HTTP 协议中还有另外一个头部与编码有关：Content-Encoding（内容编码）。Content-Encoding 通常用于对实体内容进行压缩编码，目的是优化传输，
```
Transfer-Encoding: chunked
Transfer-Encoding: compress
Transfer-Encoding: deflate
Transfer-Encoding: gzip
Transfer-Encoding: identity
```


2. 逐跳消息头  这类消息头仅对单次传输连接有意义，不能通过代理或缓存进行重新转发

1. git merge --squash develop
2. mime  https://github.com/sindresorhus/file-type  根据文件内容判断类型

1. 语义化版本控制(SemVer)
   先简单了解下什么是语义化的版本控制，其是由GitHub发起的一份用于规范版本号递增的规则，

1.  deeplinks.js allows people to easily link directly to any text selection on your website.
2.  Vue DevUI 开源的UI
3. standard-version
standard-version 会根据提交的信息类型来自动更改对应的版本号,如下:
```
feat: 次版本(minor)+1
fix: 修订号(patch) +1
BREAK CHANGE: 主板号(marjor) +1
```
1. outline 能告诉用户那一个可以激发事件的html元素获取了焦点，对钟爱键盘操作的用户尤其有意义。一个清晰悦目的outline设计能提高使用表单的用户体验。
2. CSS属性 columns 用来设置元素的列宽和列数。
重点，设置了display: contents的元素本身不会被渲染，但是其子元素能够正常被渲染。
3. 为了使我们的盒子居中，通过align-items属性，可以将交叉轴上的item对齐，此时使用的是垂直方向的块轴。而使用justify-content则可以对齐主轴上的项目，主轴是水平方向的。
align conent  用来控制多行布局   控制“多条主轴”的 flex 项目在交叉轴的对齐。

1. CSS 中的 place-items 是一个简写属性 ，它允许你在相关的布局（如 Grid 或 Flexbox）中可以同时沿着块级和内联方向对齐元素 (例如：align-items 和 justify-items 属性) 。如果未提供第二个值，则第一个值作为第二个值的默认值

1. filter CSS属性将模糊或颜色偏移等图形效果应用于元素。滤镜通常用于调整图像，背景和边框的渲染。

1. monaco 自定义language
```
register monaco.languages.register({ id: 'mySpecialLanguage' });
setMonarchTokensProvider base language 里面有3 
defineTheme  设置样式
monaco.editor.defineTheme('myCoolTheme', {
                    colors: {},
                    base: 'vs',
                    inherit: false,
                    rules: [
                        { token: 'custom-info', foreground: '808080' },
                        { token: 'custom-error', foreground: 'ff0000', fontStyle: 'bold' },
                        { token: 'custom-notice', foreground: 'FFA500' },
                        { token: 'custom-date', foreground: '008800' }
                    ]
                });
registerCompletionItemProvider  智能提示，遇到对应的关键词
```

1. Monarch  用来实现代码高亮   https://juejin.cn/post/6844903736867831822

https://microsoft.github.io/monaco-editor/monarch.html

1. xe-utils 提供工具类
1. Mitt  Tiny (~200b) functional event emitter / pubsub.
1. element-resize-detector  
1. memoize-one 记录最近的返回结果 
1. 钱其实是“保健因子”，而不是“激励因子”，是多了没用、少了不行的东西
2. 可以看到整个医改的核心就是放供给、促竞争和扶创新的过程
3. 破船能过河
4. Comlink Comlink makes WebWorkers enjoyable. 多线程
5.  
`Rails-style`: 按照文件的类型划分为不同的目录

`Domain-style`: 按照一个功能特性或业务创建单独的目录

`Ducks-style`: 优点类似于Domain-style，不过更彻底, 它通常将相关联的元素定义在一个文件下

1. 
    强约定，体现团队的规范。首先它应该避免团队成员去关心或更改构建的配置细节，暴露最小化的配置接口。 另外构建工具不仅仅是构建，通常它还会集成代码检查、测试等功能。

    方便升级。尤其是团队需要维护多个项目场景, 这一点很有意义

2. BEM
```
元素（Element），即 price 、text ，代表从属于某个块，是这个块的子元素，跟在块后面，以双下划线为间隔，使用 .btn__price 、.btn__text 表示

修饰符（Modifier），即 orange 、big ，用于修改块的状态，为块添加特定的主题或样式，跟在块后面，以双连字符为间隔，使用 .btn--orange 、.btn--big 表示

```   
1.  npm-run-all
```
Before: npm run clean && npm run build:css && npm run build:js && npm run build:html
After: npm-run-all clean build:*
```

1. display:flow-root可以让元素块状化，同时包含格式化上下文BFC，可以用来清除浮动，去除margin合并，实现两栏自适应布局等。

1. stroke-dash 是一个定义虚线和间距图形的图像工具类, 被用于轮廓描边;

1. npx degit
   
1.  有一些环境变量，比如HOME、PATH、SHELL、UID、USER等，在用户登录之前就已经被/bin/login程序设置好了。通常环境变量被定义并保存在用户家目录下的．bash_profile文件或全局的配置文件/etc/profile中

1. env命令只显示全局变量；declare命令输出所有的变量、函数、整数和已经导出的变量

1. http upgrade 通常来说这一机制总是由客户端发起的 （不过也有例外，比如说可以由服务端发起升级到传输层安全协议（TLS））， 服务端可以选择是否要升级到新协议。借助这一技术，连接可以以常用的协议启动（如HTTP/1.1），随后再升级到HTTP2甚至是WebSockets.

1. 因为 CommonJS 在运行时进行加载方式的动态解析，在运行时阶段才能确定的导入导出关系，因此无法进行静态编译优化和类型检查。​

1. JSZip  JSZip is a javascript library for creating, reading and editing .zip files, with a lovely and simple AP
   
2. spy-debugger  一站式页面调试、抓包工具。远程调试任何手机浏览器页面，任何手机移动端webview（如：微信，HybridApp等）。支持HTTP/HTTPS，无需USB连接设备
   
3. viteshot 基于vite 的快照

4. useScrollLock