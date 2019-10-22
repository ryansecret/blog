---
title: regex
date: 2019-06-24 13:56:32
tags: regex
---

### s修饰符使得 . 能够匹配任何字符
 
/foo.bar/s.test('foo\nbar')

### ? 非贪婪模式

? 非贪婪模式，只匹配最少的数据。 对 "123abc" 应用 /\d+/ 将会返回 "123"，如果使用 /\d+?/,那么就只会匹配到 "1”。

### 先行断言

x(?=y)  匹配'x'仅仅当'x'后面跟着'y'.这种叫做先行断言。例如，/Jack(?=Sprat)/会匹配到'Jack'仅仅当它后面跟着'Sprat'。/Jack(?=Sprat|Frost)/匹配‘Jack’仅仅当它后面跟着'Sprat'或者是‘Frost’。但是‘Sprat’和‘Frost’都不是匹配结果的一部分。

### 后行断言 

(?<=y)x  匹配'x'仅仅当'x'前面是'y'.这种叫做后行断言。

### 正向否定查找

x(?!y)   匹配'x'仅仅当'x'后面不跟着'y',这个叫做正向否定查找。/\d+(?!\.)/匹配一个数字仅仅当这个数字后面没有跟小数点的时候。正则表达式/\d+(?!\.)/.exec("3.141")匹配‘141’而不是‘3.141’

### 边界 
\b 匹配一个词的边界。  
\B 匹配一个非单词边界

### w
\w 匹配一个单字字符（字母、数字或者下划线）。
等价于[A-Za-z0-9_]。

例如, /\w/ 匹配 "apple," 中的 'a'，"$5.28,"中的 '5' 和 "3D." 中的 '3’。

\W 匹配一个非单字字符。

等价于[^A-Za-z0-9_]。

例如, /\W/ 或者 /[^A-Za-z0-9_]/ 匹配 "50%." 中的 '%’。

### 子字符串匹配
```
var re = /(\w+)\s(\w+)/;
var str = "John Smith";
var newstr = str.replace(re, "$2, $1");
console.log(newstr);
```

#### 非捕获组

?: 用非捕获组 提升匹配效率。

y修饰符的一个应用，是从字符串提取 token（词元），y修饰符确保了匹配之间不会有漏掉的字符。可以修改regex的 lastIndex 。

### 具名匹配

```
const RE_DATE = /(\d{4})-(\d{2})-(\d{2})/;



const matchObj = RE_DATE.exec('1999-12-31');

const year = matchObj[1]; // 1999

const month = matchObj[2]; // 12

const day = matchObj[3]; // 31

Replace 函数形式：

'2015-01-02'.replace(re, (

   matched, // 整个匹配结果 2015-01-02

   capture1, // 第一个组匹配 2015

   capture2, // 第二个组匹配 01

   capture3, // 第三个组匹配 02

   position, // 匹配开始的位置 0

   S, // 原字符串 2015-01-02

   groups // 具名组构成的一个对象 {year, month, day}

 ) => {

 let {day, month, year} = groups;

 return `${day}/${month}/${year}`;

});
```

```javascript
// 可以直接赋值
let {groups: {one, two}} = /^(?<one>.*):(?<two>.*)$/u.exec('foo:bar');
one  // foo
two  // bar

// 直接replace
let re = /(?<year>\d{4})-(?<month>\d{2})-(?<day>\d{2})/u;

'2015-01-02'.replace(re, '$<day>/$<month>/$<year>')
```

### 使用引用

使用引用：const RE_TWICE = /^(?<word>[a-z]+)!\k<word>$/;

RE_TWICE.test('abc!abc') // true
RE_TWICE.test('abc!ab') // false


