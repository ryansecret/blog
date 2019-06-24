---
title: interview
date: 2017-01-23 18:25:52
tags: interview
---
 而在底层，Node.js借助libuv来作为抽象封装层， 从而屏蔽不同操作系统的差异，Node可以借助livuv来来实现多线程。
 
 ![image](http://www.admin10000.com/UploadFiles/Document/201509/30/20150930072020634231.PNG)
 
 事件循环是单线程的，从下图可以看出
 
 ![image](http://www.admin10000.com/UploadFiles/Document/201509/30/20150930072028113909.PNG)
 
 所有的同步任务在主线程上执行，形成一个任务栈。所有的异步任务的回调在另一队列中，只有执行完
 
 tTimeout()只是将事件插入了"任务队列"，必须等到当前代码（执行栈）执行完，主线程才会去执行它指定的回调函数。要是当前代码耗时很长，有可能要等很久，所以并没有办法保证，回调函数一定会在setTimeout()指定的时间执行。
 
 Node.js也是单线程的Event Loop，但是它的运行机制不同于浏览器环境。
 
 ![image](http://image.beekka.com/blog/2014/bg2014100803.png)
 

```
process.nextTick(function A() {
  console.log(1);
  process.nextTick(function B(){console.log(2);});
});

setTimeout(function timeout() {
  console.log('TIMEOUT FIRED');
}, 0)
// 1
// 2
// TIMEOUT FIRED
```

上面代码中，由于process.nextTick方法指定的回调函数，总是在当前"执行栈"的尾部触发，所以不仅函数A比setTimeout指定的回调函数timeout先执行，而且函数B也比timeout先执行。这说明，如果有多个process.nextTick语句（不管它们是否嵌套），将全部在当前"执行栈"执行。   setImmediate总是将事件注册到下一轮Event Loop


　测试金字塔指的是： 当我们在编写测试用例时，底层的单元测试应该远比上层的端到端测试要多。
　

数组的shift和unshift  push 和 pop 

node 优势：非阻塞IO、高并发、丰富的生态环境

 node有哪些全局对象?
参考答案: process, console, Buffer和exports
![image](https://camo.githubusercontent.com/233315761d49d4c75fe7969e36bda22ecf5bbc0f/687474703a2f2f6a6f616f7073696c76612e6769746875622e696f2f74616c6b732f456e642d746f2d456e642d4a6176615363726970742d776974682d7468652d4d45414e2d537461636b2f696d672f6e6f64656a732d617263682d7070742e706e67)

process有哪些常用方法?
参考答案: process.stdin, process.stdout, process.stderr, process.on, process.env, process.argv, process.arch, process.platform, process.exit

通过domain获取eventemmiter 的异常：

```
var domain = require('domain');
    var myDomain = domain.create();
    myDomain.on('error', function(err){
        console.log('domain接收到的错误事件:', err);
    }); // 接收事件并打印
    myDomain.run(function(){
        var emitter1 = new MyEmitter();
        emitter1.emit('error', '错误事件来自emitter1');
        emitter2 = new MyEmitter();
        emitter2.emit('error', '错误事件来自emitter2');
    });
```

supper 代表父类构造函数和原形


原生构造函数：
Boolean()
Number()
String()
Array()
Date()
Function()
RegExp()
Error()
Object()

Es6 可以继承这些原生的构造函数
 
```
class MyArray extends Array {
  constructor(...args) {
    super(...args);
  }
}

var arr = new MyArray();
arr[0] = 12;
arr.length // 1

arr.length = 0;
arr[0] // undefined
```

```
class ExtendableError extends Error {
  constructor(message) {
    super();
    this.message = message;
    this.stack = (new Error()).stack;
    this.name = this.constructor.name;
  }
}

class MyError extends ExtendableError {
  constructor(m) {
    super(m);
  }
}

var myerror = new MyError('ll');
myerror.message // "ll"
myerror instanceof Error // true
myerror.name // "MyError"
myerror.stack
```

定义get set ,可在方法体内部拦截

```
class MyClass {
  constructor() {
    // ...
  }
  get prop() {
    return 'getter';
  }
  set prop(value) {
    console.log('setter: '+value);
  }
  * [Symbol.iterator]() {
    for (let arg of this.args) {
      yield arg;
    }
  }
}
```

Stream有什么好处?
参考答案: 非阻塞式数据处理提升效率，片断处理节省内存，管道处理方便可扩展等.


fs.watch和fs.watchFile有什么区别，怎么应用?
参考答案: 二者主要用来监听文件变动．fs.watch利用操作系统原生机制来监听，可能不适用网络文件系统; fs.watchFile则是定期检查文件状态变更，适用于网络文件系统，但是相比fs.watch有些慢，因为不是实时机制．

实现一个简单的HTTP 服务器。
require('http').createServer(function(req,res){}).listen(300);

spawn应用来运行返回大量数据的子进程，如图像处理，文件读取等。而exec则应用来运行只返回少量返回值的子进程，如只返回一个状态码。

有哪些常用方法可以防止程序崩溃?

参考答案: 1) try-catch-finally 2) EventEmitter/Stream error事件处理 3) domain统一控制 4) jshint静态检查 5) jasmine/mocha进行单元测试


要监控nodejs的内存使用的话，需要安装memwathch 模块

nodejs C++ 扩展的实现：
https://my.oschina.net/yushulx/blog/423704

process.argv 数组的第一个元素永远都会是 node，并且第二个参数总是指向你的程序的路径，所以，你应该从第三个元素


```
regex test   if (/^\/api\/parsetime/.test(req.url))
```


回调函数的规则：err 为第一个参数

文件的总行：
```
var lines = contents.toString().split('\n').length - 1
```


fs.unlink 删除文件


```
//创建一个tcp 服务器
var net = require('net')

var server = net.createServer(function (socket) {

  // socket 处理逻辑

})

server.listen(8000)
```


使用 socket.write(data) 可以写数据到 socket 中，用 socket.end() 可以关闭一个 socket。另外， .end() 方法也可以接收一个数据对象作为参数，因此，你可简单地使用 socket.end(data) 来完成写数据和关闭两个操作。

concat-stream：会连接多个stream,参数中不指定encoding 的话，会自行推断。

```
var arrays = concat({ encoding: 'array' }, function(out) {
    t.deepEqual(out, [1,2,3,4,5,6])
  })
  arrays.write([1,2,3])
  arrays.write([4,5,6])
  arrays.end()
```

```
fs.createReadStream(file).pipe(process.stdout);
```
使用through2 对流数据进行转换：

通过split 将流中的数据分行：

You can use the `split` module to split input by newlines. For example:
```
    var split = require('split');
    process.stdin
        .pipe(split())
        .pipe(through2(function (line, _, next) {
            console.dir(line.toString());
            next();
        }))
    ;
```