# css3伸缩布局盒模型(IE10+)
伸缩布局盒模型由于有3个版本，旧版本`display:box`，混合版本`display:flexbox`，新版本`display:flex`，各浏览器的支持程度不一样，因此建议用webpack将sass加上autoprefix编译后使用。或者直接将sass用[koala](http://koala-app.com/index-zh.html)编译使用，autoprefix选项记得勾选。移动端布局利器。

## 1、伸缩容器display
将元素设置为伸缩容器

>display : flex | inline-flex;

* flex : 将元素设置为块伸缩容器
* inline-flex : 将元素设置为内联伸缩容器

## 2、主轴对齐justify-content
定义伸缩项目沿主轴线的对齐方式

>justify-content : flex-start | flex-end | center | space-between | space-around;

* flex-start : 伸缩项目向一行的起始位置靠齐，**相邻伸缩项目无间隔**
* flex-end : 伸缩项目向一行的结束位置靠齐，**相邻伸缩项目无间隔**
* center : 伸缩项目向一行的中间位置靠齐，**相邻伸缩项目无间隔**
* space-between : 伸缩项目平均分布，**相邻伸缩项目有间隔**。第一个伸缩项目顶头，最后一个伸缩项目顶尾
* space-around : 伸缩项目平均分布，**相邻伸缩项目有间隔**，每个伸缩项目两端各保留一半空间。

## 3、侧轴对齐

### 1)align-items
定义伸缩项目沿侧轴的对齐方式

>align-items : flex-start | flex-end | center | baseline | stretch;

* 

## 、伸缩流方向flex-direction
定义伸缩项目放置在伸缩容器的方向

>flex-direction : row | row-reverse | column | column-reverse;

* row : 从左往右排列。如果设置排列方式为`direction:rtl`，则从右往左排列
* row-reverse : 从右往左排列。如果设置排列方式为`direction:rtl`，则从左往右排列
* column : 从上到下排列
* column-reverse : 与`column-reverse`相反

## 、伸缩换行flex-wrap
定义伸缩容器是单行显示还是多行显示，侧轴的方向决定了新行堆放的方向

>flex-wrap : nowrap | wrap | wrap-reverse;

* nowrap : 单行显示，**从左到右排列**
* wrap : 多行显示，**从左到右排列**
* wrap-reverse : 多行显示，**从右到左排列**



