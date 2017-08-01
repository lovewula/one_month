### 原生AJAX

Ajax主要就是使用【XmlHttpRequest】对象来完成请求的操作，该对象在浏览器中具存在，（除了早期的IE）,Ajax首次出现在IE5.5中存在（ActiveX控件）

#### 1.XmlHttpRequest对象介绍：

`XmlHttpRequest`对象的主要方法：

1. void open(String method, String Url,Boolean async )

   用于创建请求

   ​

   **参数** ：

   * `method` 请求方式（字符串类型） 如：`POST、GET、DELETE..``
   * `url`：要请求的地址（字符串类型）
   * `async` 是否异步（布尔类型）

2. void.send(String  body)

   用于发送请求

   ​

   **参数** ：

   * `body`要发送数据（字符串类型）

3. void.setRequestHeader(String header, String value)

   用于设置请求头

   ​

   **参数**：

   * `header`：请求头的`key`（字符串类型）
   * `value`：请求头的`value`（字符串类型）

4. String getAllResponseHeaders()

   获取所有的响应头

   ​

   返回值：

   * 响应头数据（字符串类型）

5. String getResponseHeader(String header)

   获取响应头中指定的`header`的值

   ​

   **参数**：

   * `header`响应头的`key`（字符串类型）

   返回值：

   * 响应头中指定的`header`对应的值

6. void abort()

   终止请求


##### XmlHttpRequest对象的主要属性：

* `Number readyState`

  状态值（整数）

  详细：

  * 0  -  未初始化 ，尚未调用`open()`方法
  * 1  -  启动，调用了`open()`方法，未调用`send()`方法
  * 2   - 发送， 已经调用了`send()`方法，未接收到响应
  * 3  -  接收，已经接收到部分响应数据 
  * 4  -  完成，已经接收到全部的响应数据

* Function onreadystatechange

  * 当`readyState`的值改变时自动触发执行其对应的函数（回调函数）

* String responseText

  * 服务器返回的数据（字符串类型）

* XmlDocument responseXML

  * 服务器返回的数据（XML对象）

* Number states

  * 状态码（整数），如：200、404....

* String statesText

  * 状态文本（字符串），如：`OK  NotFound` ...

### 2.跨浏览器支持

- XmlHttpRequest
  IE7+, Firefox, Chrome, Opera, etc.
- ActiveXObject("Microsoft.XMLHTTP")

```html
<!DOCTYPE html>
<html>
<head lang="en">
    <meta charset="UTF-8">
    <title></title>
</head>
<body>

    <h1>XMLHttpRequest - Ajax请求</h1>
    <input type="button" onclick="XmlGetRequest();" value="Get发送请求" />
    <input type="button" onclick="XmlPostRequest();" value="Post发送请求" />

    <script src="/statics/jquery-1.12.4.js"></script>
    <script type="text/javascript">

        function GetXHR(){
            var xhr = null;
            if(XMLHttpRequest){
                xhr = new XMLHttpRequest();
            }else{
                xhr = new ActiveXObject("Microsoft.XMLHTTP");
            }
            return xhr;

        }

        function XhrPostRequest(){
            var xhr = GetXHR();
            // 定义回调函数
            xhr.onreadystatechange = function(){
                if(xhr.readyState == 4){
                    // 已经接收到全部响应数据，执行以下操作
                    var data = xhr.responseText;
                    console.log(data);
                }
            };
            // 指定连接方式和地址----文件方式
            xhr.open(‘POST‘, "/test/", true);
            // 设置请求头
            xhr.setRequestHeader(‘Content-Type‘, ‘application/x-www-form-urlencoded; charset-UTF-8‘);
            // 发送请求
            xhr.send(‘n1=1;n2=2;‘);
        }

        function XhrGetRequest(){
            var xhr = GetXHR();
            // 定义回调函数
            xhr.onreadystatechange = function(){
                if(xhr.readyState == 4){
                    // 已经接收到全部响应数据，执行以下操作
                    var data = xhr.responseText;
                    console.log(data);
                }
            };
            // 指定连接方式和地址----文件方式
            xhr.open(‘get‘, "/test/", true);
            // 发送请求
            xhr.send();
        }

    </script>

