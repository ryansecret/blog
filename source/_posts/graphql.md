---
title: graphql
date: 2019-08-23 16:19:28
tags:
---
1. 
```text
function(parent, args, ctx, info) {
    …
其中的参数的意义如下：

parent: 当前上一个Resolver的返回值
args: 传入某个Query中的函数（比如上面例子中article(id: Int)中的id）
ctx: 在Resolver解析链中不断传递的中间变量（类似中间件架构中的context）
info: 当前Query的AST对象
}
```
2. query（查询）：当获取数据时，应当选取Query类型

   mutation（更改）：当尝试修改数据时，应当使用mutation类型
   
   subscription（订阅）：当希望数据更改时，可以进行消息推送，使用subscription类型
