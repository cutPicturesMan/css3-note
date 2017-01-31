# css3文本

##1、css3文本阴影属性(IE9+)
>text-shadow : [color] x-offset y-offset blur-radius;  

* color : 阴影颜色
* x-offset : 阴影水平偏移量。如果是正值，阴影在对象的右边；负值，阴影在对象的左边
* y-offset : 阴影垂直偏移量。如果是正值，阴影在对象的底部；负值，阴影在对象的顶部
* blur-radius : 阴影模糊半径。值越大，阴影向外模糊的范围越大，阴影边缘越模糊。只能为正值。

##2、css3文本溢出属性(IE6+)

>text-overflow: clip | ellipsis;

* clip : 不显示省略标记(···)，只是简单的裁切；
* ellipsis : 文本溢出时显示省略标记(···)；

tips:要想达到效果，元素必须定义宽度，以及设置white-space:nowrap;和overflow:hidden;
~~~
.text-overflow-clip{
	width: 100px;
	text-overflow:clip;		//文本裁切
	white-space:nowrap;     //强制不换行
	overflow:hidden;		//溢出隐藏
}
~~~

##3、css3文本换行

###1)word-wrap(IE6+)
实现长单词与URL地址的自动换行

>word-wrap: normal | break-word;

* normal : 默认值，**整个英文单词换行**，英文长单词不会换行，会超出破坏布局
* break-word : **整个英文单词换行**，英文长单词中间截断进行换行。会增加阅读困难

tips:word-wrap在`<pre>`和`<table>`中无任何效果

###2)word-break(IE6+)
决定自动换行的处理方式

>word-break : normal | break-all | keep-all;

* normal : 与word-wrap:normal相同，**整个英文单词换行**，英文长单词不会换行，会超出破坏布局
* break-all : 强行截断英文单词，**英文单词词内换行**（IE不允许换行之后，标点符号位于行首）
* keep-all : 整体换行。中文将整个汉语短语换行，**整个英文单词换行**，英文长单词将会撑破容器。（firefox中，中文只能在半角空格或者连字符的地方换行）

###3)white-space(IE7+)
决定元素中的空白符的处理方式

>white-space : normal | pre | nowrap | pre-line | pre-wrap | inherit

* normal : 默认值。空白处会被浏览器忽略。
* pre : 保留html代码的文本格式，空白符和换行符都将和输入一模一样，与html标签`<pre>`的效果极其相似
* nowrap : 强制文本在一行上显示，直到碰到换行标签`<br/>`，文本中的多余空白符会被忽略
* pre-line : 与pre类似，只不过会忽略多余空白符
* pre-wrap : 与pre类似

white-space:pre; 效果如下
~~~
<p>I have      multiple
spaces and a line break</p>
~~~
~~~
I have      multiple
spaces and a line break
~~~

###4)文本换行技巧

pre标签自动换行
~~~
pre{
	white-space : pre;
	white-space : pre-wrap;
	white-space : pre-line;
	word-wrap : break-word;
}
~~~

单元格（td）自动换行
~~~
table{
	table-layout : fixed;	//列宽由表格宽度和列宽度设定
	width: 200px;
}

table td{
	overflow : hidden;
	word-wrap : break-word;
}
~~~

标签内容强制不换行
~~~
elem {
	white-space : nowrap;
	word-break : keep-all;
}
~~~
