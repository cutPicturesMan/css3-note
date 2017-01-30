## css3边框

###1、css3边框颜色属性
border-color在css1中已经定义过，css3增强了这个功能，目前只有firefox在使用-moz-前缀的情况下有效，其他浏览器无效。

| 属性 | 值 | 功能 |
| -------- | ----- | ----- | 
| border-*-colors | [\<color\> \| transparent ]{1,n} \| inherit; | *方向上从外到内的颜色过渡。一种颜色占1px宽度，如果边框宽度大于设置的颜色数量，则剩余宽度全显示最后一种颜色 |

###2、css3图片边框属性
除了IE浏览器之外，其余浏览器都支持该属性

| 属性 | 值 | 功能 |
| -------- | ----- | ----- | 
| border-image | none \| \<source\> \|\| \<slice\> [\<width\>] \|\| \<repeat\> | 图片边框 |
| border-image-source | url(image url) | 背景图片地址 |
| border-image-slice | \<number\> \| \<percentage\>{1,4} | 将引入的背景图片，切割成9宫格，提取并使用其中的2,4,6,8格 |
| border-image-width | \<border-width\>{1,4} | 边框图片的宽度 |
| border-image-repeat | [stretch \| repeat \| round ]{1,2} | 边框背景图片的排列方式。stretch把相应的图片进行拉伸，适应边框大小。repeat从边框中间向两端不断平铺，在平铺过程中保持边框背景图片的切片大小，会造成两端的边缘有被切割的现象。round对边框背景图片的切片进行伸缩处理，以刚好显示。 |