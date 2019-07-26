---
title: cookies
date: 2019-06-24 14:40:18
tags: 零碎
---
### 发版
1. 发布阶段：更新chagelog ,打 git tag 。

### js

1. 随机字符串 Math.random().toString(36).substr(2));

2. Babel pollyfy 的作用 ：https://zhuanlan.zhihu.com/p/29058936

3. Babel stag2 的功能  https://github.com/babel/babel/tree/master/packages/babel-preset-stage-2
1. 所有的babel 包  https://github.com/babel/babel/tree/master/packages
1.  npx babel-upgrade
1. ES2019 中为Symbol对象添加了只读属性 description ，该对象返回包含Symbol描述的字符串。
1. 变量的临时死区  
1. SET 操作的时间复杂度
1. 如果你传的 context 就 null 或者 undefined，那么 window 对象就是默认的 context（严格模式下默认 context 是 undefined）
1. 高阶函数的定义
1. 作用域以及作用域链  函数作用域 —闭包
1. 
## mac
1. Mac 设置path  export PATH=$PATH:
1.  查看端口占用：lsof -i:3001

## npm
1. npm config edit
1. npm config set init.author.name "ryansecreat"
1. npm config set init.email='chenjingnan@jd.com’
1. npm config set init.license "MIT"
1. npm start --prefix path/to/your/folder   //指定目录下运行
1. npm repo   浏览器中打开repo

   
### vim 
j: 下移一行；

k: 上移一行；

w: 前移一个单词，光标停在下一个单词开头；

e: 前移一个单词，光标停在下一个单词末尾；

0: 移动到行首。

$: 移动到行尾。

n|: 把光标移到递n列上

zz: 将当前行移动到屏幕中央。

o: 在下面新建一行插入；

O: 在上面新建一行插入；

a: 在光标后插入；

A: 在当前行最后插入；

u: 取消一(n)个改动。

ctrl + r: 重做最后的改动。