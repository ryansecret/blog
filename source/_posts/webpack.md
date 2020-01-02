---
title: webpack
date: 2017-01-17 14:58:02
tags: webpack  
---
### babel相关
1. 虽然@babel/polyfill提供了我们想要的所有新方法新类，但是这里依然存在一些问题：
   
   体积太大：比如我只用了String的新特性，但是我把整个包都引进来了，，这不是徒增了很多无用的代码。
   污染全局环境：如果你引用了 @babel/polyfill，那么像Promise这样的新类就是挂载在全局上的，这样就会污染了全局命名空间。可能在一个团建建立的项目问题不太大，但是如果你是一个工具的开发者，你把全局环境污染了，别人用你的工具，就有可能把别人给坑了
   
1.  @babel/plugin-transform-runtime会为代码创建一个沙盒环境，为core-js这里内建的实例提供假名，你可以无缝的使用这些新特性，而不需要使用require polyfill。
    
    一个解决方案就是引入transform runtime 来替代 @babel/polyfill。
    幸运的是，我们有env这个preset，它又一个useBuiltIns选项，如果设置成"usage"，那么将会自动检测语法帮你require你代码中使用到的功能。  
1. @babel/core
   其中最核心的包就是@babel/core，它主要的作用就是编译.
   
   Babel-cli 
   光有core是无法在命令行使用这些功能的，@babel/cli支持你直接在命令行中编译代码。
   这句话会编译你src目录下的所有js代码，并编译成你想要的那样（babel.config.js配置的），并输出到lib目录下。 
1. @babel/preset-env
如果useBuiltIns为true，项目中必须引入babel-polyfill。



1.UglifyJS: vue-cli 默认使用的压缩代码方式，它使用的是单线程压缩代码，打包时间较慢
  ParallelUglifyPlugin: 开启多个子进程，把对多个文件压缩的工作分别给多个子进程去完成
1. Vue Loader 是一个 webpack 的 loader，它允许你以一种名为单文件组件 (SFCs)的格式撰写 Vue 组件.   
1. autoprefixer 自动补充前缀

1. Hot Module Replacement（以下简称 HMR）是 webpack 发展至今引入的最令人兴奋的特性之一 ，当你对代码进行修改并保存后，webpack 将对代码重新打包，并将新的模块发送到浏览器端，浏览器通过新的模块替换老的模块，这样在不刷新浏览器的前提下就能够对应用进行更新。
1.  webpack-dev-server 修改了webpack 配置中的 entry 属性，在里面添加了 webpack-dev-client 的代码，这样在最后的 bundle.js 文件中就会有接收 websocket 消息的代码了。
1. 
1. WebPack可以看做是模块打包机：它做的事情是，分析你的项目结构，找到JavaScript模块以及其它的一些浏览器不能直接运行的拓展语言（Scss，TypeScript等），并将其打包为合适的格式以供浏览器使用。

1. Webpack splitchunk 将各个模块的交集部分抽离出来 

1. Webpack ProvidePlugin 自动加载js，不必import。
   new webpack.ProvidePlugin({
     _map: ['lodash', 'map']
   })

1. Webpack在打包时可以为我们生成的source maps，这为我们提供了一种对应编译文件和源文件的方法，使得编译后的代码可读性更高，也更容易调试

具体配置参考：http://www.jianshu.com/p/42e11515c10f

感叹号的作用在于使同一文件能够使用不同类型的loader

对css 分模块：

```
{
        test: /\.css$/,
        loader: 'style!css?modules'//跟前面相比就在后面加上了?modules
}
```

Loaders和Plugins常常被弄混，但是他们其实是完全不同的东西，可以这么来说，loaders是在打包构建过程中用来处理源文件的（JSX，Scss，Less..），一次处理一个，插件并不直接操作单个文件，它直接对整个构建过程其作用。

####  常用命令


```
$ webpack --config webpack.min.js //另一份配置文件

$ webpack --display-error-details //显示异常信息

$ webpack --watch   //监听变动并自动打包
 
$ webpack -p    //压缩混淆脚本，这个非常非常重要！
 
$ webpack -d    //生成map映射文件，告知哪些模块被最终打包到哪里了
```

对公共库的封装：

```
entry: {
  vendor: ["jquery", "other-lib"],
  app: "./entry"
}
new CommonsChunkPlugin({
  name: "vendor",

  // filename: "vendor.js"
  // (Give the chunk a different name)

  minChunks: Infinity,
  // (with more entries, this ensures that no other module
  //  goes into the vendor chunk)
})
```

关于express webpack middleware 的配置

http://www.cnblogs.com/linfangshuhellowored/p/5657285.html

给文件自动添加hash后缀

根据chunkhash的定义知道，chunkhash是根据具体模块文件的内容计算所得的hash值，所以某个文件的改动只会影响它本身的hash指纹，不会影响其他文件。配置webpack的output如下：
```
output: {
    filename: '[name].[chunkhash:8].js',
    path: __dirname + '/built'
}
output: {
    filename: '[name].[hash:8].js',
    path: __dirname + '/built'
}
```