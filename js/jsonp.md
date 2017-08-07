## jsonp

自己做了一个网站。想自己的网上加一个搜索功能，但是已一己之力做出搜索引擎 明显不现实，可能以后牛逼了，但是目前至少现实



jsonp则是利用script不受跨域限制的特性，跨域获取数据





首先要了解，xhr是不支持跨域的（xhr2可以，不过要配置服务器），那么什么方法可以跨域请求呢？
script标签，没错就这货，这个标签可以在自己的网站载入其他网站的js脚本，所以jsonp实现原理：通过js动态地在文档流创建一个script标签，然后载入js脚本,服务器怎么响应这个脚本呢？？
很简单，响应这个脚本执行一个js函数就行，然后吧需要数据作为参数传入函数里，callback(data)，创建后会自动执行这个函数（当然前提你要有这么个函数）就这么简单；
前端怎么处理呢？
前端就得定义这么样的函数

function callback(data){

​	alert（data）

}
原理就是这么简单，至于jsonp与ajax有什么关系呢？
都可以用来实现网页局部更新，并不是ajax的内容（原生xhr是没有jsonp这么一说的）。



`<div></div> `弄一个搜索框

跨域

 首先打开百度搜索，然后找到那个链接

 解决缓冲问题的时间戳

一段js 是可以引用的

首先创建一个script标签

```javascript

var oS = document.createElement("script");
oS.src = 'https://sp0.baidu.com/5a1Fazu8AA54nxGko9WTAnF6hhy/su?wd='+val+'&cb=which';
document.body.appendChild(oS);
```

报错

定义一个函数

```javascript
function which( myJson ){
  	alert（myJson.s）
}
```

调用数据搞定了，纯前端的问题了

获取search的id 然后 onkeyup 键盘点击事件

```javascript

  oSearch.onkeyup = function () {
      var val = this.value;
      oS = document.createElement("script");
      oS.src = 'https://sp0.baidu.com/5a1Fazu8AA54nxGko9WTAnF6hhy/su?wd='+val+'&cb=which';
      document.body.appendChild(oS);
  };
```

然后生成  li 

```
var s = mJson.s;    
 oList.innerHTML = '';
    for(var i=0;i<s.length;i++){
    oList.innerHTML += '<li><a href="https://www.baidu.com/s?wd='+s[i]+'" target="_blank">'+ s[i] +'</a></li>';
    }
```

限制长度



jsonp 跨域的方式

