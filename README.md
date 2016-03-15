

## 前端面试题目总结

   之前在找工作找的资料都是学长们用word的形式保存下来的，觉得非常的不方便。这其中会包含一些常问的面试题，以及一些公司的面试题。希望有所帮助。

[TOC]

###提示与建议

* 拥有一颗强大无比的内心，保持自信，无论何时何地都要相信自己，不要放弃。

* 有一份用心、精致的简历。

* 在自己总结的学习中，对于一个问题最好理清思路这样面试的时候更加有条理。最好学会发散思维，联系知识点。
* 可以从以下几个方面来回答。是什么！！！优点！！缺点！（基本上从这几个方面入手，面试官）

### 前端
以下两个问题很关键，这将是一条很长的路...

*  为什么选择前端？
*  前端是什么？

### 简历

* [简历建议](http://mp.weixin.qq.com/s?__biz=MzAxODE2MjM1MA==&mid=402642996&idx=1&sn=1bdd4498df7bb4d13e58e0602104658f&scene=0#wechat_redirect)

  一些细节点注意一下。

###  看书
其实大部分的知识点都是书中的，而且书里面更加的详细，更能系统性地归纳自己的知识体系。

[前端书籍](http://pan.baidu.com/s/1jGhGikY) 提取码：h862


### HTML

1. HTML5 ，以及与html的差别
        
        1. 语义化标签
        2. 支持视频和音频
        3. Doctype类型－简单，它能在每一个浏览器中正常工作即使是名声狼藉的IE6。
        4. 离线存储 － localStorage和sessionStorage
        5. 互动效果
            a. canvas
            b. 更多API支持更好的用户体验－ 拖拽、地图、利用Native
        6. 丰富的表单控件 如 calendar、date、time、email、url、search
        7. 移动端－摆脱对平台依赖

2. doctype(文档类型) 的作用是什么

          现代浏览器包括不同的呈现模式，目的是既支持遵循标准的网页，也支持为老式浏览器而设计的网页。其中， Standards （标准）模式（也就是严格呈现模式）用于呈现遵循最新标准的网页，而 Quirks （包容）模式（也就是松散呈现模式或者兼容模式）用于呈现为传统浏览器而设计的网页。另外，注意Mozilla/Netscape 6新增了一种 Almost Standards （近似标准）模式，用于支持为标准的某个老版本而设计的网页。
        
          doctype声明指出阅读程序应该用什么规则集来解释文档中的标记。在Web文档的情况下，“阅读程序”通常是浏览器或者校验器这样的一个程序，“规则”则是W3C所发布的一个文档类型定义（DTD）中包含的规则。

3. localStorage和sessionStorage

          localStorage有效期为永久，sessionStorage有效期为顶层窗口关闭前同源文档可以读取并修改localStorage数据，sessionStorage只允许同一个窗口下的文档访问，如通过iframe引入的同源文档。
        
         Storage对象通常被当做普通javascript对象使用：通过设置属性来存取字符串值，也可以通过setItem(key, value)设置，getItem(key)读取，removeItem(key)删除，clear()删除所有数据，length表示已存储的数据项数目，key(index)返回对应索引的key


    代码如下：

        localStorage.setItem('x', 1); // storge x->1
        localStorage.getItem('x); // return value of x
    
        // 枚举所有存储的键值对
        for (var i = 0, len = localStorage.length; i < len; ++i ) {
            var name = localStorage.key(i);
            var value = localStorage.getItem(name);
        }
    
        localStorage.removeItem('x'); // remove x
        localStorage.clear();  // remove all data
    

3. 应用程序存储和离线web应用
        
        HTML5新增应用程序缓存，允许web应用将应用程序自身保存到用户浏览器中，用户离线状态也能访问。 1.为html元素设置manifest属性:<html manifest="myapp.appcache">，其中后缀名只是一个约定，真正识别方式是通过text/cache-manifest作为MIME类型。所以需要配置服务器保证设置正确 2.manifest文件首行为CACHE MANIFEST，其余就是要缓存的URL列表，每个一行，相对路径都相对于manifest文件的url。注释以#开头 3.url分为三种类型：CACHE:为默认类型。NETWORK：表示资源从不缓存。 FALLBACK:每行包含两个url，第二个URL是指需要加载和存储在缓存中的资源， 第一个URL是一个前缀。任何匹配该前缀的URL都不会缓存，如果从网络中载入这样的URL失败的话，就会用第二个URL指定的缓存资源来替代。以下是一个文件例子：

        CACHE MANIFEST
        
        CACHE:
        myapp.html
        myapp.css
        myapp.js
        
        FALLBACK:
        videos/ offline_help.html
        
        NETWORK:
        cgi/

### CSS
    
1. 盒子模型
        
        标准盒子模型：盒子模型范围包括了margin\border\padding\content.但content(width)不包括其他部分。

        IE的盒子模型的content(width)包括了border和padding

        目前css3中属性box-sizing可以解决IE7以上的问题。
        
         重新定义盒子大小，解决盒模型在不同的浏览器中表现不一致的问题。

        box-sizing: content-box | border-box;
        content-box :  定义的width和height就直接是内容的宽度
        border-box: 内容的宽度是 width -边框的宽度－padding

2. CSS定位
    * 定位机制
        
            CSS 有三种基本的定位机制：普通流、浮动和绝对定位。
            普通流：元素的位置由它在HTML中的位置决定的。
            块级框：从上到下，一个接一个，垂直距离由框的垂直空白边决定的
            行内框：水平布置。可使用水平填充，边框可调节水平间距。
            
    * position属性
        * 相对定位的盒子仍在标准流中，相对于它原本的位置，通过偏移（left、right）指定的距离，到达新的位置。它对父块没有任何影响。 
        * 使用绝对定位的盒子以它的“最近”的一个“已经定位”的“祖先元素”为基准进行偏移。如果没有已经定位的祖先元素，那么会以浏览器窗口为基准进行定位。

3. 元素选择器，优先级及匹配原理
    [选择器种类详解](http://www.uisdc.com/css-selector)
        
        css匹配原理
            从最右边的选择符开始向左进行匹配规则。只要当前选择符的左边还有其他选择符，样式系统就会继续向左移动，直到找到和规则匹配的元素，或者因为不匹配而退出。所以在使用less的时候要防止层叠过多。
            
        css权重
            通配选择符的权值 0,0,0,0
            标签的权值为 0,0,0,1
            类的权值为 0,0,1,0
            属性选择的权值为 0,0,1,1(0,0,1,0) 
            伪类选择的权值为 0,0,1,0
            伪对象选择的权值为 0,0,0,1
            ID的权值为 0,1,0,0
            important的权值为最高 1,0,0,0
            
        使用的规则也很简单，就是 选择器的权值加到一起，大的优先；如果权值相同，后定义的优先 

        从上面我们可以得出两个关键的因素：
            1.权值的大小跟选择器的类型和数量有关
            2.样式的优先级跟样式的定义顺序有关

        总结：比较同一级别的个数，数量多的优先级高，如果相同即比较下一级别的个数 ，至于各级别的优先级，大家应该已经很清楚了，就是：

        !important > 内联 > ID > 类 > 标签 | 伪类 | 属性选择 > 伪对象 > 继承 > 通配符 通配符 > 继承
    
        ID选择器的效率是最高，而伪类选择器的效率则是最低

4. Css水平居中
        
        基础布局对以后的开发很有作用。

        1. 自动空白边居中
            缺点：IE5/6不支持，需要hack，并需要对两个元素添加样式
            
            <body> <div id="wrapper"> </div></body>
            
            body{
                text-align: center; /*text-align:center让IE中的元素居中*/
                min-width: 760px; 
            }
            .wrapper{
                margin: 0 auto;
                width: 720px;
                text-align: left;       /* 防止继承父类 */
            }

        2. 使用定位和负值空白边
            
            .wrapper{
                position: relative;
                width: 720px;
                left: 50%;
                margin-left: -360px;
                //对应的垂直居中也好处理了
                top: 50%;
            }
            
        3. 神奇的弹性盒子 flex
        
            IE10+，Android2.1+ ,IOS safire3.2(添加-webkit-)兼容，所以目前移动端可以大量使用。
        
            body{
                display: flex;
                justify-content: center;  //水平居中
                //垂直居中
                align-items: center;   //当然需要设置容器的高度值
            }


5. BFC

        BFC(box , formatting context)，块级格式化上下文，一个创建了新的BFC的盒子是独立布局的，盒子里面的子元素的样式不会影响到外面的元素。在同一个 BFC 中的两个毗邻的块级盒在垂直方向（和布局方向有关系）的 margin 会发生折叠。它决定了元素如何对其内容进行布局，以及与其他元素的关系和相互作用。

        BFC布局规则

        1.内部的Box会在垂直方向，一个接一个地放置。
        2.Box垂直方向的距离由margin决定。属于同一个BFC的两个相邻Box的margin会发生重叠
        3.每个元素的margin box的左边， 与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。
        4.BFC的区域不会与float box重叠。(所以有左边宽度自适应)
        5.BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此。
        6.计算BFC的高度时，浮动元素也参与计算

            <b>哪些元素会触发BFC</b>
            根元素
            float属性不为none
            position为absolute或fixed
            display为    inline-block, table-cell, table-caption, flex, inline-flex
            overflow不为visible

            <b>IE如何解决？Layout </b> 
                position:absolute;
                float: left|right;
                display: inline-block;
                width: value;
                height: value;
                zoom:value(非normal);  //通常zoom:1;


        具有以上优点，BFC实际中的作用
            
            自适应布局、清除浮动、防止margin重叠。

6. 布局问题
        
      [移动端高清、多屏适配方案](http://www.html-js.com/article/Mobile-terminal-H5-mobile-terminal-HD-multi-screen-adaptation-scheme%203041)
        
        1）响应式布局原理
           检测设备，根据不同的设备采用不同的css，而且css都是采用的百分比的，而不是固定的宽度。
           因为大屏幕的移动设备越来越普及。而自适应布局已经无法胜任各种浏览需求。响应式设计的目的是尽可能以最好的布局显示您的数据，以实现用户友好的 Web 页面。
           现在CSS3有了个更为实用的 media query。而移动终端的浏览器（都是基于webkit内核的浏览器）基本已经完全支持了css3.他可以为你获取各种终端的数据。
           栅栏系统（响应式）
           响应式图片
           浏览器获取用户终端的屏幕尺寸、分辨率逻辑处理后输出适应的图片，如屏幕分辨率320*480，那么我们匹配给它的是宽度应小于320px的图片。如果终端屏幕的DPI(device pixels)DPI详解值很高，也就是高清屏，那么我们就得输出2倍分辨率的图形(宽:640px)；以保证在高清屏下图形的清晰度。各种移动终端的屏幕参数可通过 http://screensiz.es/phone查询。
            解决方案：响应式图形的草案：新定义标签<picture>。
            

        高清：通常指的是分辨率高，如iphone6的dpr=2,6plus的dpr=3。
    
        2）静态、自适应、流式、响应式四种网页布局有什么区别
    
           自适应布局（Adaptive Layout）
              自适应布局（Adaptive）的特点是分别为不同的屏幕分辨率定义布局。布局切换时页面元素发生改变，但在每个布局中，页面元素不随窗口大小的调整发生变化。
              你可以把自适应布局看作是静态布局的一个系列。
    
           流式布局（Liquid Layout）
              流式布局（Liquid）的特点（也叫"Fluid") 是页面元素的宽度按照屏幕进行适配调整，主要的问题是如果屏幕尺度跨度太大，那么在相对其原始设计而言过小或过大的屏幕上不能正常显示。
    
           响应式布局（Responsive Layout）
              分别为不同的屏幕分辨率定义布局，同时，在每个布局中，应用流式布局的理念，即页面元素宽度随着窗口调整而自动适配。
              把响应式布局看作是流式布局和自适应布局设计理念的融合
    
7. CSS3新特性

        选择器，文本、多列布局、渐变效果、css盒子、边框、背景、动画、转换


8. CSSHack
        
        1.什么是CSS hack
          由于不同厂商的流览器或某浏览器的不同版本（如IE6-IE11,Firefox/Safari/Opera/Chrome等），对CSS的支持、解析不一样，导致在不同浏览器的环境中呈现出不一致的页面展现效果。这时，我们为了获得统一的页面效果，就需要针对不同的浏览器或不同版本写特定的CSS样式，我们把这个针对不同的浏览器/不同版本写相应的CSS code的过程，叫做CSS hack!

        2.方式
            1).一般是针对IE浏览器处理
                    只在IE下生效
                    <!--[if IE]>
                    这段文字只在IE浏览器显示
                    <![endif]-->
                    
                    只在IE6下生效
                    <!--[if IE 6]>
                    这段文字只在IE6浏览器显示
                    <![endif]-->
                    
                    只在IE6以上版本生效
                    <!--[if gte IE 6]>
                    这段文字只在IE6以上(包括)版本IE浏览器显示
                    <![endif]-->
                    
                    只在IE8上不生效
                    <!--[if ! IE 8]>
                    这段文字在非IE8浏览器显示
                    <![endif]-->
                    
                    非IE浏览器生效
                    <!--[if !IE]>
                    这段文字只在非IE浏览器显示
                    <![endif]-->

    2).类内属性前缀法

    | hack | 写法 |
    |------|------|
    | *    |*color|
    | +    |+color |
    |-     |-color |
    |_     |_color |
    | #    |#color |
    |\0     |color:red\0 |
    |\9\0  |color:red\9\0 |
    |!important|color:blue !important;color:green; |


9. link与@import的区别
        
        1. link是HTML方式， @import是CSS方式
        2. link最大限度支持并行下载，@import过多嵌套导致串行下载，出现FOUC
        3. link可以通过rel="alternate stylesheet"指定候选样式
        4. 浏览器对link支持早于@import，可以使用@import对老浏览器隐藏样式
        5. @import必须在样式规则之前，可以在css文件中引用其他文件
        总体来说：link优于@import

10. display 属性
      主要把以下值区别开
      
         display: inline | block | inline-block | inherit ;
        
        1.inline
            a) 元素显示方式："文本方式"，1个挨着1个，不独自占有1行；高，行高及顶和底边距不可改变；宽度就是它的文字或图片的宽度，不可改变。
            
            b) 内嵌的元素也必须是内联元素：如<a></a>,不能在里面嵌入<div></div>等块级元素
            
            c) 常用的标签有：<a>、<input>、<label>、<img>
        
        2.block
        
            a) 元素显示方式：每个元素独自占有1行，相当于前后都带有换行符；
            b) 内嵌的元素可以是内联或块级元素；
            c) 常用的元素有：<h1>~<h6>、<div>、<hr>等等；

        3.inline-block(IE8+)
            对象呈递为内联对象，但是对象的内容作为块对象呈递。旁边的内联对象会被呈递在同一行内，允许空格
            
