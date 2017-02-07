**——主要参考大漠的[图解CSS3 Flexbox属性](http://www.w3cplus.com/css3/a-visual-guide-to-css3-flexbox-properties.html)**  
**——实战部分：阮一峰[Flex 布局教程：实例篇](http://www.ruanyifeng.com/blog/2015/07/flex-examples.html)**

# css3伸缩布局盒模型(IE10+)
伸缩布局盒模型由于有3个版本，旧版本`display:box`，混合版本`display:flexbox`，新版本`display:flex`，各浏览器的支持程度不一样，因此建议用webpack将sass加上autoprefix编译后使用。或者直接将sass用[koala](http://koala-app.com/index-zh.html)编译使用，autoprefix选项记得勾选。移动端布局利器。

##flex容器无效属性
* 所有column-*属性在flex容器上都不生效
* flex容器上不能使用::first-line和::first-letter伪元素

## 伸缩容器display
将元素设置为伸缩容器。以下将设置了`display:flex`的元素统称为**伸缩容器**， 子元素称为**伸缩项目**

>display : flex | inline-flex;

* flex : 将元素设置为块伸缩容器
* inline-flex : 将元素设置为内联伸缩容器

## 1、主轴对齐justify-content
定义伸缩项目沿主轴线的对齐方式

>justify-content : flex-start | flex-end | center | space-between | space-around;

* flex-start : 伸缩项目向一行的起始位置靠齐，**相邻伸缩项目无间隔**
* flex-end : 伸缩项目向一行的结束位置靠齐，**相邻伸缩项目无间隔**
* center : 伸缩项目向一行的中间位置靠齐，**相邻伸缩项目无间隔**
* space-between : 伸缩项目平均分布，**相邻伸缩项目有间隔**。第一个伸缩项目顶头，最后一个伸缩项目顶尾
* space-around : 伸缩项目平均分布，**相邻伸缩项目有间隔**，每个伸缩项目两端各保留一半空间。

## 2、侧轴对齐align-items/align-self

### 1)align-items
定义**所有**的伸缩项目沿侧轴的对齐方式

>align-items : flex-start | flex-end | center | baseline | stretch;

* flex-start : 伸缩项目的外边距盒紧靠住侧轴的起始边，**高度保持原有，不会填满侧轴**
* flex-end : 伸缩项目的外边距盒紧靠住侧轴的终点边，**高度保持原有，不会填满侧轴**
* center : 伸缩项目的外边距盒在侧轴上居中放置，**高度保持原有，不会填满侧轴**
* baseline : 伸缩项目根据所有的伸缩项目的基线对齐，**高度保持原有，不会填满侧轴**
* stretch : 默认值，伸缩项目的外边距盒在没有width/height的属性限制下尽量拉伸填充整个容器。**高度不会保持原有，会填满侧轴高度**

### 2)align-self
定义**单个**伸缩项目沿侧轴的对齐方式，值与`align-items`相同，只不过要设置在伸缩项目上

## 3、伸缩换行align-content
在多行的情况下，调整每一个伸缩行在伸缩容器里的侧轴对齐方式。参数值跟`justify-content`类似

>align-content : flex-start | flex-end | center | space-between | space-around | stretch;

* flex-start : 各行向伸缩容器的起点位置靠齐
* flex-end : 各行向伸缩容器的结束位置靠齐
* center : 各行向伸缩容器的中间位置靠齐
* space-between : 各行在伸缩容器中平均分布。第一个伸缩项目顶头，最后一个伸缩项目顶尾
* space-around : 各行在伸缩容器中平均分布。每个伸缩项目两端各保留一半空间
* stretch : 默认值，各行将会伸展以占用额外空间

## 4、伸缩性flex
根据各伸缩项目的扩展/缩小比率，来分配伸缩容器中的额外空间。当一个元素是伸缩项目时，flex属性将代替主轴长度属性决定元素的长度。默认值为`flex:0 1 auto`，`flex:none`相当于`flex:0 0 auto`，`flex:auto`相当于`flex:1 1 auto`。

>flex : none | auto | [ <flex-grow> <flex-shrink>? || <flex-basis> ]

* flex-grow : Number，默认值为0。定义伸缩项目的扩展比率。当每个伸缩项目都为`flex-grow:1`时，所有项目平均分配额外空间（如果有的话）。**当其中一个伸缩项目为`flex-grow:2`，其余的为`flex-grow:1`时，`flex-grow:2`的W3C标准盒模型宽度将是`flex-grow:1`W3C标准盒模型的2倍**

tips:所谓的额外宽度，指的是伸缩容器的宽度，减去所有伸缩项目的padding、border、margin之后得到的总宽度，即为额外宽度。将额外宽度根据`flex-grow`分配到各个子元素，即为各个子元素的W3C标准盒模型宽度。

* flex-shrink : Number，默认为1，负数无效，用的很少。定义伸缩项目的缩小比例，如果空间不足，该项目将缩小。会根据`flex-basis`的值进行加权。如果将某元素设置为`flex-shrink:0`时，它不会缩小，而是会保持原来的大小
~~~
<div class="flex">
	<div class="item">1</div>
	<div class="item">2</div>
	<div class="item">3</div>
	<div class="item">4</div>
	<div class="item">5</div>
</div>

<style>
	.flex{
		width:600px;
		display:flex;
	}
	.flex .item{
		flex:1 200px;
		border:1px solid #ccc;
	}
	.flex .item:nth-child(3){
		flex-shrink: 0;				//其他元素都缩小的时候，第三个元素不会缩小
	}
</style>
~~~

* flex-basis : Length，默认值为auto，和`width`和`height`属性相同。定义了在分配多余空间之前，伸缩项目占据的主轴空间。在`flex`缩写中省略此部件时，值为0。

## 5、伸缩流方向flex-direction
定义伸缩项目放置在伸缩容器的方向。**当设置为`flex-direction:column`时，`justify-content`表示侧轴对齐方式，`align-items`表示主轴对齐方式**

>flex-direction : row | row-reverse | column | column-reverse;

* row : 从左往右排列。如果设置排列方式为`direction:rtl`，则从右往左排列
* row-reverse : 从右往左排列。如果设置排列方式为`direction:rtl`，则从左往右排列
* column : 从上到下排列
* column-reverse : 与`column-reverse`相反

## 6、伸缩换行flex-wrap
定义伸缩容器是单行显示还是多行显示，侧轴的方向决定了新行堆放的方向

>flex-wrap : nowrap | wrap | wrap-reverse;

* nowrap : 默认值，单行显示，**从左到右排列**
* wrap : 多行显示，**从左到右排列**
* wrap-reverse : 多行显示，**从右到左排列**

## 7、伸缩换行flex-flow
`flex-direction`和`flex-wrap`的简写形式

>flex-flow : <flex-direction> || <flex-wrap>;

## 8、显示顺序order
改变伸缩项目在伸缩容器中的次序。数字小的排在前面，正负值均可。

>order : \<length\>;
