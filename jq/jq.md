## Jquery

**Jq是什么**

​	`jquery`是`javascript`编写的一个插件库，兼容`css3`

​	`1.x`的版本兼容`ie 6 7 8 ` ，`2.x`以后不兼容`ie 6 7 8`

**Jq能做什么**

​	`jquery`能够快速、简洁地处理`HTML`文档、控制事件、操作`DOM`、给页面添加动画和`Ajax效果`

   **jquery特点：**

* 开发理念：write less，do more 即“写的少、做的多”
* 具体特点：
  * 轻量级：jQuery库文件代码量非常轻巧，经过压缩后，大小保持在30KB左右
  * 功能强大的选择器：jQuery支持CSS中几乎所有的选择器，以及jQuery中特有的高级而复杂的选择器。同时，jQuery还可以加入插件使其支持XPath选择器，也允许开发者编写自己的选择器
  * 对DOM操作进行封装：jQuery中封装了大量的DOM操作
  * 完善的Ajax的封装：jQuery中将Ajax操作封装到一个函数中，似的开发者无须关心XMLHttpRequest对象的创建和使用等问题，可以专心地编写业务逻辑代码
  * 广泛的浏览器兼容性：能够在IE6.0+、FF1.5+、Safari2.0+、Opera9.0+和Chrome等主流浏览器中正常执行。jQuery同时修复了一些浏览器之间的差异，使得开发者不必担心程序的适用性
  * 链式代码方式：对于发生在同一个jQuery对象上的一组动作，可以直接链写而无需重复获取对象
  * 逻辑代码与表示代码分离：使用jQuery选择器可以直接为元素添加事件，从而将js代码和HTML代码完全分离，便于代码的维护和修改
  * 丰富的插件：jQuery的扩展性好，支持插件功能

**如何引入jQuery**

​	`jquery`说白了就是一个`.js`文件，外部的`js`文件应该怎么引入 

​	如何测试`jquery`是否引入成功 
```javascript
$(function(){
     alert(1)
})
```

**Jquery $**

```javascript
/*
	$()
		$符号 等同于 jQuery
		参数 ：
			字符串 （类似于css选择的字符串）
			js对象
*/
```

**jq获取内容和修改内容**

```javascript
    /*
        .html() 
            有参数 ： 参数是 字符串/数字   修改 html 内容
            没有参数 ： 返回第一个html内容 会带着标签也一起返回
        .text()
            有参数 ： 参数是 字符串/数字   修改 text 内容
            没有参数 ： 返回所有内容 
        .eq()
            参数是序列号，选中对应序列号的jq对象并返回
        jq 对象包含节点个数
            .length   
            .size()    // jQuery3.x以上版本不支持此方法

        .val()
            有参数  设置值
            无参数  返回值
    */
```

**Jq转js And Js转Jq(对象)**

```javascript
    /*
        jq 对象
        js 对象 / DOM对象
            js对象 转换 为 jq 对象 
                $(js对象)
            jq对象 转换为 js对象：
                get()  / []
    */
    var aP = document.getElementsByTagName('p'); 
    $(aP).html('$可以传js节点对象/集合');

    $('p').get(0).innerHTML = 'jq转js';
    $('p').[0].innerHTML = 'jq转js';

```

**Jq插入内容**

```javascript
    append()     // 在被选元素的结尾插入内容
    appendTo     // 将前面的内容添加到后面
    prepend()    // 在被选元素的开头插入内容
    prependTo()  // 将前面的内容添加到后面
    after()      // 在被选元素之后插入内容
    before()     // 在被选元素之前插入内容
    empty()     //  清除自己下面的子元素
    remove()   // 清除所有包括自己
```


**append  And prepend**

```javascript
    append()     // 在被选元素的结尾插入内容
    prepend()    // 在被选元素的开头插入内容
    $('.box p').append('<strong>这是append的内容</strong>') 		
    $('.box p').prepend('<strong>这是prepend的内容</strong>') 	
```

