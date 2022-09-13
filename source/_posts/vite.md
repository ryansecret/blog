---
title: vite 
date: 2022-06-06 15:44:53
tags:
---

1. 上面提到Vite是基于浏览器原生支持ESM的能力实现的，但要求用户的代码模块必须是ESM模块，因此必须将commonJs的文件提前处理，转化成 ESM 模块并缓存入 node_modules/.vite
2. 减少模块和请求数量  Vite 将有许多内部模块的 ESM 依赖关系转换为单个模块，以提高后续页面加载性能。
3. handleHotUpdate  热更新hook
4. configureServer   是用于配置开发服务器的钩子。最常见的用例是在内部 connect 应用程序中添加自定义中间件:

```
以下钩子在服务器启动时被调用：

options
buildStart

以下钩子会在每个传入模块请求时被调用：

resolveId
load
transform
以下钩子在服务器关闭时被调用：

buildEnd
closeBundle
如果你的插件使用 'virtual modules'（比如帮助函数），给模块名加上 \0 前缀。这可以阻止其他插件执行它。

const myPlugin = {
    name: 'my-plugin', //  必须的插件标志
    apply: 'build' | 'serve', //  表明此插件应用在何种模式
    enforce: 'post' | 'pre', //  插件排序

    // rollup通用插件，ctx是一个plugins集合的上下文
    options(ctx,pluginOptions) {
      //  返回plugin opthons ，类型：async, sequential
      return somePluginOptions
    },
    buildStart(ctx,pluginOptions) {
      //  在服务启动前开始执行，类型：async, parallel
      //  ...do something
    },
    resolveId(ctx,srouce, importer, pluginOptions) {
      //  srouce为资源的路径，importer为引入此资源的文件
      //  如果有返回值，则将替换掉importer中引入的路径，同时将返回值传递给其他hook
      //  类型 async, first
      //  ...do something
      return srouce
    },
    load(ctx,id, srr) {
      //  id为resolveId返回的值
      //  加载资源并返回 类型 async, first
      //  ...do something
      return code
    },
    transform(ctx,code, id, ssr) {
      //  code为load返回的值，id为resolveId返回的值
      //  转译code并返回转译结果 类型 async, first，
      //  ...do something
      return transformCode
    },
    buildEnd(err) {
      //  构建结束的回调，可以捕获错误。类型 async, parallel
    },
    closeBundle() {
      //  构建结束的最终回调，类型 async, parallel
    },

    //  vite 独有插件
    config(config, env) {
      //  返回一个配置对象，merge到最终config中
      //  类型 sync, sequential
      return config
    },
    configResolved(config) {
      //  解析 Vite 配置后调用 类型 sync, parallel
    },
    configureServer(server) {
      //  服务器配置完后的hook 类型 sync, paralle
    },
    transformIndexHtml() {
      // 转换 index.html 的专用钩子。钩子接收当前的 HTML 字符串和转换上下文
      // 类型 async, sequential
    },
    handleHotUpdate(HmrContext) {
      //  触发热更新时的hook，可以更加精确的控制hmr
      //  类型
    }
  }

```


1. 