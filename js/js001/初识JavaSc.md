# `JavaScript`第一节

* `JavaScript`的代码引入

  * 可以放在`head` 也可以放在`body` 里面
  * 写在一个外部的`js`文件

* `JavaScript`的一些规范

  1. 严格区分大小写
  2. 每条完整语句记得带上分号
  3. 代码缩进、对齐

* `JavaScript`的注释

  * `//`单行注释
  * `/**/` 多行注释

* `JavaScript`如何获取元素节点

  * `document.getElementById('id名字')`
  * `document.getElementsByName('class名字')`
  * `document.getElementsByTagName('标签名')`
  * `document.getElementsByName('name')`
  * **不同**  `id`获取的是苹果   其它获取的是装苹果的箱子

* `JavaScript`注册一个简单事件

  * ```javascript
    /*
    	找到对应节点
    */
    document.getElementById('box') = function(){ 
    	alert(1)
    }
    ```

* `JavaScript`修改元素内容

  * `innerHTML`
  * `innerText`
  * `innerHTML`和`innerText`区别就是`innerHTML` 可以识别标签，追加就是`+=`
  * `document.write()`
    * 必须在文档流加载完成之前使用

* `JavaScript`变量名

  * 所以变量必须先使用`var`声明后才能使用
  * 不能是`js`的关键字或者是保留字 
  * 可以是**字母、数字、下划线(`_`)、$**但是不能是数字开头

* `JavaScript`数据类型

  * 使用`typeof` 查看数据类型
  * 原始数据类型
    * `number`        //数字类型
    * `string`       //字符串
    * `boolean`     //布尔类型  `true/false`
    * `function`    // 函数类型
    * `undefined`  // 未定义
  * 对象数据类型
    * `object`       // 对象数据类型

* `JavaScript`修改样式

  * 给`style`标签加上一个`id`,通过`innerHTML`追加内容
  * 直接获取元素，然后通过修改内联样式来修改样式

* `JavaScript` 调试代码

  * `alert`
  * `console.log`

* `JavaScript`的`[]的使用`

  * 涉及到一些变量就需要`[]`

* `JavaScript`的循环

  * `for`
  * `while`
  * `do..while`

* `break`和`continue`对循环的影响

  * `break`跳出本次循环
  * `continue` 跳出当前循环

* `JavaScript`的条件语句

  * `if` 

  * `if .. elseif .. else ..`

  * `if .. else`

    ​

