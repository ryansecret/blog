---
title: webpack
date: 2017-01-17 14:58:02
tags:
---
autoprefixer 自动补充前缀


WebPack可以看做是模块打包机：它做的事情是，分析你的项目结构，找到JavaScript模块以及其它的一些浏览器不能直接运行的拓展语言（Scss，TypeScript等），并将其打包为合适的格式以供浏览器使用。

Webpack在打包时可以为我们生成的source maps，这为我们提供了一种对应编译文件和源文件的方法，使得编译后的代码可读性更高，也更容易调试

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