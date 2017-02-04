<a name='回顶部'></a>  
# CSS部分的问题及答案
####更新时间：2015-10-15
### 问题  
1、[介绍一下标准的CSS的盒子模型？与IE的盒子模型有什么不同的？](#1)   
2、[display有哪些值？说明他们的作用。position的值relative和absolute定位原点是？](#2)  
3、[为什么要初始化CSS样式?](#3)  
4、[如何创建块级格式化上下文(block formatting context),BFC有什么用?](#4)    
6、[CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？ ](#6)   
7、[CSS中 link 和@import 的区别是？](#7)  
8、[解释下 CSS sprites,以及你要如何在页面或网站中使用它？](#8)  
9、[display: none;与visibility: hidden;的区别?](#9)  
10、[PNG,GIF,JPG的区别及如何选？](#10)   
11、[请解释一下浮动和它的工作原理？清除浮动的技巧?](#11)   
12、[如何水平居中一个元素？](#12)  
13、[如何竖直居中一个元素?](#13)  
14、[什么叫外边距折叠(collapsing margins)？](#14)  
15、[css hack原理及常用hack?](#15)  
16、[CSS选择器有哪些？](#16)  
17、[CSS3有哪些新特性（包含哪些模块）？](#17)  
18、[iphone手机不同版本CSS兼容怎么实现？](#18)  


xx、[](#)  

---------------------------------------------------------分割线-----------------------------------------------------------------

<a name='1'></a>
**1、介绍一下标准的CSS的盒子模型？与IE的盒子模型有什么不同的？**  
<font size=1>
1、有两种, IE 盒子模型、标准 W3C 盒子模型；IE的content部分包含了 border 和 pading;  
2、盒模型： 内容(content)、填充(padding)、边界(margin)、 边框(border).
	文档中的每个元素被描绘为矩形盒子。确定其大小,属性——比如颜色、背景、边框,及其位置是渲染引擎的目标。CSS下这些矩形盒子由标准盒模型描述。这个模型描述元素内容占用空间。 

	盒子有四个边界：外边距边界margin edge, 边框边界border edge, 内边距边界padding edge 与 内容边界content edge。

	a.内容区域content area 是真正包含元素内容的区域。位于内容边界的内部,
		它的大小为内容宽度 或 content-box宽及内容高度或content-box高。 
		如果 box-sizing 为默认(content-box)值,由height,width 控制内容大小。如果为border-box,则width,height是包含border的；width为100px，border为1px,content的大小是98px;

	b.内边距区域padding area 用内容及可能的边框之间的空白区域扩展内容区域。
		它位于内边边界内部,通常有背景——颜色或图片（不透明图片盖住背景颜色）.
		它的大小为 padding-box  宽与 padding-box 高。
		内边距与内容边界之间的空间由padding-top,padding-right,padding-bottom,padding-left和简写padding控制。

	c.边框区域border area 是包含边框的区域,扩展了内边距区域.
		它位于边框边界内部,大小为 border-box  宽和 border-box 高。
		由 border-width 及简写属性 border控制。
	  
	d.外边距区域margin area用空白区域扩展边框区域,以分开相邻的元素。
		它的大小为margin-box,margin-top,margin-right,margin-bottom,margin-left及简写属性margin控制。
		在外边距合并的情况下,由于盒之间共享外边距,外边距不容易弄清楚。

	最后注意,对于行内非替换元素,其占用空间（行高）由 line-height 决定,即使有内边距与边框。
</font>

<a name='2'></a>
**2、display有哪些值？说明他们的作用。position的值relative和absolute定位原点是？absolute与fixed共同点与不同点？**  
<font size=1>

 	1、display
	   block 象块类型元素一样显示。
	   none 缺省值。象行内元素类型一样显示。
	   inline-block 象行内元素一样显示,但其内容象块类型元素一样显示。
	   list-item 象块类型元素一样显示,并添加样式列表标记。  
		
	2、position	
	   absolute  生成绝对定位的元素,相对于 static 定位以外的第一个父元素进行定位。 
	   fixed （老IE不支持）  	        生成绝对定位的元素,相对于浏览器窗口进行定位。 
	   relative 生成相对定位的元素,相对于其正常位置进行定位。 
	   static  默认值。没有定位,元素出现在正常的流中  
	   inherit 规定从父元素继承 position 属性的值。  
	   *（忽略 top, bottom, left, right z-index 声明）

	absolute与fixed共同点与不同点
		A、共同点：
		1.改变行内元素的呈现方式,display被置为block; 
		2.让元素脱离普通流,不占据空间; 
		3.默认会覆盖到非定位元素上;    
		B、不同点：
		absolute的”根元素“是可以设置的,而fixed的”根元素“固定为浏览器窗口。
		当你滚动网页,fixed元素与浏览器窗口之间的距离是不变的。  
</font>

<a name='3'></a>
**3、为什么要初始化CSS样式?**  
<font size=1>
	1、因为浏览器的兼容问题,不同浏览器对有些标签的默认值是不同的,如果没对CSS初始化往往会出现浏览器之间的页面显示差异。  
	2、当然,初始化样式会对SEO有一定的影响,但鱼和熊掌不可兼得,但力求影响最小的情况下初始化。  
	<li>最简单的初始化方法就是：`* {padding: 0; margin: 0;} `（不建议）</li>
	<li>[淘宝的样式初始化](http://nec.netease.com/framework/css-reset.html)</li>
</font>

<a name='4'></a>
**4、如何创建块级格式化上下文(block formatting context),BFC有什么用?**  
<font size=1>

	BFC,块级格式化上下文,一个创建了新的BFC的盒子是独立布局的,盒子里面的子元素的样式不会影响到外面的元素,
	在同一个BFC中的两个毗邻的块级盒在垂直方向（和布局方向有关系）的margin会发生折叠。

	*创建规则：
		根元素
		浮动元素（float不是none）
		绝对定位元素（position取值为absolute或fixed）
		display取值为inline-block,table-cell, table-caption,flex, inline-flex之一的元素
		overflow不是visible的元素

	*作用：
		可以包含浮动元素
		不被浮动元素覆盖
		阻止父子元素的margin折叠

	W3C CSS 2.1 规范中的一个概念,它决定了元素如何对其内容进行布局,以及与其他元素的关系和相互作用。
</font>


<a name='6'></a>
**6、CSS 选择符有哪些？哪些属性可以继承？优先级算法如何计算？ CSS3新增伪类有那些？**  
<font size=1>
	
	*   1.id选择器（ # myid）
	    2.类选择器（.myclassname）
	    3.标签选择器（div, h1, p）
	    4.相邻选择器（h1 + p）
	    5.子选择器（ul > li）
	    6.后代选择器（li a）
	    7.通配符选择器（ * ）
	    8.属性选择器（a[rel = "external"]）
	    9.伪类选择器（a: hover, li: nth - child）

	*	可继承的样式：
			1、关于文字排版的属性如：font,word-break,letter-spacing,text-align,text-rendering,
					word-spacing,white-space,text-indent,text-transform,text-shadow
			2、line-height
			3、color
			4、visibility
			5、cursor

	*	不可继承的样式：border padding margin width height ;

	*	优先级就近原则,同权重情况下样式定义最近者为准;
		!important >  id > class > tag
   		important 比 内联优先级高

	*	CSS3新增伪类举例：
		p:first-of-type 选择属于其父元素的首个 <p> 元素的每个 <p> 元素。
		p:last-of-type  选择属于其父元素的最后 <p> 元素的每个 <p> 元素。
		p:only-of-type  选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。
		p:only-child    选择属于其父元素的唯一子元素的每个 <p> 元素。
		p:nth-child(2)  选择属于其父元素的第二个子元素的每个 <p> 元素。
		:enabled  :disabled 控制表单控件的禁用状态。
		:checked        单选框或复选框被选中。
</font>

<a name='7'></a>
**7、CSS中 link 和@import 的区别是？**  
<font size=1>

	link方式的样式的权重,高于@import的权重；
	link是HTML方式,@import是CSS方式；
	link最大限度支持并行下载,@import过多嵌套导致串行下载,出现FOUC;

	*FOUC:
		Flash Of Unstyled Content：用户定义样式表加载之前浏览器使用默认样式显示文档,
		用户样式加载渲染之后再从新显示文档,造成页面闪烁。解决方法：把样式表放到文档的head;

	link可以通过rel="alternate stylesheet"指定候选样式；
	@import只在IE5以上才能识别,可以使用@import对老浏览器隐藏样式；
	@import必须在样式规则之前,可以在css文件中引用其他文件；

	总体来说：link优于@import
</font>

<a name='8'></a>
**8、解释下 CSS sprites,以及你要如何在页面或网站中使用它？**  
<font size=1>

	CSS Sprites其实就是把网页中一些背景图片整合到一张图片文件中;
	再利用CSS的“background-image”,“background- repeat,background-position”的组合进行背景定位;
	background-position可以用数字能精确的定位出背景图片的位置;

	这样可以减少很多图片请求的开销,因为请求耗时比较长；请求虽然可以并发,但是也有限制,一般浏览器都是6个;
	对于未来而言,就不需要这样做了,因为有了`http2`;

	*优点：
		减少HTTP请求数,极大地提高页面加载速度;
		增加图片信息重复度,提高压缩比,减少图片大小;
		更换风格方便,只需在一张或几张图片上修改颜色或样式即可实现;

	*缺点：
		图片合并麻烦;
		维护麻烦,修改一个图片可能需要从新布局整个图片,样式;
</font>

<a name='9'></a>
**9、display: none;与visibility: hidden;的区别?**  
<font size=1>
	
	*联系：它们都能让元素不可见

	*区别：
		display:none;会让元素完全从渲染树中消失,渲染的时候不占据任何空间；
		visibility:hidden;不会让元素从渲染树消失,渲染师元素继续占据空间,只是内容不可见；
		display:none;是非继承属性,子孙节点消失由于元素从渲染树消失造成,通过修改子孙节点属性无法显示；
		visibility:hidden;是继承属性,子孙节点消失由于继承了hidden,设置visibility: visible;可以让子孙节点显式；
		修改常规流中元素的display通常会造成文档重排。修改visibility属性只会造成本元素的重绘；
		浏览器不会读取display: none;元素内容；会读取visibility: hidden;元素内容；
</font>		

<a name='10'></a>
**10、PNG,GIF,JPG的区别及如何选？**  
<font size=1>
	
	*GIF:
		8位像素,256色
		无损压缩
		支持简单动画
		支持boolean透明
		适合简单动画

	*JPEG：
		颜色限于256
		有损压缩
		可控制压缩质量
		不支持透明
		适合照片

	*PNG：
		有PNG8和truecolor PNG
		PNG8类似GIF颜色上限为256,文件小,支持alpha透明度,无动画
		适合图标、背景、按钮
</font>

<a name='11'></a>
**11、请解释一下浮动和它的工作原理？清除浮动的技巧? **  
<font size=1>
	
	*浮动元素脱离文档流,不占据空间。浮动元素碰到包含它的边框或者浮动元素的边框停留。

	*浮动元素引起的问题：
		（1）父元素的高度无法被撑开,影响与父元素同级的元素
		（2）与浮动元素同级的非浮动元素会跟随其后
		（3）若非第一个元素浮动,则该元素之前的元素也需要浮动,否则会影响页面显示的结构

	*解决方法： 
		使用CSS中的clear:both;属性来清除元素的浮动可解决2、3问题;
		对于问题1,添加如下样式,给父元素添加clearfix样式：
		.clearfix:after{content: ".";display: block;height: 0;clear: both;visibility: hidden;}
		.clearfix{display: inline-block;} /* for IE/Mac */

	*清除浮动的几种方法：
		1,额外标签法,<div style="clear:both;"></div>（缺点：不过这个办法会增加额外的标签使HTML结构看起来不够简洁。）
		2,使用after伪类
		#parent:after{
		    content:".";
		    height:0;
		    visibility:hidden;
		    display:block;
		    clear:both;
		    }

		3,浮动外部元素
		4,设置`overflow`为`hidden`或者auto
</font>

<a name='12'></a>
**12、如何水平居中一个元素？**  
<font size=1>

	1、如果需要居中的元素为常规流中inline元素,为父元素设置text-align: center;即可实现;  
	---------------------------------------分割线---------------------------------------

	2、如果需要居中的元素为常规流中block元素：  
		1）为元素设置宽度  
		2）设置左右margin为auto  
		3）IE6下需在父元素上设置text-align: center  
		4）再给子元素恢复需要的值    
		<body>
		    <div class="content">
		    aaaaaa aaaaaa a a a a a a a a
		    </div>
		</body>
		<style>
		    body {
		        background: #DDD;
		        text-align: center; /* 3 */
		    }
		    .content {
		        width: 500px;      /* 1 */
		        text-align: left;  /* 3 */
		        margin: 0 auto;    /* 2 */

		        background: purple;
		    }
		</style>
	---------------------------------------分割线---------------------------------------

	3、如果需要居中的元素为浮动元素：
		1）为元素设置宽度
		2）position: relative
		3）浮动方向偏移量（left或者right）设置为50%
		4）浮动方向上的margin设置为元素宽度一半乘以-1
		<body>
		    <div class="content">
		    aaaaaa aaaaaa a a a a a a a a
		    </div>
		</body>
		<style>
		    body {
		        background: #DDD;
		    }
		    .content {
		        width: 500px;         /* 1 */
		        float: left;

		        position: relative;   /* 2 */
		        left: 50%;            /* 3 */
		        margin-left: -250px;  /* 4 */

		        background-color: purple;
		    }
		</style>
	---------------------------------------分割线---------------------------------------

	4、如果需要居中的元素为绝对定位元素：
		1）为元素设置宽度
		2）偏移量设置为50%
		3）偏移方向外边距设置为元素宽度一半乘以-1
		<body>
	    	<div class="content">
			    aaaaaa aaaaaa a a a a a a a a
		    </div>
		</body>
		<style>
		    body {
		        background: #DDD;
		        position: relative;
		    }
		    .content {
		        width: 800px;

		        position: absolute;
		        margin: 0 auto;
		        left: 0;
		        right: 0;

		        background-color: purple;
		    }
		</style>

</font>

<a name='13'></a>
**13、如何竖直居中一个元素?**  
<font size=1>
	<li>[垂直居中6种方法](http://blog.csdn.net/freshlover/article/details/11579669)</li> 
	
	---------------------------------------分割线---------------------------------------
	1、绝对定位居中(Absolute Centering)：
		需声明元素高度和下面的CSS:
		.Center-Container {  
		  position: relative;  
		}  
		  
		.Absolute-Center {  
		  width: 50%;  
		  height: 50%;  
		  overflow: auto;  
		  margin: auto;  
		  position: absolute;  
		  top: 0; left: 0; bottom: 0; right: 0;  
		}  
		*优点：
			1.支持跨浏览器,包括IE8-IE10
			2.无需其他特殊标记,CSS代码量少
			3.支持百分比%属性值和min-/max-属性
			4.只用这一个类可实现任何内容块居中
			5.不论是否设置padding都可居中（在不使用box-sizing属性的前提下）
			6.内容块可以被重绘
			7.完美支持图片居中
		*缺点：
			1.必须声明高度（查看可变高度Variable Height）
			2.建议设置overflow:auto来防止内容越界溢出。（查看溢出Overflow）
			3.在Windows Phone设备上不起作用
		*浏览器兼容性：
			Chrome,Firefox, Safari, Mobile Safari, IE8-10.

	---------------------------------------分割线---------------------------------------
	2、负外边距(Negative Margins)居中：如果块元素尺寸已知,最流行的方法：
		外边距margin取负数,大小为width/height（不使用box-sizing: border-box时包括padding,）的一半;
		再加上top: 50%; left: 50%;
		.is-Negative {
		        width: 300px;
		        height: 200px;
		        padding: 20px;
		        position: absolute;
		        top: 50%; left: 50%;
		        margin-left: -170px; /* (width + padding)/2 */
		        margin-top: -120px; /* (height + padding)/2 */
		}
		*优点：
			1. 良好的跨浏览器特性,兼容IE6-IE7。
			2. 代码量少
		*缺点：
			1. 不能自适应。不支持百分比尺寸和min-/max-属性设置。
			2. 内容可能溢出容器。
			3. 边距大小与padding,和是否定义box-sizing: border-box有关,计算需要根据不同情况。

	---------------------------------------分割线---------------------------------------
	3、变形（Transforms）：元素高度可变,最简单的方法：
		内容块定义transform: translate(-50%,-50%)必须带上浏览器厂商的前缀；
		再加上top: 50%; left: 50%;
		.is-Transformed {
		  width: 50%;
		  margin: auto;
		  position: absolute;
		  top: 50%; left: 50%;
		  -webkit-transform: translate(-50%,-50%);
		      -ms-transform: translate(-50%,-50%);
		          transform: translate(-50%,-50%);
		}
		*优点：
			1.内容可变高度
			2.代码量少
		*缺点：
			1.IE8不支持
			2.属性需要写浏览器厂商前缀
			3.可能干扰其他transform效果
			4.某些情形下会出现文本或元素边界渲染模糊的现象

	---------------------------------------分割线---------------------------------------
	4、表格单元格（Table-Cell）：最好的方法:
		因为内容块高度会随着实际内容的高度变化,浏览器对此的兼容性也好;
		最大的缺点是需要大量额外的标记,需要三层元素让最内层的元素居中。
		<div class="Center-Container is-Table">
		  <div class="Table-Cell">
		    <div class="Center-Block">
		    <!-- CONTENT -->
		    </div>
		  </div>
		</div>
		.Center-Container.is-Table { display: table; }
		.is-Table .Table-Cell {
		  display: table-cell;
		  vertical-align: middle;
		}
		.is-Table .Center-Block {
		  width: 50%;
		  margin: 0 auto;
		}
		*优点：
			1.高度可变
			2.内容溢出会将父元素撑开。
			3.跨浏览器兼容性好。
		*缺点：
			需要额外html标记

	---------------------------------------分割线---------------------------------------
	5、行内块元素（Inline-Block）：受欢迎的方式,
		使用display: inline-block, vertical-align: middle和一个伪元素让内容块处于容器中央；
	
		如果内容块宽度大于容器宽度,比如放了一个很长的文本,但内容块宽度设置最大不能超过容器的100%减去0.25em,	
		否则使用伪元素:after内容块会被挤到容器顶部,使用:before内容块会向下偏移100%。

		如果你的内容块需要占据尽可能多的水平空间,可以使用max-width: 99%;（针对较大的容器）或max-width: calc(100% -0.25em)（取决于浏览器和容器宽度）

		<div class="Center-Container is-Inline">
		  <div class="Center-Block">
		    <!-- CONTENT -->
		  </div>
		</div>
		.Center-Container.is-Inline {
		  text-align: center;
		  overflow: auto;
		}
		.Center-Container.is-Inline:after,
		.is-Inline .Center-Block {
		  display: inline-block;
		  vertical-align: middle;
		}
		.Center-Container.is-Inline:after {
		  content: '';
		  height: 100%;
		  margin-left: -0.25em; /* To offset spacing. May vary by font */
		}
		.is-Inline .Center-Block {
		  max-width: 99%; /* Prevents issues with long content causes the content block to be pushed to the top */
		  /* max-width: calc(100% - 0.25em) /* Only for IE9+ */
		}
		*优点：
			1.高度可变
			2.内容溢出会将父元素撑开。
			3.支持跨浏览器,也适应于IE7。
		*缺点：
			1.需要一个容器
			2.水平居中依赖于margin-left: -0.25em;该尺寸对于不同的字体/字号需要调整。
			3.内容块宽度不能超过容器的100% - 0.25em。

	---------------------------------------分割线---------------------------------------
	6、Flexbox:	这是CSS布局未来的趋势。
		Flexbox是CSS3新增属性,设计初衷是为了解决像垂直居中这样的常见布局问题。
		记住Flexbox不只是用于居中,也可以分栏或者解决一些令人抓狂的布局问题。
		body {
		   /* Remember to use the other versions for IE 10 and older browsers! */
		   display: flex;
		   justify-content: center;
		   align-items: center;
		}
		*优点：
			1.内容块的宽高任意,优雅的溢出。
			2.可用于更复杂高级的布局技术中。
		*缺点：
			1. IE8/IE9不支持。
			2. Body需要特定的容器和CSS样式。
			3.运行于现代浏览器上的代码需要浏览器厂商前缀。
			4.表现上可能会有一些问题

		*其他：
			曾经你使用负边距（Negative Margins）的地方,现在可以用绝对居中(Absolute Centering)替代了。
			你不再需要处理讨厌的边距计算和额外的标记,而且还能让内容块自适应大小居中;

	如果你的站点需要可变高度的内容,可以试试单元格(Table-Cell)和行内块元素(Inline-Block)这两种方法;	
	如果你处在流血的边缘,试试Flexbox,体验一下这一高级布局技术的好处吧。
</font>

<a name='14'></a>
**14、什么叫外边距折叠(collapsing margins)？**  
<font size=1>
	
	毗邻的两个或多个margin会合并成一个margin,叫做外边距折叠。规则如下：

	1、两个或多个毗邻的普通流中的块元素垂直方向上的margin会折叠
	2、浮动元素/inline-block元素/绝对定位元素的margin不会和垂直方向上的其他元素的margin折叠
	3、创建了块级格式化上下文的元素,不会和它的子元素发生margin折叠
	4、元素自身的margin-bottom和margin-top相邻时也会折叠
</font>

<a name='15'></a>
**15、css hack原理及常用hack?**  
<font size=1>
	
	原理：利用不同浏览器对CSS的支持和解析结果不一样编写针对特定浏览器样式。常见的hack有:
	1）属性hack
	/* IE6 */
	#once { _color: blue }

	/* IE6, IE7 */
	#doce { *color: blue; /* or #color: blue */ }

	/* Everything but IE6 */
	#diecisiete { color/**/: blue }

	/* IE6, IE7, IE8 */
	#diecinueve { color: blue\9; }

	/* IE7, IE8 */
	#veinte { color/*\**/: blue\9; }

	/* IE6, IE7 -- acts as an !important */
	#veintesiete { color: blue !ie; } /* string after ! can be anything */
	---------------------------------------分割线---------------------------------------

	2）选择器hack
	/* IE6 and below */
	* html #uno  { color: red }

	/* IE7 */
	*:first-child+html #dos { color: red }

	/* IE7, FF, Saf, Opera  */
	html>body #tres { color: red }

	/* IE8, FF, Saf, Opera (Everything but IE 6,7) */
	html>/**/body #cuatro { color: red }

	/* Opera 9.27 and below, safari 2 */
	html:first-child #cinco { color: red }

	/* Safari 2-3 */
	html[xmlns*=""] body:last-child #seis { color: red }

	/* safari 3+, chrome 1+, opera9+, ff 3.5+ */
	body:nth-of-type(1) #siete { color: red }

	/* safari 3+, chrome 1+, opera9+, ff 3.5+ */
	body:first-of-type #ocho {  color: red }

	/* saf3+, chrome1+ */
	@media screen and (-webkit-min-device-pixel-ratio:0) {
	 #diez  { color: red  }
	}

	/* iPhone / mobile webkit */
	@media screen and (max-device-width: 480px) {
	 #veintiseis { color: red  }
	}

	/* Safari 2 - 3.1 */
	html[xmlns*=""]:root #trece  { color: red  }

	/* Safari 2 - 3.1, Opera 9.25 */
	*|html[xmlns*=""] #catorce { color: red  }

	/* Everything but IE6-8 */
	:root *> #quince { color: red  }

	/* IE7 */
	*+html #dieciocho {  color: red }

	/* Firefox only. 1+ */
	#veinticuatro,  x:-moz-any-link  { color: red }

	/* Firefox 3.0+ */
	#veinticinco,  x:-moz-any-link, x:default  { color: red  }
	---------------------------------------分割线---------------------------------------

	3）IE条件注释
	<!--[if IE 6]>
	Special instructions for IE 6 here
	<![endif]-->
</font>

<a name='16'></a>
**16、CSS选择器有哪些？**  
<font size=1>
	
	**通用选择器：选择所有元素,不参与计算优先级*,兼容性IE6+
	#X id选择器：选择id值为X的元素,兼容性：IE6+
	.X 类选择器： 选择class包含X的元素,兼容性：IE6+
	X Y后代选择器： 选择满足X选择器的后代节点中满足Y选择器的元素,兼容性：IE6+
	X 元素选择器： 选择标所有签为X的元素,兼容性：IE6+
	:link,：visited,：focus,：hover,：active链接状态： 选择特定状态的链接元素,顺序LoVe HAte,兼容性: IE4+
	---------------------------------------分割线---------------------------------------
	X + Y直接兄弟选择器：在X之后第一个兄弟节点中选择满足Y选择器的元素,兼容性： IE7+
	X > Y子选择器： 选择X的子元素中满足Y选择器的元素,兼容性： IE7+
	X ~ Y兄弟： 选择X之后所有兄弟节点中满足Y选择器的元素,兼容性： IE7+
	[attr]：选择所有设置了attr属性的元素,兼容性IE7+
	[attr=value]：选择属性值刚好为value的元素
	[attr~=value]：选择属性值为空白符分隔,其中一个的值刚好是value的元素
	[attr|=value]：选择属性值刚好为value或者value-开头的元素
	[attr^=value]：选择属性值以value开头的元素
	[attr$=value]：选择属性值以value结尾的元素
	[attr*=value]：选择属性值中包含value的元素
	[:checked]：选择单选框,复选框,下拉框中选中状态下的元素,兼容性：IE9+
	X:after, X::after：after伪元素,选择元素虚拟子元素（元素的最后一个子元素）
	---------------------------------------分割线---------------------------------------
	CSS3中::表示伪元素。兼容性:after为IE8+,::after为IE9+
	:hover：鼠标移入状态的元素,兼容性a标签IE4+, 所有元素IE7+
	:not(selector)：选择不符合selector的元素。不参与计算优先级,兼容性：IE9+
	::first-letter：伪元素,选择块元素第一行的第一个字母,兼容性IE5.5+
	::first-line：伪元素,选择块元素的第一行,兼容性IE5.5+
	:nth-child(an + b)：伪类,选择前面有an + b - 1个兄弟节点的元素,其中n >= 0, 兼容性IE9+
	:nth-last-child(an + b)：伪类,选择后面有an + b - 1个兄弟节点的元素 其中n >= 0,兼容性IE9+
	X:nth-of-type(an+b)：伪类,X为选择器,解析得到元素标签,选择前面有an + b - 1个相同标签兄弟节点的元素。兼容性IE9+
	X:nth-last-of-type(an+b)伪类,X为选择器,解析得到元素标签,选择后面有an+b-1个相同标签兄弟节点的元素。兼容性IE9+
	X:first-child：伪类,选择满足X选择器的元素,且这个元素是其父节点的第一个子元素。兼容性IE7+
	X:last-child：伪类,选择满足X选择器的元素,且这个元素是其父节点的最后一个子元素。兼容性IE9+
	X:only-child：伪类,选择满足X选择器的元素,且这个元素是其父元素的唯一子元素。兼容性IE9+
	X:only-of-type：伪类,选择X选择的元素,解析得到元素标签,如果该元素没有相同类型的兄弟节点时选中它。兼容性IE9+
	X:first-of-type：伪类,选择X选择的元素,解析得到元素标签,如果该元素 是此此类型元素的第一个兄弟。选中它。兼容性IE9+
</font>

<a name='17'></a>
**17、CSS3有哪些新特性（包含哪些模块）？**  
<font size=1>
	
	1、圆角border-radius、阴影box-shadow,text-shadow、渐变gradients、过渡transitions、
		动画animations、布局multi-columns, flex box, grid layout, Opacity,color(rgb,rgba,hsl,hsla )
	2、子串匹配的属性选择器:E[attribute^="value"], E[attribute$="value"], E[attribute*="value"]
	3、新的伪类：
		:target, :enabled 和 :disabled,:checked,:indeterminate,:root,:nth-child 和 :nth-last-child,
		:nth-of-type和 :nth-last-of-type,:last-child,:first-of-type 和 :last-of-type,
		:only-child 和 :only-of-type,:empty,和 :not
	4、伪元素使用两个冒号而不是一个来表示：
		:after 变为 ::after, :before 变为 ::before, :first-letter 变为 ::first-letter, 
		还有 :first-line 变为 ::first-line。
</font>

<a name='17'></a>
**18、iphone手机不同版本CSS兼容怎么实现？**  
<font size=1>
	具体答案：
	http://stackoverflow.com/questions/12539697/iphone-5-css-media-query
</font>



<a name='xx'></a>
**xx、**  
<font size=1>

</font>






[回顶部](#回顶部)