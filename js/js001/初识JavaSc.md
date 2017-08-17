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

* `JavaScript`修改`CSS`样式

  * ``

* `JavaScript`
