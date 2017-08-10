## JSON
一种轻量级的数据交互格式，他是`字符串`(早期是使用XML：清晰易懂，占用大)  
学习Ajax前后端数据交互的第一步了解JSON  



## JSON和js对象  
| DataType |                   Description                  |
|   ---    |                       ---                      |
| js对象   | 是一种js数据类型，是js特有的，无法传递交互数据 |
| JSON     | 一种交互格式，所有的语言都有字符串，可以传递   |
> JSON是一个字符串的数据格式，它有一套规则，在js里惯用对象表示


## JSON语法规则
* JSON数据格式的键和字符串都为双引号；
* 值：整数、浮点、字符串、布尔、数组、对象、null（除了undefined、function都可以装、NAN），空值用空字符`""`串代替
> js对象最后条数据可选逗号不支持早期IE;



## JSON两种定义方式
```js
var obj = {
    "name"  : "slice",
    "age"   : 18,
    "marry" : true // 注意这个最后条数据可选逗号早期IE不支持结尾
}
// obj.name = "slice"   or   obj.age = 18   or   obj.marry = true



var obj1 = new Object(); // 只要new 的构造函数 返回的都是对象
obj1.name = "slice";
obj1.family = new Objext();
obj1.family.sister = new Array();
obj1.family.sister[0] = "大姐";
obj1.family.sister[1] = "二姐";



var s = '{"name": "slice", "age":18, "marry": false}';
```



## JSON字符串转JS对象
JSON是内置对象ES5添加的`JSON.parse()`支持IE8+  
```js
var obj = JSON.parse('{"name":"slice"}');

alert(obj.name);
```



## JS对象转JSON字符串
`JSON.stringify()` 转JSON字符串
```js
var obj = {"name": "slice", "age": 18}

obj = JSON.stringify(obj);

alert(typeof obj);
```



## 查看js对象自己所有数据
思路：递归  判断为对象继续调用自己输出
```js
var obj = {};
obj.name = "slice";
obj.age = 18;
obj.marry = false;
obj.family = {};
obj.family.sister = "大姐";
obj.family.mom = "妈妈";
obj.family.dad = "爸爸";
function each(obj) {
    for(var key in obj) {
        obj[key] instanceof Object ? each(obj[key]) : console.log(key +'========' + obj[key]);
    }
}
each(obj)
```



## jQuery解析对象   
`alert($.parseJSON('{"name": "slice", "age": 18, "cm": "150"}'))`
> ver3.0移除此方法使用==JSON.parse==代替




## 延时定时器
setTimeout()
* 参一：延时执行的函数（匿名函数或函数名字，传参数变为字符串`'a(1, 2)'`）
* 参二：延时多久     [Number]    {ms}
* 返回：定时器序列号
```js
var timer = setTimeout(fn, 2000);
function fn() {
    alert("点我开通SVIP通道，加速缓存，看视频更流畅");
}
```


## 清除延时定时器
clearTimeout(定时器返回的序列号)



## 循环定时器
setInterval()
* 参一：循环执行的函数(匿名函数或函数名字)传参数变为字符串"fn(1,5,6)"
* 参二：多久执行一次前面的函数 ————ms/Number



## 清除循环定时器
clearInterval(定时器的序列号)
```js
(function() {
    var i = 0;
    var timer2 = setInterval(function(){i++; if(i>=3) {clearInterval(timer2) } alert('每两秒我就弹一次广告') }, 2000)
})()
```



## 时间日期
```js
var data = new Date();

```
|        Method          |       Description     |
|          ---           |          ---          |
| **date X 1**           | **时间戳**            |
| **date.getTime()**     | **十三位时间戳**      |
| **date.getFullYear()** | **获取年**            |
| **date.getMonth()+1**  | **月份，从一月0开始** |
| **date.getDate()**     | **日期**              |
| **date.getHours()**    | **小时**              |
| **date.getMinutes()**  | **分**                |
| **date.getSeconds()**  | **秒**                |
| **date.getDay()**      | **星期，星期天为0**   |
> 以上获取返回都为Number
> alert( year+"年"+Month+"月"+date+"日----"+hours+"点"+minute+"分"+seconds+"秒" );



## 节点操作
|       Attribute                    |       Description          |
|          ---                       |          ---               |
| **Node.children**                  | **所有子节点，类数组**     |
| **Node.nextSibling**               | **下一个兄弟节点IE**       |
| **Node.nextElementSibling**        | **下一个兄弟节点Chrome**   |
| **Node.previousSibling**           | **上一个兄弟节点IE**       |
| **Node.previousElementSibling**    | **上一个兄弟节点Chrome**   |
| **Node.parentNode**                | **找父元素**               |
| **Node.nodeName**                  | **节点名字**               |
| **Parent.removeChild(child)**      | **通过父元素移除子元素**   |
| **Parent.appendChild(child)**      | **在内容里面最后个元素**   |
| **document.createElement("a")**    | **创建元素**               |
| **parent.insertBefore( xxx, box)** | **把xxx元素插入到box之前** |





