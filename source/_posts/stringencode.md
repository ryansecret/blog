---
title: stringencode
date: 2019-12-10 17:10:23
tags: encode decode
---

ASCII、UTF-8\16
unicode GB2312 

字符是语言中的概念，但是计算机只认识 0 和 1 这两个数字。因此要想让计算机存储、处理字符串，就必须把字符串用二进制表示出来。在 ASCII 码中，每个英文字母都有自己对应的数字。我们通常把 ASCII 码称为字符集，也就是字符的集合。了解 ASCII 码的同学应该都知道小写字母 a 可以用 97 来表示，97 也被称为字符 a 在 ASCII 字符集中的码位。

可见把字符转换成码位的过程类似于加密(encrypt)，我们称之为编码(encode)，反则则类似于解密，我们称之为解码(decode)

字符转换成码位的过程是编码，这个过程有无数种实现方式。比如 a -> 97、b -> 98 这种就是 ASCII 编码，因为 255 = 2 ^ 8，所以所有 ASCII 编码下的码位恰好都可以由一个字节表示。

除了中国人之外，各个地区的人也都根据自己的语言拓展了相应的编码方式。这样unicode就出现了。

缺点：过于庞大、

中文的utf-8 大于GBk的两个字节

因此，我们有了对 Unicode 字符再次编码的编码方式，常见的有 utf-8，utf-16 等。UTF 表示 Unicode Transfer Format，因此是针对 Unicode 字符集的一系列编码方式。utf-8 是一种变长编码，也就是说不同的 Unicode 字符在 utf-8 编码下的码位长度可能不同，如下表所示:

 |Unicode 编码(16进制) | utf-8 码位(二进制)|
 |----|----|
 |000000-00007F       |0xxxxxxx|
 |000080-0007FF|110xxxxx 10xxxxxx|
 |000800-00FFFF|1110xxxx 10xxxxxx 10xxxxxx|
 |010000-1FFFFF|11110xxx10xxxxxx10xxxxxx10xxxxxx|


1. escape
1. encodeURIComponent encodeURI

encodeURI()不会对本身属于URI的特殊字符进行编码，例如冒号、正斜杠、问号和井字号；而encodeURIComponent()则会对它发现的任何非标准字符进行编码。
使用encodeURI()编码后的结果是除了空格之外的其他字符都原封不动，只有空格被替换成了%20。而encodeURIComponent()方法则会使用对应的编码替换所有非字母数字字符。

escape 在处理 0xff 之外字符的时候，是直接使用字符的 unicode 在前面加上一个 「%u」,举例说明。
而encodeURI则是先进行 UTF-8，再在 UTF-8 的每个字节码前加上一个 「%」；
encodeURI 是W3C 的标准，而 Escape 是非标准。


JavaScript 内部，字符以 UTF-16 的格式储存，每个字符固定为2个字节。对于那些需要4个字节储存的字符（Unicode 码点大于0xFFFF的字符），JavaScript 会认为它们是两个字符。
