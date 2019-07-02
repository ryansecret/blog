---
title: es6
date: 2019-06-28 11:58:20
tags: es
---
### reflect 
1. 修改某些Object方法的返回结果，让其变得更合理
```javascript
// 老写法
try {
  Object.defineProperty(target, property, attributes);
  // success
} catch (e) {
  // failure
}

// 新写法
if (Reflect.defineProperty(target, property, attributes)) {
  // success
} else {
  // failure
}
```

1. 命令式改为函数式
```javascript
// 老写法
'assign' in Object // true

// 新写法
Reflect.has(Object, 'assign') // true
```

1. Reflect对象的方法与Proxy对象的方法一一对应
```javascript
Proxy(target, {
  set: function(target, name, value, receiver) {
    var success = Reflect.set(target, name, value, receiver);
    if (success) {
      console.log('property ' + name + ' on ' + target + ' set to ' + value);
    }
    return success;
  }
});
```
####async 函数是什么？一句话，它就是 Generator 函数的语法糖。
```javascript
const fs = require('fs');

const readFile = function (fileName) {
  return new Promise(function (resolve, reject) {
    fs.readFile(fileName, function(error, data) {
      if (error) return reject(error);
      resolve(data);
    });
  });
};

const gen = function* () {
  const f1 = yield readFile('/etc/fstab');
  const f2 = yield readFile('/etc/shells');
  console.log(f1.toString());
  console.log(f2.toString());
};
```
### module 
1. CommonJS 模块输出的是值的拷贝，也就是说，一旦输出一个值，模块内部的变化就影响不到这个值。
```javascript

var counter = 3;
function incCounter() {
  counter++;
}
module.exports = {
  counter: counter,
  incCounter: incCounter,
};

// main.js
var mod = require('./lib');

console.log(mod.counter);  // 3
mod.incCounter();
console.log(mod.counter); // 3
```
可以使用Es6 加载commonjs 模块。 CommonJS 模块的输出缓存机制，在 ES6 加载方式下依然有效。


CommonJS 模块加载 ES6 模块，不能使用require命令，而要使用import()函数。

```javascript
// es.mjs
let foo = { bar: 'my-default' };
export default foo;

// cjs.js
const es_namespace = await import('./es.mjs');
// es_namespace = {
//   get default() {
//     ...
//   }
// }
console.log(es_namespace.default);
// { bar:'my-default' }
```

### lit
1. 数组的空位 [,,,]

1. parentheses to be omitted, as in

try {
  // ...
} catch {
  // ...
}

### generator
1. Generator  yield表达式后面的表达式，只有当调用next方法、内部指针指向该语句时才会执行，因此等于为 JavaScript 提供了手动的“惰性求值”（Lazy Evaluation）的语法功能。
  yield表达式本身没有返回值，或者说总是返回undefined。next方法可以带一个参数，该参数就会被当作上一个yield表达式的返回值。

1. Co 模块相关于一个generator 的执行器。co 模块其实就是将两种自动执行器（Thunk 函数和 Promise 对象），包装成一个模块。使用 co 的前提条件是，Generator 函数的yield命令后面，只能是 Thunk 函数或 Promise 对象。
1. 代码中，虽然map方法的参数是async函数，但它是并发执行的，因为只有async函数内部是继发执行，外部不受影响。后面的for..of循环内部使用了await，因此实现了按顺序输出
```javascript
async function logInOrder(urls) {
  // 并发读取远程URL
  const textPromises = urls.map(async url => {
    const response = await fetch(url);
    return response.text();
  });

  // 按次序输出
  for (const textPromise of textPromises) {
    console.log(await textPromise);
  }
}
```
1. 对象的Symbol.iterator
  
  由于 Generator 函数就是遍历器生成函数，因此可以把 Generator 赋值给对象的Symbol.iterator属性，从而使得该对象具有 Iterator 接口。
```javascript
var myIterable = {};
myIterable[Symbol.iterator] = function* () {
  yield 1;
  yield 2;
  yield 3;
};

[...myIterable]

```
   Iterator 接口和generator 函数：
   ```javascript
let obj = {
  * [Symbol.iterator]() {
    yield 'hello';
    yield 'world';
  }
};
```

1. 只要 Generator 函数内部部署了try...catch代码块，那么遍历器的throw方法抛出的错误，不影响下一次遍历。
   
   Gnerator 嵌套：
   
```javascript
function* inner() {
       yield 'hello!';
   }
   
   function* outer1() {
       yield 'open';
       yield *inner();
       yield 'close';
   }
```
1. 异步的同步表达：
    
```javascript
   function* main() {
     var result = yield request("http://some.url");
     var resp = JSON.parse(result);
       console.log(resp.value);
   }
   
   function request(url) {
     makeAjaxCall(url, function(response){
       it.next(response);
     });
   }
   
   var it = main();
   it.next();
   
```

### proxy

1. Proxy 的 construct 用于拦截 new()
   isExtensible方法拦截Object.isExtensible操作。
   ownKeys方法用来拦截对象自身属性的读取操作。具体来说，拦截以下操作。
   
   Object.getOwnPropertyNames()
   Object.getOwnPropertySymbols()
   Object.keys()
   for...in循环
```javascript
var obj = new Proxy({}, {
     get: function (target, key, receiver) {
       console.log(`getting ${key}!`);
       return Reflect.get(target, key, receiver);
     },
     set: function (target, key, value, receiver) {
       console.log(`setting ${key}!`);
       return Reflect.set(target, key, value, receiver);
     }
   });
```

1. Class 的generator :
```javascript
class Foo {
     constructor(...args) {
       this.args = args;
     }
     * [Symbol.iterator]() {
       for (let arg of this.args) {
         yield arg;
       }
     }
   }

```
1. 绑定上下文

```javascript
function selfish (target) {
  const cache = new WeakMap();
  const handler = {
    get (target, key) {
      const value = Reflect.get(target, key);
      if (typeof value !== 'function') {
        return value;
      }
      if (!cache.has(value)) {
        cache.set(value, value.bind(target));
      }
      return cache.get(value);
    }
  };
  const proxy = new Proxy(target, handler);
  return proxy;
}

const logger = selfish(new Logger());
```   