11. display: none;与visibility: hidden;的区别
        
        共性： 都能隐藏元素
        特性： 
            1. display:none;会让元素完全从渲染树中消失，渲染的时候不占据任何空间；visibility: hidden;不会让元素从渲染树消失，渲染师元素继续占据空间，只是内容不可见
            2. display: none;是非继承属性，子孙节点消失由于元素从渲染树消失造成，通过修改子孙节点属性无法显示；visibility: hidden;是继承属性，子孙节点消失由于继承了hidden，通过设置visibility: visible;可以让子孙节点显式
            3. 修改常规流中元素的display通常会造成文档重排。修改visibility属性只会造成本元素的重绘。
            4. 读屏器不会读取display: none;元素内容；会读取visibility: hidden;元素内容

12. CSS reset
    
        浏览器样式重置。HTML标签在浏览器中都有默认的样式，例如p标签有上下边距，strong标签有字体加粗样式等。不同浏览器的默认样式之间存在差别，例如ul默认带有缩进样式，在IE下，它的缩进是由margin实现的，而在Firefox下却是由padding实现的。开发时浏览器的默认样式可能会给我们带来多浏览器兼容性问题，影响开发效率。现在很流行的解决方法是一开始就将浏览器的默认样式全部覆盖掉，这就是CSS reset。
        
        YUI为我们提供了一个很好的CSS reset，可以直接下载使用，这段代码很成熟，推荐大家使用。YUI的CSS reset主要做了下面几点：
        •   白色背景，黑色字体
        •   margin和padding设为0
        •   去掉table的边框
        •   去掉列表样式（ol，ul，dl）
        •   所有文字字号设为100%
        •   font-style和font-weight设为normal
        •   更好（但不完全）的表格字体继承
        •   减小sup和sub对line-height的影响


13. 瀑布流
    
        实现方式：
        1. 传统多列浮动
            *  各列固定宽度，并且左浮动；
            *  一列中的数据块为一组，列中的每个数据块依次排列即可；
            *  更多数据加载时，需要分别插入到不同的列上；
            优点:
                布局简单，应该说没啥特别的难点；
                不用明确知道数据块高度，当数据块中有图片时，就不需要指定图片高度。
            缺点:
                列数固定，扩展不易，当浏览器窗口大小变化时，只能固定的x列，如果要添加一列，很难调整数据块的排列；
                滚动加载更多数据时，还要指定插入到第几列中，还是不方便。
    
        2. CSS3 定义,多列布局
    
                #container {
                        -webkit-column-count: 5；
                        /*-webkit-column-gap: 10px；
                        -webkit-column-rule: 5px solid #333；
                        -webkit-column-width: 210px；*/
                
                        -moz-column-count: 5；
                        /*-moz-column-gap: 20px；
                        -moz-column-rule: 5px solid #333；
                        -moz-column-width: 210px；*/
                
                        column-count: 5；
                        /*column-gap: 10px；
                        column-rule: 5px solid #333；
                        column-width: 210px；*/
                    }

            column-count 为列数； column-gap 为每列间隔距离； column-rule 为间隔边线大小； column-width 为每列宽度； 当只设置 column-width 时，浏览器窗口小于一列宽度时，列中内容自动隐藏； 当只设置 column-count 时，平均计算每列宽度，列内内容超出则隐藏； 都设了 column-count 和column-width，浏览器会根据 count 计算宽度和 width 比较，取大的那个值作为每列宽度，然后当窗口缩小时，width 的值为每列最小宽度。

        优点:
            直接 CSS 定义，最方便了；
            扩展方便，直接往容器里添加内容即可。
        缺点:
            只有高级浏览器中才能使用；
            还有一个缺点，他的数据块排列是从上到下排列到一定高度后，再把剩余元素依次添加到下一列，这个本质上就不一样了；
            鉴于这两个主要缺点，注定了该方法只能局限于高端浏览器，而且，更适合于文字多栏排列。

        3.绝对定位（最优方案）
            方便添加数据内容，窗口变化，列数/数据块会自动调整
            缺点:
                需要实现知道数据块高度，如果其中包含图片，需要知道图片高度；
                JS 动态计算数据块位置，当窗口缩放频繁，可能会狂耗性能。


14. 什么是FOUC?如何避免

        Flash Of Unstyled Content：用户定义样式表加载之前浏览器使用默认样式显示文档，用户样式加载渲染之后再从新显示文档，造成页面闪烁。同时加载css文件会阻塞文件下载，在FF下，添加<script> </script>(中间有空格)

        解决方法：把样式表放到文档的head

15. 渐进增强和优雅降级
    
        渐进增强 ：针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。

        优雅降级 ：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。
    
