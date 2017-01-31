# css3盒模型
css中主要有以下几种盒模型：inline、inline-block、block、table、absolute position、float。 css中盒模型被分为2种：    

* W3C标准盒模型。元素的内容宽度即为width。
* IE的传统模型(IE6-、IE6~7的怪异模式)。元素的内容宽度为width - border - padding。

目前浏览器大部分元素都是基于W3C标准盒模型，但对于form中部分元素还是基于传统的盒模型，例如input中的submit、reset、button和select等元素。

## 1、css3盒模型属性(IE8+)
为了解决两种盒模型不同的宽度计算方式造成的差异，css3增添了盒模型属性`box-sizing`。

> box-sizing : content-box | border-box | inherit;

* content-box : 默认值，让元素维持W3C标准盒模型
* border-box : 让元素变成IE的传统模型
* inherit : 元素继承父级的盒模型模式

## 2、css3自由缩放属性(IE不支持)

> resize : none | both | horizontal | vertical | inherit

* none : 不允许拖动元素修改尺寸大小
* both : 可以拖动元素，修改元素的宽高
* horizontal : 修改元素的宽度，但是不能修改高度
* vertical : 修改元素的高度，但是不能修改宽度
* inherit : 继承父级的resize属性

## 3、css3外轮廓属性(IE8+)
outline属性在css2中就出现了，主要用来在元素周围绘制一条轮廓线，起到突出元素的作用。css3在此之上做了一定的拓展。用法与border类似，但是outline不像border一样可以单独设置一边，也不会像border一样占据空间。

> outline : color style width;