**appendTo And prependTo**

```javascript
appendTo     // 将前面的内容添加到后面
prependTo()  // 将前面的内容添加到后面
$('<strong>这是appendTo的内容</strong>').appendTo('.box span') 
$('<strong>这是prependTo的内容</strong>').prependTo('.box span') 
```

**before And after**

```javascript
after()      // 在被选元素之后插入内容
before()     // 在被选元素之前插入内容
$('.box p').before('<a href="#">这是before的内容</a>')  // 之前
$('.box p').after('<a href="#">这是after的内容</a>')  // 已经是不在p标签里 之后
```

**empty And remove**

```javascript
$('.box').empty()  // .box下面的所以子元素，全部清空
$('.box').remove()  //  会移除.box的所有内容包括自己
```

## Jquery设置和获取CSS样式

```javascript
     // $('.box').css( 'width' , '500px'） // 设置单个样式
     $('.box').css({
        'width' : '150px',
        'height' : '200px',
        'background' : 'red',
        'float' : 'right'
     }) //  设置多个样式
     $('.box').css('width')  //  获取样式
```

**addClass And removeClass And toggleClass**

```javascript
    $('div').addClass('on wrap box'); // 添加多个使用空格
    $('div').removeClass('on box');  //  不传参数，清除所有class
    $('p').toggleClass('on');                                 // 有的就变成没有，没有就有 交换
```

**width And Height **

```
alert($('#box').width())   // 直接获取宽高  不带px  相当于 parseInt
$('#box').width(100)  // 直接
```

**innerWidth()  / innerHeight()  **

**outerWidth / outerHeight**

只能获取，不能设置

``` 
innerWidth 可以获取padding左右加宽度  对应clientwidth
innerHeight 可以获取padding上下加高度 对应clientHeight
outerWidth()  带border    对应 offsetWidth
outerHeight() 带 border   对应 offsetHeight
```

**position()**

​	返回一个对象

​	该对象拥有`left`和`top`属性

​	分别代表元素到定位父级 左 / 上的  边框也算

​	`margin`不算 `padding`也不算

**offset**

​	返回一个对象

​	该对象拥有`left`和`top`属性

​	分别代表元素到 浏览器窗口  左 / 上的

## Jquery的事件

```javascript
    /*
        和 window.onload  = function(){} 不同
            window.onload 是要在等外部样式 外部的引入的js  内部的图片 全部加载完成
             $(document).ready 是等 dom 结构加载完成就可以了 更好用
    */
    $(document).ready(function(){

    })

    //  == >  简写

    $(function(){

    })
    // 一个页面可以用n次
```

一般都是去掉`on`变成方法 传事件函数参数

```
$('#box').click(function(){
	alert()
})
```

*onmouseenter / onmouseleave*

```javascript
$('#child').hover(function() {
	console.log(1)
}, function() {
	console.log(2)
});
不冒泡
```

**on And off**

```javascript
    /*
        on  循环添加
        off 移除事件
    */
    $('#box ul li').click(function(){
        alert( $(this).html() )  // this 是 JS的对象，需要转成jq对象
    })
    $("#box ul").on('click', 'li', function(){
        alert( $(this).html() )  //这样就能弹出后面添加的内容
    })
    $('#box ul').append('<li>123456</li>')  // 如果在次添加就不能弹出本身
```

**Jquery 操作属性**

```javascript
    /*
    2.x以下的版本已经移除了这些方法
    attr()  / removeAttr
        操作自定义标签属性
    prop()  / removeProp 方法已经被移除了
        操作合法标签属性
    */
    $('.box').attr( 'title','box' )  // 设置单个属性  多个就和 css 一样
        $('.box').attr({
            "乌拉" : "18",
            "id" :  "warp"
        })
        $('.box').prop({
            "id" : "box",
            "which" : "python"
     
        })
        console.log( $('.box').attr('乌拉') ) // 给一个值的获取
        console.log( '----------------' )
        console.log( $('.box').prop('id') ) // 给一个值的获取

```

