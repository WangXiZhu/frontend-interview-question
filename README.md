

## 前端面试题目总结

   之前在找工作找的资料都是学长们用word的形式保存下来的，觉得非常的不方便。这其中会包含一些常问的面试题，以及一些公司的面试题。希望有所帮助。

[TOC]


###提示与建议

* 拥有一颗强大无比的内心，保持自信，无论何时何地都要相信自己，不要放弃。

* 有一份用心、精致的简历。

* 在自己总结的学习中，对于一个问题最好理清思路这样面试的时候更加有条理。最好学会发散思维，联系知识点。
* 可以从以下几个方面来回答。是什么！！！优点！！缺点！（基本上从这几个方面入手，面试官也没什么问题了，剩下的就是问题的扩展）


### 前端
以下两个问题很关键，这将是一条很长的路...

*  为什么选择前端？
*  前端是什么？

### 简历

* [简历建议](http://mp.weixin.qq.com/s?__biz=MzAxODE2MjM1MA==&mid=402642996&idx=1&sn=1bdd4498df7bb4d13e58e0602104658f&scene=0#wechat_redirect)

  一些细节点注意一下。

###  看书
其实大部分的知识点都是书中的，而且书里面更加的详细，更能系统性地归纳自己的知识体系。

[前端书籍](https://pan.baidu.com/s/1EZAuOsQKT6-w6sQj1TdC8Q) 提取码：a9pn


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
4. 简述一下你对HTML语义化的理解

        用正确的标签做正确的事情。
        html语义化让页面的内容结构化，结构更清晰，便于对浏览器、搜索引擎解析;
        及时在没有样式CCS情况下也以一种文档格式显示，并且是容易阅读的;
        搜索引擎的爬虫也依赖于HTML标记来确定上下文和各个关键字的权重，利于SEO;
        使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

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
           因为大屏幕的移动设备越来越普及。而自适应布局已经无法胜任各种