### JavaScript
推荐：[javascript秘密花园](http://bonsaiden.github.io/JavaScript-Garden/zh/#core.undefined)    
    
1. 数据类型

        基础数据类型：null、undefined、boolean、string、number
        引用数据类型：Object 、Array 、Date、RegExp 、Function、自定义对象

2. undefined与null
    
        JavaScript 有两个表示‘空’的值，其中比较有用的是 undefined。

        undefined 的值

        undefined 是一个值为 undefined 的类型。

        这个语言也定义了一个全局变量，它的值是 undefined，这个变量也被称为 undefined。 但是这个变量不是一个常量，也不是一个关键字。这意味着它的值可以轻易被覆盖。

        ES5 提示: 在 ECMAScript 5 的严格模式下，undefined 不再是 可写的了。 但是它的名称仍然可以被隐藏，比如定义一个函数名为 undefined。
        下面的情况会返回 undefined 值：

        1.访问未修改的全局变量 undefined。
        2.由于没有定义 return 表达式的函数隐式返回。
        3.return 表达式没有显式的返回任何内容。
        4.访问不存在的属性。
        5.函数参数没有被显式的传递值。
        6.任何被设置为 undefined 值的变量。
        7.处理 undefined 值的改变
    
        由于全局变量 undefined 只是保存了 undefined 类型实际值的副本， 因此对它赋新值不会改变类型 undefined 的值。
        
        然而，为了方便其它变量和 undefined 做比较，我们需要事先获取类型 undefined 的值。
        
        为了避免可能对 undefined 值的改变，一个常用的技巧是使用一个传递到匿名包装器的额外参数。 在调用时，这个参数不会获取任何值。
        
        var undefined = 123;
        (function(something, foo, undefined) {
            // 局部作用域里的 undefined 变量重新获得了 `undefined` 值
        
        })('Hello World', 42);
        另外一种达到相同目的方法是在函数内使用变量声明。
        
        var undefined = 123;
        (function(something, foo) {
            var undefined;
            ...
        
        })('Hello World', 42);
        这里唯一的区别是，在压缩后并且函数内没有其它需要使用 var 声明变量的情况下，这个版本的代码会多出 4 个字节的代码。
    
        null 的用处
        
        JavaScript 中的 undefined 的使用场景类似于其它语言中的 null，实际上 JavaScript 中的 null 是另外一种数据类型。
        
        它在 JavaScript 内部有一些使用场景（比如声明原型链的终结 Foo.prototype = null），但是大多数情况下都可以使用 undefined 来代替。

3. 创建对象-面向对象

        //1.对象字面量
        var newObject1 =  {};
    
        //原型只能是一个对象或者 null
        var newObject2 = Object.create( null ); //null不能少！！！
        
        //构造器模式
        var newObject3 = new Object();
        newObject.key = " Hello js ";
        newObject[ "key" ] = "hello js";
        
        //Object.defineProperty与Object.defineProperties
        Object.defineProperty ( obj , key , value ); ==> obj[key] = value;
        Object.defineProperties( obj , {
    
            "key" : {
                value : 1
            },
            "anotherkey" : {
                value : 2
            }
        });
    
4.  继承

     [js继承方式](https://segmentfault.com/a/1190000002440502)

        1、原型链继承
        2、借用构造函数继承
        3、组合继承(原型+借用构造)
        4、原型式继承
        5、寄生式继承
        6、寄生组合式继承

5.  闭包

        闭包是在某个作用域内定义的函数，它可以访问这个作用域内的所有变量。闭包作用域链通常包括三个部分：
    
        * 函数本身作用域。
        * 闭包定义时的作用域。
        * 全局作用域。
    
        闭包常见用途：
    
        * 创建特权方法用于访问控制
        * 事件处理程序及回调
        * 模块化代码，减少全局污染

        缺点：
            1）由于闭包会使得函数中的变量都被保存在内存中，内存消耗很大，所以不能滥用闭包，否则会造成网页的性能问题，在IE中可能导致内存泄露。解决方法是，在退出函数之前，将不使用的局部变量全部删除。
            2）闭包会在父函数外部，改变父函数内部变量的值。所以，如果你把父函数当作对像（object）使用，把闭包当作它的公用方法（Public Method），把内部变量当作它的私有属性（private value），这时一定要小心，不要随便改变父函数内部变量的值。


6. 模块化
    
        使用模块化的原因？恼人的命名冲突,烦琐的文件依赖
        通过匿名函数的形式来模仿模块化
        
        (function(){
            //块级作用域
        })( );

        对象形式
         var module1 = new Objec({
            name : 'xhay',
            m1 : function(){
                ...
            },
            m2 : function(){
                ...
            }
            return{
                m1:m1,
                m2:m2
            }
        });


        可扩展的写法
        var module1 = (function(mod){
            mod.m3 = function(){
                ...
            }
            return mod；
        })(window.module1||{});

7. CMD 与AMD & CommonJs
        
    [AMD 规范](https://github.com/amdjs/amdjs-api/wiki/AMD)
    [CMD规范](https://link.zhihu.com/?target=https://github.com/seajs/seajs/issues/242)
        
          AMD 是 RequireJS 在推广过程中对模块定义的规范化产出。
          CMD 是 SeaJS 在推广过程中对模块定义的规范化产出。
          类似的还有 CommonJS Modules/2.0 规范，是 BravoJS 在推广过程中对模块定义的规范化产出。还有不少⋯⋯
          这些规范的目的都是为了 JavaScript 的模块化开发，特别是在浏览器端的。
          目前这些规范的实现都能达成浏览器端模块化开发的目的。
          
          commonJs是应用在NodeJs，是一种同步的模块机制.
            大致写法：
                var firstModule = require("firstModule");
                //your code...
                module.export = anotherModule 
           npm成为主流的JavaScript组件发布平台，也越来越多会依赖。 

           
        区别：
    
        1. 对于依赖的模块，AMD 是提前执行，CMD 是延迟执行。不过 RequireJS 从 2.0 开始，也改成可以延迟执行（根据写法不同，处理方式不同）。CMD 推崇 as lazy as possible.
    
        2. CMD 推崇依赖就近，AMD 推崇依赖前置。看代码：
    
            // CMD
            define(function(require, exports, module) {
                var a = require('./a')
                a.doSomething()
                // 此处略去 100 行
                var b = require('./b') // 依赖可以就近书写
                b.doSomething()
                // ... 
            })
            
                // AMD 默认推荐的是
            define(['./a', './b'], function(a, b) { // 依赖必须一开始就写好
                a.doSomething()
                // 此处略去 100 行
                b.doSomething()
                ...
            }) 
    
        虽然 AMD 也支持 CMD 的写法，同时还支持将 require 作为依赖项传递，但 RequireJS 的作者默认是最喜欢上面的写法，也是官方文档里默认的模块定义写法。
    
    
        3. AMD 的 API 默认是一个当多个用，CMD 的 API 严格区分，推崇职责单一。比如 AMD 里，require 分全局 require 和局部 require，都叫 require。CMD 里，没有全局 require，而是根据模块系统的完备性，提供 seajs.use 来实现模块系统的加载启动。CMD 里，每个 API 都简单纯粹。
    



8. 原型链
    
        在 javaScript 中，每个对象都有一个指向它的原型（prototype）对象的内部链接。这个原型对象又有自己的原型，直到某个对象的原型为 null 为止（也就是不再有原型指向），组成这条链的最后一环。这种一级一级的链结构就称为原型链（prototype chain）。

9. 作用域与作用域链
            
          简单的说，作用域就是变量与函数的可访问范围，即作用域控制着变量与函数的可见性和生命周期。在JavaScript中，变量的作用域有全局作用域和局部作用域两种。
    
        全局作用域
        （1）最外层函数和在最外层函数外面定义的变量拥有全局作用域。
        （2）所有末定义直接赋值的变量自动声明为拥有全局作用域
        （3）所有window对象的属性拥有全局作用域
        局部作用域
          局部作用域一般只在固定的代码片段内可访问到，最常见的例如函数内部。也为函数作用域。
        
        作用域链
          函数对象和其它对象一样，拥有可以通过代码访问的属性和一系列仅供JavaScript引擎访问的内部属性。其中一个内部属性是[[Scope]]，由ECMA-262标准第三版定义，该内部属性包含了函数被创建的作用域中对象的集合，这个集合被称为函数的作用域链。
        每个执行环境都有一个与之关联的变量对象，而每个函数都有自己的执行环境。

10. 事件模型与实现机制
        

 ![盗图](http://images.cnitblog.com/blog/294743/201312/07132637-3ecf3bb32e3b45968f27d21bf1fe3aa5.png)

        在传递到目标元素后，如果它有子元素并不会停还是会往下传。

       
        事件模型： 原生事件模型、标准事件模型、IE事件模型
        1.基础事件处理
            a).HTML标签的事件
                <div onmouseover = "f(this,event)">
            b).javascript事件处理
                element.onmouseover = function(){}
        2.高级事件
            事件传播：事件冒泡，事件捕获
            标准事件：既能冒泡传播也能捕获传播
                addEventListener("click",f,false/true);
                //可以注册多个事件处理函数
                
            IE事件模型
                只支持事件冒泡传播
                attachEvent("onclick",f);
                同时IE的Event对象是window的全局对象，只有事件发生时可以访问。
                
        事件冒泡是否想起了冒泡算法，即由最具体的元素（文档嵌套最深节点）接收，然后逐步上传至document。
        事件捕获会由最先接收到事件的元素然后传向最里边（我们可以将元素想象成一个盒子装一个盒子，而不是一个积木堆积）
            
        DOM事件流

        DOM2级事件规定事件包括三个阶段：
            ① 事件捕获阶段
            ② 处于目标阶段
            ③ 事件冒泡阶段
        停止冒泡，阻止事件的默认行为
            
        不冒泡的事件：load, change, submit, focus, blur

            

11.  HTML DOM 事件（不同浏览器）


| IE事件    |  标准事件 | 
| :-------- | :--------| 
| srcElement |   target |   
| cancelBubble=false |   stopPropagation() |
| detachEvent("name", fn)|   addEventListener("name", fn ,false) |
| returnValue=false | preventDefault() |



12.  深度克隆函数deepClone与浅克隆

          浅克隆是简单的复制对象，如果对象其中一个属性是引用型变量，就会出现这种情况，因为引用型变量保存的是内存地址。
          深克隆就是在克隆的时候判断一下属性的类型是不是引用型变量，如果是的话就用递归方法让它一层一层进去复制自己
       
        function deepClone(obj) {
            var _toString = Object.prototype.toString;
        
            // null, undefined, non-object, function
            if (!obj || typeof obj !== 'object') {
                return obj;
            }
        
            // DOM Node
            if (obj.nodeType && 'cloneNode' in obj) {
                return obj.cloneNode(true);
            }
        
            // Date
            if (_toString.call(obj) === '[object Date]') {
                return new Date(obj.getTime());
            }
        
            // RegExp
            if (_toString.call(obj) === '[object RegExp]') {
                var flags = [];
                if (obj.global) { flags.push('g'); }
                if (obj.multiline) { flags.push('m'); }
                if (obj.ignoreCase) { flags.push('i'); }
        
                return new RegExp(obj.source, flags.join(''));
            }
        
            var result = Array.isArray(obj) ? [] :
                obj.constructor ? new obj.constructor() : {};
        
            for (var key in obj ) {
                result[key] = deepClone(obj[key]);
            }
        
            return result;
        }
        
        function A() {
            this.a = a;
        }
        
        var a = {
            name: 'qiu',
            birth: new Date(),
            pattern: /qiu/gim,
            container: document.body,
            hobbys: ['book', new Date(), /aaa/gim, 111]
        };
        
        var c = new A();
        var b = deepClone(c);
        console.log(c.a === b.a);
        console.log(c, b);


13. 跨域

*同源策略* 

          所谓同源是指，域名，协议，端口相同。限制了一个源(origin)中加载文本或脚本与来自其它源(origin)中资源的交互方式。
          当一个浏览器的两个tab页中分别打开来 百度和谷歌的页面
          当浏览器的百度tab页执行一个脚本的时候会检查这个脚本是属于哪个页面的，
          即检查是否同源，只有和百度同源的脚本才会被执行。
*JSONP*
    
        原理是：动态插入script标签，通过script标签引入一个js文件，这个js文件载入成功后会执行我们在url参数中指定的函数，并且会把我们需要的json数据作为参数传入。
                由于同源策略的限制，XmlHttpRequest只允许请求当前源（域名、协议、端口）的资源，为了实现跨域请求，可以通过script标签实现跨域请求，然后在服务端输出JSON数据并执行回调函数，从而解决了跨域的数据请求。
            

            function handleResponse(response){
                alert("You’ re at IP address " + response.ip + ", which is in " +
                 response.city + ", " + response.region_name);
            }
            
            var script = document.createElement("script");
            script.src = "http://freegeoip.net/json/?callback=handleResponse";
            document.body.insertBefore(script, document.body.firstChild);


            优点是兼容性好，简单易用，支持浏览器与服务器双向通信。
            缺点是只支持GET请求,JSONP 是从其他域中加载代码执行，安全不能保证。
        
    *Window.name+iframe*

        原理：在一个窗口(window)的生命周期内,窗口载入的所有的页面都是共享一个window.name的，每个页面对window.name都有读写的权限，window.name是持久存在一个窗口载入过的所有页面中的，并不会因新页面的载入而进行重置。
        跨域数据即由iframe的window.name从外域传递到本地域类似src属性，则绕过了跨域。
    
        限制：window.name的值只能是字符串的形式，这个字符串的大小最大能允许2M左右，取决于浏览器， IE和firefox下可以大至32M左右
             
        优点：安全（可以销毁iframe，不被其他域frame js访问），比FIM更快
    
        总结：iframe的src属性由外域转向本地域，跨域数据即由iframe的window.name从外域传递到本地域。巧妙地绕过了浏览器的跨域访问限制，但同时它又是安全操作。


        使用方式：
           a.com/app.html：应用页面。
           a.com/proxy.html：代理文件，一般是一个没有任何内容的html文件，需要和应用页面在同一域下。
           b.com/data.html：应用页面需要获取数据的页面，可称为数据页面。
            

    *通过修改document.domain来跨子域*
    

    *动态创建script*


        原理：浏览器并不禁止在页面中引用其他域的JS文件，并可以自由执行引入的JS文件中的function。可以方便地通过创建script节点的方法来实现完全跨域的通信。
            
        注意：ie只能通过script的readystatechange属性，其它浏览器是script的load事件。以下是部分判断script加载完毕的方法。
    
        js.onload = js.onreadystatechange = function() {        
            if (!this.readyState || this.readyState === 'loaded' || this.readyState === 'complete') {                
                // callback在此处执行                 
                js.onload = js.onreadystatechange = null;       
            }   
        };
        
        扩展： a.使用了Ajax，如何解决跨域问题
        1. 通过修改document.domain和隐藏的IFrame来实现跨域请求。这种方案可能是最简单的一种跨域请求的方案，但是它同样是一种限制最大的方 案。首先，它只能实现在同一个顶级域名下的跨域请求；另外，当在一个页面中还包含有其它的IFrame时，可能还会产生安全性异常，拒绝访问。
    
        2.通过请求当前域 的代理，由服务器 代理去访问另一个域的资源。XMLHttpRequest通过请求本域内的一个服务器资源 ，将要访问的目标资源提供给服务器，交由服务器 去代理访问目标资源。这种方案，可以实现完全的跨域访问，但是开发，请求过程的消费会比较大。
        
        3.jQuery的ajax有jsonp这样的属性可以用来解决跨域的问题。
        
        4. 一个专门用来解决跨域问题的jQuery插件-jquery-jsonp。


14. 内存泄漏
    
        内存泄漏指任何对象在您不再拥有或需要它之后仍然存在。垃圾回收器定期扫描对象，并计算引用了每个对象的其他对象的数量。如果一个对象的引用数量为 0（没有其他对象引用过该对象），或对该对象的惟一引用是循环的，那么该对象的内存即可回收。 setTimeout 的第一个参数使用字符串而非函数的话，会引发内存泄漏。 闭包、控制台日志、循环（在两个对象彼此引用且彼此保留时，就会产生一个循环）
        
        （1）、内存溢出：当你运行一个程序的时候，程序所需要的内存系统无法满足（系统的内存空间不够），造成内存溢出。
        在IE下的JS编程中，以下的编程方式都会造成即使关闭IE也无法释放内存的问题给DOM对象添加的属性是一个对象的引用。
        范例 1：
            var MyObject = {};
            document.getElementById('myDiv').myProp = MyObject;

        解决方法：
            在window.onunload事件中写上: 
                document.getElementById('myDiv').myProp = null;
        
        DOM对象与JS对象相互引用。
        
        范例 2：
            function Encapsulator(element) {
                this.elementReference = element;
                    element.myProp = this;
                }
                new Encapsulator(document.getElementById('myDiv'));
            }
        解决方法：
            在onunload事件中写上: document.getElementById('myDiv').myProp = null;
        给DOM对象用attachEvent绑定事件。

        范例 3：
            function doClick() {}
            element.attachEvent("onclick", doClick);
        解决方法：
            在onunload事件中写上: element.detachEvent('onclick', doClick);

        范例4: 从外到内执行appendChild。这时即使调用removeChild也无法释放。范例：
            var parentDiv = document.createElement("div");
            var childDiv = document.createElement("div");
            document.body.appendChild(parentDiv);
            parentDiv.appendChild(childDiv);
        解决方法：从内到外执行appendChild:
            var parentDiv = document.createElement("div");
            var childDiv = document.createElement("div");
            parentDiv.appendChild(childDiv);
            document.body.appendChild(parentDiv);
        
        范例5：反复重写同一个属性会造成内存大量占用(但关闭IE后内存会被释放)。

        for(i = 0; i < 5000; i++) {
            hostElement.text = "zchubyoyo";
        }
        这种方式相当于定义了5000个属性！
        
        （2）.内存泄漏：当运行程序的时候，系统会按照所需分配给内存，当程序运行之后，这些内存空间没有办法被收回，就是造成了内存的泄漏。
        
        常见的内存溢出--循环引用
        function fun(){
           var element = document.getElementById(“id”);
           element.onclick = function(){
               alert(element.id);
            }
        }
        这个是我们在js中经常写的一个方法，它将导致内存的泄漏，你想到了吗？
        解决方案：
        function fun(){
            var element = document.getElementById(“id”);
            var id = element.id;
            element.onclick = function(){
                    alert(id);
            }
            element = null;
        }
    
    
15. Ajax
    
        1.干掉了Back和History功能，浏览器后退机制的破坏
            解决方式：Gmail (通过创建或使用一个隐藏的IFRAME来重现页面上的变更),它在一个隐藏的IFRAME中进行搜索，然后将搜索结果反映到Ajax元素上，以便将应用程序状态恢复到当时的状态
            缺点：开发成本是非常高的
    
        2.安全问题 
            ajax的逻辑可以对客户端的安全扫描技术隐藏起来，允许黑客从远端服务器上建立新的攻击
    
            优点
            1.页面无刷新，在页面内与服务器通信，给用户的体验非常好
            2.使用异步方式与服务器通信，不需要打断用户的操作
            3.前端和后端负载平衡。减轻服务器的负担，可以最大程度的减少冗余请求，和响应对服务器造成的负担。
    
            Ajax的工作原理相当于在用户和服务器之间加了—个中间层(AJAX引擎),使用户操作与服务器响应异步化。并不是所有的用户请求都提交给服务器,像—些数据验证和数据处理等都交给Ajax引擎自己来做, 只有确定需要从服务器读取新数据时再由Ajax引擎代为向服务器提交请求。
        
        Ajax其核心有JavaScript、XMLHTTPRequest、DOM对象组成，通过XmlHttpRequest（get与post方式）对象来向服务器发异步请求，从服务器获得数据，然后用JavaScript来操作DOM而更新页面。这其中最关键的一步就是从服务器获得请求数据
        
        XMLHttpRequest是ajax的核心机制
        
        ajax所包含的技术 
        大家都知道ajax并非一种新的技术，而是几种原有技术的结合体。它由下列技术组合而成。 
        1.使用CSS和XHTML来表示。 
        2. 使用DOM模型来交互和动态显示。 
        3.使用XMLHttpRequest来和服务器进行异步通信。 
        4.使用javascript来绑定和调用。

16. NodeJs
    
        适用场景：高并发、聊天、实时消息推送

17. jQuery
        
        jquery缺点
            安全问题：由于JavaScript在客户端运行，可能被用于黑客目的。
            冲突问题：有多个插件容易引起冲突。尤其是这些插件依赖相同事件或selector时最为明显。
            插件兼容性。在最新版jQuery版本下，现有插件可能无法正常使用。
            不能向后兼容。每一个新版本不能兼容早期的版本。这可能会影响到开发者已经编写好的代码或插件。
        优点：
        1.强大的选择器
            许开发者使用从CSS1到CSS3几乎所有的选择器或自定义的选择器
        2.DOM操作的封装
            JQuery封装了大量常用的DOM操作，使开发者在编写DOM操作相关程序的时候能够得心应手
        3.不污染顶级变量
             JQuery只建立一个名为JQuery的对象，其所有的函数方法都在这个对象之下。其别名$也可以随时交流控制权，绝对不会污染其他的对象。
        4.链式操作方式
            JQuery中最有特色的莫过于它的链式操作方式——即对发生在同一个JQuery对象上的一组动作，可以直接接连写无需要重复获取对象。这一特点使得JQuery的代码无比优雅。


18.  HTML DOM 操作
        
        （1）创建新节点
              createDocumentFragment()    //创建一个DOM片段
              createElement()   //创建一个具体的元素
              createTextNode()   //创建一个文本节点
        （2）添加、移除、替换、插入
              appendChild()
              removeChild()
              replaceChild()
              insertBefore()
        （3）查找
              getElementsByTagName()    //通过标签名称
              getElementsByName()    //通过元素的Name属性的值
              getElementById()    //通过元素Id，唯一性
              querySelector(".class");  //返回文档中匹配指定的CSS选择器的第一元素
              querySelectorAll(); //返回文档中匹配的CSS选择器的所有元素节点列表
        （4）复制
              importNode(node,deep)//如果为 true，还要递归复制node的所有子孙节点。

19. ajax过程
    
        (1)创建`XMLHttpRequest`对象,也就是创建一个异步调用对象.

        (2)创建一个新的`HTTP`请求,并指定该`HTTP`请求的方法、`URL`及验证信息.
    
        (3)设置响应`HTTP`请求状态变化的函数.
    
        (4)发送`HTTP`请求.
    
        (5)获取异步调用返回的数据.
    
        (6)使用JavaScript和DOM实现局部刷新.
    
    
        var xmlHttp = new XMLHttpRequest();
    
        xmlHttp.open('GET','demo.php','true');
    
        xmlHttp.send()
    
        xmlHttp.onreadystatechange = function(){
    
            if(xmlHttp.readyState === 4 & xmlHttp.status === 200){
    
            }
    
        }
   
   
20. Promise编程
          
          Promise 有四种状态：
                pending: 初始状态, 非 fulfilled 或 rejected.
                fulfilled: 成功的操作.
                rejected: 失败的操作.
                settled: Promise已被fulfilled或rejected，且不是pending
            
         Promise 对象用来进行延迟(deferred) 和异步(asynchronous ) 计算。
        
        如何构造？
            var promise = new Promise(function(resolve, reject) {

                if (...) {  // succeed
        
                    resolve(result);
        
                } else {   // fails
        
                    reject(Error(errMessage));
        
                }
        
            });



21. MVC和MVVM的理解
    
        MVC代表： backboneJs
            Controller/Presenter负责逻辑的处理，Model提供数据，View负 责显示。在MVC中View会从直接Model中读取数据。
            组成部分：
                View 传送指令到 Controller
                Controller 完成业务逻辑后，要求 Model 改变状态
                Model 将新的数据发送到 View，用户得到反馈
        MVVM : AngularJs,Avalon
            是真正将页面与数据逻辑分离的模式，在开发方式上，它是真正将前台代码开发者（JS+HTML）与后台代码开发者分离的模式。
            组成部分Model、View、ViewModel：
                View：UI界面
                ViewModel：它是View的抽象，负责View与Model之间信息转换，将View的Command传送到Model；
                Model：数据访问层

22. ES6了解
        
        语言语法 – 语法解析规则、关键字、语句、声明、运算符等。
        类型 – 布尔型、数字、字符串、对象等。
        原型和继承
        内建对象和函数的标准库 – JSON、Math、数组方法、对象自省方法等。

23.  arguments变量
    
        1.arguments所有函数中都包含的一个局部变量，是一个类数组对象，对应函数调用时的实参。如果函数定义同名参数会在调用时覆盖默认对象
    
        2.arguments[index]分别对应函数调用时的实参，并且通过arguments修改实参时会同时修改实参
    
        3.arguments.length为实参的个数（Function.length表示形参长度）
        4.arguments.callee为当前正在执行的函数本身，使用这个属性进行递归调用时需注意this的变化
        arguments.caller为调用当前函数的函数（已被遗弃）
    
        转换为数组：var args = Array.prototype.slice.call(arguments, 0);
        
### 计算机网络

1. 状态码
[状态码](http://www.w3school.com.cn/tags/html_ref_httpmessages.asp)
    
        1XX：信息状态码
        2XX：成功状态码
        3XX：重定向
        4XX：客户端错误
        5XX: 服务器错误
        
   常见具体状态码
   

| 状态码      |     含义 |   
| :-------- | :------|  
| 100 Continue    |   客户端应当继续发送请求。 |
| 200 OK：    |   请求成功，请求所希望的响应头或数据体将随此响应返回 |
| 202 Accepted   |   客户端应当继续发送请求。 |
| 301 Moved Permanently | 永久移除 | 
| 304 Not Modified(还是要访问服务器)| 客户端有缓冲的文档并发出了一个条件性的请求 |
| 400 Bad Request | 服务器未能理解请求 |
| 401 Unauthorized | 被请求的页面需要用户名和密码 |
| 403 Forbidden    | 对被请求页面的访问被禁止。|
|500 Internal Server Error  | 请求未完成。服务器遇到不可预知的情况。|
|502 Bad Gateway |  请求未完成。服务器从上游服务器收到一个无效的|
|504 Gateway Timeout|   网关超时。 |

         
2. 浏览器访问页面发生了什么－详述
        
        第一步，解析域名，找到主机IP

        （1）浏览器会缓存DNS一段时间，一般2-30分钟不等。如果有缓存，直接返回IP，否则下一步。

        （2）缓存中无法找到IP，浏览器会进行一个系统调用，查询hosts文件。如果找到，直接返回IP，否则下一步。（在计算机本地目录etc下有一个hosts文件，hosts文件中保存有域名与IP的对应解析，通常也可以修改hosts科学上网或破解软件。）

        （3）进行了（1）（2）本地查询无果，只能借助于网络。路由器一般都会有自己的DNS缓存，ISP服务商DNS缓存，这时一般都能够得到相应的IP。如果还是无果，只能借助于DNS递归解析了。

        （4）这时，ISP的DNS服务器就会开始从根域名服务器开始递归搜索，从.com顶级域名服务器，到baidu的域名服务器。

          到这里，浏览器就获得了IP。在DNS解析过程中，常常会解析出不同的IP。比如，电信的是一个IP，网通的是另一个IP。这是采取了智能DNS的结果，降低运营商间访问延时，在多个运营商设置主机房，就近访问主机。电信用户返回电信主机IP，网通用户返回网通主机IP。当然，劫持DNS，也可以屏蔽掉一部分网点的访问，某防火长城也加入了这一特性。

        第二部，浏览器与网站建立TCP连接

          浏览器利用IP直接与网站主机通信。浏览器发出TCP（SYN标志位为1）连接请求，主机返回TCP（SYN，ACK标志位均为1）应答报文，浏览器收到应答报文发现ACK标志位为1，表示连接请求确认。浏览器返回TCP（）确认报文，主机收到确认报文，三次握手，TCP链接建立完成。

        第三部分，浏览器发起GET请求

          浏览器向主机发起一个HTTP-GET方法报文请求。请求中包含访问的URL，也就是http://www.baidu.com/ ，还有User-Agent用户浏览器操作系统信息，编码等。值得一提的是Accep-Encoding和Cookies项。Accept-Encoding一般采用gzip，压缩之后传输html文件。Cookies如果是首次访问，会提示服务器建立用户缓存信息，如果不是，可以利用Cookies对应键值，找到相应缓存，缓存里面存放着用户名，密码和一些用户设置项。

        第四部分，显示页面或返回其他

          返回状态码200 OK，表示服务器可以相应请求，返回报文，由于在报头中Content-type为“text/html”，浏览器以HTML形式呈现，而不是下载文件。

          但是，对于大型网站存在多个主机站点，往往不会直接返回请求页面，而是重定向。返回的状态码就不是200 OK，而是301,302以3开头的重定向码，浏览器在获取了重定向响应后，在响应报文中Location项找到重定向地址，浏览器重新第一步访问即可。

          补充一点的就是，重定向是为了负载均衡或者导入流量，提高SEO排名。利用一个前端服务器接受请求，然后负载到不同的主机上，可以大大提高站点的业务并发处理能力；重定向也可将多个域名的访问，集中到一个站点；由于baidu.com，www.baidu.com会被搜索引擎认为是两个网站，照成每个的链接数都会减少从而降低排名，永久重定向会将两个地址关联起来，搜索引擎会认为是同一个网站，从而提高排名。
    
3. DNS解析过程详解

        1、在浏览器中输入www.example.com域名，操作系统会先检查自己本地的hosts文件是否有这个网址映射关系，如果有，就先调用这个IP地址映射，完成域名解析。 
        
        2、如果hosts里没有这个域名的映射，则查找本地DNS解析器缓存，是否有这个网址映射关系，如果有，直接返回，完成域名解析。 
        
        3、如果hosts与本地DNS解析器缓存都没有相应的网址映射关系，首先会找TCP/ip参数中设置的首选DNS服务器，在此我们叫它本地DNS服务器，此服务器收到查询时，如果要查询的域名，包含在本地配置区域资源中，则返回解析结果给客户机，完成域名解析，此解析具有权威性。 
        
        4、如果要查询的域名，不由本地DNS服务器区域解析，但该服务器已缓存了此网址映射关系，则调用这个IP地址映射，完成域名解析，此解析不具有权威性。
        
        5、如果本地DNS服务器本地区域文件与缓存解析都失效，则根据本地DNS服务器的设置（是否设置转发器）进行查询，如果未用转发模式，本地DNS就把请求发至13组根DNS，根DNS服务器收到请求后会判断这个域名(.com)是谁来授权管理，并会返回一个负责该顶级域名服务器的一个IP。本地DNS服务器收到IP信息后，将会联系负责.com域的这台服务器。这台负责.com域的服务器收到请求后，如果自己无法解析，它就会找一个管理.com域的下一级DNS服务器地址(example.com)给本地DNS服务器。当本地DNS服务器收到这个地址后，就会找example.com域服务器，重复上面的动作，进行查询，直至找到www.example.com主机。 
        
        6、如果用的是转发模式，此DNS服务器就会把请求转发至上一级DNS服务器，由上一级服务器进行解析，上一级服务器如果不能解析，或找根DNS或把转请求转至上上级，以此循环。不管是本地DNS服务器用是是转发，还是根提示，最后都是把结果返回给本地DNS服务器，由此DNS服务器再返回给客户机。

4. cookie及其操作
           
            目前还是很多登陆的方式还是通过cookie的方式来处理的。

            cookie是web浏览器存储的少量数据，最早设计为服务器端使用，作为HTTP协议的扩展实现。cookie数据会自动在浏览器和服务器之间传输。
            通过读写cookie检测是否支持
            cookie属性有名，值，max-age，path, domain，secure；
            cookie默认有效期为浏览器会话，一旦用户关闭浏览器，数据就丢失，通过设置max-age=seconds属性告诉浏览器cookie有效期
            cookie作用域通过文档源和文档路径来确定，通过path和domain进行配置，web页面同目录或子目录文档都可访问
           通过cookie保存数据的方法为：为document.cookie设置一个符合目标的字符串如下
            读取document.cookie获得'; '分隔的字符串，key=value,解析得到结果。
    

            document.cookie = 'name=qiu; max-age=9999; path=/; domain=domain; secure';

            document.cookie = 'name=aaa; path=/; domain=domain; secure';
            // 要改变cookie的值，需要使用相同的名字、路径和域，新的值
            // 来设置cookie，同样的方法可以用来改变有效期
        
            // 设置max-age为0可以删除指定cookie
        
            //读取cookie，访问document.cookie返回键值对组成的字符串，
            //不同键值对之间用'; '分隔。通过解析获得需要的值

5. HTTP请求头了解
        
        HTTP请求信息由3部分组成：
           请求方法URI协议/版本
           请求头(Request Header)
           请求正文
    
        date：请求时间
        expires:过期时间
        
        referer:关联连接
            Referer可以记录访问的来源，统计访问量，可以用来防盗链。
            利用Referer防止图片盗链
            但是referer可以被修改
        1.服务器端修改Referer，通过webClient，直接设置访问可以达到修改目的。
        2.可以使用Fiddler修改Referer。

        If- Modified-Since：与客户端缓存相关，如果有，服务器返回304

6. TCP 三次握手与四次挥手
     
         三次握手：
        第一次握手：客户端发送syn包(syn=x)到服务器，并进入SYN_SEND状态，等待服务器确认；
        
        第二次握手：服务器收到syn包，必须确认客户的SYN（ack=x+1），同时自己也发送一个SYN包（syn=y），即SYN+ACK包，此时服务器进入SYN_RECV状态；
        
        第三次握手：客户端收到服务器的SYN＋ACK包，向服务器发送确认包ACK(ack=y+1)，此包发送完毕，客户端和服务器进入ESTABLISHED状态，完成三次握手。

        握手过程中传送的包里不包含数据，三次握手完毕后，客户端与服务器才正式开始传送数据。理想状态下，TCP连接一旦建立，在通信双方中的任何一方主动关闭连接之前，TCP 连接都将被一直保持下去。

        四次握手

        与建立连接的“三次握手”类似，断开一个TCP连接则需要“四次握手”。
        
        第一次挥手：主动关闭方发送一个FIN，用来关闭主动方到被动关闭方的数据传送，也就是主动关闭方告诉被动关闭方：我已经不 会再给你发数据了(当然，在fin包之前发送出去的数据，如果没有收到对应的ack确认报文，主动关闭方依然会重发这些数据)，但是，此时主动关闭方还可 以接受数据。
        
        第二次挥手：被动关闭方收到FIN包后，发送一个ACK给对方，确认序号为收到序号+1（与SYN相同，一个FIN占用一个序号）。
        第三次挥手：被动关闭方发送一个FIN，用来关闭被动关闭方到主动关闭方的数据传送，也就是告诉主动关闭方，我的数据也发送完了，不会再给你发数据了。
        第四次挥手：主动关闭方收到FIN后，发送一个ACK给被动关闭方，确认序号为收到序号+1，至此，完成四次挥手。

7. CDN
    
          CDN的全称是Content Delivery Network，即内容分发网络。
          构建目的：是使用户可就近取得所需内容，解决 Internet网络拥挤的状况，提高用户访问网站的响应速度。
        
          CDN（内容《对象》，分发《方法》，网络《载体》）
          内容：主要是静态资源，页面，图片，脚本等。
          分发：（主动）去源站抓取数据和提供用户上传的接口，（被动）缓存设备和软件 
          网络：基础（电信），专营（卫通）
          作用：本地cache加速，镜像服务，远程加速，宽带优化，集群抗攻击
        
        Cdn的技术原理
          负载均衡分布，网络传送上利用缓存技术，就近获取资源。
          减少网络中冗余数据的重复传输，使之最小化，将广域传输转为本地或就近访问。互联网上传递的内容，大部分为重复的Web/FTP数据。（Cache服务器具有缓存，优化数据链路性能，大部分为网页对象：（web Page object,html 等页面文件，图片文件。但要通过简单的认证））
        
          多台Cache加速服务器且分布在不同地域，需要通过有效地机制管理Cache网络，引导用户就近访问，全局负载均衡流量。复制到网络“边缘”，缩小“请求点”与”交互点“。
        
        内容发布网络(CDN)是一个经策略性部署的整体系统，包括分布式存储、负载均衡、网络请求的重定向和内容管理４个要件。
        内容服务基于缓存服务器（代理缓存）,离用户只有“一跳”。而（城域网，域内网络快主要是Internet的内容高速缓存到本地，cache放在各POP点上）
        
        工作原理：CDN中间添加了Cache层，然后通过接管DNS来引导数据获得源服务器的数据。
         
        常用的技术手段：高速缓存、镜像服务器。适用于(静态和准动态数据同步)
        
        全局负载均衡DNS通过一组预先定义好的策略，将当时最接近用户的节点地址提供给用户，使用户能够得到快速的服务。
        
        负载均衡设备负责每个节点中各个Cache的负载均衡，保证节点的工作效率；同时，负载均衡设备还负责收集节点与周围环境的信息，保持与全局负载DNS的通信，实现整个系统的负载均衡。
        
        　  高速缓存服务器（Cache）负责存储客户网站的大量信息，就像一个靠近用户的网站服务器一样响应本地用户的访问请求。
        
           简单地说，内容分发网络是一个经策略性部署的整体系统，包括分布式存储、负载均衡、网络请求的重定向和内容管理4个要求，而内容管理和全局的网络流量管理是CDN的核心所在。通过用户就近性和服务器负载的判断，CDN确保内容以一种极为高效的方式为用户的请求提供服务。
        分发服务系统：最基本的工作单元就是Cache设备，cache（边缘cache）负责直接响应最终用户的访问请求，把缓存在本地的内容快速地提供给用户。同时cache还负责与源站点进行内容同步，把更新的内容以及本地没有的内容从源站点获取并保存在本地。Cache设备的数量、规模、总服务能力是衡量一个CDN系统服务能力的最基本的指标
        负载均衡系统：主要功能是负责对所有发起服务请求的用户进行访问调度，确定提供给用户的最终实际访问地址。两级调度体系分为全局负载均衡（GSLB）和本地负载均衡（SLB）。GSLB主要根据用户就近性原则，通过对每个服务节点进行“最优”判断，确定向用户提供服务的cache的物理位置。SLB主要负责节点内部的设备负载均衡。
        使用CDN的好处，优点
            1. 不用担心自己网站访客，在任何时间，任何地点，任何网络运营商，都能快速打开网站。
            2. 各种服务器虚拟主机带宽等采购成本，包括后期运维成本都会大大减少。
            3. 给网站直接带来的好处就是：流量，咨询量，客户量，成单量，都会得到大幅度提升。


8. HTTPS
    
        HTTPS（全称：Hypertext Transfer Protocol over Secure Socket Layer），是以安全为目标的HTTP通道，简单讲是HTTP的安全版。即HTTP下加入SSL层，HTTPS的安全基础是SSL，因此加密的详细内容请看SSL。
        SSL的工作原理
            握手协议（Handshake protocol）
            记录协议（Record protocol）
            警报协议（Alert protocol）
        
9. HTTP/2.0
        
        相比HTTP1.1优点集中在：
            异步连接多路复用
            HEAD 压缩
            压缩HTTP头；
            服务器推送流（即Server Push技术）；
            优先级请求
            请求/响应管线化；
10. cookie 和session 的区别
    
        1、cookie数据存放在客户的浏览器上，session数据放在服务器上。
        2、cookie不是很安全，别人可以分析存放在本地的COOKIE并进行COOKIE欺骗
        3、session会在一定时间内保存在服务器上。当访问增多，会比较占用你服务器的性能考虑到减轻服务器性能方面，应当使用COOKIE。
        4、单个cookie保存的数据不能超过4K，很多浏览器都限制一个站点最多保存20个cookie。
        5、所以个人建议：
           将登陆信息等重要信息存放为SESSION
           其他信息如果需要保留，可以放在COOKIE中

11. 网络七层模型
        
        物理层：通过媒介传输比特,确定机械及电气规范（比特Bit）
        数据链路层：将比特组装成帧和点到点的传递（帧Frame）
        网络层：负责数据包从源到宿的传递和网际互连（包PackeT）
        传输层：提供端到端的可靠报文传递和错误恢复（段Segment）
        会话层：建立、管理和终止会话（会话协议数据单元SPDU）
        表示层：对数据进行翻译、加密和压缩（表示协议数据单元PPDU）
        应用层：允许访问OSI环境的手段（应用协议数据单元APDU）
        
### 前端性能
    
1.雅虎14条优化原则，《高性能网站建设指南》以及《高性能网站建设进阶指南》中提到的优化点做一次梳理，按照优化方向分类，可以得到这样一张表格。


| 优化方向   |  优化手段 |                                 
| :-----------------: | :----------------------|   
 | 请求数量 | 合并脚本和样式表，CSS Sprites，拆分初始化负载，划分主域|
    | 请求带宽 | 开启GZip，精简JavaScript，移除重复脚本，图像优化  |
    | 缓存利用 | 使用CDN，使用外部JavaScript和CSS，添加Expires头，减少DNS查找，配置ETag，使AjaX可缓存 |
    | 页面结构 |将样式表放在顶部，将脚本放在底部，尽早刷新文档的输出|
    | 代码校验 | 代码校验 |
        
        
        静态资源版本更新与缓存

        虽然我们处理文件缓存的问题，但是要试想一下如果文件修改了。客户端应该怎么解决？

        最有效的解决方案是修改其所有链接，这样，全新的请求将从原始服务器下载最新的内容。修改其所有链接？ 对，可以使用版本控制。静态资源文件版本更新是“覆盖式”的，
    
        <script type="text/javascript" src="a.js?v=0.0.1"></script>

        但是如果通过这样叠加版本号(v)的方式，如果发布两版面临的问题。
        
        1）.如果先覆盖index.html，后覆盖a.js，用户在这个时间间隙访问，会得到新的index.html配合旧的a.js的情况，从而出现错误的页面。
        2）.如果先覆盖a.js，后覆盖index.html，用户在这个间隙访问，会得到旧的index.html配合新的a.js的情况，从而也出现了错误的页面。


        基于文件内容的hash版本冗余机制。

        工程师写法： <script src="a.js"></script>>
        线上代码：   <script scr="a_844583j.js"></script>

        后面的hash值是通过a.js的文件内容hash运算得到。类似github的版本控制

        好处：
       
            1）.线上的a.js不是同名文件覆盖，而是文件名+hash的冗余，所以可以先上线静态资源，再上线html页面，不存在间隙问题；
            2）.遇到问题回滚版本的时候，无需回滚a.js，只须回滚页面即可；
            3）.由于静态资源版本号是文件内容的hash，因此所有静态资源可以开启永久强缓存，只有更新了内容的文件才会缓存失效，缓存利用率大增；
            4）.修改静态资源后会在线上产生新的文件，一个文件对应一个版本，因此不会受到构造CDN缓存形式的攻击


其中由于移动端的特殊性，我们需要考虑的性能方面的东西比较多。



2.  图片懒加载
          
        实现大致思路：
        模版渲染时,不赋值src
        插入DOM树时进行可视区域计算
        如果图片在可视区内,赋值src
        如果图片在可视区外,留着scroll 处理
        
        例子：有很多基于jquery或者zepto来进行开发的，由于项目中依赖了这两个库。
    
    [基于jquery和zepto的load插件](https://github.com/jieyou/lazyload/blob/master/lazyload.js)

3. 图片预加载
    
        实现预载的方法非常多，可以用CSS(background)、JS(Image)、HTML(<img />)都可以。常用的是new Image();，设置其src来实现预载，再使用onload方法回调预载完成事件。只要浏览器把图片下载到本地，同样的src就会使用缓存，这是最基本也是最实用的预载方法。当Image下载完图片头后，会得到宽和高，因此可以在预载前得到图片的大小(方法是用记时器轮循宽高变化)。
常用方式：

        function loadImage(url,callback) {     
            var img = new Image();     
            img.src = url;     
            img.onload = function(){         
                document.appendChild(img); //添加到document中        
                callback.call(img);     
            }
         }

    
      
        改进：处理部分浏览器的缓存。提前获取图片大小，Image中有complete但是必须加载完后才能使用。所以使用javascript定时侦测图片的尺寸状态便可得知图片尺寸就绪的状态。
    
        缺点：由于前期加载资源，所以会增加服务前端的压力


4. 域名收敛

          因为DNS使用UDP不稳定，随时可能丢在保证了域名收敛之后，同样域名下的资源请求将可以完全复用第一次的DNS建连和SSL握手，
    
          第一个就是减少 DNS 的请求，第二个就是缩短 DNS 解析路径。
    
          第一个就是做域名收敛的主要原因，相比于 PC 是对于域名的并发限制，无线上来说对并发的要求会弱很多（一般尽量是第一屏，后面使用懒加载）。
    
          第二个就是缩短解析路径，这里所说的缩短解析路径其实就说各级的缓存：本机的缓存，LocalDNS 的缓存，不过他们或多或少也不靠谱，尤其是运营商的 LocalDNS 给你劫持一下，篡改一下都是常有的事情，于是这个情况下，就有了 HttpDNS。
    
          HttpDNS 是为了解决移动端 DNS 解析请求而生的，顺便解决 DNS 劫持，合并请求和缓存结果进而提高解析质量。
    
          而在我们访问网络中 DNS解析过程（域名 --> 运营商（localDNS）—-> 权威DNS）

5. DNS预解析
         
        <meta http-equiv="x-dns-prefetch-control" content="on" />
        <link rel="dns-prefetch" href="http://bdimg.share.baidu.com" />

    

6. 如何提高移动端性能

![ ](http://7xklhg.com1.z0.glb.clouddn.com/h5-xingnengyouhua.png)

### Web浏览器安全

1. XSS
    
        xss(cross site script)跨站脚本攻击通过属性”src”加载来执行代码在获取网站或者网站服务器的部分或者全部权限后，在网页文件中插入一段恶意代码，来实现攻击。
        
        1.DOM—based XSS

        该漏洞是基于文档对象模型Document Objeet Model,DOM)触发的。
    
        <div id="print"></div>
    
        //javascript
        var text = document.getElementById("print");
        print.innerHTML = text.value;
    
        解决方式：
        
        * 编码方式
    
            //将要转换的字符串设置为这个元素的innerText(ie支持)或者textContent(火狐，google支持)
            (temp.textContent != undefined ) ? (temp.textContent = html) : (temp.innerText = html);
    
            //返回这个元素的innerHTML，即得到经过HTML编码转换的字符串了
            var output = temp.innerHTML;
    
    
        * 解码方式
    
            //将要转换的字符串设置为这个元素的innerHTML(ie，火狐，google都支持)
            temp.innerHTML = text;
    
            //返回这个元素的innerText(ie支持)或者textContent(火狐，google支持)，即得到经过HTML解码的字符串了。
            var output = temp.innerText || temp.textContent;


        2.存储型xss
        
        即通常我们在录入数据时通过闭合标签的方式把数据存储到数据库中，再次显示的时候触发。
        
        解决方式：转义标签
    
        如：
            <  转义为  &lt； 
            >  转义为  &gt； 
    
    
        3.反射型xss
        
        仍然来自于直接的用户输入，是在通过url控制了页面的输出（处理：转义字符）根据浏览器去bypass各种过滤，易用性稍微差一些。但最后在页面中显示出来，并需要用户自己去点击链接才能触发XSS的是反射型XSS。
    
        如：

        http://www.jpl.nasa.gov/about_JPL /maps.cfm?departure=lax%22 %3Cimg%20src=k.png%20onerror=alert(%22XSSed%20by%20sH%22)%20/%3E
    
        总结：反射型xss和dom-xss都需要在url加入js代码才能够触发。

2. CSRF[cross site request fork]
    
        跨站请求伪造,攻击者盗用了你的身份，以你的名义发送恶意请求。
        
    原理
![enter image description here](http://pic002.cnblogs.com/img/hyddd/200904/2009040916453171.jpg)


    如何防御
        一般网站有三种防御CSRF攻击的方案。
        （1）验证token值。
            在每个HTTP请求里附加一部分信息是一个防御CSRF攻击的很好的方法，因为这样可以判断请求是否已经授权。这个“验证token”应该不能轻易的被未登录的用户猜测出来。如果请求里面没有这个验证token或者token不能匹配的话，服务器应该拒绝这个请求。
        （2）验证HTTP头的Referer。
            大多数情况下，当浏览器发起一个HTTP请求，其中的Referer标识了请求是从哪里发起的。如果HTTP头里包含有Referer的时候，我们可以区分请求是同域下还是跨站发起的，因为Referer离标明了发起请求的URL。网站也可以通过判断有问题的请求是否是同域下发起的来防御CSRF攻击。
            缺点：通常Referer会包含有一些敏感信息，可能会侵犯用户的隐私
        （3）用XMLHttpRequest附加在header里。以上三种方法都在广泛使用，但是他们的效果都不是那么的令人满意。
            在使用这种方法来防御CSRF攻击的时候，网站必须在所有的请求里使用XMLHttpRequest并附加一个自定义头（比如X-Requested-By），并且拒绝所有没有自定义头的的请求。例如，为了防御登陆CSRF的攻击，网站必须通过XMLHttpRequest的方式发送用户的身份验证信息到服务器。在我们的实验里，在服务器接收到的请求里面，大约有99.90–99.99%的请求是含有X-Requested-By头的，这表明这一方法适用于绝大多数的用户。
        
        推荐：Origin字段
            修改浏览器在发送POST请求的时候加上一个Origin字段，这个Origin字段主要是用来标识出最初请求是从哪里发起的。如果浏览器不能确定源在哪里，那么在发送的请求里面Origin字段的值就为空。
            隐私上：方式比Referer更人性化，因为它尊重了用户的隐私

3. sql注入
        
        sql注入是攻击者把SQL命令插入到Web表单的输入域或页面请求的查询字符串，欺骗服务器执行恶意的SQL命令。在某些表单中，用户输入的内容直接用来构造（或者影响）动态SQL命令，或作为存储过程的输入参数，这类表单特别容易受到SQL注入式攻击。
        
        需要注意点：
        
            1.永远不要信任用户的输入，要对用户的输入进行校验，可以通过正则表达式，或限制长度，对单引号和双"-"进行转换等。

            2.永远不要使用动态拼装SQL，可以使用参数化的SQL或者直接使用存储过程进行数据查询存取。

            3.永远不要使用管理员权限的数据库连接，为每个应用使用单独的权限有限的数据库连接。

            4.不要把机密信息明文存放，请加密或者hash掉密码和敏感的信息。
            
### 前端工程化

前端构建工具目的就是为了开始开发。让前端开发真正达到工程化。先明确几个概念。
    
        包管理工具（package manager）：npm、bower、jspm、cnpm 等等
        模块加载器（module loader）: requirejs、modjs、seajs 等等，模块加载器又主要遵循AMD、CMD、Commonjs三种规范
        打包工具（bundler）：r.js、browserify、webpack
        版本仓库： gitlab,coding,github
        构建工具：gulp(基于stream的构建工具)、grunt

 1. gulp

          gulp.js 是一种基于流的，代码优于配置的新一代构建工具。gulp.js 是一个自动化构建工具,开发者可以使用它在项目开发过程中自动执行常见任务。是基于 Node.js 构建的,利用 Node.js 流的威力,你可以快速构建项目
        
        gulp有很多插件－而这些插件就赋予了gulp众多的功能
            编译Sass (gulp-ruby-sass)
            Autoprefixer (gulp-autoprefixer)
            缩小化(minify)CSS (gulp-minify-css)
            JSHint (gulp-jshint)
            拼接 (gulp-concat)
            丑化(Uglify) (gulp-uglify)
            图片压缩 (gulp-imagemin)
            即时重整(LiveReload) (gulp-livereload)
            清理档案 (gulp-clean)
            图片快取，只有更改过得图片会进行压缩 (gulp-cache)
            更动通知 (gulp-notify)
    
        优点：
            易于使用: 通过代码优于配置的策略，Gulp 让简单的任务简单，复杂的任务可管理。
            构建快速:利用 Node.js 流的威力，你可以快速构建项目并减少频繁的 IO 操作。
            插件高质:Gulp 严格的插件指南确保插件如你期望的那样简洁高质得工作。    


2. webpack + tree-shaking
    
    
    [webpack是什么](https://github.com/webpack)

        Webpack 是德国开发者 Tobias Koppers 开发的模块加载器,在 Webpack 当中, 所有的资源都被当作是模块, js, css, 图片等等..因此, Webpack 当中 js 可以引用 css, css 中可以嵌入图片 dataUrl

        module: {
            loaders: [
              { test: /\.coffee$/, loader: 'coffee-loader' },
              { test: /\.js$/, loader: 'jsx-loader?harmony' } // loaders can take parameters as a querystring
            ]
        },
        
        我理解就是：你在开发的过程中，需要通过AMD、CMD的方式引入其他文件，这时就需要webpack把它们组装起来，里面可以引入图片或者css文件。这样的好处自然就非常明显了，减少请求。
        
        特点：
            a) 模块来源广泛，支持包括npm/bower等等的各种主流模块安装／依赖解决方案
            b) 模块规范支持全面，amd/cmd/commonjs/shimming等完全支持
            c) 浏览器端足迹小，移动端友好，却对热加载乃至热替换有很好的支持
            d) 插件机制完善，实现本身实现同样模块化，容易扩展，支持es6，react等
            e) 需要手写配置
            
        tree-shaking
            tree-shaking是RollUP中的一种技术，tree-shaking是下一代前端打包工具(PS:这一代斗没有用好，前端发展太快了)
            通过 tree-shaking 打包的结果只包括  /*实际用到的 exports*/。Three-shaking 的关键在于依赖 ES6 模块的静态结构。“静态结构”意味着在编译时他们是可分解的，而不用执行它们的任何代码，简单理解是ES6导出的部分如果在其它模块没有调用，rollup在输出时会直接把这部分作为死码删除。

3. github与Git
    
      
          Git是一个分布式的版本控制系统,版本控制工具。
          github是一个用git做版本控制的项目托管平台，用来存放仓库(repo)。
          作为前端，开源的世界很美好。


4. npm [官方网站](http://npmjs.org)  

        NPM的全称是Node Package Manager ，是一个NodeJS包管理和分发工具。 我们在安装很多项目中，有使用npm install就是依赖了很多放在npm上的包。类似java中的jar包。

        NPM是基于couchdb的一个数据库，详细记录了每个包的信息，包括作者、版本、依赖、授权信息等。它的一个很重要的作用就是：将开发者从繁琐的包管理工作（版本、依赖等）中解放出来，更加专注于功能的开发。

        基本信息：

            package.json：包描述信息，里面的dependencies参数就是 npm install 时需要安装的包。应用依赖模块会安装到当前模块的node_modules目录下。
            
            package版本：常见版本声明形式。


### 数据结构

作为学过java的童鞋，还是不要把数据结构忘了，记得某某人说过 “程序 ＝ 数据结构 ＋ 算法”，所以把他们放得这么靠后。


### 算法

1. 常规算法复杂度
    
![常用算法时间复杂度](http://7xklhg.com1.z0.glb.clouddn.com/algorithm%20complexity.png)

2. js实现常规排序
    
    
### 操作系统

1. 堆和栈的区别
            
        栈中存放的数据类型有：局部变量、操作数、动态连接、返回地址
        堆同时也是被所有线程所共享。存放对象实例，几乎所有的对象实例以及数组都要在这里分配内存。被GC（Garbage Colletor）管理。可以自动回收
        1、内存分配方面：
            堆：一般由程序员分配释放，并指明大小。  若程序员不释放，程序结束时可能由OS回收 。和数据结构不同，分配方式是类似于链表。可能用到的关键字如下：new、malloc、delete、free等等。
            栈：由编译器(Compiler)自动分配释放，存放函数的参数值，局部变量的值等。
        
        2.系统响应
            堆：操作系统有一个记录空闲内存地址的链表，当系统收到程序的申请时，会遍历该链表，寻找第一个空间大于所申请空间的堆结点，然后将该结点从空闲结点链表中删除，并将该结点的空间分配给程序
            栈：只要栈的剩余空间大于所申请空间，系统将为程序提供内存，否则将报异常提示栈溢出。
        
        3.大小限制
            堆：是向高地址扩展的数据结构，由于链表，所以是不连续的内存区域。堆的大小受限于计算机系统中有效的虚拟内存。
            栈：在Windows下, 栈是向低地址扩展的数据结构，是一块连续的内存的区域。WINDOWS下，栈的大小是固定的（是一个编译时就确定的常数），如果申请的空间超过栈的剩余空间时，将提示overflow。
        
        4.效率方面
            堆：是由new分配的内存，一般速度比较慢，而且容易产生内存碎片
            栈：由系统自动分配，速度较快。但程序员是无法控制的。
        
        5.存取效率
            堆：char *s1 = "Hellow Word"；是在编译时就确定的；
            栈：char s1[] = "Hellow Word"； 是在运行时赋值的；用数组比用指针速度要快一些，因为指针在底层汇编中需要用edx寄存器中转一下，而数组在栈上直接读取。


2. 什么是死锁？其条件是什么？怎样避免死锁？
        
        死锁的概念：在两个或多个并发进程中，如果每个进程持有某种资源而又都等待别的进程释放它或它们现在保持着的资源，在未改变这种状态之前都不能向前推进，称这一组进程产生了死锁。通俗地讲，就是两个或多个进程被无限期地阻塞、相互等待的一种状态。
        死锁产生的原因主要是：？ 系统资源不足；？ 进程推进顺序非法。
        产生死锁的必要条件：
        （1）互斥（mutualexclusion），一个资源每次只能被一个进程使用；
        （2）不可抢占（nopreemption），进程已获得的资源，在未使用完之前，不能强行剥夺；
        （3）占有并等待（hold andwait），一个进程因请求资源而阻塞时，对已获得的资源保持不放；
        （4）环形等待（circularwait），若干进程之间形成一种首尾相接的循环等待资源关系。
        这四个条件是死锁的必要条件，只要系统发生死锁，这些条件必然成立，而只要上述条件之一不满足，就不会发生死锁。
        死锁的解除与预防：理解了死锁的原因，尤其是产生死锁的四个必要条件，就可以最大可能地避免、预防和解除死锁。所以，在系统设计、进程调度等方面注意如何不让这四个必要条件成立，如何确定资源的合理分配算法，避免进程永久占据系统资源。此外，也要防止进程在处于等待状态的情况下占用资源。因此，对资源的分配要给予合理的规划。
        死锁的处理策略：鸵鸟策略、预防策略、避免策略、检测与恢复策略。

