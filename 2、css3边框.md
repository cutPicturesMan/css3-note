## css3边框

###1、css3边框颜色属性
border-color在css1中已经定义过，css3增强了这个功能，目前只有firefox在使用-moz-前缀的情况下有效，其他浏览器无效。

>border-*-colors : [ \<color\> | transparent ]{1,n} | inherit;

*方向上从外到内的颜色过渡。一种颜色占1px宽度，如果边框宽度大于设置的颜色数量，则剩余宽度全显示最后一种颜色

###2、css3图片边框属性(IE11+)
>border-image : \<source\> || \<slice\> [\<width\>] || \<repeat\>;   //url(border.png) 27 stretch repeat;

* border-image-source : url(image url);
背景图片地址
* border-image-slice : \<number\> | \<percentage\>{1,4} [fill];
将引入的背景图片，切割成9宫格，提取并使用其中的2,4,6,8格。如果填写fill，5格将保留下来
* border-image-width : [\<length\> | \<percentage\> | \<number\> | \<auto\>]{1,4};
边框图片的宽度
* border-image-repeat : [stretch | repeat | round ]{1,2};
边框背景图片的排列方式。stretch把相应的图片进行拉伸，适应边框大小。repeat从边框中间向两端不断平铺，在平铺过程中保持边框背景图片的切片大小，会造成两端的边缘有被切割的现象。round对边框背景图片的切片进行伸缩处理，以刚好显示。

###3、css3圆角边框属性(IE8+)

>border-radius : \<length\> {1,4} [/\<length\> {1,4}]? 

参数值为圆角的半径，4个方向：top-left,top-right,bottom-right,bottom-left。如果"/"一直存在，"/"前面的值是设置圆角的水平方向半径，"/"后面的值是设置圆角垂直方向的半径。当圆角半径>=border厚度的时候，元素边框内部具有圆角效果。table中border-collapse:collapse时，border-radius无效，border-collapse:separate时border-radius才有效

###4、css3盒子阴影属性(IE9+)

>box-shadow:[ [inset] x-offset y-offset [blur-radius] [spread-radius] [color] ]+;

* inset : 阴影类型。如果不设置，默认外阴影。如果取唯一值"inset"，则设置内阴影，x-offset等效果与外阴影时相反。
* x-offset : 阴影水平偏移量，可正可负。如果取正值，则阴影在元素右边；反之取负值，阴影在元素左边。
* y-offset : 阴影垂直偏移量，可正可负。如果取正值，则阴影在元素底部；反之取负值，阴影在元素顶部。
* blur-radius : 阴影模糊半径。只能为正值，取值越大，阴影边缘越模糊。
* spread-radius : 阴影扩散半径，可正可负。如果取正值，则整个阴影都延展扩大；反之取负值，阴影缩小。
* color : 阴影颜色，不设置浏览器将会取默认颜色。

一些效果：
>box-shadow:0 -4px 5px -3px red;  //单边阴影      
>box-shadow:0 0 10px -10px red;  //无阴影效果    
>box-shadow:0 0 0 10px red;    //效果等同于border:10px solid red;

tips:内阴影用在img标签上无效果，可以这样做：
~~~
<div class="box-shadow">
	<img src="border.jpg" alt="" width="200" />
 </div>
~~~
~~~
.box-shadow {
  display: inline-block;
  box-shadow: inset 5px 5px 10px #06c;
}
img {
  position:relative;
  z-index: -1;
  vertical-align: top;
}
~~~

多色边框，要注意阴影顺序，最先写的阴影将显示在最顶层：
~~~
box-shadow: 
            0 0 0 1px red,
            0 0 0 5px blue,
            0 0 0 8px green,
            0 0 0 12px yellow,
            0 0 0 16px orange,
            0 0 0 20px #06c;  
~~~
