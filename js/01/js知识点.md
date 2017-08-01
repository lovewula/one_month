### 第一节JavaScript知识点

`innerHTML`和`innerText`的区别

innerHTML 可以渲染HTML标签

innerText 不能渲染HTML标签


浏览器容错率比较高，包容


script一般放在头部结束之前，或者body之前


document.write()在页面加载完后，就会重新覆盖页面

所以document.write()最后是在文档流加载之前

页面在加载标签的时候，就会读取文档流

页面加载完之后，文档流就关闭

定义变量



```javascript
document.getElementById('box').onclick = function(){
  
}
```





JavaScript 弱语言 定义变量就是直接 var  一个变量

取名不能取 

* 不能用关键字 和 保留字
* 可以使用 字母，数字  划线或 $ 开头 并且不能是数字开头



JavaScript的一些数据类型

- `number`数字类型，包括了整数和浮点数
- `string`：字符串类型
- `undefined`：声明了变量名但是没赋值
- `oebject`：对象类型，包括(`Array,Null,Date,json`系统自带的对象)
- `function`函数类型
- `boolean`布尔类型，一般值不是为`true`就是`false`‘




除了通过`id`的另外几种获取方式

```javascript
document.getElementById('id') // 这样是返回单个dom元素的节点对象，只有对象才能去点方法或属性
document.getElementsByClassName ('通过class名字') //这样获取到的一个装了很多苹果的篮子
document.getElementsByTagName('div') // 通过标签获取的一个集合
document.getElementsByName('name名字') // 这样获取到name 属性 一般只用于form表单的input
```







