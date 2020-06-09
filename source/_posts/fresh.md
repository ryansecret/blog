---
title: fresh
date: 2020-06-04 10:33:26
tags:
---

1.  十进制转为 2 进制，除 2 取余，然后余数反向
    
    十进制转为 2 进制小时，**乘 2 取整**
    
2.  最优子结构、边界、动态转移方程。动态规划的核心—》从低向上，从而不会像递归那样保留调用栈。
    
3.  Element.getBoundingClientRect() 方法返回元素的大小及其相对于视口的位置。
    
4.  window.requestAnimationFrame() 告诉浏览器——你希望执行一个动画，并且要求浏览器在下次重绘之前调用指定的回调函数更新动画。该方法需要传入一个回调函数作为参数，该回调函数会在浏览器下一次重绘之前执行
    
5.  浏览器中 customevent
    

```
var event = new CustomEvent("cat", {  detail: {    hazcheeseburger: true  }});obj.dispatchEvent(event);
```

---

1.  Tcp 的滑动窗口增大了吞吐量，但是并没有解决队头堵塞得问题
    
2.  preload 是声明式的 fetch，可以强制浏览器请求资源，同时不阻塞文档 onload 事件。Prefetch 提示浏览器这个资源将来可能需要，但是把决定是否和什么时间加载这个资源的决定权交给浏览器。
    
3.  首屏加载时间
    performance.timing.domContentLoadedEventStart-performance.timing.navigationStart
    
4.  所以函数防抖适用的场景：监听窗口的滚动，缩放。高频发生的一些事件；函数节流适用的场景：涉及与后端交互的按钮，由于网络原因或者其他原因，导致接口没有返回值，用户一直点点点的问题。
    
5.  当用户输入关键字并键入回车之后，这意味着当前页面即将要被替换成新的页面，不过在这个流程继续之前，浏览器还给了当前页面一次执行 `beforeunload` 事件的机会，`beforeunload` 事件允许页面在退出之前执行一些数据清理操作，还可以询问用户是否要离开当前页面。
    
6.  wrong pronouce
```text
     analogy 类比 [əˈnælədʒi]
      Apache [ə’pætʃɪ]
      AJAX [‘eidʒæks]
      array [ə’rei]
      deque dek 双端队列
      Java ['dʒɑːvə]
      Realm [relm]
    
 ```
    
7.  http 挥手 主动关闭有个time_wait,这个标准的持续时间是4分钟

     ISN(Initial Sequence Number) 是固定的么，
     
      客户端的syn_send 状态、服务端的syn_rcvd
      
     Tcp 报文段：tcp 首部+tcp 数据部分
     
      Fuction 形参是引用类型的话，只是引用
      
      半链接队列—超时重传
      
     等待2个msl 确保服务端能收到ack,能正常关闭
     
      关闭连接时，当收到对方的FIN报文时，仅仅表示对方不再发送数据了但是还能接收数据，己方也未必全部数据都发送给对方了，所以己方可以立即close，也可以发送一些数据给对方后，再发送FIN报文给对方来表示同意现在关闭连接，因此，己方ACK和FIN一般都会分开发送。
 
    
8.  如果 300 的话会进行重定向，这里会有个重定向计数器，避免过多次的重定向，超过次数也会报错。
    
9.  而HTTP的204(No Content)响应, 就表示执行成功, 但是没有数据, 浏览器不用刷新页面.也不用导向新的页面.  
     205 Reset Content, 表示执行成功, 重置页面(Form表单).