**scroll() And scrollTop or scrollLeft**

```javascript
    $(window).scroll(function(){
        var t = $(document).scrollTop();  // 滚动条距离顶部的距离
        var l = $(document).scrollLeft(); // 滚动条距离左边的距离
        console.log('距离顶部'+t)
        console.log('距离左边'+l)
    });
```

**each() And index()**
```javascript
    $(document).click(function(){
        // $('p').html('1');
        $('p').each(function(index){  //第一个参数充当序列号的作用 // 指定当前$('p')里面的序列号
            $(this).html(index+1);  // 序列号都是从零开始的  
        });
    });   

    $('p').click(function(){
            // index() 默认返回元素在同级兄弟所以元素序列号
            // 可以传参数  选择器规定范围  序列号不存在 返回 -1 
            console.log( $(this).index( 'p' ) );
    })
```

**jq 选择器**

```javascript

    /*
     选择器
        1. *：选取所有元素。
        2. p：选取所有的p标签。
        3. #test：选取id为test的标签。
        4. .test：选取所有class为test的标签。
        5. :button：选取所有input标签的type为button的元素。
        6. div > p：选取div下面的所有子p元素。注意，这个只包括直接子元素。
        7. eq(index)：对一个已经选取后的元素集选取索引值为index的元素。
        8. :first 选中第一个 等同于 eq(0)
        9. :not() 排除元素
        10. gt(index)：对一个已经选取后的元素集选取索引值大于index的元素。
        11. lt(index)：对一个已经选取后的元素集选取索引值小于index的元素。
    */
    /*
    :not( 选择器 )
        排除

    :gt( 序列号 )
        大于某序列才被选中
    */
```

**hasClass() And children() And find()**
```javascript
    /*
        hasClass ( class名字 )
            返回 布尔值   如果有 返回 true   如果没有 返回 false
        is()
            返回 布尔值   如果有 返回 true   如果没有 返回 false
        children()
            无参数 返回所有的子元素
            有参数  返回类型
            两次就是返回孙子元素
        find()
            找到所有的子类

    */
    console.log($('p').hasClass('which'));
    // alert( $('.on').is('p') );
    var $obj = $('div').children('span').children( 'i' ) ; // 两次就是孙子元素
    // alert( $obj.length );
    $obj.append('which');
```

**parent And parents**
```javasctipt
    /*
        parent()
            找父辈
        parents()
            找祖辈  传 选择器 不然所有的祖辈选中
    */
        $('span').parent().append('qwe')
        $('span').parents('div').append('qwe')

```

**siblings**

```javascript
    /*
        siblings
            所有的同级兄弟
            可以传参数
    */
    $('span').siblings().append('which');  // 无参就是所有的兄弟元素
    $('span').siblings('span').append('which'); // 兄弟元素中选择器为span的所有兄弟元素
```


## jquery效果

**show() And hide()**

```javascript
    /*
        show 
            显示
            能传参数 
            slow  60000000 
        hide 
            隐藏
            能传参数
    */

```

**animate And stop**

```javascript
    /*
        animate 
            动画
        stop 
            暂停动画
            第一个值：如果设置成true，则清空队列。可以立即结束动画 第二个值：如果设置成true，则完成队列。可以立即完成动画
    */

    
```

**ScrollTop Demo**

```javascript
    // 点击返回顶部
        $('.w_top').click(function(){
            $("html,body").animate({
                scrollTop:0
            },1000)
        });
        // 设置滚动条
        $(window).scroll(function(){
            if( $(window).scrollTop() >= 100){
                // $('.w_top').fadeIn(1000); //  没讲fadeIn 之前先使用css样式
                $('.w_top').css("display","block");
            }else {
                // $('.w_top').css("display","none");
                $('.w_top').stop(true,true).fadeOut(1000)//  没讲fadeOut 之前先使用css样式           
            }
        })
```
