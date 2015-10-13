<a name='回顶部'></a>  
# CSS部分的问题及答案
####更新时间：2015-10-15
1、[介绍一下标准的CSS的盒子模型？与IE的盒子模型有什么不同的？](#1)   
2、[display有哪些值？说明他们的作用。position的值relative和absolute定位原点是？](#2)  
3、[为什么要初始化CSS样式?](#3)  
4、[对BFC规范的理解？](#4)    
5、[display:none和visibility:hidden的区别？](#5)    
6、[CSS权重优先级是如何计算的？ ](#6)   
7、[absolute的containing\block计算方式跟正常流有什么不同？](#7)  
8、[对BFC规范的理解？](#8)  
9、[CSS里的visibility属性有个collapse属性值是干嘛用的？在不同浏览器下以后什么区别？](#9)  
10、[CSS权重优先级是如何计算的？](#10)   
11、[请解释一下浮动和它的工作原理？清除浮动的技巧](#11)   
12、[移动端的布局用过媒体查询吗？](#12)  
13、[CSS优化、提高性能的方法有哪些？](#13)  
14、[浏览器是怎样解析CSS选择器的？](#14)  
15、[在网页中的应该使用奇数还是偶数的字体？为什么呢？](#15)  
16、[margin和padding分别适合什么场景使用？](#16)  
17、[元素竖向的百分比设定是相对于容器的高度吗？](#17)  
18、[全屏滚动的原理是什么？用到了CSS的那些属性？](#18)  
19、[什么是响应式设计？响应式设计的基本原理是什么？如何兼容低版本的IE？](#19)  
20、[什么是伪元素，什么是伪类？,他们的区别是什么？](#20)  
21、[如何修改chrome记住密码后自动填充表单的黄色背景？](#21)  
22、[你对line-height是如何理解的？](#22)  
23、[`position:fixed;`在android下无效怎么处理？](#23)  
24、[`display:inline-block;`什么时候会显示间隙?](#24)  
25、[`overflow:scroll;`时不能平滑滚动的问题怎么处理？](#25)  
26、[怎么让Chrome支持小于12px;的文字？](#26)  
27、[CSS3有哪些新特性（包含哪些模块）？](#27)  
28、[请解释一下CSS3的Flexbox（弹性盒布局模型）,以及适用场景？](#28)  
29、[IE各个版本兼容性及hack](#29)   
xx、[](#) 

<a name='1'></a>
**1、介绍一下标准的CSS的盒子模型？与IE的盒子模型有什么不同的？**  
<font size=1>
1，有两种， IE 盒子模型、标准 W3C 盒子模型；IE的content部分包含了 border 和 pading;  
2，盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border).
	文档中的每个元素被描绘为矩形盒子。确定其大小，属性——比如颜色、背景、边框，及其位置是渲染引擎的目标。CSS下这些矩形盒子由标准盒模型描述。这个模型描述元素内容占用空间。 

	盒子有四个边界：外边距边界margin edge, 边框边界border edge, 内边距边界padding edge 与 内容边界content edge。

	a.内容区域content area 是真正包含元素内容的区域。位于内容边界的内部，它的大小为内容宽度 或 content-box宽及内容高度或content-box高。
	  如果 box-sizing 为默认值， width, min-width, max-width, height, min-height 与 max-height 控制内容大小。

	b.内边距区域padding area 用内容及可能的边框之间的空白区域扩展内容区域。
	  它位于内边边界内部，通常有背景——颜色或图片（不透明图片盖住背景颜色）. 它的大小为 padding-box  宽与 padding-box 高。
	  内边距与内容边界之间的空间可以由 padding-top, padding-right, padding-bottom, padding-left 和简写属性 padding 控制。

	c.边框区域border area 是包含边框的区域，扩展了内边距区域。它位于边框边界内部，大小为 border-box  宽和 border-box 高。
	  由 border-width 及简写属性 border控制。
	  
	d.外边距区域margin area用空白区域扩展边框区域，以分开相邻的元素。
	  它的大小为 margin-box,margin-top, margin-right, margin-bottom, margin-left 及简写属性 margin 控制。
	  在外边距合并的情况下，由于盒之间共享外边距，外边距不容易弄清楚。

	最后注意，对于行内非替换元素，其占用空间（行高）由 line-height 决定，即使有内边距与边框。
</font>

<a name='2'></a>
**2、display有哪些值？说明他们的作用。position的值relative和absolute定位原点是？absolute与fixed共同点与不同点？**  
<font size=1>

 	1、display
	   block 象块类型元素一样显示。
	   none 缺省值。象行内元素类型一样显示。
	   inline-block 象行内元素一样显示，但其内容象块类型元素一样显示。
	   list-item 象块类型元素一样显示，并添加样式列表标记。  
		
	2、position	
	   absolute  生成绝对定位的元素，相对于 static 定位以外的第一个父元素进行定位。 
	   fixed （老IE不支持）  	        生成绝对定位的元素，相对于浏览器窗口进行定位。 
	   relative 生成相对定位的元素，相对于其正常位置进行定位。 
	   static  默认值。没有定位，元素出现在正常的流中  
	   inherit 规定从父元素继承 position 属性的值。  
	   *（忽略 top, bottom, left, right z-index 声明）

	absolute与fixed共同点与不同点
		A、共同点：
		1.改变行内元素的呈现方式，display被置为block; 
		2.让元素脱离普通流，不占据空间; 
		3.默认会覆盖到非定位元素上;    
		B、不同点：
		absolute的”根元素“是可以设置的，而fixed的”根元素“固定为浏览器窗口。当你滚动网页，fixed元素与浏览器窗口之间的距离是不变的。  
</font>

<a name='3'></a>
**3、为什么要初始化CSS样式?**  
<font size=1>
	1，因为浏览器的兼容问题，不同浏览器对有些标签的默认值是不同的，如果没对CSS初始化往往会出现浏览器之间的页面显示差异。  
	2，当然，初始化样式会对SEO有一定的影响，但鱼和熊掌不可兼得，但力求影响最小的情况下初始化。  
	<li>最简单的初始化方法就是：`* {padding: 0; margin: 0;} `（不建议）</li>
	<li>[淘宝的样式初始化](http://nec.netease.com/framework/css-reset.html)</li>
</font>

<a name='4'></a>
**4、对BFC规范的理解？**  
<font size=1>

	BFC，块级格式化上下文，一个创建了新的BFC的盒子是独立布局的，盒子里面的子元素的样式不会影响到外面的元素。
	在同一个BFC中的两个毗邻的块级盒在垂直方向（和布局方向有关系）的margin会发生折叠。  

	W3C CSS 2.1 规范中的一个概念，它决定了元素如何对其内容进行布局，以及与其他元素的关系和相互作用。
</font>

<a name='5'></a>
**5、display:none和visibility:hidden的区别？**  
<font size=1>

	display:none 隐藏对应的元素，在文档布局中不再给它分配空间，它各边的元素会合拢，就当他从来不存在。
	visibility:hidden  隐藏对应的元素，但是在文档布局中仍保留原来的空间。
</font>

<a name='6'></a>
**6、CSS权重优先级是如何计算的？ **  
<font size=1>

</font>

<a name='7'></a>
**7、**  
<font size=1>

</font>

<a name='8'></a>
**8、**  
<font size=1>

</font>

<a name='9'></a>
**9、**  
<font size=1>

</font>

<a name='10'></a>
**10、**  
<font size=1>

</font>

<a name='11'></a>
**11、**  
<font size=1>

</font>

<a name='12'></a>
**12、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>

<a name='1'></a>
**2、**  
<font size=1>

</font>







[回顶部](#回顶部)