</body>
</html>
```

基于原生AJAX - Demo



### JQuery Ajax

jQuery其实就是一个JavaScript的类库，其将复杂的功能做了上层封装，使得开发者可以在其基础上写更少的代码实现更多的功能。

- jQuery 不是生产者，而是大自然搬运工。
- jQuery Ajax本质 XMLHttpRequest 或 ActiveXObject 

注：2.+版本不再支持IE9以下的浏览器



* JQuery.get(...)

  * 所有参数：
    * `url`：待载入页面的URL地址
    * `data`：待发送`Key/value`参数
    * `success`载入成功时回调函数
    * `dataType` ：返回内容格式，`xml 、json 、script 、 text html`

* JQuery.post(...)

  * 所有参数：
    * `url`待载入页面的URL地址
    * `data`待发送`key/value`参数
    * `success`：载入成功时回调函数
    * `dataType`返回内容格式,`xml 、 json 、 script 、text、 html`

* JQuery.getJSON(...)

  * 所有参数：
    - `url`待载入页面的URL地址
    - `data`待发送`key/value`参数
    - `success`：载入成功时回调函数

* JQuery.getScript(...)

  * 所有参数：
    - `url`待载入页面的URL地址
    - `data`待发送`key/value`参数
    - `success`：载入成功时回调函数

* JQuery.ajax(...)

  * 部分参数：

    * `url`：请求地址

    * `type`请求方式，`GET、POST(1.9.0之后用method)`

    * `headers` ：请求头

    * `data`：要发送的数据

    * `contentType`即将发送信息至服务器的内容编码类型（默认`"application/x-www-form-urlencoded; charset=UTF-8"`） 

    * `async`是否异步

    * `timeout`设置请求超时时间（毫秒）

    * `beforeSend`：发送请求前执行的函数（全局）

    * `complete`：完成之后执行的回调函数（全局）

    * `success`：成功之后执行的回调函数（全局）

    * `error`：失败之后执行的回调函数（全局）

    * `accepts`:通过请求头发送给服务器，告诉服务器当前客户端接受的数据类型

    * `dataType`将服务器端返回的数据转换成指定类型

      * `"xml"`：将服务器端返回的内容转换成`xml`格式

      * `"text"：`将服务器端返回的内容转换成普通文本格式

      * `"html"`： 将服务器端返回的内容转换成普通文本格式，在插入DOM中时，如果包含JavaScript标签，则会尝试去执行

      * `script`尝试将返回值当作`JavaScript`,然后再将服务器返回的内容转换成普通文本格式

      * `"json"`:将服务器端返回的内容转换成相应的`JavaScript`对象

      * `"jsonp"` `JSONP` 格式   使用` JSONP` 形式调用函数时，如 `"myurl?callback=?" jQuery` 将自动替换 ? 为正确的函数名，以执行回调函数

      * 如果不指定，`JQuery`将自动根据`HTTP`包`MIME`信息返回相应类型(`an XML MIME type will yield XML, in 1.4 JSON will yield a JavaScript object, in 1.4 script will execute the script, and anything else will be returned as a string`)

      * `converters`:转换器，将服务器端的内容根据指定的dataType转换类型，并传值给success回调函数

        ```javascript
        $.ajax({
            accepts: {
                mycustomtype: ‘application / x - some - custom - type‘
            },

            // Expect a `mycustomtype` back from server
            dataType: ‘mycustomtype‘

            // Instructions for how to deserialize a `mycustomtype`
            converters: {‘text mycustomtype‘: function(result) {
                    // Do Stuff
                    return newresult;
                }
            },
        });
          
        ```

        ​