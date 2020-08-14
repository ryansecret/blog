---
title: js
date: 2020-08-13 15:17:58
tags:
---


    >console.log('子君' instanceof String)  
1. prototype
```text
   function f() {}
var a = f.prototype, b = Object.getPrototypeOf(f);
a === b    
解析：a是构造函数f的原型 ： {constructor: ƒ}
b是实例f的原型对象 ： ƒ () { [native code] }
```
1. webpack hmr
```text
1.当修改了一个或多个文件；
2.文件系统接收更改并通知webpack；
3.webpack重新编译构建一个或多个模块，并通知HMR服务器进行更新；
4.HMR Server 使用webSocket通知HMR runtime 需要更新，HMR运行时通过HTTP请求更新jsonp；
5.HMR运行时替换更新中的模块，如果确定这些模块无法更新，则触发整个页面刷新。
```
1. Git submodule 
```text
$ git submodule init
Submodule 'assets' (https://github.com/maonx/vimwiki-assets.git) registered for path 'assets'
```

```text
$ git submodule add https://github.com/maonx/vimwiki-assets.git assets

$ git submodule update —remote
```

1.  所以函数防抖适用的场景：监听窗口的滚动，缩放。高频发生的一些事件；函数节流适用的场景：涉及与后端交互的按钮，由于网络原因或者其他原因，导致接口没有返回值，用户一直点点点的问题。 
2.  最优子结构、边界、动态转移方程。动态规划的核心—》从低向上，从而不会像递归那样保留调用栈。
3.  十进制转为 2 进制，除 2 取余，然后余数反向
    
    十进制转为 2 进制小时，**乘 2 取整**
4. in操作符:检测指定对象(右边)原型链上是否有对应的属性值。 
    hasOwnProperty方法:检测指定对象自身上是否有对应的属性值。两者的区别在于in会查找原型链,而hasOwnProperty不会。
   
   for...in...遍历对象上除了Symbol以外的可枚举属性,包括原型链上的属性。
   
   Object.keys & Object.assign & JSON.stringify: excluding non-enumerable & __proto__
5. 堆
堆的底层实际上是一棵完全二叉树，可以用数组实现
每个的节点元素值不小于其子节点 - 最大堆
每个的节点元素值不大于其子节点 - 最小堆

1.  浏览器中 customevent
    
```js
var event = new CustomEvent("cat", {  detail: {    hazcheeseburger: true  }});obj.dispatchEvent(event);
```

1.  window.requestAnimationFrame() 告诉浏览器——你希望执行一个动画，并且要求浏览器在下次重绘之前调用指定的回调函数更新动画。该方法需要传入一个回调函数作为参数，该回调函数会在浏览器下一次重绘之前执行
1. Element.getBoundingClientRect() 方法返回元素的大小及其相对于视口的位置。
1.  regex  y stick 粘连修饰符 

1.普通函数在被调用时，JS引擎会创建一个栈帧，在里面准备好局部变量、函数参数、临时值、代码执行的位置（也就是说这个函数的第一行对应到代码区里的第几行机器码），在当前栈帧里设置好返回位置，然后将新帧压入栈顶。待函数执行结束后，这个栈帧将被弹出栈然后销毁，返回值会被传给上一个栈帧。

   当执行到yield语句时，Generator的栈帧同样会被弹出栈外，但Generator在这里耍了个花招——它在堆里保存了栈帧的引用（或拷贝）！这样当iter.next方法被调用时，JS引擎便不会重新创建一个栈帧，而是把堆里的栈帧直接入栈。因为栈帧里保存了函数执行所需的全部上下文以及当前执行的位置，所以当这一切都被恢复如初之时，就好像程序从原本暂停的地方继续向前执行了。

    而因为每次yield和iter.next都对应一次出栈和入栈，所以可以直接利用已有的栈机制，实现值的传出和传入。
1. Array(10)  稀疏矩阵
2. clone
```text
function initData(target) {
  return new target.constructor()
}
return Object(Symbol.prototype.valueOf.call(targe));

function cloneReg(targe) {
    const reFlags = /\w*$/;
    const result = new targe.constructor(targe.source, reFlags.exec(targe));
    result.lastIndex = targe.lastIndex;
    return result;
}
```     
1. js 在底层存储变量的时候，会在变量的机器码的低位1-3位存储其类型信息👉
   
   000：对象
   010：浮点数
   100：字符串
   110：布尔
   1：整数
   
   but, 对于 undefined 和 null 来说，这两个值的信息存储是有点特殊的。
   
   null：所有机器码均为0
   
   undefined：用 −2^30 整数来表示
1. console 分组
```javascript
console.group('action', 'A');

console.log('%c prev state', "color: #dddddd", '\n', {
    name: 'a'
});
console.log('%c next state', "color: #dddddd", '\n',  {
    name: 'b'
});

console.groupCollapsed();
console.log('我是group折叠内容');
console.groupEnd();
console.groupEnd();
```
1.  Object.create(null) 和 {}
1.  每次JavaScript对DOM的操作都会改变当前页面的呈现，并重新刷新整个页面，从而消耗了大量的时间。而createDocumentFragment()的作用，就是可以创建一个文档碎片，
把所有的新节点附加其上，然后把文档碎片的内容一次性添加到document中。

