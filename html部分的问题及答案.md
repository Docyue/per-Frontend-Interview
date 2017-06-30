<a name='回顶部'></a>  
# HTML部分的问题及答案
####更新时间：2015-10-15
### 问题  
1、[Doctype作用？严格模式与混杂模式如何区分？它们有何意义?有多少种Doctype文档类型？](#1)  
2、[文本流和文档流](#2)    
3、[什么是web语义化,有什么好处?](#3)    
4、[`<img>`的title和alt有什么区别?](#4)   
5、[HTML全局属性(global attribute)有哪些?](#5)  
6、[行内元素有哪些？块级元素有哪些？空(void)元素有那些？](#6)  
7、[页面导入样式时，使用link和@import有什么区别？](#7)  
8、[常见的浏览器内核有哪些?](#8)   
9、[html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分HTML和HTML5？](#9)  
10、[HTML5的离线储存怎么用，工作原理能不能解释一下？](#10)  
11、[浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？](#11)  
12、[请描述一下cookies,sessionStorage和localStorage的区别？](#12)  
13、[iframe有哪些缺点？](#13)  
14、[如何实现浏览器内多个标签页之间的通信? ](#14)  
15、[如何使用websocket？如何兼容低浏览器？](#15)  
16、[HTML5的form如何关闭自动完成功能？](#16)   
17、[什么叫优雅降级和渐进增强？](#17)   
18、[了解 HTML5 中的 download 属性](#18)   
19、[](#19)   
20、[](#20)   
21、[](#21)   


xx、[](#)  

---------------------------------------------------------分割线-----------------------------------------------------------------

<a name='1'></a>
**1、Doctype作用？有多少种Doctype文档类型？严格模式与混杂模式如何区分？**  
作用:

	<!DOCTYPE> 声明位于文档中的最前面，处于 <html> 标签之前。告知浏览器以何种模式来渲染文档；
	DOCTYPE不存在或格式不正确会导致文档以混杂模式呈现；

有多少种Doctype文档类型:

	HTML5 只有一种文档类型：<!DOCTYPE html>  
	HTML 4.01 规定了三种文档类型：Strict、Transitional 以及 Frameset。      
	XHTML 1.0 规定了三种 XML 文档类型：Strict、Transitional 以及 Frameset。  

如何区分:

	1、严格模式也就是标准模式的排版和 JS 运作模式是以该浏览器支持的最高标准运行，用于呈现遵循最新标准的网页。  
	2、在包容模式中，页面以宽松的向后兼容的方式显示。模拟老式浏览器的行为以防止站点无法工作。 
  

<a name='2'></a>
**2、文本流和文档流**  

	1，文档流：将窗体自上而下分成一行一行,并在每行中按从左至右的挨次排放元素,即为文档流。每个非浮动块级元素都独有一行, 浮动元素则按规则浮在行的一端. 若当时行容不下, 则另起新行再浮动。内联元素也不会独有一行. 一切元素(包括块级,内联和列表元素)均可生成子行, 用于摆放子元素。  
	2，文本流: 文本流其实就是一系列字符，可以由多行构成，每行由一个换行符终止。
**有三种状况将使得元素离开文档流而存在,分别是浮动、绝对定位、固定定位; 然而在IE中浮动元素也存在于文档流中。**      
浮动元素不占任何正常文档流空间，而浮动元素的定位照样基于正常的文档流，然后从文档流中抽出并尽能够远的挪动至左侧或许右侧。当一个元素脱离正常文档流后，依然在文档流中的其他元素将忽略该元素并填补其原先的空间。 基于文档流，理解以下的定位形式: 

	相对定位：元素框偏移某个距离。元素仍保持其未定位前的形状，它原本所占的空间仍保留。  
	绝对定位：即完全离开文档流, 相关于position属性非static值的比来父级元素进行偏移。  
	固定定位：即完全离开文档流，相关于视区进行偏移。  


<a name='3'></a>
**3、什么是web语义化,有什么好处?**  


	1，去掉或者丢失样式的时候能够让页面呈现出清晰的结构。     
	2，有利于SEO：和搜索引擎建立良好沟通，有助于爬虫抓取更多的有效信息：爬虫依赖于标签来确定上下文和各个关键字的权重。   
	3，方便其他设备解析（如屏幕阅读器、盲人阅读器、移动设备）以意义的方式来渲染网页。   
	4，便于团队开发和维护，语义化更具可读性，是下一代网页的重要动向，遵循W3C标准的团队都遵循这个标准，可以减少差异化。  

<a name='4'></a>
**4、`<img>`的title和alt有什么区别？**  


	1，title是global attributes之一，用于为元素提供附加的advisory information。通常当鼠标滑动到元素上的时候显示。  
	2，alt是<img>的特有属性，是图片内容的等价描述，用于图片无法加载时显示、读屏器阅读图片。可提图片高可访问性，
	除了纯装饰图片外都必须设置有意义的值，搜索引擎会重点分析。

<a name='5'></a>
**5、HTML全局属性(global attribute)有哪些?**  
 

	accesskey:设置快捷键，提供快速访问元素如aaa在windows下的firefox中按alt + shift + a可激活元素  
	class:为元素设置类标识，多个类名用空格分开，CSS和javascript可通过class属性获取元素  
	contenteditable: 指定元素内容是否可编辑  
	contextmenu: 自定义鼠标右键弹出菜单内容  
	data-*: 为元素增加自定义属性  
	dir: 设置元素文本方向  
	draggable: 设置元素是否可拖拽  
	dropzone: 设置元素拖放类型： copy, move, link  
	hidden: 表示一个元素是否与文档。样式上会导致元素不显示，但是不能用这个属性实现样式效果  
	id: 元素id，文档内唯一  
	lang: 元素内容的的语言  
	spellcheck: 是否启动拼写和语法检查  
	style: 行内css样式  
	tabindex: 设置元素可以获得焦点，通过tab可以导航  
	title: 元素相关的建议信息  
	translate: 元素和子孙节点内容是否需要本地化  


<a name='6'></a>
**6、行内元素有哪些？块级元素有哪些？空(void)元素有那些？**  

首先：CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值，如div的display默认值为“block”，则为“块级”元素；span默认display属性值为“inline”，是“行内”元素。

	1，行内元素有：`a b span img input select strong（强调的语气）`  
	2，块级元素有：`div ul ol li dl dt dd h1 h2 h3 h4…p`  
	3，常见的空元素：  
	`<br> <hr> <img> <input> <link> <meta>`  
	鲜为人知的是：  
	`<area> <base> <col> <command> <embed> <keygen> <param> <source> <track> <wbr>`

<a name='7'></a>
**7、页面导入样式时，使用link和@import有什么区别？**  


	1，link属于XHTML标签，除了加载CSS外，还能用于定义RSS, 定义rel连接属性等作用；而@import是CSS提供的，只能用于加载CSS;  
	2，页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;  
	3，import是CSS2.1 提出的，只在IE5以上才能被识别，而link是XHTML标签，无兼容问题;  

<a name='8'></a>
**8、常见的浏览器内核有哪些?**  


	1，Trident内核：IE,MaxThon,TT,The World,360,搜狗浏览器等。[又称MSHTML]  
	2，Gecko内核：Netscape6及以上版本，FF,MozillaSuite/SeaMonkey等  
	3，Presto内核：Opera7及以上。      [Opera内核原为：Presto，现为：Blink;]  
	4，Webkit内核：Safari,Chrome等。   [ Chrome的：Blink（WebKit的分支）]  

<a name='9'></a>
**9、html5有哪些新特性、移除了那些元素？如何处理HTML5新标签的浏览器兼容问题？如何区分HTML和HTML5？**  

1，HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。

	绘画 canvas;  
	用于媒介回放的 video 和 audio 元素;  
	本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失;  
	sessionStorage 的数据在浏览器关闭后自动删除;  
	语意化更好的内容元素，比如 article、footer、header、nav、section;  
	表单控件，calendar、date、time、email、url、search;  
	新的技术webworker, websockt, Geolocation;  
2，移除的元素：

	纯表现的元素：basefont，big，center，font, s，strike，tt，u;  
    对可用性产生负面影响的元素：frame，frameset，noframes；

3，支持HTML5新标签：

	IE8/IE7/IE6支持通过document.createElement方法产生的标签，
	可以利用这一特性让这些浏览器支持HTML5新标签，
	浏览器支持新标签后，还需要添加标签默认的样式。

	当然最好的方式是直接使用成熟的框架、使用最多的是html5shim框架
	<!--[if lt IE 9]>
	<script> src="http://html5shim.googlecode.com/svn/trunk/html5.js"</script>
	<![endif]-->1
4，如何区分： DOCTYPE声明\新增的结构元素\功能元素

<a name='10'></a>
**10、HTML5的离线储存怎么用，工作原理能不能解释一下？什么是应用程序缓存（Application Cache）？**  

在用户没有与因特网连接时，可以正常访问站点或应用，在用户与因特网连接时，更新用户机器上的缓存文件。  
<b>原理：</b>HTML5的离线存储是基于一个新建的.appcache文件的缓存机制(不是存储技术)，通过这个文件上的解析清单离线存储资源，这些资源就会像cookie一样被存储了下来。之后当网络在处于离线状态下时，浏览器会通过被离线存储的数据进行页面展示。  

<b>应用程序缓存:</b>HTML5 引入了应用程序缓存，这意味着 web 应用可进行缓存，并可在没有因特网连接时进行访问。所有主流浏览器均支持应用程序缓存，除了 Internet Explorer。

<b>应用程序缓存为应用带来三个优势：</b>
离线浏览 - 用户可在应用离线时使用它们
速度 - 已缓存资源加载得更快
减少服务器负载 - 浏览器将只从服务器下载更新过或更改过的资源。


	如何使用：
	1、页面头部像下面一样加入一个manifest的属性；
	2、在cache.manifest文件的编写离线存储的资源；
	    CACHE MANIFEST
	    #v0.11
	    CACHE:
	    js/app.js
	    css/style.css
	    NETWORK:
	    resourse/logo.png
	    FALLBACK:
	    / /offline.html
	3、在离线状态时，操作window.applicationCache进行需求实现。

<a name='11'></a>
**11、浏览器是怎么对HTML5的离线储存资源进行管理和加载的呢？**  

在线的情况下，浏览器发现html头部有manifest属性，它会请求manifest文件，如果是第一次访问app，那么浏览器就会根据manifest文件的内容下载相应的资源并且进行离线存储。如果已经访问过app并且资源已经离线存储了，那么浏览器就会使用离线的资源加载页面，然后浏览器会对比新的manifest文件与旧的manifest文件，如果文件没有发生改变，就不做任何操作，如果文件改变了，那么就会重新下载文件中的资源并进行离线存储。
离线的情况下，浏览器就直接使用离线存储的资源。


<a name='12'></a>
**12、请描述一下cookies,sessionStorage和localStorage的区别？**  

1，cookie是网站为了标示用户身份而储存在用户本地终端（Client Side）上的数据（通常经过加密）。  
2，cookie数据始终在同源的http请求中携带（即使不需要），记会在浏览器和服务器间来回传递。  
3，sessionStorage和localStorage不会自动把数据发给服务器，仅在本地保存。

	存储大小：
	    cookie数据大小不能超过4k。
	    sessionStorage和localStorage 虽然也有存储大小的限制，但比cookie大得多，可以达到5M或更大。
	有效时间：
	    localStorage    存储持久数据，浏览器关闭后数据不丢失除非主动删除数据；
	    sessionStorage  数据在当前浏览器窗口关闭后自动删除。
	    cookie          设置的cookie过期时间之前一直有效，即使窗口或浏览器关闭

<a name='13'></a>
**13、iframe有哪些缺点？**  


	1，iframe会阻塞主页面的Onload事件；  
	2，搜索引擎的检索程序无法解读这种页面，不利于SEO；  
	3，iframe和主页面共享连接池，而浏览器对相同域的连接有限制，所以会影响页面的并行加载； 
	使用iframe之前需要考虑这两个缺点。如果需要使用iframe，最好是通过javascript
	动态给iframe添加src属性值，这样可以可以绕开以上两个问题。

<a name='14'></a>
**14、如何实现浏览器内多个标签页之间的通信?**

	 
	 调用localstorge、cookies等本地存储方式

<a name='15'></a>
**15、如何使用websocket？如何兼容低浏览器？**  


	Adobe Flash Socket 、 ActiveX HTMLFile (IE) 、 基于 multipart 编码发送 XHR 、 基于长轮询的 XHR

<a name='16'></a>
**16、HTML5的form如何关闭自动完成功能？**  


	给不想要提示的 form 或下某个input 设置为 autocomplete=off。

<a name='17'></a>
**17、什么叫优雅降级和渐进增强？**  


	1，优雅降级：Web站点在所有新式浏览器中都能正常工作，如果用户使用的是老式浏览器，则代码会检查以确认它们是否能正常工作。由于IE独特的盒模型布局问题，
	针对不同版本的IE的hack实践过优雅降级了,为那些无法支持功能的浏览器增加候选方案，	使之在旧式浏览器上以某种形式降级体验却不至于完全失效.  

	2，渐进增强：从被所有浏览器支持的基本功能开始，逐步地添加那些只有新式浏览器才支持的功能,向页面增加无害于基础浏览器的额外样式和功能的。
	当浏览器支持时，它们会自动地呈现出来并发挥作用。

<a name='xx'></a>
**18、了解HTML5中的download属性**  

	<a href="http://www.zhangxinxu.com/wordpress/2016/04/know-about-html-download-attribute/">了解HTML5中的download属性</a>

<a name='xx'></a>
**xx、**  





[回顶部](#回顶部)