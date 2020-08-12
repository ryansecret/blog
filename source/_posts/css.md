---
title: css
date: 2019-05-07 15:12:57
tags: css
---
1. flex-basis 分配多余空间之前占据的主轴空间。
1. 多行文本溢出隐藏变为...
     p {
       overflow: hidden;
       
       /* 限制在一个块元素显示的文本的行数，即行数设置 */
       line-clamp: 3;
      
     }
1. !important，作用是提高指定样式规则的应用优先权
1. $border-color:#ccc !default; //声明变量 !default只能使用与变量中
1.  sass 的控制指令
```text 
      .el-col-0 {
         display: none;
       }

       @for $i from 0 through 24 {
         .el-col-#{$i} {
           width: (1 / 24 * $i * 100) * 1%;
         }
       }
 ```
1. 使用%定义一个被继承的样式，类似静态语言中的抽象类，他本身不起作用，只用于被其他人继承。
2. SCSS 是 Sass 3 引入新的语法，其语法完全兼容 CSS3，并且继承了 Sass 的强大功能。也就是说，任何标准的 CSS3 样式表都是具有相同语义的有效的 SCSS 文件

3. SCSS提供了一个选择器可以选中当前元素的父元素，使用&表示.
4. CSS的transition-delay属性规定了在过渡效果开始作用之前需要等待的时间。
5. object-fit CSS 属性指定可替换元素的内容应该如何适应到其使用的高度和宽度确定的框。
6. transform-origin CSS属性让你更改一个元素变形的原点。
7.  响应式图像 srcSet 
```javastript
return <img
     src={src}
     onError={this.handleError}
     alt={alt}
     srcSet={srcSet}
     style={{ 'object-fit': fit }}/>;
```
1. CSS 的 outline 属性是在一条声明中设置多个轮廓属性的简写属性 ， 例如 outline-style, outline-width 和 outline-color。
2. transition-property transition-duration transition-timing-function and transition-delay.
1. cursor: not-allowed;
1. inline-block的默认对齐方式是vertical-block：baseline，  vertical-align :middle
1. !default 声明赋值的变量赋值，此时，如果变量已经被赋值，不会再被重新赋值，但是如果变量还没有被赋值，则会被赋予新的值。
2. 属性嵌套：
```css
div {  

  font: {  

    size: 10px;  

    weight: bold;  

  }  }
```

4.   @minxin @include  @extend 
 ```css
 @for $i from 1 through 1000 {
    .#{unique-id()}-#{$i} {
        ...
    }
}
 ```


1. 支持布尔型的 and or 以及 not 运算。  @if  or or 
```css
$i: 6;
@while $i > 0 {
  .item-#{$i} { width: 2em * $i; }
  $i: $i - 2;
}

@for $i from 1 through 3 {
  .item-#{$i} { width: 2em * $i; }
}

@each $animal in puma, sea-slug, egret, salamander {
  .#{$animal}-icon {
    background-image: url('/images/#{$animal}.png');
  }
}

@each $animal, $color, $cursor in (puma, black, default),
                                  (sea-slug, blue, pointer),
                                  (egret, white, move) {
  .#{$animal}-icon {
    background-image: url('/images/#{$animal}.png');
    border: 2px solid $color;
    cursor: $cursor;
  }
}
```
1. css3 选择器
```text
:first-of-type	p:first-of-type	选择属于其父元素的首个 <p> 元素的每个 <p> 元素。
:last-of-type	p:last-of-type	选择属于其父元素的最后 <p> 元素的每个 <p> 元素。

element element	div p	选择 <div> 元素内部的所有 <p> 元素。	
element>element	div>p	选择父元素为 <div> 元素的所有 <p> 元素。	
element+element	div+p	选择紧接在 <div> 元素之后的所有 <p> 元素。
```
1. scss 
   >@content
 ```text
   @mixin colors($color: blue) {
  background-color: $color;
  @content;
  border-color: $color;
}
.colors {
  @include colors { color: $color; }
}
```
1. async 会打乱html解析，defer 总是在html解析完成后执行。
1. 伪元素(Pseudo-elements)
DOM树没有定义的虚拟元素
```text
核⼼就是需要创建通常不存在于⽂档中的元素，

```
1.  fr 关键字：Grid 布局还引入了一个另外的长度单位来帮助我们创建灵活的网格轨道。fr 单位代表网格容器中可用空间的一等份。grid-template-columns: 200px 1fr 2fr 表示第一个列宽设置为 200px，后面剩余的宽度分为两部分，宽度分别为剩余宽度的 1/3 和 2/3。
1. auto-fill 关键字：表示自动填充，让一行（或者一列）中尽可能的容纳更多的单元格。grid-template-columns: repeat(auto-fill, 200px) 表示列宽是 200 px，但列的数量是不固定的，只要浏览器能够容纳得下，就可以放置元素
1. flex Flex-grow flex-shrink flex-basis
2. Flex 主轴（x）、交叉轴(y)
3. calc函数是css3新增的功能，可以使用calc()计算border、margin、pading、font-size和width等属性设置动态值。   width: calc(100% - 200px);
1.触发BFC条件  BFC（Block Formatting Context）格式化上下文，把它理解成是一个独立的容器，并且这个容器里box的布局与这个容器外的box毫不相干。
                                               
