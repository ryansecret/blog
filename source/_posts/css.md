---
title: css
date: 2019-05-07 15:12:57
tags: css
---

1. overflow:https://developer.mozilla.org/zh-CN/docs/Web/CSS/overflow

2. Element.scrollTop 属性可以获取或设置一个元素的内容垂直滚动的像素数。

offsetTop: 当前元素顶部距离最近父元素顶部的距离,和有没有滚动条没有关系。单位px，只读元素。

scrollHeight: 因为子元素比父元素高，父元素不想被子元素撑的一样高就显示出了滚动条，在滚动的过程中本元素有部分被隐藏了，scrollHeight代表包括当前不可见部分的元素的高度。而可见部分的高度其实就是clientHeight，也就是scrollHeight>=clientHeight恒成立。在有滚动条时讨论scrollHeight才有意义，在没有滚动条时scrollHeight==clientHeight恒成立。单位px，只读元素。

https://imweb.io/topic/57c5409e808fd2fb204eef52

clientheight offsetheight 


3. 相对位置：
https://developer.mozilla.org/zh-CN/docs/Web/CSS/position

4. Image alt 属性是一个必需的属性，它规定在图像无法显示时的替代文本。


text-decoration 设置下划线等
https://jsfiddle.net/ryansecreat/58um7k43/

document​.active​Element

 返回当前页面中获得焦点的元素,也就是说,如果此时用户按下了键盘上某个键,会在该元素上触发键盘事件.该属性是只读的.


#### 块元素是一个元素，占用了全部宽度，在前后都是换行符。
   ```text
   块元素的例子：
   
   <h1>
   <p>
   <div>
   内联元素只需要必要的宽度，不强制换行。
   
   内联元素的例子：
   
   <span>
   <a>
   
```

#### 内容对齐（justify-content）属性应用在弹性容器上，把弹性项沿着弹性容器的主轴线（main axis）对齐。
       
   align-items 设置或检索弹性盒子元素在侧轴（纵轴）方向上的对齐方式。
   设置"margin"值为"auto"值，自动获取弹性容器中剩余的空间。所以设置垂直方向margin值为"auto"，可以使弹性子元素在弹性容器的两上轴方向都完全居中。 当容器为flex时会自动居中。
   
   如果在元素上设置了 box-sizing: border-box; 则 padding(内边距) 和 border(边框) 也包含在 width 和 height 中:
   
   transform: rotateX(120deg);  x轴旋转 
   
   
   