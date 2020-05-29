---
title: package
date: 2019-02-14 17:19:12
tags: useful package
---

1. Opn: A better node-open. Opens stuff like websites, files, executables. Cross-platform.
2. Ora:进度条和文字。
3. joi：数据验
4. satisfies ：版本工具
5. minimist：简单的参数处理
6. read-pkg:规范化解析pkg
7. inquirer:询问时可以给出选项
8. Resovel:解析包的安装路径
9. slash:Convert Windows backslash paths to slash paths: foo\\bar ➔ foo/bar
1. klaw-sync:回遍历出所有文件，并返回文件路径和文件夹
1. mime-types content-type 工具：1. 可以根据文件后缀获取 2. 根据content-type获取charset 3. 根据content-type 获取默认的文件名
1. CodeMirror是一个运行在浏览器中的在线代码编辑器，支持100多种语言，高度可定制。
1. @typescript-eslint/eslint-plugin.  eslint 检测typescript 
1. nanoid  A tiny, secure, URL-friendly, unique string ID generator for JavaScript.
1. mm 对mudule 中的方法mock
1. numerify  用来格式化数字 
   
1. utils-lite  前端提供debounce、thorttling、clone、cloneDeep 等方法
1. is-type-of   node check 数据类型
1. on-finished  Execute a callback when a HTTP request closes, finishes, or errors
1. await-event  封装了promise 
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
1. ShellJS 是Unix shell命令在Node.js API上的可移植实现
1. graceful-process   graceful exit process even parent exit on SIGKILL.
1. semver.gte(process.version, '7.0.0’)  版本的比对 
1. pkgfiles  自动再package中添加 npm publish 文件
1. depd  标注方法deprecating 
1. http-errors   http错误  
1. Global-tunnel  http请求的全局代理  
1. humanize-ms  转义为ms  
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