1. 递归 o(2**n)-》带备忘录 o(n),自顶向下-》动态规划（自底向上）
  ```text
  根元素
  float的值不为none
  overflow的值不为visible
  display的值为inline-block、table-cell、table-caption
  position的值为absolute、fixed
  弹性盒（flex或inline-flex）
  display: flow-root
```

1. Stylelint css 的lint  
1. 多行文本： Table cell 垂直居中  vertical-align
1. 块级：1. position absolute margin-top:-50px(translate(0,-50%))  2. Top 0 bottom 0  margin:auto
1. 当元素浮动后不会影响块级元素的布局 只会影响内联元素的布局
   
   双飞布局时中间栏内容部分为两边腾开位置。

1. 使用vw设置，vw也是一个相对单位，100vw等于屏幕宽度
1. Flex-shrink、flex-grow   溢出空间和剩余空间
1. max-width/min-width > flex-basis > width > box
1. &:nth-child(odd)  选择器
1. writing-mode: vertical-rl;  设置文字方向
1. text-align-last  描述的是一段文本中最后一行在被强制换行之前的对齐规则
```text
justify

最后一行文字的开头与内容盒子的左侧对齐，末尾与右侧对齐

```
1.设置打印样式
  
  @media print {
    /* print styles here. */
  }. 
1. line-clamp 定义文字显示行数
1. pointer-events: none; 禁用点击事件
1. focus-within是一个伪类，现在已经被列入到CSS选择器中。当元素本身或其后代元素获得焦点时，:focus-within伪类的元素就会有效。 
1. 单冒号(:)用于 CSS3 伪类，双冒号(::)用于 CSS3 伪元素。
1. 但是有个好处是当元素没有内容时候，设置height:100%该元素不会被撑开，
   
   但是设置height:100vh，该元素会被撑开屏幕高度一致。 

1. 伪类：
   https://user-gold-cdn.xitu.io/2019/12/12/16ef8eecad4f1adb?imageView2/0/w/1280/h/960/format/webp/ignore-error/1
   
1. 伪元素用于创建一些不在文档树中的元素，并为其添加样式。比如说，我们可以通过:before来在一个元素前增加一些文本，并为这些文本添加样式。虽然用户可以看到这些文本，但是这些文本实际上不在文档树中。常见的伪元素有：::before，::after，::first-line，::first-letter，::selection、::placeholder等. 伪类和伪元素的区别在于有没有创建一个文档书之外的元素。
1.    
1. 这是一个叫做@font-face 的CSS @规则 ，它允许网页开发者为其网页指定在线字体。 通过这种作者自备字体的方式，@font-face 可以消除对用户电脑字体的依赖。
1. overflow:https://developer.mozilla.org/zh-CN/docs/Web/CSS/overflow

1. Element.scrollTop 属性可以获取或设置一个元素的内容垂直滚动的像素数。

