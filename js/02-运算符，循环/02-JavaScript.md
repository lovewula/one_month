



## js 02

首先， 我们讲解下作业，然后我们接着昨天的知识点，我们上一节课讲了一些什么哇。同学们还记得吗，让我们来简单回顾下

我们是不是说了获取元素， 那我们一共讲了几种方法，有同学还记得吗，还记得的同学打个1，

那让我们回顾一下吧，首先是不是说了一个通过`id`来获取元素，对吗，这个应该怎么写，是不是`document.getElementById('id名')`，那么除了`id`我是不是还有通过` class`还有`tag`这两种，还有同学记得这两种方法吗,那让我们也来回顾下吧，  `document.getElementsByClassName('')`

`docuemnt.GetElementsByTagName('')`，那我们昨天是不是讲了它们的其中一个不同点，是不是 ，如果通过`id`获取元素的话，前面是必须为` document`，然后如果是通过`class`或`tag`

是不是前面就不一定的是`document`，对不对，这个同学们还记得吗，记得的同学打个1 或者是刷朵花，然后我们昨天还漏讲了一个，我们漏讲了一个通过`Name`来获取元素啊，大家就是比较常见的`name`这个属性的出现在哪里，是不是一般情况下，都是`form`表单的里面的`input`的这个属性

那下面我来演示下，好吧

```
<form>
	<input type='text' name='username' placeholder='请输入用户名' />
</form>

<script>
	// 字母， 下划线 ，$  开头， 变量名，最好的见名知意
	
	类数组
	var  names = document.getElementsByName('username');
	alert( names.length )  // 弹出有多少个
</script>
```

讲到这里，还有同学不理解的吗，理解的话打个1 或者刷朵鲜花 `document.getElementsByName`

```javascript
docuemnt.getElementById()
	// 前面必须的 document
document.getElementsByName()
document.getElementsByTagName()
docuement.getElementsByClassName()
	// 就不一定是document
```

那这个我们就过了啊，然后接下来，我们讲解下今天的知识点，今天我们。。。对了，我们昨天是不是简单的介绍了下`js`六大基本数据类型，对不对， 这个还有同学记得吗，记得的同学可以在公评上打出来啊，我们来看下有那六个基本数据类型，

```
1. number   // 数字  js中不区分整数和浮点数，统称数字
2. string   // 字符串  只要用引号包裹起来的都是字符串
3. boolean  // 布尔   是只有 true 和 false   
4. function  // 函数     
5. undefined // 未定义 声明了一个变量 没定义啊
6. object  // 对象  
```

style修改样式注意：

	1.style 只能修改样式，不能获取样式，行内样式是可以的
	2.复合样式要使用驼峰法则


然后我们接下来我们进入今天的内容，我们首先趁热打铁， 先讲下关于运算符的一些知识

### javascript符号

* 运算符  ` + - *  / %` 

* 赋值符  `= += -= *= /= %= ++ -- `

* 比较符 `> >=  <  <= == ===`

* 逻辑符 `&& || ! `

* 位运算 `^ & | >> << ` 简单了解

  ​

首先讲解下，运算符 ，简单的介绍下  + - * / ，然后讲解下，`%`,然后就是说下。当 + 两边出现字符串的时候，那么就会实现拼接，不做任何运算。不仅仅是数字，当是true的时候，就就会变成 `true+'px'，只要出现了字符串就会拼接在一起`

如果是布尔就会 `true => 1 flase =>0`转换成数字进行运算

当运算符两边不是数字的时候就会出现的各种情况 （通过某些运算，数据的类型发生改变）

* `+`号两边只要出现字符串，就是拼接
* 布尔值 和 数字 运算  true => 1  fasle => 0 
* `-  * / %  ` 会强制 转化成数字进行运算

**赋值符号**

```
var a = 2;
a += 2    // a = a + 2 

var b = a++ ;  // b = a ; a = a+1
var b = ++a ;  // a = a+1 ; b = a
```

**比较符号**

比较符得到的值不true 就是false

`> >=  <  <= == ===`

== 是数值的比较

==== 是数值和数据类型的比较

**逻辑符**

&&  与  遇到假就停   and

||   或  遇到真就停  or 
!      非  一定会返回一个布尔值  not

那些数据在做判断的时候为假

- undefined
- null
- 0
- NaN
- ""   // 空字符串

> 以上五个在做条件判断的时候都为假，其余都为真，包括空对象、空数组
> Boolean转Number ==> **true为1、fasel为0**

