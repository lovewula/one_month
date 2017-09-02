## 今天，我们来学习下Ajax



### 什么是 AJAX 

AJAX = 异步 JavaScript 和 XML。

AJAX 是一种用于创建快速动态网页的技术。

通过在后台与服务器进行少量数据交换，AJAX 可以使网页实现异步更新。这意味着可以在不重新加载整个网页的情况下，对网页的某部分进行更新。

传统的网页（不使用 AJAX）如果需要更新内容，必需重载整个网页面。

Ajax的作用，局部刷新 在不重新加载整个页面 

Ajax的一些案例 简书

### Google Suggest

在 2005 年，Google 通过其 Google Suggest 使 AJAX 变得流行起来。

Google Suggest 使用 AJAX 创造出动态性极强的 web 界面：当您在谷歌的搜索框输入关键字时，JavaScript 会把这些字符发送到服务器，然后服务器会返回一个搜索建议的列表



jsonp不是使用xhr对象发送请求，而是创建一个script标签，标签的src属性设置成要请求的URL。当标签插入dom时浏览器就会自动请求这个URL，并把结果当做js代码执行。这样做的优点是跨域，缺点是只能使用get，而且不能设置header。因为请求完全不受js控制



首先写一个简单的Ajax

```javascript
document.onclick = function () {
    var xhr = new XMLHttpRequest();
    xhr.open('get', 'http://127.0.0.1:5000/static/test.txt', true);
    xhr.send();
    xhr.onreadystatechange = function () {
        if(xhr.readyState == 4){
             alert(xhr.responseText)
        }
    }
};
```

然后一条一条介绍

1.  var xhr = new XMLHttpRequest();

   * 创建一个Ajax对象

2. `xhr.open('get', 'http://127.0.0.1:5000/static/test.txt', true);`

   *  （准备工作）open(*method*,*url*,*async*)
     * 请求方式
       * `get`
       * `post`
       * 讲解下 `form`的`get` 和` psot`的案例
     * 访问的页面
       * 路径
     * 是否异步
       * `true`
       * `false`

3.  `xhr.send(string);`

   * 正式发送请求 string 仅用于post方法

4.  ```javascript
    xhr.onreadystatechange = function () {
           if(xhr.readyState == 4){
                alert(xhr.responseText)
           }
       }
    ```

   * ` onreadystatechange`  当请求的状态码发生改变的时候触发
   * `readyState` 请求的状态码
     * 0   请求还没准备好 （open执行之前）
     * 1   请求准备好了 （open执行之后）
     * 2  请求正式发送  （send执行之后）
     * 3  请求已经受理了   有一部分数据已经可以用了，但是还是没有处理完成
     * 4 请求已经完全完成了
   * responseText  ： 后台返回的结果  一般情况是字符串


然后讲解下 Ajax  不通过form 表单  提交数据



如果为post需要加上这么一句

`xhr.setRequestHeader('content-type' , 'application/x-www-form-urlencoded');`



封装Ajax

```javascript
<!DOCTYPE HTML>
<html>
	<head>
		<title>please enter your title</title>
		<meta charset="gbk">
		<meta name="Author" content="">
		<style type='text/css'>
			*{ margin:0; padding:0;}

		</style>
		
	</head>
	<body>
		<script>
			/*
			//HTTP状态码
			var xhr = new XMLHttpRequest();
			xhr.open( 'get' , 'data.php?user=afei&age=18&o=45' , true );
			xhr.setRequestHeader('content-type' , 'application/x-www-form-urlencoded');
			xhr.send('user=afei&age=18&o=45');
			xhr.onreadystatechange = function(){
				if ( xhr.readyState == 4 )
				{
					if ( xhr.status >= 200 && xhr.status < 300 )
					{
						alert( xhr.responseText );
					}
					else
					{
						alert( '访问出错了！错误信息：' + xhr.status );
					};
				}
			};
			*/
			
			// type url data
			
			ajax({
				type : 'get',
				url : 'data.php',
				data : {'user' : 'afei','age' : '18'},
				success : function( goudan ){
					alert( goudan );
				},
				error : function( s ){
					alert( s );
				}
			});
			

			//参数：
				//{
				//	type :访问方式（get/post），默认'get' ，string 
				//	url : 访问地址，必传，string
				//	data : 发送的数据，需要传数据才写，json
				//	success : 请求成功的回调函数，第一个形参代表返回的数据，function
				//	error : 请求失败的回调函数，第一个形参代表HTTP状态码，function
				//}
			function ajax(mJson){
				var type=mJson.type || 'get';
				var url=mJson.url;
				var data=mJson.data;
				var dataStr='';
				var success=mJson.success;
				var error=mJson.error;
				if (data){
					for(var key in data )dataStr+=key+'='+data[key]+'&';
					dataStr+='_='+new Date().getTime();
					if(type.toLowerCase()=='get')url+='?'+dataStr;
				};
				var xhr=new XMLHttpRequest();
				xhr.open(type,url,true);
				xhr.setRequestHeader('content-type','application/x-www-form-urlencoded');
				xhr.send(dataStr);
				xhr.onreadystatechange=function(){
					if (xhr.readyState==4)
					(xhr.status>=200&&xhr.status<300)?(success&&success(xhr.responseText)):(error&&error(xhr.status));
				};
			};
			
			
		</script>
	</body>
</html>
```



使用jQuery的Ajax  get 获取

```javascript
 			btn.click(function (){
                $.ajax({
                    'url' : '/article/',
                    'type' : 'GET',
                    'success' : function (data) {
                        var articles = data['articles'];
                        var oList = $("#list");
                        for(var i=0;i<articles.length;i++){
                            var article = articles[i];
                            var title = article['title'];
                            var liStr = '<li>'+title+'</li>';
                            var li = $(liStr);
                            oList.append(li);
                        }
                    },
                    'error' : function (error) {
                        console.log('fail');
                        console.log(data);
					}
                })
            })
```

flask后台代码

```python
# 如果是Ajax交互的
if flask.request.is_xhr:
    articles = []
    for x in range(1,10):
        article = {}
        article['title'] = 'title' + str(random.randint(100,1000))
     
        articles.append(article)
    return jsonify({'articles':articles})
```



Ajax是不能跨域的  只能在自己服务器下访问

是为了安全 不能发送数据  只想获取数据不想发送数据  请求图片就是一个例子  引入别人的jQuery 不跨域的 举个例子