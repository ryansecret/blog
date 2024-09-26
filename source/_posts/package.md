---
title: package
date: 2019-02-14 17:19:12
tags: useful package
---
1. vue-loading-overlay 方便添加蒙层
1. Vue-intro  新功能引导  
1. zebra-editor-core  富文本编辑器
1.  lucky sheet 在线的excel编辑
1. generic-pool  资源池，可以reuse 和限制一些比较贵的资源比如数据库链接。
1. Mind elixir 浏览器思维导图js module
1.  cp-cli  copy 跨平台
1.  markdown-it :  markdown parser
1. web-storage-cache 对HTML5 localStorage 和sessionStorage 进行了扩展，添加了超时时间，序列化方法。可以直接存储json对象，同时可以非常简单的进行超时时间的设置。
1. ImmortalDB 是在浏览器中存储持久键值数据的最佳方法。保存到 ImmortalDB 的数据被冗余地存储在 Cookies，IndexedDB 和 localStorage 中，并且如果其中的任何数据被删除或损坏，它们将不断进行自我修复。
1. localForage 是一个快速简单的 JavaScript 存储库。 它通过使用类似于 localStorage 的简单 API 来使用异步存储（IndexedDB 或 WebSQL)），进而改善你的 Web 应用程序的离线体验。
1. webworker-threads  node 多线程模块处理计算密集任务
1. Textures.js  基于d3 生成纹理
1. robotjs 控制键盘、鼠标、屏幕
1. vue-count-to  的数字滚动组件，vue-count-to是一个无依赖，轻量级的vue组件，可以自行覆盖easingFn。你可以设置 startVal 和 endVal，它会自动判断计数或倒计时
1. fullpagejs  通过调用本库可轻易创建全屏滚动网站(也称为单页网站)。 本库可创建全屏滚动网站，同时也可在网站中添加横向滚动条。
1. Opn: A better node-open. Opens stuff like websites, files, executables. Cross-platform.
2. Ora:进度条和文字。
3. joi：数据验
4. minimist：简单的参数处理
5. read-pkg:规范化解析pkg
6. inquirer:询问时可以给出选项
7. Resovel:解析包的安装路径
8. slash:Convert Windows backslash paths to slash paths: foo\\bar ➔ foo/bar
9. klaw-sync:回遍历出所有文件，并返回文件路径和文件夹
10. mime-types content-type 工具：1. 可以根据文件后缀获取 2. 根据content-type获取charset 3. 根据content-type 获取默认的文件名
11. CodeMirror是一个运行在浏览器中的在线代码编辑器，支持100多种语言，高度可定制。
1. @typescript-eslint/eslint-plugin.  eslint 检测typescript 
1. nanoid  A tiny, secure, URL-friendly, unique string ID generator for JavaScript.
2. mm 对mudule 中的方法mock
3. numerify  用来格式化数字 
   
4. utils-lite  前端提供debounce、thorttling、clone、cloneDeep 等方法
5. is-type-of   node check 数据类型
6. on-finished  Execute a callback when a HTTP request closes, finishes, or errors
7. await-event  封装了promise 

