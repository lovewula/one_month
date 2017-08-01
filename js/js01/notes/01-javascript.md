###　JavaScript01 

​                   

## Js是什么

直译语言    就是会将代码一句一句直接运行  不像Java一样，需要先编译在执行  该语言通过解释器，在运行期间动态直译，不用通过编译器先行编译为机器码，再在CPU中运行

```javascript
var x = 5; // 5
x += 'A'  // 'A'
```

弱类型   类型完全是由当前的值来定义的   弱类型的好处就是十分灵活。 可以写出非常简洁的代码

动态类型就是，x可以一会是字符串，一会是number 这就是弱类型

至于原型语言就是基于对象，只有对象而没有类，对象继承对象而不是类继承类

​    `javascript`是一种**直译式**脚本语言，是一种动态类型、弱类型、基于原型的语言，内置支持类型。直译式**是什么意思？动态类型和弱类型以及基于原型又是什么意思？首先解释一下**直译式：该语言通过解释器，在运行期间动态直译，不用通过编译器先行编译为机器码，再在CPU中运行。解释下一个问题，需要先定义一个变量，这个变量可以动态的改变类型就是动态类型语言，可以赋不同类型的值就是弱类型语言的体现；至于原型语言就是基于对象，只有对象而没有类，对象继承对象而不是类继承类。综上所述，`JavaScript`又有如下定义：基于对象和事件驱动并具有相对安全性的客户端脚本语言。

1995年时，由[Netscape](http://baike.baidu.com/item/Netscape)公司的[Brendan Eich](http://baike.baidu.com/item/Brendan%20Eich)，在[网景导航者](http://baike.baidu.com/item/%E7%BD%91%E6%99%AF%E5%AF%BC%E8%88%AA%E8%80%85)浏览器上首次设计实现而成。因为[Netscape](http://baike.baidu.com/item/Netscape)与[Sun](http://baike.baidu.com/item/Sun/69463)合作，[Netscape](http://baike.baidu.com/item/Netscape)管理层希望它外观看起来像[Java](http://baike.baidu.com/item/Java/85979)，因此取名为JavaScript。但实际上它的语法风格与[Self](http://baike.baidu.com/item/Self/4959923)及[Scheme](http://baike.baidu.com/item/Scheme)较为接近 

**JS是单线程  一报错就停止运行**

## Js 的执行方式

1. 直接使用`script`标签写在页面中,可以放在`body`还有`head`里面,写在`head`里面要加上

   * ```javascript
     window.onload =  function(){
       
     }
     ```

     这么一段代码，因为页面是从上到下的执行,`window.onload`就是在整个页面全部加载完在才会执行

2. 引入外部的`.js`文件，这也是比较常用的，方便管理

## Js的注释

```javascript
// 单行注释

/*
	多行注释
*/
```

## JS的注意事项

* 严格区分大小写
* 每条完整语句后面都要记得带上分号
* 代码要缩进，对齐

## JS 获取元素节点

```javascript
document.getElementById('') //通过id来获取元素
	// 前面的节点对象一定是 document
	// 静态方法
document.getElementsByClassName('兼容ie8以上') // 通过class获取是一个装了多苹果的集合
document.getElementsByTagName('span')  // 通过标签获取的也是一个集合
document.getElementsByName('username') // 通过name属性获取，一般情况都是用于form表单的input标签
	// 前面的对象不一定是document
	// 动态方法
```

## JS的简单注册事件

```javascript
/*
	关于HTML标签 我们在js里面称为 节点 / 元素	
*/
document.getElementById('box')  通过 id 找元素  单双对应
```

```javascript
docuemnt.getElementById('box').onclick = function(){
  alert(1)
}

document是整个文档对象
```

## document.write()

向`body`后面添加内容，可以解析HTML标签，必须是在文档流加载之前，如果文档流加载完成之后，在执行`document.write`就会覆盖页面

## JS写入内容

1. 获取节点对象
2. 改变内容

`javascript`可以通过`innerHTML`和`innerText`写入内容

`innerHTML`  和 `innerText`之前的区别就是 `innerHTML`认识`HTML`标签

```javascript
var oBox = document.getElementById('box');   // 首先获取元素，定义变量
// 更改节点中的内容
oBox.innerText = '乌拉老师好漂亮'
// 追加内容
oBox.innerText += 'which老师很喜欢'

// 但是如果想添加一个标签怎么办
oBox.innerHTML = '<h1>slice老师很厉害</h1>'

// 追加内容
oBox.innerHTML = '<a href='hhtp://www.baidu.com'>slice老师很厉害</a>'
```

## JS的事件

| EventListener | Description |
| ------------- | ----------- |
| onclick       | 鼠标左键点击      |
| ondblclick    | 鼠标左键双击事件    |
| onmouseenter  | 鼠标划入        |
| onmouseleave  | 鼠标划出        |
| onmouseover   | 鼠标划入（冒泡）    |
| onmouseout    | 鼠标划出（冒泡）    |
| onmousemove   | 鼠标移动        |
| onblur        | 失去焦点        |
| onfocus       | 得到焦点        |
| onkeydown     | 键盘按下某键      |
| onkeyup       | 键盘抬起某键      |
| onkeypress    | 键盘按下并抬起某键   |
| onresize      | 浏览器窗口大小被改变  |
|               |             |

## JS变量

在`javascript`中应该如何定义变量，使用一个`var`

变量名的取名规则

* 可以是**字母，数字，下划线,，$**等，但是必须是以`字母 或 _ （下划线） 或 $ (美元符号）`开头

* 不能使用`javascript`关键字或者保留字作为变量名

* 所有的变量必须使用`var`声明后才能使用

* 定义变量没赋值，就是`undefined`这是`js`一种数据类型

  ```javascript
    var _ = "1998";
    var abc1 = "1999";
    var $  = "2000";

    var a = 1;
    var b = 2;
    var c = 3;
    // ==>
    var a = 1, b = 2, c = 3;

  // ==>  最好的简写方式
    var a = 1,
    b = 2,
    c = 3;
  ```



## JS的数据类型

JavaScript有6大数据类型

- 原始数据类型

  - `number`    // 数字类型  
  - `string`  //   字符串
  - `boolean`  //布尔类型   `true/false`
  - `function` // 函数类型         
  - `undefined`  // 未定义
- 对象数据类型
  - `object`  // 对象数据类型


## JS修改样式

使用`javacript`修改样式有两种方法

- 给`style`标签加上一个`id`然后通过获取元素来修改 ，但是这种不推荐，因为这种优先级不高
- 直接获取元素，然后通过修改内联样式来修改样式

### 讲解下除了id获取的另外两种方式

## console.log 

首先讲解下`alert`弹出，比如说 

```javascript
<div id='box'></div>

<div class='box'></div>
<div class='box'></div>
<div class='box'></div>

// var a = null;
// var a  = ['which',520,'which']
// var a  = {}  // 空对象
// var a = document;
// var a = document.getElementById('box');
var a = document.getElementsByClassName('box');
alert( a )

console.log(a)
```


## for 

```javascript
for(var i=0;i<4;i++){
  console.log[i]
}
```





















```
var name1 = 'which';

var name2 = 'slice';

var name3 = 'tuple';

alert( name1+'发工资了')

alert( name2+'发工资了')

alert( name3+'发工资了')


```




```

```