offsetTop: 当前元素顶部距离最近父元素顶部的距离,和有没有滚动条没有关系。单位px，只读元素。

  scrollHeight: 因为子元素比父元素高，父元素不想被子元素撑的一样高就显示出了滚动条，在滚动的过程中本元素有部分被隐藏了，scrollHeight代表包括当前不可见部分的元素的高度。而可见部分的高度其实就是clientHeight，也就是scrollHeight>=clientHeight恒成立。在有滚动条时讨论scrollHeight才有意义，在没有滚动条时scrollHeight==clientHeight恒成立。单位px，只读元素。

   https://imweb.io/topic/57c5409e808fd2fb204eef52

   clientheight offsetheight 


1. 相对位置：
https://developer.mozilla.org/zh-CN/docs/Web/CSS/position

1. Image alt 属性是一个必需的属性，它规定在图像无法显示时的替代文本。


text-decoration 设置下划线等
https://jsfiddle.net/ryansecreat/58um7k43/

document​.active​Element

 返回当前页面中获得焦点的元素,也就是说,如果此时用户按下了键盘上某个键,会在该元素上触发键盘事件.该属性是只读的.
 
 #### 性能  
1. 尽量使用 flexbox 而不是老的布局模型。它运行速度更快，可为你的应用程序创造巨大的性能优势。
1. 根据 Google Developer，渲染线程分为 主线程 (main thread) 和 合成线程 (compositor thread)。如果 CSS 动画只是改变 transforms 和 opacity，这时整个 CSS 动画得以在 合成线程完成（而JS动画则会在 主线程 执行，然后触发合成线程进行下一步操作），在 JS 执行一些昂贵的任务时，主线程繁忙，CSS 动画由于使用了合成线程可以保持流畅
1. CSS动画有天然事件支持（TransitionEnd、AnimationEnd，但是它们都需要针对浏览器加前缀），JS则需要自己写事件。
1. 在实现一些小的交互动效的时候，就多考虑考虑 CSS 动画。对于一些复杂控制的动画，使用 javascript 比较可靠。

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
   
#### 不被选中
body{

-webkit-touch-callout: none;

-webkit-user-select: none;

-khtml-user-select: none;

-moz-user-select: none;

-ms-user-select: none;

user-select: none;

}

#### 隐藏

1.opacity：0,该元素隐藏起来了，但不会改变页面布局，并且，如果该元素已经绑定了一些事件，如click事件也能触发 2.visibility:hidden,该元素隐藏起来了，但不会改变页面布局，但是不会触发该元素已经绑定的事件 3.display:node, 把元素隐藏起来，并且会改变页面布局，可以理解成在页面中把该元素删掉
#### html 生成
将html代码按照深度优先遍历来生成DOM树。 css文件下载完后也会进行渲染，生成相应的CSSOM。 当所有的css文件下载完且所有的CSSOM构建结束后，就会和DOM一起生成Render Tree。 接下来，浏览器就会进入Layout环节，将所有的节点位置计算出来。 最后，通过Painting环节将所有的节点内容呈现到屏幕上。
 #### base64
 TMLCanvasElement.toDataURL() 方法返回一个包含图片展示的 data URI 。可以使用 type 参数其类型，默认为 PNG 格式。图片的分辨率为96dpi。
 
#### base64 渲染图片

使用 Base64 编码渲染图片有以下优点：

有效减少 HTTP 请求次数
可对数据进行简单加密，无法肉眼获取信息
没有跨域问题，无需考虑图片缓存
凡事皆有利弊，使用 Base64 编码同时也会带来一些问题：

编码后文件体积增大，仅适用于小体积图片编码
增加了编码和解码的工作量
不支持 IE 8.0 以下版本   

#### 单位

1. px：绝对单位，页面按精确像素展示
2. em：相对单位，基准点为父节点字体的大小，如果自身定义了font-size按自身来计算（浏览器默认字体是16px），整个页面内1em不是一个固定的值
3. rem：相对单位，可理解为”root em”, 相对根节点html的字体大小来计算，CSS3新加属性，chrome/firefox/IE9+支持
4. vw：viewpoint width，视窗宽度，1vw等于视窗宽度的1%
5. vh：viewpoint height，视窗高度，1vh等于视窗高度的1%
6. vmin：vw和vh中较小的那个
7. vmax：vw和vh中较大的那个
8. %:百分比

