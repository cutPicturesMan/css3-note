## css3边框

###1、css3边框颜色属性
border-color在css1中已经定义过，css3增强了这个功能，目前只有firefox在使用-moz-前缀的情况下有效，其他浏览器无效。

| 属性 | 值 | 功能 |
| -------- | ----- | ----- | 
| border-*-colors | [\<color\> &#124; transparent ]{1,n} &#124; inherit; | *方向上从外到内的颜色过渡。一种颜色占1px宽度，如果边框宽度大于设置的颜色数量，则剩余宽度全显示最后一种颜色 |

###2、css3图片边框属性
IE11+

| 属性 | 值 | 功能 |
| -------- | ----------------- | ----- | 
| border-image | none &#124; \<source\> &#124;&#124; \<slice\> [\<width\>] &#124;&#124; \<repeat\> | 图片边框，如url(border.png) 27 stretch repeat; |
| border-image-source | url(image url) | 背景图片地址 |
| border-image-slice | \<number\> &#124; \<percentage\>{1,4} [fill] | 将引入的背景图片，切割成9宫格，提取并使用其中的2,4,6,8格。如果填写fill，5格将保留下来 |
| border-image-width | [\<length\> &#124; \<percentage\> &#124; \<number\> &#124; \<auto\>]{1,4} | 边框图片的宽度 |
| border-image-repeat | [stretch &#124; repeat &#124; round ]{1,2} | 边框背景图片的排列方式。stretch把相应的图片进行拉伸，适应边框大小。repeat从边框中间向两端不断平铺，在平铺过程中保持边框背景图片的切片大小，会造成两端的边缘有被切割的现象。round对边框背景图片的切片进行伸缩处理，以刚好显示。 |

###2、css3圆角边框属性
IE8+
| 属性 | 值 | 功能 |
| -------- | ----------------- | ----- | 
| border-radius | <length> {1,4} [/<length> {1,4}]? | 参数值为圆角的半径，4个方向：top-left,top-right,bottom-right,bottom-left。如果"/"一直存在，"/"前面的值是设置圆角的水平方向半径，"/"后面的值是设置圆角垂直方向的半径。当圆角半径>=border厚度的时候，元素边框内部具有圆角效果。table中border-collapse:collapse时，border-radius无效，border-collapse:separate时border-radius才有效 |

###3、css3盒子阴影属性
IE9+，用于定义元素的盒子阴影

