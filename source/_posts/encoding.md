---
title: encoding
date: 2019-11-08 14:11:43
tags:
---
1. charCodeAt() 返回表示给定索引的字符的Unicode的值。 codePointAt() 返回使用UTF-16编码的给定位置的值的非负整数。
1. Transfer-Encoding   数据以一系列分块的形式进行发送。 Content-Length 首部在这种情况下不被发送。。在每一个分块的开头需要添加当前分块的长度，以十六进制的形式表示，后面紧跟着 '\r\n' ，之后是分块本身，后面也是'\r\n' 。终止块是一个常规的分块，不同之处在于其长度为0。终止块后面是一个挂载（trailer），由一系列（或者为空）的实体消息首部构成。
1. ascii 第一个bit为0，也就是当第一个bit是0时仍表示之前那些常用的字符.当为1时就表示其他补充的字符，例如西欧国家的文字。
1. utf-8  Refer:https://segmentfault.com/a/1190000014324711
```text
0xxxxxxx,如果是这样的01串,也就是以0开头后面是啥就不用管了XX代表任意bit.就表示把一个字节做为一个单元.就跟ASCII完全一样.
   110xxxxx 10xxxxxx.如果是这样的格式,则把两个字节当一个单元
   
   1110xxxx 10xxxxxx 10xxxxxx 如果是这种格式则是三个字节当一个单元
```   

1. 