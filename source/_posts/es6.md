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
 
### lit
1. 数组的空位 [,,,]

1. parentheses to be omitted, as in

try {
  // ...
} catch {
  // ...
}

 
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

#### console 
```javascript

console.table()
console.dir()
console.count()
Console.time() 
consoel.timeLog()
console.time("answer time");
alert("Click to continue");
console.timeEnd("answer time”);

```