```javascript
var PassThrough = require('stream').PassThrough
 
var stream = new PassThrough()
// you attach it directly on an event emitter
stream.await = require('await-event')
 
co(function* () {
  var chunk = yield stream.await('data')
  var chunk = yield stream.await('data')
  var chunk = yield stream.await('data')
}).catch(noop)
 
stream.write('some chunk’) 
```
1. get-ready  NodeJS mixin to add one-time ready event
2. ShellJS 是Unix shell命令在Node.js API上的可移植实现
3. graceful-process   graceful exit process even parent exit on SIGKILL.
4. semver.gte(process.version, '7.0.0’)  版本的比对 
5. pkgfiles  自动再package中添加 npm publish 文件
6. depd  标注方法deprecating 
7. http-errors   http错误  
8. Global-tunnel  http请求的全局代理  
9. humanize-ms  转义为ms  
```
transform humanize time to ms  ms('1s') // 1000
ms(1000) // 1000
```
1. Exceljs 一个功能强大的excel 处理包
1. ready-callback 所有注册的事件完成后，才执行ready中方法
1. Get-ready  NodeJS mixin to add one-time ready event，ready 后执行相关方法
1. xml2js  将xml 转换为json 
1. debug  调试状态输出  debug=*  debug=work:*   
1. delegates  node模块中代理proto中属性的方法、setter和getter
1. chokidar filewatch 
1. Puppeteer  headless browser
1. cross-env Run scripts that set and use environment variables across platforms
1. simplemde  markdown editor 
1. serialize-javascript  Serialize JavaScript to a superset of JSON that includes regular expressions and functions.
1.route-cache  express router cache
```javascript
var routeCache = require('route-cache');
 
// cache route for 20 seconds
app.get('/index', routeCache.cacheSeconds(20), function(req, res){
  // do your dirty work here...
  console.log('you will only see this every 20 seconds.');
  res.send('this response will be cached');
});
```
1. Ws server 端的websoket 
1. fastclick  解决浏览器点击的延迟
1. Qs  A querystring parsing and stringifying library with some added security.
1. lru-cache  A cache object that deletes the least-recently-used items.
1. memory-fs  A simple in-memory filesystem. Holds data in a javascript object
1. faker.js  generate massive amounts of fake data in the browser and node.js
1. parseurl 等同node url parse，加了cache
1. vue-lazy-component   Vue.js 2.x 组件级懒加载方案-Vue.js 2.x component level lazy loading solution
1. async-validator  数据验证
1. fast-safe-stringify    Safe and fast serialization alternative to JSON.stringify.
1. node-notifier   Send cross platform native notifications using Node.js.
1. dateformat   node 时间处理函数
1. agentkeepalive  defaut is keepalive
1. copy-to   copy an object's properties to another one, include propertiy, getter and setter.
1. platform   A platform detection library that works on nearly all JavaScript platforms.

1. svg-captcha 验证码  
1. vue-virtual-scroller  加载大量数据
1. FileSaver.js  保存大于 ram的文档
1. vue-draggable-resizable  Vue2 Component for draggable and resizable elements.
1. ScrollTrigger  根据滚动位置出发事件
1. Vue Virtual Scroller   RecycleScroller 可以渲染列表中的可见项目。如果你不知道项目的大小，最好使用 DynamicScroller
1. Vuetensils  没有样式的component,可定制自己样式
1. v-calendar  日历插件
1. vue-grid-layout 可以拖拽的布局控件
1. Vue-content-loader  占位符控件
1. Sinon   node 端监控方法执行、mock、spy
1. figlet  控制台标题文字
1. Cockatiel  是一个弹性和瞬态故障处理库，如重试，断路器，超时，隔板隔离和回退之类的策略。
1. Signale  一个 Node 的日志格式库，自带16个级别，可以定制颜色和 Emoji。
1. Wiki.js  构建wiki 文档管理 
1. fast-xml-parser xml 和     json 转换
1. js-cloudimage-360-view 360度查看
1. crontab ui
1. X-spreadsheet css 实现的sheet
1. SitDown  [html to markdown](http://domchristie.github.io/turndown/)
1. Wekan 一个开源的看板软件
1. droppy  提供web界面的可本地部署的文件管理
1. uplot 渲染大量数据，占用资源少
1. https://github.com/jlongster/absurd-sql  sqllite 对indexdb的封装
2. https://www.npmjs.com/package/zx   zx node shell 的脚本终极方案
 
 
2. chan  A golang like channel implementation for JavaScript that works well with co.
3. pump  When using standard source.pipe(dest) source will not be destroyed if dest emits close or an error. You are also not able to provide a callback to tell when then pipe has finished.
4. npx cloc path 用来统计代码行数
5. acorn  A tiny, fast JavaScript parser written in JavaScript.
6.  picocolors  The tiniest and the fastest library for terminal output formatting with ANSI colors.添加背景色的。
7.  hash-sum  blazing fast unique hash generator
8.  micromatch  Glob matching for javascript/node.js. A replacement and faster alternative to minimatch and multimatch.
9.  xterm-addon-attach  An addon for xterm.js that enables attaching to a web socket. This addon requires xterm.js v4+.
10. node-pty 虚拟的terminal forkpty(3) bindings for node.js. This allows you to fork processes with pseudoterminal file descriptors. It returns a terminal object which allows reads and writes.
  asdf
1. dom-to-image 一个可以将任意DOM节点转换为用JavaScript编写的矢量（SVG）或光栅（PNG或JPEG）图像的库
2. pako js 用来压缩和解压
 