```javascript
var a = 1 < 2  &&   3 >2   // false  true  往后走 遇到 false就听

var a  = 1>2 || 2>3  // false  flase 往后走，遇到真就停

var a = 3> 4 || 5>19 || 2 // false  false  2

var a = 0 || '' || 5-5    // 0 || "" | 0 这里就可以讲那些东西在判断的时候为假

var a = 5 || 0 || '';

var a = 5 && 0 && '';  

var a = 5 || 3 && 0;  // 同时存在 先执行 && 在执行 ||  这是弹出 5

alert( a )
```

这个都理解了吗，理解的话打个 1 ，那我们就过了好吧  我们前面是不是讲到了隐式转换，对不对，那接下来我们讲下显示转换，什么是显示转换，我们先来举个例子

```
var num = 12;
var a = num.toString()
```



数字的一些方法


```

.toSting(x)   // x进制的字符串
.toFixed(x)   // 保留x位小数   5舍6入
Math.random()  //（0 ，1） 随机数，，无需参数 0-1的之间的随机数  可以等于0 不能等于1 传了参数 ，没有意义  没有形参去对应
Math.abs(number)  //绝对值
Math.ceil(number) //向上取整 （ 有小数 整数就加1）
Math.floor(number) //向下取整 （舍去小数）
Math.round(number)  //四舍五入
Math.max(1,3) // 取最大值
Math.min(2,12,) //取最小值
Math.PI()  //圆周率
Math.pow()  //取平方根 
parseInt(string) // 强制取整  
parseFloat()    // 强制取数字（包含小数）
Number()   //　这个方法比较弱　只有写的工工整整才能转换

```



**parseInt**

```
var num = '  '  //第一位非空格的开始  数学
' 100 110px '  //弹出100
```

**Number**

```
要写的很规范 
比较奇怪
Number(false)   // 0
Number('')  // 空的字符串  0
Number(null) // 0 
Number(undefined) // NaN
```



NaN是number类型 。不是数字

所有数字都是number类型

字符串的一些方法

```javascript
var s = 'which'

str[]  // 取字符的索引啊，  支持 ie8+ 以上
str.charAt[]  //  支持所有
str.split('')  // 会按照你的那个字符里面来区分
str.substring(2, 5) //	从2开始取到第5位，小于会交换位置，负数为0
str.slice(5, 1)	// 取不到会为空，不会交换位置，负数倒着数
str.indexOf('which', 5)	查找文本，从第5位开始查找，成功返回索引否则返回-1
str.tuUpperCase()	全部转换大写，无参
str.toLowerCase()	全部转换为小写，无参
```

**split例子**

```javascript
var str1 = "username----which|password----1234";
var arr = str1.split('|');
arr[0] // 第一组账号数据 username----which
arr[1] // 第一组账号数据 password----1234    账号密码再分离就再通过“----”切 
console.log(arr[0])
console.log(arr[1])

console.log( arr[0].split('----') )
console.log( arr[1].split('----') )
```

**substring例子**

```javascript
str.substring(1, 3) // 从第二位开始 取到第六位
str.substring(6, -1)// 负数为0，小的参数会放在前面，0-6
str.substring(2, 5) //	从2开始取到第5位，小于会交换位置，负数为0
```

**slice例子**

```
var a = slice
a.slice(5, 1)	// 取不到会为空，不会交换位置，负数倒着数
a.splie(1, 5)	// 从1 到 5位
a.splie(5, -1)  // 从第五位，然后下个值就是 从后面开始
```



## Array数组

```
var arr = [0, 1, 2];  
alert(typeof arr); // Object，无法确认
```

判断是否为数组：typeof返回的结果是Object对象，无法判断准确

| Method                    | Description                  |
| ------------------------- | ---------------------------- |
| **Array.isArray(arr);**   | **返回true是数组**                |
| **arr.join("== 字符串 ==")** | **0== 字符串 1 字符串 ==2**Array数组 |



      var arr = [1,2,4,'which','乌拉'];
      var str =  '1,2,4,which,乌拉'
      alert( arr )
      alert( typeof arr )
      alert( Array.isArray(arr) );
      alert( arr.join(' ') )



数据类型转换：

- 隐式类型转换：（通过某些运算，数据的类型发生改变）
  - 如果 **`+`**两边有字符串，那就是拼接
    - ` 1 + '2'    = > '12'    ture + '2' = 'true2' `
  - `- * / %`就会使两边强制进行数字运算
    - `'2' - 1 = 1     '2'*2 =4`
  - 布尔值和数字进行运算会变成 `true  = >1 / false = > 0`
    - `true + 1 => 2`
  - !  和 比较符总会返回布尔值   `!5 =>false`
- 显示转换 （）
  - ​