```js
/**
 *  IE
 *      节点对象.previousSibling         ==>  谷歌返回文本节点(对象)
 *  Chrome/ FireFox
 *      节点对象.preivousElementSibling  ==>  IE返回undefined
 *  注： 如果没有上个同级的兄弟节点返回null，null在做判断为False;
 */
// alert(box.previousElementSibling);

function previousElement(obj) {
    if(obj.previousElementSibling===undefined) {// 如果没有返回null为false
        return obj.previousSibling;// 始终都是返回这个属性
    } else {
        return obj.previousElementSibling;
    }
};
// alert(previousElement(box));

/**
 *  function previousElement(obj) {
 *      return obj.previousElementSibling===undefined ? obj.previousSibling : obj.previousElementSibling
 *  }
 */
```


### 创建元素
```js
var a = document.createElement("a");
a.href="http://www.qq.com";
```


### 插入元素
```js
/**
 *  插入在元素的前面 ==> 同级关系
 *  参一：插入的元素
 *  参二：插入哪个元素之前
 */
boxparent.insertBefore( xxx, box ) // 父元素里面把xxx元素 插入到box元素之前  
```

```html
<body>
    
    <div id="box">
        <div id="img">
            <img src="img/yhd1.jpg" alt="" width="750" height="398">
            <img src="img/yhd2.jpg" alt="" width="750" height="398">
            <img src="img/yhd3.jpg" alt="" width="750" height="398">
            <img src="img/yhd4.jpg" alt="" width="750" height="398">
            <img src="img/yhd5.jpg" alt="" width="750" height="398">
            <img src="img/yhd6.jpg" alt="" width="750" height="398">
            <img src="img/yhd7.jpg" alt="" width="750" height="398">
            <img src="img/yhd8.jpg" alt="" width="750" height="398">
            <img src="img/yhd9.jpg" alt="" width="750" height="398">
        </div>
        <div id="page">
            <a class="page prev" style="text-indent: -10px;" href="javascript: void(0);">&#xe68b;</a>
            <a class="page next" href="javascript: void(0);">&#xe68a;</a>
        </div>
        <ul id="btn">
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
            <li></li>
        </ul>
        
    </div>
<script src="http://apps.bdimg.com/libs/jquery/1.11.3/jquery.min.js"></script>
<script>


    /* ======================================= */
    /*  Gobal
    /* ======================================= */
    var box = document.getElementById('img');
    var imgs = document.getElementById('img').getElementsByTagName("img");
    var pages = document.getElementById('page').getElementsByTagName("a");
    var btn = document.getElementById("btn").getElementsByTagName("li");
    var index = 0;
    var timer = 0;



    /* ======================================= */
    /*  Default
    /* ======================================= */
    imgs[0].style.display = "block";
    btn[0].className = "on";



    /* ======================================= */
    /*  Img and Li related
    /* ======================================= */
    for(var i=0; i<btn.length; i++) {
        btn[i].index = i;
        btn[i].onmouseover = function() {

            btn[index].className = "";
            imgs[index].style.display = "none";
            
            index = this.index;

            btn[index].className = "on";
            imgs[index].style.display = "block";
        };
    }



    /* ======================================= */
    /*  paging
    /* ======================================= */
    function nextPage() {
        imgs[index].style.display = "none";
        btn[index].className = "";
        index++;
        index%=imgs.length;
        imgs[index].style.display = "block";
        btn[index].className = "on";
    };

    function previousPage() {
        imgs[index].style.display = "none";
        btn[index].className = "";
        index--;
        if(0>index) index=imgs.length-1;
        imgs[index].style.display = "block";
        btn[index].className = "on";
    }
    // function
    function paging(callback) {
        imgs[index].style.display = "none";
        btn[index].className = "";
        callback&&callback();
        imgs[index].style.display = "block";
        btn[index].className = "on";
    };

    pages[0].onclick = function() {paging(function() {index--;if(0>index) index=imgs.length-1;}) };
    pages[1].onclick = function() {paging(function() {index++;index%=imgs.length;}) };



    /* ======================================= */
    /*  Auto Banner
    /* ======================================= */
    function auto() {
        timer=setInterval( nextPage, 500 );
    };

    function stop() {
        clearInterval(timer);
    }

    box.onmouseout = auto;
    box.onmouseover = stop;

    auto();

    

</script>
</body>
```