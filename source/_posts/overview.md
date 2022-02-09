---
title: overview
date: 2021-12-13 17:38:48
tags: overview
---

1.  临时安全令牌（Security Token Service，STS）
2.  *** 获取文本px宽度* @param font{String}: 字体样式**

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

