## Json

一定要使用  双引号    包裹起来 

因为json作为一种使用广泛的数据交换格式，既然是交换必然是多种语言之间，所以必须要加入。

```
var obj = {
  "name" : "which"，
  "age" : "18",
  "sex" : "male",
}



alert( obj.name );
obj.marry = false;
alert( obj.marry );

for(var x in obj){
  console.log(x);
  console.log(obj[x]);
}

for(var key in document){
  console.log()
}

```

### Date

```javascript

var a = new Date();
var y = a.getFullYear(); // 年
var m = a.getMonth()+1;　// 月 外国是从0开始
var d = a.getDate();    // 日 
var hh = a.getHours();  // 小时
var mm = a.getMinutes();  // 分钟
var ss = a.getSeconds();  // 秒
var day = a.getDay();  // 当前的周几 但是。。周日为0
alert( day )   
alert( a - 0 )  //获取时间差　　从当前时间到－1970，1，1，00：00的毫秒
```
