---
title: pattern
date: 2016-12-26 14:05:38
tags:
---
##  装饰模式

```
'use strict';
class Sale {
  constructor(price) {
    [this.decoratorsList, this.price] = [[], price];
  }

  decorate(decorator) {
    if (!Sale[decorator]) throw new Error(`decorator not exist: ${decorator}`);
    this.decoratorsList.push(Sale[decorator]);
  }

  getPrice() {
    for (let decorator of this.decoratorsList) {
      this.price = decorator(this.price);
    }
    return this.price.toFixed(2);
  }

  static quebec(price) {
    return price + price * 7.5 / 100;
  }

  static fedtax(price) {
    return price + price * 5 / 100;
  }
}
module.exports=Sale;
```

## 工厂模式


```
 
'use strict';
class CarMaker {
  constructor() {
    this.doors = 0;
  }

  drive() {
    console.log(`jaja, i have ${this.doors} doors`);
  }

  static factory(type) {
    return new CarMaker[type]();
  }
}

CarMaker.Compact = class Compact extends CarMaker {
  constructor() {
    super();
    this.doors = 4;
  }
};

module.exports=CarMaker;

```

## 策略模式 --自行脑补
## 单例模式


```
'use strict';
let __instance = function () {
  let instance;
  return (newInstance) => {
    if (newInstance) instance = newInstance;
    return instance;
  }
}();

class Universe {
  constructor() {
    if (__instance()) return __instance();
    __instance(this);
  }
}
module.exports=Universe;

```

##订阅者模式


```
/**
 * Created by ryan on 2016/8/29.
 */
'use strict';
class Event {
  constructor() {
    this.subscribers = new Map([['any', []]]);
  }

  on(fn, type = 'any') {
    let subs = this.subscribers;
    if (!subs.get(type)) return subs.set(type, [fn]);
    subs.set(type, (subs.get(type).push(fn)));
  }

  emit(content, type = 'any') {
    for (let fn of this.subscribers.get(type)) {
      fn(content);
    }
  }
}

let event = new Event();

event.on((content) => console.log(`get published content: ${content}`), 'myEvent');
event.emit('jaja', 'myEvent'); //get published content: jaja

```
