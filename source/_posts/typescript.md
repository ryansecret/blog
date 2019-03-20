---
title: typescript
date: 2019-02-25 10:16:27
tags: ts
---

### 只读属性
```
interface Point {
    readonly x: number;
    readonly y: number;
}
```

###  接口继承  
    支持多重继承, 比较有意思的事接口可以继承类

### 枚举类型
 ```
 enum Color {Red, Green, Blue}
 let c: Color = Color.Green;
```

### any 
```angular2html
let notSure: any = 4;
notSure = "maybe a string instead";
notSure = false; // okay, definitely a boolean

```
### 类型断言 
as 和 <>

### 剩余参数 
```angular2html
function invokeLater(args: any[], callback: (...args: any[]) => void) {
    /* ... Invoke callback with 'args' ... */
}

// Unsound - invokeLater "might" provide any number of arguments
invokeLater([1, 2], (x, y) => console.log(x + ', ' + y));

```

### 交叉类型 特色
Person & Serializable & Loggable同时是 Person 和 Serializable 和 Loggable。 就是说这个类型的对象同时拥有了这三种类型的成员。

### 联合类型 
 如果一个值的类型是 A | B，我们能够 确定的是它包含了 A 和 B中共有的成员。 -- 用来做代码检查的
 ```
interface Bird {
    fly();
    layEggs();
}

interface Fish {
    swim();
    layEggs();
}

function getSmallPet(): Fish | Bird {
    // ...
}

let pet = getSmallPet();
pet.layEggs(); // okay
pet.swim();    // error

需要类型转换：(<Fish>pet).swim()

```
 
###  谓词为 parameterName is Type这种形式
```
function isFish(pet: Fish | Bird): pet is Fish {
    return (<Fish>pet).swim !== undefined;
}
```
### 参数指定默认值 
```angular2html
function keepWholeObject(wholeObject: { a: string, b?: number }) {
    let { a, b = 1001 } = wholeObject;
}
TypeScript编译器不允许展开泛型函数上的类型参数 。 这个特性会在TypeScript的未来版本中考虑实现。 ...


function buildName(firstName: string, lastName: string = 'Cat') {
    return firstName + ' ' + lastName;
}

```
### 数组泛型   
Array<number>  

let list: any[] = ['Xcat Liu', 25, { website: 'http://xcatliu.com' }];

用接口表示数组：

interface NumberArray {
    [index: number]: number;
}

### 声明语句 
declare var jQuery: (string) => any;

我们约定声明文件以 .d.ts 为后缀。
### 元组 
```angular2html
let xcatliu: [string, number];
xcatliu[0] = 'Xcat Liu';
xcatliu[1] = 25;
```
### 命名空间  来源于C# 
namespace Validation {}

import 别名
```angular2html
amespace Shapes {
    export namespace Polygons {
        export class Triangle { }
        export class Square { }
    }
}

import polygons = Shapes.Polygons;
let sq = new polygons.Square();
```
### index 
```angular2html
type Index = 'a' | 'b' | 'c'
type FromIndex = { [k in Index]?: number }

const good: FromIndex = {b:1, c:2}

// Error:
// Type '{ b: number; c: number; d: number; }' is not assignable to type 'FromIndex'.
// Object literal may only specify known properties, and 'd' does not exist in type 'FromIndex'.
const bad: FromIndex = {b:1, c:2, d:3};
```
### this 参数
```angular2html
interface Card {
    suit: string;
    card: number;
}
interface Deck {
    suits: string[];
    cards: number[];
    createCardPicker(this: Deck): () => Card;
}
let deck: Deck = {
    suits: ["hearts", "spades", "clubs", "diamonds"],
    cards: Array(52),
    // NOTE: The function now explicitly specifies that its callee must be of type Deck
    createCardPicker: function(this: Deck) {
        return () => {
            let pickedCard = Math.floor(Math.random() * 52);
            let pickedSuit = Math.floor(pickedCard / 13);

            return {suit: this.suits[pickedSuit], card: pickedCard % 13};
        }
    }
}
```

