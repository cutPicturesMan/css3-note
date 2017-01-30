## css3选择器

###1、层次选择器（IE7+）

| 选择器 | 功能 |
| -------- | ----- | 
| elem1 > elem2 | 匹配elem1的第一级子元素elem2 |
| elem1 + elem2 | 匹配紧邻elem1之后的第一个elem2元素 |
| elem1 ~ elem2 | 匹配紧邻elem1之后的所有elem2元素 |

###2、动态伪类选择器

| 选择器 | 功能 |
| -------- | ----- | 
| :link | 超链接未被访问过 |
| :visited | 超链接被访问过 |
| :active | 元素被激活（鼠标按下，IE8+） |
| :hover | 鼠标停留在元素上 |
| :focus | 元素获得焦点（IE8+）|

###3、目标伪类选择器

| 选择器 | 功能 |
| -------- | ----- | 
| :target | 匹配URI中#标识符的目标元素（IE9+） | 

###结构伪类选择器
除了:first-child是IE7+，其余的都是IE9+

| 选择器 | 功能 | 
| -------- | ----- | 
| E:first-child | 匹配父元素下所有子元素中的第一个子元素 && 该子元素必须是E | 
| E:last-child | 匹配父元素下所有子元素中的最后一个子元素 && 该子元素必须是E | 
| E:nth-child(expression) | 匹配父元素下所有子元素中的第expression个子元素 && 该子元素必须是E | 
| E:nth-last-child(expression) | 匹配父元素下的倒数第expression个子元素 && 该子元素必须是E | 
| E:nth-of-type(expression) | 匹配父元素下的众多E元素中的第expression个E元素 |
| E:nth-last-of-type(expression) | 匹配父元素下的众多E元素中的倒数第expression个E元素 |
| E:first-of-type | 匹配父元素下的众多E元素中的第1个E元素 |
| E:last-of-type | 匹配父元素下的众多E元素中的倒数第1个E元素 |
| E:only-child | 父元素只有一个子元素 && 该子元素必须是E | 
| E:only-of-type | 匹配父元素下的众多子元素中的一个子元素 && 该子元素必须是E | 
| E:empty | 选择没有任何内容的元素（一点内容都没有，哪怕是一个空格） | 
| E:not(F) | 匹配所有除了F元素外的E元素，如input:not([type="submit"])，li:not(:hover) | 

| expression | 功能 |
| -------- | ----- | 
|0        | 一个都不选 |
|2n/even  |  选中偶数行|
|2n±1/odd |  选中奇数行|
|n+3      |  选中从第3行直到最后一个元素|
|-n+3     |  选中前3个元素|
|n		  |  全选中 |

###4、伪元素
	IE6~8仅支持css2.1的单冒号写法，不支持css3的双冒号写法

| 名称 | 功能 | 
| -------- | ----- | 
| :first-letter | 选择文本块的第一个字母，如果第一个字母前有标点符号，也会匹配。IE6/7只匹配第一个符号 |
| :first-line | 选择文本块的第一行 |
| ::selection | 选中的文本块，只支持双冒号，只能使用background、color属性 |
| :before | 在元素内部开头插入额外内容(IE8+) |
| :after | 在元素内部末尾插入额外内容(IE8+)，例如：a链接后显示链接地址，a:after{content:'(' attr(href) ')';} |

###5、属性选择器