1. indexedDB 的特点：存储空间大：存储空间可以达到几百兆甚至更多；

               >> 支持二进制存储：它不仅可以存储字符串，而且还可以存储二进制数据；
               >> IndexedDB 有同源限制，每一个数据库只能在自身域名下能访问，不能跨域名访问；
               >> 支持事务型：IndexedDB 执行的操作会按照事务来分组的，在一个事务中，要么所有的操作都成功，要么所有的操作都失败；
               >> 键值对存储：IndexedDB 内部采用对象仓库（object store）存放数据。所有类型的数据都可以直接存入，包括 JavaScript 对象。对象仓库中，数据以 “键值对” 的形式保存，每一个数据记录都有对应的主键，主键是独一无二的，不能有重复，否则会抛出一个错误。
               >> 数据操作是异步的：使用 IndexedDB 执行的操作是异步执行的，以免阻塞应用程序。
5. Usecapture:
   true - 事件句柄在捕获阶段执行。事件捕获从父到子。
   false- false- 默认。事件句柄在冒泡阶段执行
1. 浏览器标签页被隐藏或显示的时候会触发visibilitychange事件. document.addEventListener('visibilitychange')
2. Object.assign 继承的否Object.keys & Object.assign & JSON.stringify: excluding non-enumerable & __proto__

3. let is not global while var is.
4. download
```javascript
function download (url, name) {
  const a = document.createElement('a')
  a.download = name
  a.rel = 'noopener'
  a.href = url
  // 触发模拟点击
  a.dispatchEvent(new MouseEvent('click'))
  // 或者 a.click()
}

// 方案一：Text -> DataURL
const dataUrl = `data:,${str}`
download(dataUrl, 'demo.json')

// 方案二：Text -> Blob -> ObjectURL
const url = URL.createObjectURL(new Blob(str.split('')))
download(url, 'demo1.json')

```  
1. stringfy 格式化
```js

const json = {
  a: 3,
  b: 4,
  c: 5
}
const str = JSON.stringify(json, null, 2)

```  
1. proxy 
```js
const negativeArray = els =>
    new Proxy(els, {
        get: (target, propKey, receiver) =>
            Reflect.get(
                target,
                +propKey < 0 ? String(target.length + +propKey) : propKey,
                receiver
            )
    });
const unicorn = negativeArray(["京", "程", "一", "灯"]);
unicorn[-1]; 
``` 
1. 能优化[1,2,5,10].sort()  默认按照字典序  
1.  对于 undeclared 变量的引用，浏览器会报引用错误，如 ReferenceError: b is not defined 。
1. Es6->babel paser->babel traverse->babel core
1.  类数组向数组转换 Array.from slice 。 aguments 就是arrarylike   
1.  xhr  
```js
 
var request = new XMLHttpRequest()
 request.open('GET', 'index/a/b/c?name=TianTian', true);
 request.onreadystatechange = function () {
   if(request.readyState === 4 && request.status === 200) {
     console.log(request.responseText);
   }};
 request.send();
```   
1. V8 对重复的js代码有优化 即时编译技术，如果发现一段代码经常使用，则不用转字节码 直接执行机器码

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
1. ES6 模块功能是它的导入模块是导出时模块的实时只读视图。（相比起 CommonJS，导入的是导出模块的拷贝副本，因此也不是实时的）。只读视图和内存拷贝的区别。
1. atob() 对经过 base-64 编码的字符串进行解码,btoa() base64加吗
1. Console.dir  显示对象所有的属性和方法
1. Broadcast Channel API 允许同一原始域和用户代理下的所有窗口,iFrames 等进行交互。也就是说，如果用户打开了同一个网站的的两个标签窗口，如果网站内容发生了变化，那么两个窗口会同时得到更新通知。
1. escape 在处理 0xff 之外字符的时候，是直接使用字符的 unicode 在前面加上一个 「%u」，而encodeURI则是先进行 UTF-8，再在 UTF-8 的每个字节码前加上一个 「%」； 所以通过encodeUrI 可以获取utf-8 字节长度
1. js value
1. Prototype 包含constructor 和 __proto__. 原型链存储共有的属性和方法，减少内存
1. 基本的数据类型 
```text
基本的数据类型
undefined
null
string
boolean
number
symbol(ES6)

```
1. navigator.userAgent: 返回当前浏览器的user agent字符串
1. 懒加载：
   Javascript 脚步通常要等到 DOM 加载完后才会执行，如果加载的资源过多，可能会影响网页的正常使用。
   能够节省流量和减轻服务器压力，更近一步就是能够为公司省成本。
1. String 和 new String 区别
1. 

```text
对象转原始类型，会调用内置的[ToPrimitive]函数，对于该函数而言，其逻辑如下：

如果Symbol.toPrimitive()方法，优先调用再返回
调用valueOf()，如果转换为原始类型，则返回
调用toString()，如果转换为原始类型，则返回
如果都没有返回原始类型，会报错
var a = {
  value: 0,
  valueOf: function() {
    this.value++;
    return this.value;
  }
};
console.log(a == 1 && a == 2);//true

```
1. Same origin 可以使用broadcast channel 两页面间通信。
1. 注意闭包内this的指向
2. 对于instanceof,无法判断基本类型，但可以正确判断引用类型
3. let x = 2_3333_3333 
4. 哪些操作会造成内存泄漏？
```text
1.意外的全局变量
2.被遗忘的计时器或回调函数
3.脱离 DOM 的引用
4.闭包
```
1.  Map 对象中的数据是根据用户set 的顺序排序的，object 先排数字开头的。


### dataStructure

1. BST 查询二叉树
若任意节点的左⼦子树不不空，则左⼦子树上所有结点的值均⼩小于它的 根结点的值;
若任意节点的右⼦子树不不空，则右⼦子树上所有结点的值均⼤大于它的 根结点的值;
任意节点的左、右⼦子树也分别为⼆二叉查找树。