# css3-note

## 1、选择器

###层次选择器（IE7+）

* elem1 > elem2 匹配elem1的第一级子元素elem2
* elem1 + elem2 匹配紧邻elem1之后的第一个elem2元素
* elem1 ~ elem2 匹配紧邻elem1之后的所有elem2元素

###动态伪类选择器

* :link    超链接未被访问过
* :visited 超链接被访问过
* :active  元素被激活（鼠标按下，IE8+）
* :hover   鼠标停留在元素上
* :focus   元素获得焦点（IE8+）

###目标伪类选择器

* :target 匹配URI中#标识符的目标元素（IE9+）

###结构伪类选择器
除了:first-child是IE7+，其余的都是IE9+

* E:first-child　　　　　　匹配父元素下的第一个子元素   && 该子元素必须是E
* E:last-child　　　　　　　匹配父元素下的最后一个子元素 && 该子元素必须是E
* E:nth-child(expression)　　匹配父元素下的第n个子元素    && 该子元素必须是E 			
				 **expression** **behavior**
				 0			一个都不选
				 2n/even    选中偶数行
				 2n±1/odd   选中奇数行
				 n+3        选中从第3行直到最后一个元素
				 -n+3       选中前3个元素
				 n			全选中