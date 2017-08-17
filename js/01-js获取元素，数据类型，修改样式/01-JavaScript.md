首先讲解 <`script`>标签的位置    然后一般都是放在`body`结束标签之前

浏览器容错率比较高，包容强

如果是`head`头部写JavaScript代码，那就是要加上一句

```javascript
window.onload = function(){
  // 页面加载完成后才执行
}
```

然后就是引入外部的`js`文件

做一个示范

- 新建JavaScript文件
- 然后输入alert(123)

`JavaScript`的注释

```
// 单行注释
/*
	多行注释
*/
```

然后`JavaScript`的一些规范

1. 严格区分大小写
2. 半角符号
3. 每条完整语句 要 分号 结尾
4. 代码要缩进
5. 不能随便回车 

讲个简单的注册事件

首先就是讲下 通过`document.getElementById('')`来获取到元素的节点，`.onclick`点击事件来执行

```javascript
docuemnt.getElementById('id名').onclick = funtion(){
 	alert(1)
}
```

这就一个简单的点击事件，其它还有很多事件 ，比如：

| EventListener    | Descripti           |
| ---------------- | ------------------- |
| **onmouseent**   | **鼠标划入(不冒泡)**       |
| **onmouseover**  | **鼠标划入**            |
| **onmouseleave** | **鼠标划出(不冒泡)**       |
| **onmouseout**   | **鼠标划出**            |
| **onmousemove**  | **监听鼠标移动**          |
| **onclick**      | **鼠标左键单击**          |
| **ondblclick**   | **鼠标左键双击**          |
| **onkeydown**    | **键盘按下某键**          |
| **onkeyup**      | **键盘抬起某键**          |
| **onkeypress**   | **键盘按下并抬起某键**       |
| **onblur**       | **失去焦点，能失获得焦点才有事件** |
| **onfocus**      | **获得焦点，能被获得焦点才有事件** |
| **onresize**     | **浏览器窗口大小被改变**      |

然后获取到了 `dom`元素，然后就使用`innerHTML 和 innerText `来给元素加上内容`innerHTML` 和` innerText` 两者之间的不同,`innerHTML` 可以解析`HTML`标签

然后讲一个`document.write`这就是向`body`屁股后添加内容，然后这种`document.write()`只能在**文档流**结束之前使用

document.write()在文档流后，就会重新覆盖页面

所以document.write()最后是在文档流加载之前

页面在加载标签的时候，就会读取文档流

页面加载完之后，文档流就关闭

```javascript
window.onload = function(){
  document.write('which老师好帅')
}
```

然后就是 定义变量

讲解一个鼠标移入移出事件 ，然后定义变量

```javascript
onmouseenter onmouseover  移入   在冒泡事件的时候讲
onmouseleave onmouseout   移出
```

因为`JavaScript`是 属于弱类型语言，只有一个变量标识符`var`，但是内部区分数据类型

定义 `var`

变量取名规则：

1.  可以使用 字母，数字  划线或 $ 开头 并且不能是数字开头
2.  不能使用js自带的关键字和保留字
    * 比如 ：`class `之类的保留字  以后可能用的上的
      JavaScript的一些数据类型

- `number`数字类型，包括了整数和浮点数

- `string`：字符串类型

- `undefined`：声明了变量名但是没赋值

- `oebject`：对象类型，包括(`Array,Null,Date,json`系统自带的对象)

- `function`函数类型

- `boolean`布尔类型，一般值不是为`true`就是`false`‘

  ```javascript
  var a = 123;  // number   js中的不区分整数和小数
  var b = 'abc'  // string 
  var c = true / false  // boolean
  var d = ['which', 'slice', 'tuple'] // object
  var e  = { "name" : "which"}  // object
  var f = null; //object
  var g = funtion(){
    alert(123)
  }
  ```


 

修改`style`样式

  ```javascript
  oBtn.onclick = function(){
    this.style.Height = '100px';
    this.style.Width = '100px'; 
     大多数情况下，都是字符串
     this.style.marginLeft = ''
     this.style.cssText = '';
  }
  ```

  ```javascript
  box.style.cssFloat = "right"; // Chrome
  box.style.styleFloat = "right"; // IE678 如果要考虑兼容两者都要写。
  ```

  通过移除class名字来修改样式，这样比较方便

`  dom节点对象.className = 'on'`

### 关于 []的使用

首先是数组 

`var arr = ['qwe','qwe']`是要的数据类型都能忘数组里面放

`arrt[0]`修改值的时候，用到

除了数组，还有别的地方

```
var x = 'height'

document.onclick = function(){
  oBox.style.x = '200px'; // 这样不行，这样就是 style=“x:200px”
  // 点的就是对象的属性 不是变量的属性
  oBox.style[x] = '200px'
  
}
```

js里面绝大部分的 **. ** 都可以用`[]` 不过要变成字符串，需要用变量代替某一个属性， 就可以这样做 



## js 操作标签的属性

* 合法标签属性:

  * 对象.标签属性名 
  * class  === 》 className 

* 自定义标签属性:

  * 对象.getAttribute("属性名")
  * 对象.setAtrribute("属性名", 值)
  * 对象.removeAttribute(”属性名“)

* js对象的自定义属性

  ​

`JavaScript`获取元素的方法

```javascript
document.getElementById('id') // 这样是返回单个dom元素的节点对象，只有对象才能去点方法或属性
document.getElementsByClassName ('通过class名字') //这样获取到的一个装了很多苹果的篮子
document.getElementsByTagName('div') // 通过标签获取的一个集合
document.getElementsByName('name名字') // 这样获取到name 属性 一般只用于form表单的input
```

类数组 类似数组，有数组的方法，比如 .length  然后还有下标

```
var box = document.getElementsByClassName('box');
box.innerHTML = 'qwe123'; // 不会报错，也不会添加内容

box[0].innerHTML = '123456'

就跟获取一个箱子一样，想要吃苹果，不能抱着箱子啃，要把箱子里的苹果拿出来啃，就算只有一个class，那获取的也是箱子

document.getElementsByTagname 获取到的也是箱子
```


然后讲解下
```javascript

通过id获取和class获取的一个区别:

​```javascript
document.getElementById()
	//前面的主体对象必须是document
	//静态方法  就找一次
document.getElementsByClassName()
document.getElementsByTagName()
	//前面的主体对象不一定是document
	//动态方法   用一次箱子，找一次

var oBox = document.getElementById('box');
var aP = document.getElementsTagName('p');
```



## for循环

```javascript
for( 1 ; 2 ; 3 ){
  4
}

1 》 2 》 4 》 3 》 2 》 4 》 3 》 2 .。。》 2 
```

然后讲解一个for的案例,讲不完就是当成作业





## console.log 的使用

打印日志，也是调试代码的



  ​









 



